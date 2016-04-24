# Athletics API

Monthly campus athletics API with daily timing schedules. Data is currently only available for UTSC and UTM.

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
