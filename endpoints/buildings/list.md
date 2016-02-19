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
    "id":"005",
    "code":"MS",
    "name":"Medical Sciences Building",
    "short_name":"MSB",
    "campus":"UTSG",
    "lat":43.66074,
    "lng":-79.39373,
    "address":{
      "street":"1  King's College Circle",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5S 1A8"
    }
  },
  {
    "id":"158",
    "code":"CN",
    "name":"Chestnut Residence and Conference Centre",
    "short_name":"Chestnut-89",
    "campus":"UTSG",
    "lat":43.65431,
    "lng":-79.38536,
    "address":{
      "street":"89  Chestnut Street",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5G 1R1"
    }
  }
]
```
