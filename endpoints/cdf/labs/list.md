# GET cdf/labs

Returns a list of CDF labs and current usage information.

## URL

```
https://cobalt.qas.im/api/1.0/cdf/labs
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.

## Example

```
https://cobalt.qas.im/api/1.0/cdf/labs
```

```json
{
  "timestamp":"2016-05-07 11:35:01 EST",
  "labs":[
    {
      "name":"BA 2200",
      "available":10,
      "busy":0,
      "total":10,
      "percent":0.0
    },
    {
      "name":"BA 2270",
      "available":6,
      "busy":0,
      "total":6,
      "percent":0.0
    },
    {
      "name":"BA 3175",
      "available":25,
      "busy":0,
      "total":25,
      "percent":0.0
    },
    {
      "name":"BA 3185",
      "available":16,
      "busy":0,
      "total":16,
      "percent":0.0
    },
    {
      "name":"BA 3195",
      "available":19,
      "busy":0,
      "total":19,
      "percent":0.0
    },
    {
      "name":"BA 3200",
      "available":9,
      "busy":0,
      "total":9,
      "percent":0.0
    },
    {
      "name":"NX",
      "available":9,
      "busy":3,
      "total":12,
      "percent":25.0
    }
  ]
}
```
