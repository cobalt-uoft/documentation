# Food API

Campus food vender API with daily time schedules. __Note:__ Endpoints for this API are still [underdevelopment](https://github.com/cobalt-uoft/cobalt/issues/22#issuecomment-204856970).

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
