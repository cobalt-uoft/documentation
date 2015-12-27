# GET courses/list

Returns a list of courses.

## URL

```
https://cobalt.qas.im/api/1.0/courses
```

## Parameters

`key` _(required)_
Your unique API key.
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
https://cobalt.qas.im/api/1.0/courses?limit=2
```

```json
[
  {
    "id":"IRE346H1F20159",
    "code":"IRE346H1F",
    "name":"Human Resource Planning",
    "description":"An understanding is developed of how essential elements of the human resource planning process support organizational goals and strategies. Topics such as environmental influences, job analysis, forecasting human resource needs and ascertaining supply, succession planning, downsizing and restructuring, mergers and acquisitions, outsourcing, and strategic international issues are examined.",
    "division":"Faculty of Arts and Science",
    "department":"Centre for Industrial Relations and Human Resources",
    "prerequisites":"IRE240H1/WDW240H1/IRE244H1/WDW244H1/IRE260H1/WDW260H1/",
    "exclusions":"WDW346H1",
    "level":300,
    "campus":"UTSG",
    "term":"2015 Fall",
    "meeting_sections":[
      {
        "code":"L5101",
        "size":65,
        "enrolment":0,
        "times":[
          {
            "day":"TUESDAY",
            "start":18,
            "end":21,
            "duration":3,
            "location":"WW 126"
          }
        ],
        "instructors":[
          "E Mock"
        ]
      }
    ],
    "breadths":[
      3
    ]
  },
  {
    "id":"ENG370H1S20161",
    "code":"ENG370H1S",
    "name":"Postcolonial and Transnational Discourses",
    "description":"This course focuses on recent theorizations of postcoloniality and transnationality through readings of fictional and non-fictional texts, along with analyses of contemporary films and media representations.",
    "division":"Faculty of Arts and Science",
    "department":"English",
    "prerequisites":"2.0 ENG FCE and any 4.0 FCE",
    "exclusions":"",
    "level":300,
    "campus":"UTSG",
    "term":"2016 Winter",
    "meeting_sections":[
      {
        "code":"L0101",
        "size":45,
        "enrolment":0,
        "times":[
          {
            "day":"TUESDAY",
            "start":11,
            "end":12,
            "duration":1,
            "location":"BF 323"
          },
          {
            "day":"THURSDAY",
            "start":11,
            "end":13,
            "duration":2,
            "location":"BF 323"
          }
        ],
        "instructors":[
          "C Suzack"
        ]
      }
    ],
    "breadths":[
      1
    ]
  }
]
```
