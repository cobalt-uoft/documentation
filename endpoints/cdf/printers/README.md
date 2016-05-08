# CDF Prints API

API for real-time CDF printer usage.

<div id="reference">
  <h2>Reference</h2>
  <ul>
    <li><a href="./list.md">GET cdf/printers</a></li>
  </ul>
</div>

## Format

```js
{
  "timestamp": String,
  "printers": [{
    "name": String,
    "description": String,
    "length": Number
    "jobs": [{
      "rank": String,
      "job": String,
      "size": String,
      "time": String,
      "error": String
    }]
  }]
}
```
