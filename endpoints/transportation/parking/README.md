# Parking API

Parking information across all three campuses.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="./list.md">GET transportation/parking</a></li>
    <li><a href="./show.md">GET transportation/parking/:id</a></li>
    <li><a href="./search.md">GET transportation/parking/search</a></li>
    <li><a href="./filter.md">GET transportation/parking/filter</a></li>
  </ul>
</div>

## Format

```js
{
  id:String,
  title:String,
  building_id:String,
  campus:String,
  type:String,
  description:String,
  lat:Number,
  lng:Number,
  address:String
}
```
