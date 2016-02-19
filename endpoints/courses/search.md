# GET course/search

Returns a list of courses that match a text search on the `code`, `name`, and `description` keys.

## URL

```
https://cobalt.qas.im/api/1.0/courses/search
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The string to perform a text search with. It is also possible to do a verbatim search by surrounding the string in double quotes.
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
https://cobalt.qas.im/api/1.0/courses/search?q="natural language computing"
```

```json
[
  {
    "id":"CSC401H1S20161",
    "code":"CSC401H1S",
    "name":"Natural Language Computing",
    "description":"Introduction to techniques involving natural language and speech in applications such as information retrieval, extraction, and filtering; intelligent Web searching; spelling and grammar checking; speech recognition and synthesis; and multi-lingual systems including machine translation. N-grams, POS-tagging, semantic distance metrics, indexing, on-line lexicons and thesauri, markup languages, collections of on-line documents, corpus analysis. PERL and other software.",
    "division":"Faculty of Arts and Science",
    "department":"Computer Science",
    "prerequisites":"CSC207H1/CSC209H1; STA247H1/STA255H1/STA257H1",
    "exclusions":"",
    "level":400,
    "campus":"UTSG",
    "term":"2016 Winter",
    "meeting_sections":[
      {
        "code":"L0101",
        "size":200,
        "enrolment":0,
        "times":[
          {
            "day":"WEDNESDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"OI G162"
          },
          {
            "day":"MONDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"OI G162"
          },
          {
            "day":"FRIDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"OI G162"
          }
        ],
        "instructors":[
          "F Rudzicz"
        ]
      },
      {
        "code":"L2001",
        "size":40,
        "enrolment":0,
        "times":[
          {
            "day":"MONDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"OI G162"
          },
          {
            "day":"WEDNESDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"OI G162"
          },
          {
            "day":"FRIDAY",
            "start":10,
            "end":11,
            "duration":1,
            "location":"OI G162"
          }
        ],
        "instructors":[
          "F Rudzicz"
        ]
      }
    ],
    "breadths":[
      5
    ]
  }
]
```
