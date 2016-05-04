# Food API

Campus food vender API with daily time schedules.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/food/list.md">GET food</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/food/show.md">GET food/:id</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/food/search.md">GET food/search</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/food/filter.md">GET food/filter</a></li>
  </ul>
</div>

## Format

```js
{
  "id": String,
  "building_id": String,
  "name": String,
  "short_name": String,
  "description": String,
  "url": String,
  "tags": [String],
  "image": String,
  "campus": String,
  "lat": Number,
  "lng": Number,
  "address": String,
  "hours": {
    "sunday": {
      "closed": Boolean,
      "open": Number,
      "close": Number
    },
    "monday": {
      "closed": Boolean,
      "open": Number,
      "close": Number
    }
    "tuesday": {
      "closed": Boolean,
      "open": Number,
      "close": Number
    },
    "wednesday": {
      "closed": Boolean,
      "open": Number,
      "close": Number
    },
    "thursday": {
      "closed": Boolean,
      "open": Number,
      "close": Number
    },
    "friday": {
      "closed": Boolean,
      "open": Number,
      "close": Number
    }
  }
}
```
