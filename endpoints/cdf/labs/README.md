# CDF Labs API

API for real-time CDF computer usage.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="./list.md">GET cdf/labs</a></li>
  </ul>
</div>

## Format

```js
{
  "timestamp":String,
  "labs":[{
    "name":String,
    "available":Number,
    "busy":Number,
    "total":Number,
    "percent":Number,
  }]
}
```
