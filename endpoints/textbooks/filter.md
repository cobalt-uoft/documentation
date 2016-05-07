# GET textbooks/filter

Returns a list of textbooks that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/textbooks/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For numerical filters:
* No operator indicates equal to (eg. `edition:3`)
* `>` indicates greater than (eg. `price:>30`)
* `<` indicates less than (eg. `price:<1`)
* `>=` indicates greater than or equal to (eg. `edition:>=2`)
* `<=` indicates less than or equal to (eg. `price:<=200`)
* `!` indicates not (eg. `edition:!1`)

For string filters:
* No operator indicates contains (eg. `title:"Organic Chemistry"`)
* `!` indicates not (eg. `author:!"Meyer, Stephenie"`)

Examples of filter combinations:
* `price:>500`
* `edition:5 AND price:<60`
* `author:"Queen"`

- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -edition`. The default value is `+id`.

## Filter keys

The following is a list of all filter keys that can be used in the `q` parameter.

| Key                  | Type   | Example                          |
|----------------------|--------|----------------------------------|
| `isbn`               | String | `isbn:"9780024089403"`           |
| `title`              | String | `title:!"linear programming"`    |
| `edition`            | Number | `edition:1`                      |
| `author`             | String | `author:"Kolman"`                |
| `price`              | Number | `price:<=100`                    |
| `course_id`          | String | `course_id:"CSC108H1F20169"`     |
| `course_code`        | String | `course_code:"MAT137"`           |
| `course_requirement` | String | `course_requirement:!"required"` |
| `meeting_code`       | String | `meeting_code:"L0101"`           |
| `instructor`         | String | `instructor:"D Liu"`             |

## Example

```
https://cobalt.qas.im/api/1.0/textbooks/filter?q=author:"Queen"
```

```json
[
  {
    "id":"10604397",
    "isbn":"9780791428443",
    "title":"Engaged Buddhism",
    "edition":1,
    "author":"Queen",
    "image":"http://uoftbookstore.com/cover_image.asp?Key=9780791428443&Size=L&p=1",
    "price":42.25,
    "url":"http://uoftbookstore.com/buy_book_detail.asp?pf_id=10604397",
    "courses":[{
      "id":"NEW214Y1Y20161",
      "code":"NEW214Y1Y",
      "requirement":"required",
      "meeting_sections":[{
        "code":"L0101",
        "instructors":[
          "S Henry"
        ]
      }]
    }]
  }
]
```
