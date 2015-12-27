# GET courses/show/:id

Returns a specific course identified by the `id` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/courses/:id
```

## Parameters

`key` _(required)_
Your unique API key.
- - -
`:id` _(required)_
The unique identifier for the course.

## Example

```
https://cobalt.qas.im/api/1.0/courses/show/CSC148H1F20159
```

```json
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
  "meeting_sections":[
    {
      "code":"L0101",
      "size":156,
      "enrolment":0,
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
      "instructors":[
        "D Liu"
      ]
    },
    {
      "code":"L0201",
      "size":156,
      "enrolment":0,
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
      "instructors":[
        "D Liu"
      ]
    },
    {
      "code":"T0101",
      "size":108,
      "enrolment":0,
      "times":[
        {
          "day":"THURSDAY",
          "start":9,
          "end":11,
          "duration":2,
          "location":""
        }
      ],
      "instructors":[

      ]
    },
    {
      "code":"T0201",
      "size":108,
      "enrolment":0,
      "times":[
        {
          "day":"THURSDAY",
          "start":11,
          "end":13,
          "duration":2,
          "location":""
        }
      ],
      "instructors":[

      ]
    },
    {
      "code":"T5101",
      "size":72,
      "enrolment":0,
      "times":[
        {
          "day":"THURSDAY",
          "start":19,
          "end":21,
          "duration":2,
          "location":""
        }
      ],
      "instructors":[

      ]
    },
    {
      "code":"T0301",
      "size":36,
      "enrolment":0,
      "times":[
        {
          "day":"THURSDAY",
          "start":13,
          "end":15,
          "duration":2,
          "location":""
        }
      ],
      "instructors":[

      ]
    }
  ],
  "breadths":[
    5
  ]
}
```
