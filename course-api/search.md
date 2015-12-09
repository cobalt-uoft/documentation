# GET course/search

Returns a list of courses that match a text search on the `code`, `name`, and `description` keys.

## URL

```
https://cobalt.qas.im/api/1.0/courses/search
```

## Parameters

<p>
  <div class="param grid-container">
    <div class="grid-20">
      <code>key</code>
      <div class="sub">required</div>
    </div>
    <div class="grid-80">
      Your unique API key.
    </div>
  </div>
</p>
- - -
<p>
  <div class="param grid-container">
    <div class="grid-20">
      <code>q</code>
      <div class="sub">required</div>
    </div>
    <div class="grid-80">
      The string to perform a text search with. It is also possible to do a verbatim search by surrounding the string in double quotes.
    </div>
  </div>
</p>
- - -
<p>
  <div class="param grid-container">
    <div class="grid-20">
      <code>limit</code>
      <div class="sub">optional</div>
    </div>
    <div class="grid-80">
      The number of results to return, up to a maximum of 100 per request. The default value is 10.
    </div>
  </div>
</p>
- - -
<p>
  <div class="param grid-container">
    <div class="grid-20">
      <code>skip</code>
      <div class="sub">optional</div>
    </div>
    <div class="grid-80">
      The number of results to skip. The default value is 0.
    </div>
  </div>
</p>
- - -
<p>
  <div class="param grid-container">
    <div class="grid-20">
      <code>sort</code>
      <div class="sub">optional</div>
    </div>
    <div class="grid-80">
      <p>
        The sorting procedure to be used on the returned list. A <code>+</code> before a parameter implies ascending, and a <code>-</code> implies descending. You can also stack procedures, separating them with a space.<br />(eg. <code>+id -department</code>)
      </p>
      <p>
        The default value is <code>+id</code> (sort by id, ascending).
      </p>
    </div>
  </div>
</p>

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
