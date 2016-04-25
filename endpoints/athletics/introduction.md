# Athletics API

Monthly campus athletics API with daily timings. As of right now, data is only available for UTSC and UTM.

## Format

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
