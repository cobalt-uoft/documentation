# GET transportation/parking/search

Returns a list of parking spots that match a text search on the `title`, `description`, and `address` keys.

## URL

```
https://cobalt.qas.im/api/1.0/transportation/parking/search
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -title`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/transportation/parking/search?q="bloor"&limit=2
```

```json
[
  {
    "id":"0123",
    "title":"371 Bloor Street West",
    "building_id":"014",
    "campus":"UTSG",
    "type":"car",
    "description":"Cash Parking\n$3.00 half hour\n$10.00 Maximum until 10pm\nOvernight parking 4pm to 6:0am $7.00\nWeekends $7.00\nUnreserved Permit Parking\n24/7 parking \nCash parking receipts are not transferable and are valid at the parking lot where purchased.",
    "lat":43.66623,
    "lng":-79.4025,
    "address":"371 Bloor St W, Toronto, ON M5S 2R7, Canada"
  },
  {
    "id":"0259",
    "title":"Bicycle Parking:371 Bloor Street West",
    "building_id":"14",
    "campus":"UTSG",
    "type":"bicycle",
    "description":"29 post & ring stands, 2 racks, and 3 bicycle lockers",
    "lat":43.66654,
    "lng":-79.40331,
    "address":""
  }
]
```
