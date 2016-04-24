## Textbook API

Undergraduate textbook API with book details and which courses they are required for. This API shows textbook information for the current school session.

#### Reference

* [GET textbooks](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/list.md)
* [GET textbooks/:id](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/show.md)
* [GET textbooks/search](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/search.md)
* [GET textbooks/filter](https://github.com/cobalt-uoft/documentation/blob/master/endpoints/textbooks/filter.md)

#### Format

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
