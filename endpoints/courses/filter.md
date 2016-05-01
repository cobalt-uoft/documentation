# GET courses/filter

Returns a list of courses that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/courses/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For numerical and time filters:
* No operator indicates equal to (eg. `breadth:5`)
* `>` indicates greater than (eg. `class_size:>30`)
* `<` indicates less than (eg. `class_enrolment:>1`)
* `>=` indicates greater than or equal to (eg. `start_time:>=64800`)
* `<=` indicates less than or equal to (eg. `course_level:<=200`)

For string filters:
* No operator indicates contains (eg. `code:"CSC"`)
* `-` indicates not (eg. `department:-"architecture"`)

For time filters:
* All numerical operators work with time parameters. You can provide the time as a string (i.e. `"HH:MM"`).
* Alternatively, you can just specify the time as an integer representing the seconds since midnight.

Examples of filter combinations:
* `instructor:"D Liu" AND code:"CSC" AND level:<=200`
* `breadth:2 OR breadth:3`
* `prerequisites:"CSC207H1" AND code:"-MAT" OR code:"-CSC"`
* `start_time:>"16:00" AND duration:10800`

For filters that involve properties from `meeting_sections`, an additional key is returned called `matched_meeting_sections`, which contains only the meeting sections that match the filter.
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
https://cobalt.qas.im/api/1.0/courses/filter?q=instructor:"D Liu" AND code:"CSC" AND level:<=200
```

```json
[
  {
    "id":"CSC148H1F20159",
    "code":"CSC148H1F",
    "name":"Introduction to Computer Science",
    "description":"Abstract data types and data structures for implementing them. Linked data structures. Encapsulation and information-hiding. Object-oriented programming. Specifications. Analyzing the efficiency of programs. Recursion. This course assumes programming experience as provided by CSC108H1. Students who already have this background may consult the Computer Science Undergraduate Office for advice about skipping CSC108H1. Practical (P) sections consist of supervised work in the computing laboratory. These sections are offered when facilities are available, and attendance is required. NOTE: Students may go to their college to drop down from CSC148H1 to CSC108H1. See above for the drop down deadline.",
    "division":"Faculty of Arts and Science",
    "department":"Computer Science",
    "prerequisites":"CSC108H1/(equivalent programming experience)",
    "exclusions":"CSC150H1; you may not take this course after taking more than two CSC courses at the 200-level or higher",
    "level":100,
    "campus":"UTSG",
    "term":"2015 Fall",
    "breadths":[
      5
    ],
    "meeting_sections":[
      {
        "code":"L0101",
        "instructors":[
          "D Liu"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"RW 110"
          },
          {
            "day":"WEDNESDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"RW 110"
          },
          {
            "day":"FRIDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"RW 110"
          }
        ],
        "size":156,
        "enrolment":0
      },
      {
        "code":"L0201",
        "instructors":[
          "D Liu"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":"RW 117"
          },
          {
            "day":"WEDNESDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":"RW 117"
          },
          {
            "day":"FRIDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":"RW 117"
          }
        ],
        "size":156,
        "enrolment":0
      },
      {
        "code":"T0101",
        "instructors":[

        ],
        "times":[
          {
            "day":"THURSDAY",
            "start":9,
            "end":11,
            "duration":2,
            "location":""
          }
        ],
        "size":108,
        "enrolment":0
      },
      {
        "code":"T0201",
        "instructors":[

        ],
        "times":[
          {
            "day":"THURSDAY",
            "start":11,
            "end":13,
            "duration":2,
            "location":""
          }
        ],
        "size":108,
        "enrolment":0
      },
      {
        "code":"T5101",
        "instructors":[

        ],
        "times":[
          {
            "day":"THURSDAY",
            "start":19,
            "end":21,
            "duration":2,
            "location":""
          }
        ],
        "size":72,
        "enrolment":0
      },
      {
        "code":"T0301",
        "instructors":[

        ],
        "times":[
          {
            "day":"THURSDAY",
            "start":13,
            "end":15,
            "duration":2,
            "location":""
          }
        ],
        "size":36,
        "enrolment":0
      }
    ],
    "matched_meeting_sections":[
      {
        "code":"L0101",
        "instructors":[
          "D Liu"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"RW 110"
          },
          {
            "day":"WEDNESDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"RW 110"
          },
          {
            "day":"FRIDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"RW 110"
          }
        ],
        "size":156,
        "enrolment":0
      },
      {
        "code":"L0201",
        "instructors":[
          "D Liu"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":"RW 117"
          },
          {
            "day":"WEDNESDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":"RW 117"
          },
          {
            "day":"FRIDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":"RW 117"
          }
        ],
        "size":156,
        "enrolment":0
      }
    ]
  },
  {
    "id":"CSC209H1S20161",
    "code":"CSC209H1S",
    "name":"Software Tools and Systems Programming",
    "description":"Software techniques in a Unix-style environment, using scripting languages and a machine-oriented programming language (typically C). What goes on in the operating system when programs are executed. Core topics: creating and using software tools, pipes and filters, file processing, shell programming, processes, system calls, signals, basic network programming.",
    "division":"Faculty of Arts and Science",
    "department":"Computer Science",
    "prerequisites":"CSC207H1",
    "exclusions":"CSC372H1, CSC369H1, CSC469H1",
    "level":200,
    "campus":"UTSG",
    "term":"2016 Winter",
    "breadths":[
      5
    ],
    "meeting_sections":[
      {
        "code":"L0101",
        "instructors":[
          "M Craig"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":12,
            "end":13,
            "duration":1,
            "location":"RW 110"
          },
          {
            "day":"WEDNESDAY",
            "start":12,
            "end":13,
            "duration":1,
            "location":"RW 110"
          }
        ],
        "size":146,
        "enrolment":0
      },
      {
        "code":"L0201",
        "instructors":[
          "D Liu"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"LM 161"
          },
          {
            "day":"WEDNESDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"LM 161"
          }
        ],
        "size":140,
        "enrolment":0
      },
      {
        "code":"L5101",
        "instructors":[
          "M Craig"
        ],
        "times":[
          {
            "day":"WEDNESDAY",
            "start":18,
            "end":20,
            "duration":2,
            "location":"LM 162"
          }
        ],
        "size":146,
        "enrolment":0
      },
      {
        "code":"T0101",
        "instructors":[

        ],
        "times":[
          {
            "day":"FRIDAY",
            "start":13,
            "end":14,
            "duration":1,
            "location":""
          }
        ],
        "size":96,
        "enrolment":0
      },
      {
        "code":"T0201",
        "instructors":[

        ],
        "times":[
          {
            "day":"FRIDAY",
            "start":14,
            "end":15,
            "duration":1,
            "location":""
          }
        ],
        "size":96,
        "enrolment":0
      },
      {
        "code":"T0301",
        "instructors":[

        ],
        "times":[
          {
            "day":"FRIDAY",
            "start":15,
            "end":16,
            "duration":1,
            "location":""
          }
        ],
        "size":96,
        "enrolment":0
      },
      {
        "code":"T5101",
        "instructors":[

        ],
        "times":[
          {
            "day":"WEDNESDAY",
            "start":20,
            "end":21,
            "duration":1,
            "location":""
          }
        ],
        "size":96,
        "enrolment":0
      }
    ],
    "matched_meeting_sections":[
      {
        "code":"L0201",
        "instructors":[
          "D Liu"
        ],
        "times":[
          {
            "day":"MONDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"LM 161"
          },
          {
            "day":"WEDNESDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"LM 161"
          }
        ],
        "size":140,
        "enrolment":0
      }
    ]
  }
]
```
