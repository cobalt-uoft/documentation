# GET buildings

Returns a list of buildings.

## URL

```
https://cobalt.qas.im/api/1.0/buildings
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -department`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/buildings?limit=2
```

```js
[
  {
    "id":"001",
    "code":"UC",
    "name":"University College",
    "short_name":"UC",
    "campus":"UTSG",
    "address":{
      "street":"15  King's College Circle",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5S 3H7"
    },
    "lat":43.66319655917286,
    "lng":-79.395819910554,
    "polygon":[
      [43.66252,-79.39552],
      [43.66254,-79.39551],
      [43.66255,-79.39548],
               ...
      [43.66253,-79.39561],
      [43.66254,-79.39556],
      [43.66252,-79.39555]
    ]
  },
  {
    "id":"002",
    "code":"HH",
    "name":"Hart House",
    "short_name":"Hart House",
    "campus":"UTSG",
    "address":{
      "street":"7  Hart House Circle",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5S 3H3"
    },
    "lat":43.663700559989046,
    "lng":-79.3945183686304,
    "polygon":[
      [43.66357,-79.39516],
      [43.66354,-79.39515],
      [43.6636,-79.39485],
               ...
      [43.6638,-79.39493],
      [43.66376,-79.39512],
      [43.66359,-79.39506]
    ]
  }
]
```
