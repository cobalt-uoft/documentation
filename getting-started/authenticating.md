# Authenticating

In order to provide API request analytics and prevent abuse, Cobalt requires that you authenticate all of your API requests with a valid key.

You can access your unique API key from your [dashboard](https://cobalt.qas.im/dashboard).

## Usage

Each API request you make requires that you either set the `Authorization` header to your API key, or alternatively specify the `key` URL parameter with your API key.

For example, in order to find information about Bahen (`080`), you can call the building API with the following header and URL:

```
Authorization: YOUR_API_KEY
https://cobalt.qas.im/api/1.0/buildings/080
```

Or, to avoid setting any headers, you can also specify the `key` URL parameter instead. Following our example, your request would look like the following:

```
https://cobalt.qas.im/api/1.0/buildings/080?key=YOUR_API_KEY
```

Here is the server's response, using either of the methods described:

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
