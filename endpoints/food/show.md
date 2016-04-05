# GET food/:id

Returns a specific vendor identified by the `:id` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/food/:id
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:id` _(required)_
The unique identifier for the course.

## Example

```
https://cobalt.qas.im/api/1.0/food/451
```

```json
{
  "id":"451",
  "building_id":"602",
  "name":"The Buttery",
  "short_name":"the-buttery",
  "description":"A la carte cafeteria offering a variety of hot meals and grab and go options. Menu includes Pizza Pizza; Design your own sandwich deli; Grab and Go Sandwiches; Salads; Yogurt Parfaits; Soups; Freshly baked goods; Starbucks Coffee; Fruit; & Snacks.",
  "url":"",
  "image":"",
  "campus":"UTSG",
  "lat":43.66565,
  "lng":-79.39703,
  "address":"15 Devonshire Pl, Toronto, ON M5S 2C8",
  "hours":{
    "sunday":{
      "closed":true,
      "open":0,
      "close":0
    },
    "monday":{
      "closed":true,
      "open":0,
      "close":0
    },
    "tuesday":{
      "closed":true,
      "open":0,
      "close":0
    },
    "wednesday":{
      "closed":true,
      "open":0,
      "close":0
    },
    "thursday":{
      "closed":true,
      "open":0,
      "close":0
    },
    "friday":{
      "closed":true,
      "open":0,
      "close":0
    },
    "saturday":{
      "closed":true,
      "open":0,
      "close":0
    }
  },
  "tags":[
    "Trinity",
    "Sandwiches",
    "Drinks",
    "Soups",
    "Salads"
  ]
}
```
