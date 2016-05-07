# GET transportation/parking/filter

Returns a list of parking spots that match specified filters.

## URL

```
https://cobalt.qas.im/api/1.0/transportation/parking/filter
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`q` _(required)_
The filters to be applied, specified in the filter query format. Each filter within the query can be joined with either an `AND` or an `OR`.

For numerical filters:
* No operator indicates equal to (eg. `lat:46`)
* `>` indicates greater than (eg. `lng:>30`)
* `<` indicates less than (eg. `lat:<60`)
* `>=` indicates greater than or equal to (eg. `lng:>=18`)
* `<=` indicates less than or equal to (eg. `lat:<=-70`)
* `!` indicates not (eg. `lng:!40`)

For string filters:
* No operator indicates contains (eg. `title:"Innis"`)
* `!` indicates not (eg. `campus:!"UTSC"`)

Examples of filter combinations:
* `type:"car" AND campus:"UTM"`
* `title:"Bahen" OR type:!"bicycle"`

- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -edition`. The default value is `+id`.

## Filter keys

The following is a list of all filter keys that can be used in the `q` parameter.

| Key                  | Type   | Example                          |
|----------------------|--------|----------------------------------|
| `id`                 | String | `id:"0298"`                      |
| `title`              | String | `title:!"robarts"`               |
| `building_id`        | String | `building_id:"80"`               |
| `campus`             | String | `campus:!"UTM"`                  |
| `type`               | String | `type:"car"`                     |
| `description`        | String | `description:"free"`             |
| `lat`                | Number | `lat:>43`                        |
| `lng`                | Number | `lng:<=-79"`                     |
| `address`            | String | `address:"st. george"`           |

## Example

```
https://cobalt.qas.im/api/1.0/transportation/parking/filter?limit=3&q=type:"car" AND campus:"UTM"
```

```json
[
  {
    "id":"1242",
    "title":"Barrier Free (Accessible) Parking - AH",
    "building_id":"330",
    "campus":"UTM",
    "type":"car",
    "description":"Number of barrier free (accessible) spaces:One (1)",
    "lat":43.54464,
    "lng":-79.66056,
    "address":"Alumni House"
  },
  {
    "id":"1296",
    "title":"Barrier Free (Accessible) Parking - KN",
    "building_id":"314",
    "campus":"UTM",
    "type":"car",
    "description":"Number of barrier free (accessible) parking spaces:Five (5)",
    "lat":43.54814,
    "lng":-79.66383,
    "address":"Kaneff"
  },
  {
    "id":"1301",
    "title":"Barrier Free (Accessible) Parking - CCT",
    "building_id":"329",
    "campus":"UTM",
    "type":"car",
    "description":"Number of barrier free (accessible) parking spaces:Six (6)\nTwo spaces available on each alternating level, P1, P3 and P5",
    "lat":43.55008,
    "lng":-79.66302,
    "address":"CCT Underground Parking Garage"
  }
]
```
