# Building API

Campus building API with geographic location information.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/list.md">GET buildings</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/show.md">GET buildings/:id</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/search.md">GET buildings/search</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/buildings/filter.md">GET buildings/filter</a></li>
  </ul>
</div>

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
