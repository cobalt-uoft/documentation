# GET exams/:d

Returns a specific exam identified by the `:id` parameter.

## URL

```
https:/cobalt.qas.im/api/1.0/exams/:id
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`:d` _(required)_
The unique identifier for the exam.

## Example

```
https:/cobalt.qas.im/api/1.0/exams/CSC148H1F20159DEC15
```

```json
{
  "id":"CSC148H1F20159DEC15",
  "course_id":"CSC148H1F20159",
  "course_code":"CSC148H1F",
  "campus":"UTSG",
  "period":"DEC15",
  "date":"2015-12-15",
  "start_time":32400,
  "end_time":43200,
  "duration":10800,
  "sections":[
    {
      "lecture_code":"",
      "exam_section":"A - K",
      "location":"BR 200"
    },
    {
      "lecture_code":"",
      "exam_section":"L - Q",
      "location":"EM 119"
    },
    {
      "lecture_code":"",
      "exam_section":"R - Y",
      "location":"TC 239"
    },
    {
      "lecture_code":"",
      "exam_section":"Z - Z",
      "location":"WY 119"
    }
  ]
}
```
