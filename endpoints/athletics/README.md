## Athletics API

Monthly campus athletics API with daily timings. As of right now, data is only available for UTSC and UTM.

#### Reference

* [GET athletics](./list.md)
* [GET athletics/:id](./show.md)
* [GET athletics/search](./search.md)
* [GET athletics/filter](./filter.md)

#### Format

```js
{
  "id":String,
  "date":String,
  "campus":String,
  "events":[{
    "title":String,
    "location":String,
    "building_id":String,
    "start_time":String,
    "end_time":String
  }]
}
```
