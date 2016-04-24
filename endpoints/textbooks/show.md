# GET textbooks/:id

Returns a specific textbook identified by the `:id` parameter.

## URL

```
https://cobalt.qas.im/api/1.0/textbooks/:id
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:id` _(required)_
The unique identifier for the textbook.

## Example

```
https://cobalt.qas.im/api/1.0/textbooks/10557372
```

```json
{
  "id":"10557372",
  "isbn":"9780130652652",
  "title":"Advanced Calculus",
  "edition":1,
  "author":"Folland",
  "image":"http://uoftbookstore.com/cover_image.asp?Key=9780130652652&Size=L&p=1",
  "price":125.25,
  "url":"http://uoftbookstore.com/buy_book_detail.asp?pf_id=10557372",
  "courses":[
    {
      "id":"MAT237Y1Y20161",
      "code":"MAT237Y1Y",
      "requirement":"required",
      "meeting_sections":[
        {
          "code":"L0101",
          "instructors":[
            "L Daniel Tuan-Dan"
          ]
        },
        {
          "code":"L0201",
          "instructors":[
            "M Elio"
          ]
        },
        {
          "code":"L5101",
          "instructors":[
            "H Tyler"
          ]
        }
      ]
    }
  ]
}
```
