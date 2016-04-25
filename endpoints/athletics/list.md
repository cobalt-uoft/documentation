# GET athletics

Returns a list of athletics.

## URL

```
https://cobalt.qas.im/api/1.0/athletics
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
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
https://cobalt.qas.im/api/1.0/athletics?limit=2
```

```json
[
  {
    "id":"01M",
    "date":"2016-04-01T00:00:00.000Z",
    "campus":"UTM",
    "events":[
      {
        "title":"Length Swim",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T11:00:00.000Z",
        "end_time":"2016-04-01T13:00:00.000Z"
      },
      {
        "title":"Drop-in Indoor Soccer",
        "location":"Gym C",
        "building_id":"332",
        "start_time":"2016-04-01T13:00:00.000Z",
        "end_time":"2016-04-01T18:00:00.000Z"
      },
      {
        "title":"Women's Only Swim",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T15:10:00.000Z",
        "end_time":"2016-04-01T16:00:00.000Z"
      },
      {
        "title":"Pilates-Fit",
        "location":"Dance Studio",
        "building_id":"332",
        "start_time":"2016-04-01T16:10:00.000Z",
        "end_time":"2016-04-01T17:00:00.000Z"
      },
      {
        "title":"Length Swim",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T16:10:00.000Z",
        "end_time":"2016-04-01T19:00:00.000Z"
      },
      {
        "title":"Aqua-Fit",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T16:10:00.000Z",
        "end_time":"2016-04-01T17:00:00.000Z"
      },
      {
        "title":"Zumba",
        "location":"Dance Studio",
        "building_id":"332",
        "start_time":"2016-04-01T17:10:00.000Z",
        "end_time":"2016-04-01T18:00:00.000Z"
      },
      {
        "title":"Drop-in Volleyball",
        "location":"Gym C",
        "building_id":"332",
        "start_time":"2016-04-01T18:30:00.000Z",
        "end_time":"2016-04-01T20:30:00.000Z"
      },
      {
        "title":"Drop-in Basketball",
        "location":"Gym C",
        "building_id":"332",
        "start_time":"2016-04-01T18:30:00.000Z",
        "end_time":"2016-04-01T20:30:00.000Z"
      },
      {
        "title":"Drop-in Badminton",
        "location":"Gym C",
        "building_id":"332",
        "start_time":"2016-04-01T21:00:00.000Z",
        "end_time":"2016-04-02T00:00:00.000Z"
      },
      {
        "title":"Length Swim",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T21:10:00.000Z",
        "end_time":"2016-04-01T23:00:00.000Z"
      }
    ]
  },
  {
    "id":"01SC",
    "date":"2016-04-01T00:00:00.000Z",
    "campus":"UTSC",
    "events":[
      {
        "title":"Basketball",
        "location":"Gym 3",
        "building_id":"208",
        "start_time":"2016-04-01T12:00:00.000Z",
        "end_time":"2016-04-01T14:00:00.000Z"
      },
      {
        "title":"Pilates",
        "location":"Studio 1",
        "building_id":"208",
        "start_time":"2016-04-01T12:00:00.000Z",
        "end_time":"2016-04-01T12:50:00.000Z"
      },
      {
        "title":"Aquafit",
        "location":"Training Pool",
        "building_id":"208",
        "start_time":"2016-04-01T13:30:00.000Z",
        "end_time":"2016-04-01T14:20:00.000Z"
      },
      {
        "title":"Booty Camp",
        "location":"Studio 2",
        "building_id":"208",
        "start_time":"2016-04-01T15:00:00.000Z",
        "end_time":"2016-04-01T15:50:00.000Z"
      },
      {
        "title":"Rock Climbing Club",
        "location":"Climbing Wall",
        "building_id":"208",
        "start_time":"2016-04-01T16:00:00.000Z",
        "end_time":"2016-04-01T18:30:00.000Z"
      },
      {
        "title":"Tabata Bootcamp",
        "location":"Studio 2",
        "building_id":"208",
        "start_time":"2016-04-01T16:00:00.000Z",
        "end_time":"2016-04-01T16:50:00.000Z"
      },
      {
        "title":"Badminton/Table Tennis",
        "location":"Gym 4",
        "building_id":"208",
        "start_time":"2016-04-01T17:00:00.000Z",
        "end_time":"2016-04-01T19:00:00.000Z"
      },
      {
        "title":"Bosu",
        "location":"Studio 2",
        "building_id":"208",
        "start_time":"2016-04-01T17:00:00.000Z",
        "end_time":"2016-04-01T17:30:00.000Z"
      },
      {
        "title":"Drop-In Climbing",
        "location":"Climbing Wall",
        "building_id":"208",
        "start_time":"2016-04-01T20:00:00.000Z",
        "end_time":"2016-04-02T01:00:00.000Z"
      },
      {
        "title":"Learn to Climb",
        "location":"Climbing Wall",
        "building_id":"208",
        "start_time":"2016-04-01T20:00:00.000Z",
        "end_time":"2016-04-02T01:00:00.000Z"
      },
      {
        "title":"Basketball",
        "location":"Gym 1 & 2",
        "building_id":"208",
        "start_time":"2016-04-01T20:00:00.000Z",
        "end_time":"2016-04-01T22:00:00.000Z"
      }
    ]
  }
]
```
