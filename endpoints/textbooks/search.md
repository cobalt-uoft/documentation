# GET textbooks/search

Returns a list of textbooks that match a text search on the `title` key.

## URL

```
https://cobalt.qas.im/api/1.0/textbooks/search
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
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -edition`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/textbooks/search?q="atmospheric science"
```

```json
[
  {
    "id":"12447565",
    "isbn":"9780127329512",
    "title":"Atmospheric Science",
    "edition":2,
    "author":"Wallace",
    "image":"http://uoftbookstore.com/cover_image.asp?Key=9780127329512&Size=L&p=1",
    "price":99.3,
    "url":"http://uoftbookstore.com/buy_book_detail.asp?pf_id=12447565",
    "courses":[
      {
        "id":"PHY392H1S20161",
        "code":"PHY392H1S",
        "requirement":"required",
        "meeting_sections":[
          {
            "code":"L0101",
            "instructors":[
              "J Dylan"
            ]
          },
          {
            "code":"L2001",
            "instructors":[
              "J Dylan"
            ]
          }
        ]
      }
    ]
  }
]
```
