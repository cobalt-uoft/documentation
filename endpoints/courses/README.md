## Course API

Undergraduate course API with up to date calendar and timetable information. This API shows course information for the current school year.

#### Format

```js
{
  "id":String,
  "code":String,
  "name":String,
  "description":String,
  "division":String,
  "department":String,
  "prerequisites":String,
  "exclusions":String,
  "level":Number,
  "campus":String,
  "term":String,
  "breadths":[Number],
  "meeting_sections":[{
    "code":String,
    "instructors":[String],
    "times":[{
      "day":String,
      "start":Number,
      "end":Number,
      "duration":Number,
      "location":String
    }],
    "size":Number,
    "enrolment":Number
  }]
}
```

#### Reference

* [Introduction](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/introduction.md)
* [GET courses](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/list.md)
* [GET courses/:id](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/show.md)
* [GET courses/search](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/search.md)
* [GET courses/filter](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/filter.md)
