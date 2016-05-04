# GET athletics/filter

Returns a list of athletics that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/athletics/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For date and time filters:
* No operator indicates equal to (eg. `date:"2016-06-03"`)
* `>` indicates greater than (eg. `duration:>"2:00"`)
* `<` indicates less than (eg. `start:<"12:00"`)
* `>=` indicates greater than or equal to (eg. `date:>="2016-04-20"`)
* `<=` indicates less than or equal to (eg. `duration:<=7200`)
* `!` indicates not (eg. `date:!"2016-09-17"`)

For date filters:
* All numerical operators work with date keys. The date must be provided as a formatted string (i.e. `YYYY-MM-DD`).

For time filters:
* All numerical operators work with time keys. The time can be provided as a formatted string (i.e. `"HH:MM"`).
* Alternatively, the time can be provided as an integer representing the seconds since midnight (i.e. `32400` for 9:00).

For string filters:
* No operator indicates contains (eg. `location:"pool"`)
* `!` indicates not (eg. `campus:!"UTSC"`)

Examples of filter combinations:
* `location:"pool" AND campus:"UTM" AND start:<"12:00"`
* `title:"Basketball" AND date:"2016-04-01"`

For filters that involve properties from `events`, an additional key is returned called `matched_events`, which contains only the events that match the filter.
- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `-campus +date`. The default value is `+date`.

## Filter keys

The following is a list of all filter keys that can be used in the `q` parameter.

| Key           | Type   | Example             |
|---------------|--------|---------------------|
| `date`        | Date   | `date:"2016-04-20"` |
| `title`       | String | `title:!"swim"`     |
| `campus`      | String | `campus:"UTSG"`     |
| `location`    | String | `location:!"gym"`   |
| `building_id` | String | `building_id:"332"` |
| `start`       | Time   | `start:<"12:00"`    |
| `end`         | Time   | `end:>"18:00"`      |
| `duration`    | Time   | `duration:7200`     |

## Example

```
https://cobalt.qas.im/api/1.0/athletics/filter?q=location:"pool" AND campus:"UTM" AND date:"2016-04-01" AND start:"7:00"
```

```json
[
  {
    "date":"2016-04-01",
    "matched_events":[
      {
        "title":"Length Swim",
        "campus":"UTM",
        "location":"Pool",
        "building_id":"332",
        "start_time":25200,
        "end_time":32400,
        "duration":7200
      }
    ],
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
      },
      {
        "title":"Women's Only Swim",
        "campus":"UTM",
        "location":"Pool",
        "building_id":"332",
        "start_time":40200,
        "end_time":43200,
        "duration":3000
      },
      {
        "title":"Pilates-Fit",
        "campus":"UTM",
        "location":"Dance Studio",
        "building_id":"332",
        "start_time":43800,
        "end_time":46800,
        "duration":3000
      },
      {
        "title":"Length Swim",
        "campus":"UTM",
        "location":"Pool",
        "building_id":"332",
        "start_time":43800,
        "end_time":54000,
        "duration":10200
      },
      {
        "title":"Aqua-Fit",
        "campus":"UTM",
        "location":"Pool",
        "building_id":"332",
        "start_time":43800,
        "end_time":46800,
        "duration":3000
      },
      {
        "title":"Zumba",
        "campus":"UTM",
        "location":"Dance Studio",
        "building_id":"332",
        "start_time":47400,
        "end_time":50400,
        "duration":3000
      },
      {
        "title":"Drop-in Volleyball",
        "campus":"UTM",
        "location":"Gym C",
        "building_id":"332",
        "start_time":52200,
        "end_time":59400,
        "duration":7200
      },
      {
        "title":"Drop-in Basketball",
        "campus":"UTM",
        "location":"Gym C",
        "building_id":"332",
        "start_time":52200,
        "end_time":59400,
        "duration":7200
      },
      {
        "title":"Drop-in Badminton",
        "campus":"UTM",
        "location":"Gym C",
        "building_id":"332",
        "start_time":61200,
        "end_time":72000,
        "duration":10800
      },
      {
        "title":"Length Swim",
        "campus":"UTM",
        "location":"Pool",
        "building_id":"332",
        "start_time":61800,
        "end_time":68400,
        "duration":6600
      },
      {
        "title":"Basketball",
        "campus":"UTSC",
        "location":"Gym 3",
        "building_id":"208",
        "start_time":28800,
        "end_time":36000,
        "duration":7200
      },
      {
        "title":"Pilates",
        "campus":"UTSC",
        "location":"Studio 1",
        "building_id":"208",
        "start_time":28800,
        "end_time":31800,
        "duration":3000
      },
      {
        "title":"Aquafit",
        "campus":"UTSC",
        "location":"Training Pool",
        "building_id":"208",
        "start_time":34200,
        "end_time":37200,
        "duration":3000
      },
      {
        "title":"Booty Camp",
        "campus":"UTSC",
        "location":"Studio 2",
        "building_id":"208",
        "start_time":39600,
        "end_time":42600,
        "duration":3000
      },
      {
        "title":"Rock Climbing Club",
        "campus":"UTSC",
        "location":"Climbing Wall",
        "building_id":"208",
        "start_time":43200,
        "end_time":52200,
        "duration":9000
      },
      {
        "title":"Tabata Bootcamp",
        "campus":"UTSC",
        "location":"Studio 2",
        "building_id":"208",
        "start_time":43200,
        "end_time":46200,
        "duration":3000
      },
      {
        "title":"Badminton/Table Tennis",
        "campus":"UTSC",
        "location":"Gym 4",
        "building_id":"208",
        "start_time":46800,
        "end_time":54000,
        "duration":7200
      },
      {
        "title":"Bosu",
        "campus":"UTSC",
        "location":"Studio 2",
        "building_id":"208",
        "start_time":46800,
        "end_time":48600,
        "duration":1800
      },
      {
        "title":"Drop-In Climbing",
        "campus":"UTSC",
        "location":"Climbing Wall",
        "building_id":"208",
        "start_time":57600,
        "end_time":75600,
        "duration":18000
      },
      {
        "title":"Basketball",
        "campus":"UTSC",
        "location":"Gym 1 & 2",
        "building_id":"208",
        "start_time":57600,
        "end_time":64800,
        "duration":7200
      },
      {
        "title":"Learn to Climb",
        "campus":"UTSC",
        "location":"Climbing Wall",
        "building_id":"208",
        "start_time":61200,
        "end_time":75600,
        "duration":14400
      }
    ]
  }
]
```
