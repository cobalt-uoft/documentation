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

For string filters:
* No operator indicates contains (eg. `name:"Subway"`)
* `-` indicates not (eg. `campus:-UTSC`)
* String filters can be applied to name, address and campus

Special filters:
* `open`
  * Each vendor is open a set number of hours for the 7 days of the week. Use this filter to find when a restaurant is open or closed.
  * Separate days with a comma. Each comma represents an `AND` conjunction, an inclusive search (`OR`) can be done with: `open:"day1" OR open:"day2"`.
  * To check for specific timings, include hours in parentheses after the day.
    * No operator means "open at":
      * `open:"sunday(14)"` => "open Sunday at 2 pm"
      * `open:"monday(23.5),thursday(19)"` => "open Monday at 11:30 pm __and__ Thursday at 7 pm"
    * `|` means "open between (inclusive)":
      * `open:"monday(16|20.25)"` => "open Monday between 4 pm and 8:15 pm"
      * `open:"tuesday(7|13),friday(14)` => "open Tuesday between 7 am and 1 pm __and__ Friday at 3 pm"
    * `>` means "open after"
      * `open:"friday(>15)"` => "open Friday after 3 pm"
    * `<` means "open before"
      * `open:"friday(<15)"` => "open Friday before 3 pm"
  * No parentheses checks if the vendor is open at all on that day. Use `-` to check not open.
    * `open:"monday,-sunday"` => "open Monday __and__ not Sunday"
    * `open:"monday" OR open:"-sunday"` => "open Monday __or__ not open Sunday"
* `tags`
  * Each vendor has a list of `tags` that represent what they sell or what category of food they offer. Use this key to filter through vendors based on their tags.
  * Separate tags with a comma. Each comma represents an `AND` conjunction, for an inclusive search use: `tags:"tag1,tag2" OR tags:"tag3"`.
  * Some examples:
    * `tags:"pizza,coffee"` => "vendors that offer both pizza __and__ coffee"
    * `tags:"pizza" OR tags:"coffee"` => "vendors that offer pizza __or__ vendors that offer coffee"
  * You can also use `-` to filter for vendors that _don't_ have a certain tag:
    * `tags:"pizza,-coffee"` => "vendors that offer pizza __and__ not coffee"
    * `tags:"pizza" OR tags:"-coffee"` => "vendors that offer pizza __or__ vendors that don't offer coffee"

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

```json
[
  {
    "id":"366",
    "building_id":"006",
    "name":"Robarts Cafeteria",
    "short_name":"robarts_cafeteria",
    "description":"Located on the second floor of Robarts Library across from the T-Card office, this full cafeteria includes Subway, Pizza Pizza, Chicken Chicken, Euro Market, Express, Expressos, Benne Pasta and Bento Nouveau Sushi. ",
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
        "open":8,
        "close":18
      },
      "tuesday":{
        "closed":false,
        "open":8,
        "close":18
      },
      "wednesday":{
        "closed":false,
        "open":8,
        "close":18
      },
      "thursday":{
        "closed":false,
        "open":8,
        "close":18
      },
      "friday":{
        "closed":false,
        "open":8,
        "close":17
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

```
https://cobalt.qas.im/api/1.0/food/filter?q=campus:"UTSC" AND name:"Subway"
```

```json
[
  {
    "id":"1231",
    "building_id":"203",
    "name":"Subway",
    "short_name":"subway_utsc",
    "description":"Located on the Ground Level of the Student Centre, this food outlet offers various submarine sandwiches, salads and snacks For hours of operation, visit http://uoft.me/utscfood",
    "url":"",
    "image":"",
    "campus":"UTSC",
    "lat":43.78508,
    "lng":-79.18703,
    "address":"1265 Military Trail, Toronto ON, M1C 1A4",
    "hours":{
      "sunday":{
        "closed":false,
        "open":9.5,
        "close":21
      },
      "monday":{
        "closed":false,
        "open":7,
        "close":21.5
      },
      "tuesday":{
        "closed":false,
        "open":7,
        "close":21.5
      },
      "wednesday":{
        "closed":false,
        "open":7,
        "close":21.5
      },
      "thursday":{
        "closed":false,
        "open":7,
        "close":21.5
      },
      "friday":{
        "closed":false,
        "open":7,
        "close":21.5
      },
      "saturday":{
        "closed":false,
        "open":7,
        "close":21.5
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

```
https://cobalt.qas.im/api/1.0/food/filter?q=open:"monday(16)" AND campus:"UTM" AND tags:"quick,-snacks" OR tags:"indian"
```

```json
[  
  {  
    "id":"1176",
    "building_id":"313",
    "name":"Temporary Food Court",
    "short_name":"tfc_utm",
    "description":"The Temporary Food Court is host to several quality dining options including: *Booster Juice *Elements *International Kitchen *Pizza Pizza *Quick Cuisine *Tandoori Indian Cuisine *Tim Hortons Express *Deli (Opening 2014) *Hours subject to change",
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
        "open":8,
        "close":21
      },
      "tuesday":{  
        "closed":false,
        "open":8,
        "close":21
      },
      "wednesday":{  
        "closed":false,
        "open":8,
        "close":21
      },
      "thursday":{  
        "closed":false,
        "open":8,
        "close":21
      },
      "friday":{  
        "closed":false,
        "open":8,
        "close":19
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
  }
]
```
