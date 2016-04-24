# Course API

Undergraduate course API with up to date calendar and timetable information. This API shows course information for the current school year.

## Format

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
