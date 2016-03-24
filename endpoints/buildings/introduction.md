# Building API

Campus building API with geographic location information.

## Format

```js
{
  "id":String,
  "code":String,
  "name":String,
  "short_name":String,
  "campus":String,
  "address":{
    "street":String,
    "city":String,
    "province":String,
    "country":String,
    "postal":String
  },
  "lat":Number,
  "lng":Number,
  "polygon":[
    [Number, Number]
  ]
}
```
