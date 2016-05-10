# GET food

Returns a list of food vendors.

## URL

```
https://cobalt.qas.im/api/1.0/food
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
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
https://cobalt.qas.im/api/1.0/food?limit=2
```

```json
[
  {
    "id":"0274",
    "building_id":"152",
    "name":"Rehabilitation Sciences Veda",
    "short_name":"rehab_veda",
    "description":"Located inside the Rehabilitation Sciences builing at 500 University Avenue, Veda offers Indian takeout. Catering available 416-961-9797. Menu includes hot meals and snacks like curries, sandwiches, pizzas & samosas. Halal & Vegan options available.",
    "url":"http://www.vedatakeout.com/index.php",
    "image":"",
    "campus":"UTSG",
    "lat":43.65541,
    "lng":-79.38912,
    "address":"500 University Ave, Toronto, ON M5G 1V7",
    "hours":{
      "sunday":{
        "closed":true,
        "open":0,
        "close":0
      },
      "monday":{
        "closed":false,
        "open":36000,
        "close":54000
      },
      "tuesday":{
        "closed":false,
        "open":36000,
        "close":54000
      },
      "wednesday":{
        "closed":false,
        "open":36000,
        "close":54000
      },
      "thursday":{
        "closed":false,
        "open":36000,
        "close":54000
      },
      "friday":{
        "closed":false,
        "open":36000,
        "close":50400
      },
      "saturday":{
        "closed":true,
        "open":0,
        "close":0
      }
    },
    "tags":[
      "snacks",
      "beverage",
      "lug a mug",
      "microwave",
      "indian",
      "samosa",
      "curry"
    ]
  },
  {
    "id":"0276",
    "building_id":"068A",
    "name":"Athletic Centre Starbucks",
    "short_name":"starbucks_ac",
    "description":"Starbucks location with seating. Serving Starbucks snacks, beverages and merchandise. Located on the lower level of the Athletic Centre.",
    "url":"http://www.starbucks.com/ ",
    "image":"http://map.utoronto.ca/_assets/_m_b/AC_Starbucks.jpg",
    "campus":"UTSG",
    "lat":43.66292,
    "lng":-79.40131,
    "address":"55 Harbord St, Toronto, ON M5S 2W6",
    "hours":{
      "sunday":{
        "closed":false,
        "open":32400,
        "close":64800
      },
      "monday":{
        "closed":false,
        "open":25200,
        "close":75600
      },
      "tuesday":{
        "closed":false,
        "open":25200,
        "close":75600
      },
      "wednesday":{
        "closed":false,
        "open":25200,
        "close":75600
      },
      "thursday":{
        "closed":false,
        "open":25200,
        "close":75600
      },
      "friday":{
        "closed":false,
        "open":25200,
        "close":75600
      },
      "saturday":{
        "closed":false,
        "open":25200,
        "close":64800
      }
    },
    "tags":[
      "starbucks",
      "coffee",
      "beverage",
      "muffins",
      "cookies",
      "ac"
    ]
  }
]
```
