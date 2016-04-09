# GET textbooks

Returns a list of textbooks.

## URL

```
https://cobalt.qas.im/api/1.0/textbooks
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -edition`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/textbooks?limit=2
```

```json
[
  {
    "id":"10551332",
    "isbn":"9780024089403",
    "title":"Jewish People, Jewish Thought",
    "edition":0,
    "author":"Seltzer",
    "image":"http://uoftbookstore.com/cover_image.asp?Key=9780024089403&Size=L&p=1",
    "price":189.4,
    "url":"http://uoftbookstore.com/buy_book_detail.asp?pf_id=10551332",
    "courses":[
      {
        "id":"RLG202Y1Y20161",
        "code":"RLG202Y1Y",
        "requirement":"required",
        "meeting_sections":[
          {
            "code":"L0101",
            "instructors":[
              "G Kenneth"
            ]
          }
        ]
      }
    ]
  },
  {
    "id":"10551592",
    "isbn":"9780060429959",
    "title":"Organic Chemistry",
    "edition":4,
    "author":"Huheey (Do Not Use)",
    "image":"http://uoftbookstore.com/cover_image.asp?Key=9780060429959&Size=L&p=1",
    "price":164.4,
    "url":"http://uoftbookstore.com/buy_book_detail.asp?pf_id=10551592",
    "courses":[
      {
        "id":"CHM238Y1Y20161",
        "code":"CHM238Y1Y",
        "requirement":"referenced",
        "meeting_sections":[
          {
            "code":"L0101",
            "instructors":[
              "S Datong"
            ]
          }
        ]
      }
    ]
  }
]
```
