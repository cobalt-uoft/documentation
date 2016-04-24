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

For string filters:
* No operator indicates contains (eg. `location:"Gym"`)
* `-` indicates not (eg. `campus:-"UTSC"`)
* String filters can be applied to:
  * campus (eg. `campus:"UTM"`)
  * title (eg. `title:"Basketball"`)
  * location (eg. `location:"Gym"`)

For date filters:
* Valid date formats: 
  1. [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date/datetime (eg. `date:"2016-09-25T23:59:59-04:00"`)
  2. Comma separated date, formatted as `y,m,d,H,M,S` (eg. `date:"2016,09,25,23,59,59"`)
  3. Milliseconds since January 1, 1970 (as an integer, __not__ a string) [eg. `date:1443196799`]
  4. Empty string means "current time" (eg. `date:""`)
* Operations:
  * No operator indicates equal to (eg. `date:"2016-04-01"`)
  * `>` indicates greater than (eg. `start:>1461474000`)
  * `<` indicates less than (eg. `end:<""`)
  * `>=` indicates greater than or equal to (eg. `lng:>=1461474000`)
  * `<=` indicates less than or equal to (eg. `date:<="2016,04,01"`)
* Date filters can be applied to:
  * date (eg. `date:"2016-04-24"`)
  * start time (eg. `start:>="2016,04,24"`)
  * end time (eg. `end:<""`)
* __Note__: Dates are served (and stored) with a [UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time) offset.

Examples of filter combinations:
* `location:"pool" AND campus:"UTM" AND start:<"2016-04-02"`
* `title:"Basketball" AND date:"2016-04-01"`

- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -campus`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/athletics/filter?q=location:"pool" AND campus:"UTM" AND start:<"2016-04-01T16:00:00"
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
    ],
    "matched_events":[
      {
        "title":"Length Swim",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T11:00:00.000Z",
        "end_time":"2016-04-01T13:00:00.000Z"
      },
      {
        "title":"Women's Only Swim",
        "location":"Pool",
        "building_id":"332",
        "start_time":"2016-04-01T15:10:00.000Z",
        "end_time":"2016-04-01T16:00:00.000Z"
      }
    ]
  }
]
```

```
https://cobalt.qas.im/api/1.0/athletics/filter?limit=1&q=title:"Basketball" AND date:"2016-04-01"
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
    ],
    "matched_events":[
      {
        "title":"Drop-in Basketball",
        "location":"Gym C",
        "building_id":"332",
        "start_time":"2016-04-01T18:30:00.000Z",
        "end_time":"2016-04-01T20:30:00.000Z"
      }
    ]
  }
]
```
