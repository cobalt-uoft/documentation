# GET exams

Returns a list of exams.

## URL

```
https://cobalt.qas.im/api/1.0/exams
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -course_id`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/exams?limit=2
```

```json
[
  {
    "id":"ABS201Y1Y20149DEC15",
    "course_id":"ABS201Y1Y20149",
    "course_code":"ABS201Y1Y",
    "campus":"UTSG",
    "period":"DEC15",
    "date":"2015-12-15",
    "start_time":50400,
    "end_time":61200,
    "duration":10800,
    "sections":[
      {
        "lecture_code":"",
        "exam_section":"A - K",
        "location":"MP 202"
      },
      {
        "lecture_code":"",
        "exam_section":"L - Z",
        "location":"MP 203"
      }
    ]
  },
  {
    "id":"ABS201Y1Y20159APR16",
    "course_id":"ABS201Y1Y20159",
    "course_code":"ABS201Y1Y",
    "campus":"UTSG",
    "period":"APR16",
    "date":"2016-04-15",
    "start_time":50400,
    "end_time":61200,
    "duration":10800,
    "sections":[
      {
        "lecture_code":"",
        "exam_section":"A - L",
        "location":"SS 2102"
      },
      {
        "lecture_code":"",
        "exam_section":"M - Z",
        "location":"SS 2135"
      }
    ]
  }
]
```
