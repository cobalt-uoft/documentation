# Authenticating

In order to provide API request analytics and prevent abuse, Cobalt requires that you authenticate all of your API requests with a valid key.

You can access your unique API key from your [dashboard](https://cobalt.qas.im/dashboard).

## Usage

Each API request you make will require the `key` parameter. Replace `API_KEY` with your own API key. For example, in order to find information about Bahen (`080`), you would call the building API as follows:

```
https://cobalt.qas.im/api/1.0/buildings/080?key=API_KEY
```

```json
{
  "id":"080",
  "code":"BA",
  "name":"Bahen Centre for Information Technology",
  "short_name":"Bahen Centre",
  "campus":"UTSG",
  "lat":43.65967,
  "lng":-79.39737,
  "address":{
    "street":"40  St. George Street",
    "city":"Toronto",
    "province":"ON",
    "country":"Canada",
    "postal":"M5S 2E4"
  }
}
```
