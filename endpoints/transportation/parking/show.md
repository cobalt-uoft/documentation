# GET transportation/parking/:id

Returns a specific parking spot identified by the `:id` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/transportation/parking/:id
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:id` _(required)_
The unique identifier for the parking spot.

## Example

```
https://cobalt.qas.im/api/1.0/transportation/parking/0272
```

```json
{
  "id":"0272",
  "title":"Bicycle Parking:Innis Residence",
  "building_id":"133",
  "campus":"UTSG",
  "type":"bicycle",
  "description":"10 post & ring bicycle stands",
  "lat":43.66586,
  "lng":-79.39897,
  "address":""
}
```
