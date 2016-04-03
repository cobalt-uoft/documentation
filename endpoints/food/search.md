# GET food/search

Returns a list of vendors that match a text search on the `name`, `description`, `campus`, and `tags` keys.

## URL

```
https://cobalt.qas.im/api/1.0/food/search
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -department`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/food/search?q="pizza"&limit=2
```

```js
[
  {
    id: "1152",
    building_id: "200M",
    name: "Beechgrove Cafe",
    short_name: "beechgrove_cafe_utsc",
    description: "This cafe on the ground level features the coffee line from Seattle's Best Coffee as well as quick grab and go snack items, sandwiches, cold beverages and Pizza Pizza slices. For hours of operation, visit http://uoft.me/utscfood",
    url: "http://www.utsc.utoronto.ca/~facilities/food_bev.html",
    image: "",
    campus: "UTSC",
    lat: 43.78286,
    lng: -79.18618,
    address: "1265 Military Trail, Toronto ON, M1C 1A4",
    hours: {
      saturday: {
        closed: true,
        open: 0,
        close: 0
      },
      friday: {
        closed: false,
        open: 8.5,
        close: 15
      },
      thursday: {
        closed: false,
        open: 8.5,
        close: 20.5
      },
      wednesday: {
        closed: false,
        open: 8.5,
        close: 20.5
      },
      tuesday: {
        closed: false,
        open: 8.5,
        close: 16
      },
      monday: {
        closed: false,
        open: 8.5,
        close: 16
      },
      sunday: {
        closed: true,
        open: 0,
        close: 0
      }
    },
    tags: [
      "snacks",
      "coffee",
      "seattle's best coffee",
      "pizza",
      "sandwiches"
    ]
  },
  {
    id: "1176",
    building_id: "313",
    name: "Temporary Food Court",
    short_name: "tfc_utm",
    description: "The Temporary Food Court is host to several quality dining options including: *Booster Juice *Elements *International Kitchen *Pizza Pizza *Quick Cuisine *Tandoori Indian Cuisine *Tim Hortons Express *Deli (Opening 2014) *Hours subject to change",
    url: "",
    image: "http://map.utoronto.ca/_assets/_m_b/TemporayFoodCourt.png",
    campus: "UTM",
    lat: 43.54822,
    lng: -79.66209,
    address: "Davis Building, 3359 Mississauga Rd. Mississauga Ontario",
    hours: {
      saturday: {
        closed: true,
        open: 0,
        close: 0
      },
      friday: {
        closed: false,
        open: 8,
        close: 19
      },
      thursday: {
        closed: false,
        open: 8,
        close: 21
      },
      wednesday: {
        closed: false,
        open: 8,
        close: 21
      },
      tuesday: {
        closed: false,
        open: 8,
        close: 21
      },
      monday: {
        closed: false,
        open: 8,
        close: 21
      },
      sunday: {
        closed: true,
        open: 0,
        close: 0
      }
    },
    tags: [
      "indian",
      "international",
      "quick",
      "pizza",
      "juice",
      "food court",
      "takeout",
      "grab and go",
      "smoothies",
      "salads",
      "coffee"
    ]
  }
]
```
