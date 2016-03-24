# GET buildings/search

Returns a list of buildings that match a text search on the `code`, `name`, and `short_name` keys.

## URL

```
https://cobalt.qas.im/api/1.0/buildings/search
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -campus`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/buildings/search?q=SF
```

```js
[
  {
    "id":"009",
    "code":"SF",
    "name":"Sandford Fleming Building",
    "short_name":"Sandford Flm",
    "campus":"UTSG",
    "address":{
      "street":"10  King's College Road",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5S 3G4"
    },
    "lat":43.66012007293862,
    "lng":-79.3951037607479,
    "polygon":[
      [43.66051,-79.39503],
      [43.66051,-79.39498],
      [43.66027,-79.39488],
               ...
      [43.6604,-79.39512],
      [43.66045,-79.39514],
      [43.66048,-79.39502]
    ]
  }
]
```
