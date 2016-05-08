# GET cdf/printers

Returns a list of CDF printers and current usage information.

## URL

```
https://cobalt.qas.im/api/1.0/cdf/printers
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.

## Example

```
https://cobalt.qas.im/api/1.0/cdf/printers
```

```json
{
  "timestamp":"2016-05-07 11:50:01 EST",
  "printers":[
    {
      "name":"p2210a",
      "description":"Kyocera Network Printer in BA2210",
      "length":1,
      "jobs":[
        {
          "rank":"error",
          "job":"925",
          "owner":"",
          "class":"",
          "files":"",
          "size":"0",
          "time":"",
          "error":"ERROR: too many errors"
        }
      ]
    },
    {
      "name":"p2210b",
      "description":"Kyocera Network Printer in BA2210",
      "length":1,
      "jobs":[
        {
          "rank":"error",
          "job":"278",
          "owner":"",
          "class":"",
          "files":"",
          "size":"0",
          "time":"",
          "error":"ERROR: too many errors"
        }
      ]
    },
    {
      "name":"p3185a",
      "description":"Printer p3185a redirected to p3175a in BA3175 (dest p3175a@printsrv)",
      "length":2,
      "jobs":[
        {
          "rank":"done",
          "job":"431",
          "owner":"",
          "class":"",
          "files":"",
          "size":"114825",
          "time":"10:03:11",
          "error":""
        },
        {
          "rank":"error",
          "job":"431",
          "owner":"",
          "class":"",
          "files":"",
          "size":"0",
          "time":"",
          "error":"ERROR: too many errors"
        }
      ]
    },
    {
      "name":"p3175a",
      "description":"Kyocera Network Printer in BA3175",
      "length":1,
      "jobs":[
        {
          "rank":"error",
          "job":"431",
          "owner":"",
          "class":"",
          "files":"",
          "size":"0",
          "time":"",
          "error":"ERROR: too many errors"
        }
      ]
    }
  ]
}
```
