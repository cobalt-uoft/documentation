# GET buildings/filter

Returns a list of buildings that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/buildings/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For numerical filters:
* No operator indicates equal to
* `>` indicates greater than
* `<` indicates less than
* `>=` indicates greater than or equal to
* `<=` indicates less than or equal to
* `!` indicates not

For string filters:
* No operator indicates contains (eg. `name:"University College"`)
* `!` indicates not (eg. `campus:!"UTSC"`)

Examples of filter combinations:
* `campus:"UTSG" AND street:"King's College Circle"`
* `name:"Medical"`
* `short_name:"BA"`

- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `-campus +id`. The default value is `+id`.

## Filter keys

The following is a list of all filter keys that can be used in the `q` parameter.

| Key            | Type   | Example               |
|----------------|--------|-----------------------|
| `code`         | String | `code:"UC"`           |
| `name`         | String | `name:!"New College"` |
| `short_name`   | String | `short_name:"Bahen"`  |
| `campus`       | String | `campus:!"UTSG"`      |
| `street`       | String | `street:"Bloor"`      |
| `city`         | String | `city:"Mississauga"`  |
| `country`      | String | `country:"Canada"`    |
| `postal`       | String | `postal:"M5T"`        |
| `lat`          | Number | `lat:>-43.658`        |
| `lng`          | Number | `lng:<79.394`         |

## Example

```
https://cobalt.qas.im/api/1.0/buildings/filter?q=campus:"UTSG" AND street:"McCaul St"
```

```json
[
  {
    "id":"083",
    "code":"RM",
    "name":"McCaul Street-254/256",
    "short_name":"McCaul-254/6",
    "campus":"UTSG",
    "lat":43.65857109807999,
    "lng":-79.3936037353563,
    "address":{
      "street":"254-256 McCaul Street",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5T 1W5"
    },
    "polygon":[
      [43.65861, -79.39386],
      [43.65858, -79.39385],
      [43.65857, -79.39388],
               ...
      [43.6586, -79.39342],
      [43.6586, -79.3934],
      [43.65869, -79.39344]
    ]
  },
  {
    "id":"155",
    "code":"EX",
    "name":"Exam Centre",
    "short_name":"Exam Centre",
    "campus":"UTSG",
    "lat":43.658476013981854,
    "lng":-79.3928580812502,
    "address":{
      "street":"255 McCaul Street",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5T 1W7"
    },
    "polygon":[
      [43.65872, -79.39316],
      [43.65816, -79.39294],
      [43.65824, -79.39253],
               ...
      [43.6588, -79.39271],
      [43.65879, -79.39275],
      [43.6588, -79.39275]
    ]
  },
  {
    "id":"156",
    "code":"OA",
    "name":"Old Admin Bldg (Board of Ed)",
    "short_name":"Old Admin",
    "campus":"UTSG",
    "lat":43.65880832236425,
    "lng":-79.392504700212,
    "address":{
      "street":"263 McCaul Street",
      "city":"Toronto",
      "province":"ON",
      "country":"Canada",
      "postal":"M5T 1W7"
    },
    "polygon":[
      [43.6589, -79.39267],
      [43.65895, -79.39244],
      [43.65885, -79.3924],
               ...
      [43.65881, -79.39239],
      [43.65871, -79.39234],
      [43.65866, -79.39257]
    ]
  }
]
```
