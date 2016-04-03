# GET food

Returns a list of food vendors.

## URL

```
https://cobalt.qas.im/api/1.0/food
```

## Parameters

`key` _(required)_
Your unique API key. If you do not provide this, you must set the `Authorization` header to your API key instead.
- - -
`limit` _(optional)_
The number of results to return, up to a maximum of 100 per request. The default value is 10.
- - -
`skip` _(optional)_
The number of results to skip. The default value is 0.
- - -
`sort` _(optional)_
The sorting procedure to be used on the returned list. A `+` followed by a parameter implies ascending, and a `-` implies descending. You can also stack procedures, separating them with a space: `+id -department`. The default value is `+id`.

## Example

```
https://cobalt.qas.im/api/1.0/food?limit=2
```

```js
[
  {
    id: "1086",
    building_id: "504",
    name: "Burwash Dining Hall",
    short_name: "burwash_dining_hall",
    description: "The main dining hall at Vic, Burwash has an all-you-care-to-eat 5 week menu that is always rotating. Burwash and Ned’s cafe do not accept UeaT meal plans or flex dollars. Mon-Fri: 7:30-3:00 and 4:00-7:30 Sat-Sun: 10:00-3:00 and 4:00-7:00",
    url: "http://www.vicu.utoronto.ca/hospitality/Food_Services/Burwash_Dining_Hall.htm",
    image: "",
    campus: "UTSG",
    lat: 43.66744,
    lng: -79.39178,
    address: "89 Charles Street West",
    hours: {
      saturday: {
        closed: false,
        open: 10,
        close: 19
      },
      friday: {
        closed: false,
        open: 7.5,
        close: 19.5
      },
      thursday: {
        closed: false,
        open: 7.5,
        close: 19.5
      },
      wednesday: {
        closed: false,
        open: 7.5,
        close: 19.5
      },
      tuesday: {
        closed: false,
        open: 7.5,
        close: 19.5
      },
      monday: {
        closed: false,
        open: 7.5,
        close: 19.5
      },
      sunday: {
        closed: false,
        open: 10,
        close: 19
      }
    },
    tags: [
      "Burwash",
      "Dining Hall",
      "Meals",
      "Chef Nathan Barratt"
    ]
  },
  {
    id: "1087",
    building_id: "056",
    name: "Harvest Noon Cafe",
    short_name: "harvest_noon_cafe-1027",
    description: "Located on the 2nd floor of the Graduate Students’ Union at 16 Bancroft Ave., the cafe offers vegetarian & vegan options in a relaxed and inclusive space. Open for special programming, workshops, and select meals. Check website: harvestnoon.com",
    url: "http://harvestnoon.com/",
    image: "",
    campus: "UTSG",
    lat: 43.66072,
    lng: -79.40022,
    address: "16 Bancroft Ave",
    hours: {
      saturday: {
        closed: true,
        open: 0,
        close: 0
      },
      friday: {
        closed: false,
        open: 10,
        close: 14
      },
      thursday: {
        closed: false,
        open: 10,
        close: 14
      },
      wednesday: {
        closed: false,
        open: 10,
        close: 14
      },
      tuesday: {
        closed: false,
        open: 10,
        close: 14
      },
      monday: {
        closed: false,
        open: 10,
        close: 14
      },
      sunday: {
        closed: true,
        open: 0,
        close: 0
      }
    },
    tags: [
      "Vegan",
      "Vegetarian",
      "Coffee",
      "Tea",
      "Lunch"
    ]
  }
]
```
