# Exams API

Undergraduate exams API across all three campuses. This API shows exam information for the current school period.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="./list.md">GET exams</a></li>
    <li><a href="./show.md">GET exams/:id</a></li>
    <li><a href="./filter.md">GET exams/filter</a></li>
  </ul>
</div>

## Format

```js
{
  "id":String,
  "course_id":String,
  "course_code":String,
  "campus":String,
  "period":String,
  "date":String,
  "start_time":Number,
  "end_time":Number,
  "duration":Number,
  "sections":[{
    "lecture_code":String,
    "exam_section":String,
    "location":String
  }]
}
```
