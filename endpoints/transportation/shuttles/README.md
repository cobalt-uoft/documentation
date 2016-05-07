# Shuttles API

Monthly UTM shuttle data.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="./list.md">GET transportation/parking</a></li>
    <li><a href="./show.md">GET transportation/parking/:date</a></li>
  </ul>
</div>

## Format

```js
{
  date:String,
  routes:[{
    id:String,
    name:String,
    stops:[{
      location:String,
      building_id:String,
      times:[{
        time:Number,
        rush_hour:Boolean,
        no_overload:Boolean
      }]
    }]
  }]
}
```
