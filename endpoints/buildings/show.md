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
  "lat":43.66074,
  "lng":-79.39373,
  "address":{
    "street":"1  King's College Circle",
    "city":"Toronto",
    "province":"ON",
    "country":"Canada",
    "postal":"M5S 1A8"
  }
}
```
