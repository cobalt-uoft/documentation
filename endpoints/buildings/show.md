# GET buildings/:id

Returns a specific building identified by the `:id` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/buildings/:id
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:id` _(required)_
The unique identifier for the building.

## Example

```
https://cobalt.qas.im/api/1.0/buildings/005
```

```js
{
  "id":"005",
  "code":"MS",
  "name":"Medical Sciences Building",
  "short_name":"MSB",
  "campus":"UTSG",
  "address":{
    "street":"1  King's College Circle",
    "city":"Toronto",
    "province":"ON",
    "country":"Canada",
    "postal":"M5S 1A8"
  },
  "lat":43.660739554480855,
  "lng":-79.3937338224935,
  "polygon":[
    [43.66119,-79.39353],
    [43.6611,-79.39349],
    [43.66111,-79.39344],
             ...
    [43.6613,-79.39322],
    [43.66131,-79.39319],
    [43.66127,-79.39318]
  ]
}
```
