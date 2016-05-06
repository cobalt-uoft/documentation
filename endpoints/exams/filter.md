# GET exams/filter

Returns a list of exams that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/exams/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For numerical and time filters:
* No operator indicates equal to (eg. `duration:10800`)
* `>` indicates greater than (eg. `start_time:>32400`)
* `<` indicates less than (eg. `end_time:<43200`)
* `>=` indicates greater than or equal to (eg. `start_time:>=50400`)
* `<=` indicates less than or equal to (eg. `end_time:<=61200`)
* `!` indicates not (eg. `duration:!7200`)

For string filters:
* No operator indicates contains (eg. `code:"CSC"`)
* `!` indicates not (eg. `period:!"DEC15"`)

For time filters:
* All numerical operators work with time keys. The time can be provided as a formatted string (i.e. `"HH:MM"`).
* Alternatively, the time can be provided as an integer representing the seconds since midnight (i.e. `32400` for 9:00).

Examples of filter combinations:
* `campus:"UTSG" AND id:"CSC" AND date:"2016-04-14"`
* `code:"ECO" AND lecture:"L2001" AND period:!"DEC15"`
* `start:>"16:00" AND duration:10800 OR end:<49500`

For filters that involve properties from `sections`, an additional key is returned called `matched_sections`, which contains only the sections that match the filter.
- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -department`. The default value is `+id`.

## Filter keys

The following is a list of all filter keys that can be used in the `q` parameter.

| Key            | Type   | Example                          |
|----------------|--------|----------------------------------|
| `id`           | String | `id:"ANT"`                       |
| `code`         | String | `code:"CSC"`                     |
| `campus`       | String | `campus:!"UTSC"`                 |
| `period`       | String | `period:"APR16"`                 |
| `date`         | Date   | `date:"2016-04-28"`              |
| `start`        | Time   | `start:>=75600`                  |
| `end`          | Time   | `end:<"21:00"`                   |
| `duration`     | Time   | `duration:"3:00"`                |
| `lecture`      | String | `lecture:"L0101"`                |
| `location`     | String | `location:"BA"`                  |

## Example

```
https://cobalt.qas.im/api/1.0/courses/filter?q=code:"ECO" AND lecture:"L2001" AND period:!"DEC15"
```

```json
[
  {
    "id":"ECO100Y1Y20159APR16",
    "course_id":"ECO100Y1Y20159",
    "course_code":"ECO100Y1Y",
    "campus":"UTSG",
    "period":"APR16",
    "date":"2016-04-12",
    "start_time":68400,
    "end_time":79200,
    "duration":10800,
    "sections":[
      {
        "lecture_code":"L0101",
        "exam_section":"A - LE",
        "location":"BN 2N"
      },
      {
        "lecture_code":"L0101",
        "exam_section":"LI - WA",
        "location":"BN 2S"
      },
      {
        "lecture_code":"L0101",
        "exam_section":"WE - Z",
        "location":"BN 3"
      },
      {
        "lecture_code":"L0201",
        "exam_section":"A - GA",
        "location":"BN 3"
      },
      {
        "lecture_code":"L0201",
        "exam_section":"GE - Y",
        "location":"EX 100"
      },
      {
        "lecture_code":"L0201",
        "exam_section":"Z - Z",
        "location":"EX 200"
      },
      {
        "lecture_code":"L0301",
        "exam_section":"A - P",
        "location":"EX 200"
      },
      {
        "lecture_code":"L0301",
        "exam_section":"Q - W",
        "location":"EX 300"
      },
      {
        "lecture_code":"L0301",
        "exam_section":"X - Z",
        "location":"EX 310"
      },
      {
        "lecture_code":"L0401",
        "exam_section":"A - DO",
        "location":"GB 304"
      },
      {
        "lecture_code":"L0401",
        "exam_section":"DU - J",
        "location":"GB 404"
      },
      {
        "lecture_code":"L0401",
        "exam_section":"K - ME",
        "location":"GB 405"
      },
      {
        "lecture_code":"L0401",
        "exam_section":"MI - V",
        "location":"NR 25"
      },
      {
        "lecture_code":"L0401",
        "exam_section":"W - Z",
        "location":"ST VLAD"
      },
      {
        "lecture_code":"L2001",
        "exam_section":"",
        "location":"HA 401"
      },
      {
        "lecture_code":"L5101",
        "exam_section":"A - LE",
        "location":"BR 200"
      },
      {
        "lecture_code":"L5101",
        "exam_section":"LI - O",
        "location":"EM 119"
      },
      {
        "lecture_code":"L5101",
        "exam_section":"P - WA",
        "location":"TC 239"
      },
      {
        "lecture_code":"L5101",
        "exam_section":"WE - Z",
        "location":"WY 119"
      },
      {
        "lecture_code":"L5201",
        "exam_section":"A - CHA",
        "location":"EX 310"
      },
      {
        "lecture_code":"L5201",
        "exam_section":"CHE - KI",
        "location":"EX 320"
      },
      {
        "lecture_code":"L5201",
        "exam_section":"KO - Q",
        "location":"SF 3202"
      },
      {
        "lecture_code":"L5201",
        "exam_section":"R - X",
        "location":"UC 266"
      },
      {
        "lecture_code":"L5201",
        "exam_section":"Y - Z",
        "location":"UC 273"
      }
    ],
    "matched_sections":[
      {
        "lecture_code":"L2001",
        "exam_section":"",
        "location":"HA 401"
      }
    ]
  }
]
```
