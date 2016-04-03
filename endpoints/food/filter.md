# GET food/filter

Returns a list of food vendors that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/food/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For numerical filters:
* No operator indicates equal to (eg. `lat:46`)
* `>` indicates greater than (eg. `lng:>30`)
* `<` indicates less than (eg. `lat:<60`)
* `>=` indicates greater than or equal to (eg. `lng:>=18`)
* `<=` indicates less than or equal to (eg. `lat:<=200`)
* Currently, the only numerical keys are `lat` & `lng`

For string filters:
* No operator indicates contains (eg. `name:"Subway"`)
* `-` indicates not (eg. `campus:-UTSC`)
* String filters can be applied to name, address and campus

Special filters:
* `open`
  * Comma-separated list of days with _optional_ hours (eg. `open:"monday,tuesday(<8)"`)
  * Include hours in parentheses after the day (eg. `open:monday(4|8),tuesday(>9)`) for specific timings
    * No operator indicates "open at" (eg. `open:"sunday(14)" => "open on sunday at 2 pm"`)
    * `|` indicates "open between" (eg. `open:"monday(4|8)" => "open on monday between 4 am and 8 am (inclusive)"`)
    * `>` indicates "open after" (eg. `open:"friday(>15)" => "open on friday after 3 pm`)
    * `<` indiciates "open before" (eg. `open:"tuesday(<10)" => "open on tuesday before 10 am"`)
  * No parentheses checks if the vendor is open at all on that day. Use `-` to check for not open. (eg. `open:"monday,-sunday" => "open on monday and not on sunday"`)
* `tags`
  * Comma-separated list of tags to filter for
  * Each comma represents `AND`, for an inclusive search use `tags:tag1,tag2 OR tags:tag3`
    *  `tags:"pizza,coffee"` filters vendors that offer pizza AND coffee
    *  `tags:"pizza" OR tags:"coffee"` filters vendors that offer pizza OR vendors that offer coffee
  * You can also use `-` for vendors that don't have the tag (eg. `tags:pizza,-coffee => vendors that offer pizza AND not coffee`

Examples of filter combinations:
* `address:"St. George" AND tags:"pizza" AND open:"monday(>18)"`
* `campus:"UTSC" AND name:"Subway"`
* `open:"monday(16)" AND campus: "UTM" AND tags:"quick,-snacks" OR tags:"indian"`

- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -building_id`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/food/filter?q=address:"St. George" AND tags:"pizza" AND open:"monday(>18)"
```

```javascript
[
  {
    "id": "366",
    "building_id": "006",
    "name": "Robarts Cafeteria",
    "short_name": "robarts_cafeteria",
    "description": "Located on the second floor of Robarts Library across from the T-Card office, this full cafeteria includes Subway, Pizza Pizza, Chicken Chicken, Euro Market, Express, Expressos, Benne Pasta and Bento Nouveau Sushi. ",
    "url": "",
    "image": "http://map.utoronto.ca/_assets/_m_b/Robarts.jpg",
    "campus": "UTSG",
    "lat": 43.66454,
    "lng": -79.39911,
    "address": "130 St. George St, Toronto, ON M5S 1A5",
    "hours": {
      "saturday": {
        "closed": true,
        "open": 0,
        "close": 0
      },
      "friday": {
        "closed": false,
        "open": 8,
        "close": 17
      },
      "thursday": {
        "closed": false,
        "open": 8,
        "close": 18
      },
      "wednesday": {
        "closed": false,
        "open": 8,
        "close": 18
      },
      "tuesday": {
        "closed": false,
        "open": 8,
        "close": 18
      },
      "monday": {
        "closed": false,
        "open": 8,
        "close": 18
      },
      "sunday": {
        "closed": true,
        "open": 0,
        "close": 0
      }
    },
    "tags": [
      "library",
      "pizza",
      "pasta",
      "sandwiches",
      "coffee",
      "snacks"
    ]
  }
]
```

```
https://cobalt.qas.im/api/1.0/food/filter?q=campus:"UTSC" AND name:"Subway"
```

```javascript
[
  {
    "id": "1231",
    "building_id": "203",
    "name": "Subway",
    "short_name": "subway_utsc",
    "description": "Located on the Ground Level of the Student Centre, this food outlet offers various submarine sandwiches, salads and snacks For hours of operation, visit http://uoft.me/utscfood",
    "url": "",
    "image": "",
    "campus": "UTSC",
    "lat": 43.78508,
    "lng": -79.18703,
    "address": "1265 Military Trail, Toronto ON, M1C 1A4",
    "hours": {
      "saturday": {
        "closed": false,
        "open": 7,
        "close": 21.5
      },
      "friday": {
        "closed": false,
        "open": 7,
        "close": 21.5
      },
      "thursday": {
        "closed": false,
        "open": 7,
        "close": 21.5
      },
      "wednesday": {
        "closed": false,
        "open": 7,
        "close": 21.5
      },
      "tuesday": {
        "closed": false,
        "open": 7,
        "close": 21.5
      },
      "monday": {
        "closed": false,
        "open": 7,
        "close": 21.5
      },
      "sunday": {
        "closed": false,
        "open": 9.5,
        "close": 21
      }
    },
    "tags": [
      "subs",
      "salads",
      "snacks"
    ]
  }
]
```

```
https://cobalt.qas.im/api/1.0/food/filter?q=open:"monday(16)" AND campus: "UTM" AND tags:"quick,-snacks" OR tags:"indian"
```

```json
[
  {
    "id": "1176",
    "building_id": "313",
    "name": "Temporary Food Court",
    "short_name": "tfc_utm",
    "description": "The Temporary Food Court is host to several quality dining options including: *Booster Juice *Elements *International Kitchen *Pizza Pizza *Quick Cuisine *Tandoori Indian Cuisine *Tim Hortons Express *Deli (Opening 2014) *Hours subject to change",
    "url": "",
    "image": "http://map.utoronto.ca/_assets/_m_b/TemporayFoodCourt.png",
    "campus": "UTM",
    "lat": 43.54822,
    "lng": -79.66209,
    "address": "Davis Building, 3359 Mississauga Rd. Mississauga Ontario",
    "hours": {
      "saturday": {
        "closed": true,
        "open": 0,
        "close": 0
      },
      "friday": {
        "closed": false,
        "open": 8,
        "close": 19
      },
      "thursday": {
        "closed": false,
        "open": 8,
        "close": 21
      },
      "wednesday": {
        "closed": false,
        "open": 8,
        "close": 21
      },
      "tuesday": {
        "closed": false,
        "open": 8,
        "close": 21
      },
      "monday": {
        "closed": false,
        "open": 8,
        "close": 21
      },
      "sunday": {
        "closed": true,
        "open": 0,
        "close": 0
      }
    },
    "tags": [
      "indian",
      "international",
      "quick",
      "pizza",
      "juice",
      "food court",
      "takeout",
      "grab and go",
      "smoothies",
      "salads",
      "coffee"
    ]
  }
]
```
