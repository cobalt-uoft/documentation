# Athletics API

Monthly campus athletics API with daily timings. As of right now, data is only available for UTSC and UTM.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="./list.md">GET athletics</a></li>
    <li><a href="./show.md">GET athletics/:id</a></li>
    <li><a href="./search.md">GET athletics/search</a></li>
    <li><a href="./filter.md">GET athletics/filter</a></li>
  </ul>
</div>

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
