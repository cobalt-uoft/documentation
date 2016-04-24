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
* `-` indicates not (eg. `campus:-"UTSC"`)
* String filters can be applied to:
  * name (eg. `name:"Subway"`)
  * address (eg. `address:"St. George"`)
  * campus (eg. `campus:"UTM"`)
  * tags (eg. `tag:"innis"`)

Special filters:
* `open`
  * Each vendor is open a set number of hours for the 7 days of the week. Use this filter to find when a restaurant is open or closed.
  * To check for specific timings, include hours in parentheses after the day.
    * No operator means "open at":
      * `open:"sunday(14)"` => "open Sunday at 2 pm"
      * `open:"monday(23.5)" AND open:"thursday(19)"` => "open Monday at 11:30 pm __and__ Thursday at 7 pm"
    * `|` means "open between (inclusive)":
      * `open:"monday(16|20.25)"` => "open Monday between 4 pm and 8:15 pm"
      * `open:"tuesday(7|13)" OR open:"friday(14)"` => "open Tuesday between 7 am and 1 pm __or__ open Friday at 3 pm"
    * `>` means "open after"
      * `open:"friday(>15)"` => "open Friday after 3 pm"
    * `<` means "open before"
      * `open:"friday(<15)"` => "open Friday before 3 pm"
  * No parentheses checks if the vendor is open at all on that day. Use `-` to check not open.
    * `open:"monday" AND open:-"sunday"` => "open Monday __and__ not Sunday"
    * `open:"monday" OR open:-"sunday"` => "open Monday __or__ not open Sunday"

Examples of filter combinations:
* `address:"St. George" AND tag:"pizza" AND open:"monday(>14)"`
* `campus:"UTSC" AND name:"Subway"`
* `open:"thursday(16)" AND campus:"UTM" AND tag:"breakfast" OR tag:"quick"`

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
https://cobalt.qas.im/api/1.0/food/filter?q=address:"St. George" AND tag:"pizza" AND open:"monday(>14)"
```

```json
[
  {
    "id":"0366",
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
        "close":17
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

---

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

---

```
https://cobalt.qas.im/api/1.0/food/filter?q=open:"open:"thursday(16)" AND campus:"UTM" AND tag:"breakfast" OR tag:"quick"
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
        "open":11,
        "close":16
      },
      "monday":{
        "closed":false,
        "open":7.5,
        "close":22
      },
      "tuesday":{
        "closed":false,
        "open":7.5,
        "close":22
      },
      "wednesday":{
        "closed":false,
        "open":7.5,
        "close":22
      },
      "thursday":{
        "closed":false,
        "open":7.5,
        "close":22
      },
      "friday":{
        "closed":false,
        "open":7.5,
        "close":19
      },
      "saturday":{
        "closed":false,
        "open":11,
        "close":16
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
  },
  {
    "id":"1186",
    "building_id":"334",
    "name":"On the Go",
    "short_name":"otg_ib_utm",
    "description":"Offers freshly prepared & pre-packaged meals, snacks, and beverages so you can take your food 'On the Go!' Select from a variety of sandwiches, wraps, sushi, and salad or enjoy healthy snacks such as yogurt, parfait, fruit cups, and pita with humus.",
    "url":"",
    "image":"http://map.utoronto.ca/_assets/_m_b/On_The_Go_Logo1.jpg",
    "campus":"UTM",
    "lat":43.55122,
    "lng":-79.66373,
    "address":"Instructional Centre, 3359 Mississauga Rd., Mississauga, Ontario",
    "hours":{
      "sunday":{
        "closed":true,
        "open":0,
        "close":0
      },
      "monday":{
        "closed":false,
        "open":10.5,
        "close":17
      },
      "tuesday":{
        "closed":false,
        "open":10.5,
        "close":17
      },
      "wednesday":{
        "closed":false,
        "open":10.5,
        "close":17
      },
      "thursday":{
        "closed":false,
        "open":10.5,
        "close":17
      },
      "friday":{
        "closed":false,
        "open":10.5,
        "close":15
      },
      "saturday":{
        "closed":true,
        "open":0,
        "close":0
      }
    },
    "tags":[
      "sandwiches",
      "salads",
      "snacks",
      "sushi",
      "quick",
      "on the go"
    ]
  }
]
```
