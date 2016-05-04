# GET athletics/:date

Returns a specific entry identified by the `:date` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/athletics/:date
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:date` _(required)_
The date for the entry.

## Example

```
https://cobalt.qas.im/api/1.0/athletics/2016-04-01
```

```json
{
  "date":"2016-04-01",
  "events":[
    {
      "title":"Length Swim",
      "campus":"UTM",
      "location":"Pool",
      "building_id":"332",
      "start_time":25200,
      "end_time":32400,
      "duration":7200
    },
    {
      "title":"Drop-in Indoor Soccer",
      "campus":"UTM",
      "location":"Gym C",
      "building_id":"332",
      "start_time":32400,
      "end_time":50400,
      "duration":18000
    }
  ]
}
```
