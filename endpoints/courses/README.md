## Course API

Undergraduate course API with up to date calendar and timetable information. This API shows course information for the current school year.

<div class="reference">
  <h4>Reference</h4>
  <ul>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/list.md">GET courses</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/show.md">GET courses/:id</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/search.md">GET courses/search</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/courses/filter.md">GET courses/filter</a></li>
  </ul>
</div>

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
