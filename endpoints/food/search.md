# GET food/search

Returns a list of vendors that match a text search on the `name`, `description`, `campus`, and `tags` keys.

## URL

```
https://cobalt.qas.im/api/1.0/food/search
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The string to perform a text search with. It is also possible to do a verbatim search by surrounding the string in double quotes.
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
https://cobalt.qas.im/api/1.0/food/search?q="pizza"&limit=2
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
        "open":10,
        "close":15
      },
      "tuesday":{
        "closed":false,
        "open":10,
        "close":15
      },
      "wednesday":{
        "closed":false,
        "open":10,
        "close":15
      },
      "thursday":{
        "closed":false,
        "open":10,
        "close":15
      },
      "friday":{
        "closed":false,
        "open":10,
        "close":14
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
    "id":"0313",
    "building_id":"009",
    "name":"Hard Hat Cafe",
    "short_name":"hard_hat_cafe",
    "description":"Located in the basement of Sandford Fleming, this cafe is owned and operated by the Engineering Society. Offerings include coffee, baked goods, pizza, frozen entrees, beverages and snacks.",
    "url":"",
    "image":"",
    "campus":"UTSG",
    "lat":43.66018,
    "lng":-79.3951,
    "address":"10 King's College Rd, Toronto, ON M5S 3G4",
    "hours":{
      "sunday":{
        "closed":true,
        "open":0,
        "close":0
      },
      "monday":{
        "closed":false,
        "open":10,
        "close":17
      },
      "tuesday":{
        "closed":false,
        "open":10,
        "close":17
      },
      "wednesday":{
        "closed":false,
        "open":10,
        "close":17
      },
      "thursday":{
        "closed":false,
        "open":10,
        "close":17
      },
      "friday":{
        "closed":false,
        "open":10,
        "close":19
      },
      "saturday":{
        "closed":true,
        "open":0,
        "close":0
      }
    },
    "tags":[
      "engsoc",
      "skule",
      "pit stop",
      "sandford"
    ]
  }
]
```
