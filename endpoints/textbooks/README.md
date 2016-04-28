# Textbook API

Undergraduate textbook API with book details and which courses they are required for. This API shows textbook information for the current school session.

<div class="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/list.md">GET textbooks</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/show.md">GET textbooks/:id</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/search.md">GET textbooks/search</a></li>
    <li><a href="https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/filter.md">GET textbooks/filter</a></li>
  </ul>
</div>

## Format

```js
{  
  "id": String,
  "isbn": String,
  "title": String,
  "edition": Number,
  "author": String,
  "image": String,
  "price": Number,
  "url": String,
  "courses":[{
    "id": String,
    "code": String,
    "requirement": String,
    "meeting_sections":[{
      "code": String,
      "instructors": [String]
    }]
  }]
}
```
