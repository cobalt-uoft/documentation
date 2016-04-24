# GET athletics/:id

Returns a specific entry identified by the `:id` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/athletics/:id
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:id` _(required)_
The unique identifier for the entry.

## Example

```
https://cobalt.qas.im/api/1.0/athletics/30M
```

```json
{
  "id":"30M",
  "date":"2016-04-30T00:00:00.000Z",
  "campus":"UTM",
  "events":[
    {
      "title":"Yogilates",
      "location":"Dance Studio",
      "building_id":"332",
      "start_time":"2016-04-30T16:10:00.000Z",
      "end_time":"2016-04-30T17:00:00.000Z"
    },
    {
      "title":"Length Swim",
      "location":"Pool",
      "building_id":"332",
      "start_time":"2016-04-30T17:10:00.000Z",
      "end_time":"2016-04-30T20:00:00.000Z"
    }
  ]
}
```
