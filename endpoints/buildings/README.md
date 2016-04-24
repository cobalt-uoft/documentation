## Building API

Campus building API with geographic location information.

#### Format

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

#### Reference

* [Introduction](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/introduction.md)
* [GET buildings](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/list.md)
* [GET buildings/:id](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/show.md)
* [GET buildings/search](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/search.md)
* [GET buildings/filter](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/filter.md)
