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
* `<=` indicates less than or equal to (eg. `lat:<=-70`)
* `!` indicates not (eg. `lng:!40`)

For string filters:
* No operator indicates contains (eg. `name:"Subway"`)
* `!` indicates not (eg. `campus:!"UTSC"`)

Special filters:
* `open`
  * Each vendor is open a set number of hours for the 7 days of the week. Use this filter to find when a restaurant is open or closed.
  * To check for specific timings, include the time in parentheses after the day.
    * Time can take 2 forms:
      1. Formatted time string
        * `9:00` for 9:00 AM
        * `14:00` for 2:00 PM
      2. String representing seconds since midnight
        * `32400` for 9:00 AM
        * `50400` for 2:00 PM
    * No operator means "open at":
      * `open:"sunday(50400)"` for "open Sunday at 2 pm"
      * `open:"monday(11:30)" AND open:"thursday(68400)"` for "open Monday at 11:30 pm __and__ Thursday at 7 pm"
    * `|` means "open between (inclusive)":
      * `open:"monday(57600|20:15)"` for "open Monday between 4 pm and 8:15 pm"
      * `open:"tuesday(7:00|13:00)" OR open:"friday(50400)"` for "open Tuesday between 7 am and 1 pm __or__ open Friday at 3 pm"
    * `>` means "open after"
      * `open:"friday(>15:00)"` for "open Friday after 3 pm"
    * `<` means "open before"
      * `open:"friday(<15:00)"` for "open Friday before 3 pm"
  * No parentheses checks if the vendor is open at all on that day. Use `!` to check not open.
    * `open:"monday" AND open:!"sunday"` for "open Monday __and__ not Sunday"
    * `open:"monday" OR open:!"sunday"` for "open Monday __or__ not open Sunday"

Examples of filter combinations:
* `address:"St. George" AND tag:"pizza" AND open:"monday(>14:00)"`
* `campus:"UTSC" AND name:"Subway"`
* `open:"thursday(57600)" AND campus:"UTM" AND tag:"breakfast" OR tag:"quick"`

- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -building_id`. The default value is `+id`.

## Filter keys

The following is a list of all filter keys that can be used in the `q` parameter.

| Key            | Type   | Example                |
|----------------|--------|------------------------|
| `name`         | String | `name:!"Subway"`       |
| `short_name`   | String | `short_name:"coffee"`  |
| `campus`       | String | `campus:!"UTSG"`       |
| `address`      | String | `address:"St. George"` |
| `lat`          | Number | `lat:>43.5`            |
| `lng`          | Number | `lng:<=0`              |
| `tag`          | String | `tag:"pizza"`          |
| `open`         | Day    | `open:"monday(14:00)"` |

## Example

```
https://cobalt.qas.im/api/1.0/food/filter?q=address:"St. George" AND tag:"pizza" AND open:"monday(>14:00)"
```

```json
[
  {
    "id":"0366",
    "building_id":"006",
    "name":"Robarts Cafeteria",
    "short_name":"robarts_cafeteria",
    "description":"Located on the second floor of Robarts Library across from the T-Card office, this full cafeteria includes Subway, Pizza Pizza, Chicken Chicken, Euro Market, Express, Expressos, Benne Pasta and Bento Nouveau Sushi.\n",
    "url":"",
    "image":"http://map.utoronto.ca/_assets/_m_b/Robarts.jpg",
    "campus":"UTSG",
    "lat":43.66454,
    "lng":-79.39911,
    "address":"130 St. George St, Toronto, ON M5S 1A5",
    "hours":{
      "sunday":{
        "closed":true,
        "open":0,
        "close":0
      },
      "monday":{
        "closed":false,
        "open":28800,
        "close":64800
      },
      "tuesday":{
        "closed":false,
        "open":28800,
        "close":64800
      },
      "wednesday":{
        "closed":false,
        "open":28800,
        "close":64800
      },
      "thursday":{
        "closed":false,
        "open":28800,
        "close":64800
      },
      "friday":{
        "closed":false,
        "open":28800,
        "close":61200
      },
      "saturday":{
        "closed":true,
        "open":0,
        "close":0
      }
    },
    "tags":[
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

---

```
https://cobalt.qas.im/api/1.0/food/filter?q=campus:"UTSC" AND name:"Subway"
```

```json

  {
    "id":"1231",
    "building_id":"203",
    "name":"Subway",
    "short_name":"subway_utsc",
    "description":"Located on the Ground Level of the Student Centre, this food outlet offers various submarine sandwiches, salads and snacks\n\nFor hours of operation, visit http://uoft.me/utscfood",
    "url":"",
    "image":"",
    "campus":"UTSC",
    "lat":43.78508,
    "lng":-79.18703,
    "address":"1265 Military Trail, Toronto ON, M1C 1A4",
    "hours":{
      "sunday":{
        "closed":false,
        "open":34200,
        "close":75600
      },
      "monday":{
        "closed":false,
        "open":25200,
        "close":77400
      },
      "tuesday":{
        "closed":false,
        "open":25200,
        "close":77400
      },
      "wednesday":{
        "closed":false,
        "open":25200,
        "close":77400
      },
      "thursday":{
        "closed":false,
        "open":25200,
        "close":77400
      },
      "friday":{
        "closed":false,
        "open":25200,
        "close":77400
      },
      "saturday":{
        "closed":false,
        "open":25200,
        "close":77400
      }
    },
    "tags":[
      "subs",
      "salads",
      "snacks"
    ]
  }
]
```

---

```
https://cobalt.qas.im/api/1.0/food/filter?limit=2&q=open:"open:"thursday(57600)" AND campus:"UTM" AND tag:"breakfast" OR tag:"quick"
```

```json
[
  {
    "id":"1176",
    "building_id":"313",
    "name":"Temporary Food Court",
    "short_name":"tfc_utm",
    "description":"The Temporary Food Court is host to several quality dining options including:\n*Booster Juice\n*Elements\n*International Kitchen\n*Pizza Pizza\n*Quick Cuisine\n*Tandoori Indian Cuisine\n*Tim Hortons Express\n*Deli (Opening 2014)\n*Hours subject to change",
    "url":"",
    "image":"http://map.utoronto.ca/_assets/_m_b/TemporayFoodCourt.png",
    "campus":"UTM",
    "lat":43.54822,
    "lng":-79.66209,
    "address":"Davis Building, 3359 Mississauga Rd. Mississauga Ontario",
    "hours":{
      "sunday":{
        "closed":true,
        "open":0,
        "close":0
      },
      "monday":{
        "closed":false,
        "open":28800,
        "close":75600
      },
      "tuesday":{
        "closed":false,
        "open":28800,
        "close":75600
      },
      "wednesday":{
        "closed":false,
        "open":28800,
        "close":75600
      },
      "thursday":{
        "closed":false,
        "open":28800,
        "close":75600
      },
      "friday":{
        "closed":false,
        "open":28800,
        "close":68400
      },
      "saturday":{
        "closed":true,
        "open":0,
        "close":0
      }
    },
    "tags":[
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
  },
  {
    "id":"1179",
    "building_id":"313",
    "name":"Tim Hortons",
    "short_name":"tim_dv_utm",
    "description":"Tim Hortons offers its own special blend coffee, traditional doughnuts and other baked goods, breakfast, soups & chili, as well as an excellent selection of sandwiches and wraps.",
    "url":"http://www.dineoncampus.ca/utm/?cmd=Menus",
    "image":"http://map.utoronto.ca/_assets/_m_b/Tim-Hortons.jpg",
    "campus":"UTM",
    "lat":43.54817,
    "lng":-79.66138,
    "address":"Davis Building Meeting Place, 3359 Mississauga Rd. Mississauga Ontario",
    "hours":{
      "sunday":{
        "closed":false,
        "open":39600,
        "close":57600
      },
      "monday":{
        "closed":false,
        "open":27000,
        "close":79200
      },
      "tuesday":{
        "closed":false,
        "open":27000,
        "close":79200
      },
      "wednesday":{
        "closed":false,
        "open":27000,
        "close":79200
      },
      "thursday":{
        "closed":false,
        "open":27000,
        "close":79200
      },
      "friday":{
        "closed":false,
        "open":27000,
        "close":68400
      },
      "saturday":{
        "closed":false,
        "open":39600,
        "close":57600
      }
    },
    "tags":[
      "coffee",
      "tea",
      "sweets",
      "savoury",
      "sandwich",
      "soup",
      "breakfast",
      "lunch",
      "dinner"
    ]
  }
]
```
