# Self hosting

Using the hosted version of Cobalt works well but may not be ideal as there is a network latency along with occasional rate limiting during peak hours. To avoid these issues, you can self host Cobalt on your own server.

## Requirements

Ensure that the following software has been installed on your server:

* [Node.js](https://nodejs.org/) ^5.6 ([nvm](https://github.com/creationix/nvm) recommended)
* [MongoDB](https://www.mongodb.org/) ^3.0.2

## Installation

Verify that MongoDB is installed and running. Refer to the [MongoDB installation guide](https://docs.mongodb.org/manual/installation/) for more information.

Next, install Cobalt.
```bash
$ npm install -g cobalt-uoft
```

You'll need to set the following environment variable (refer to [this guide](http://www.schrodinger.com/kb/1842) if you're unsure how to do so).

* `COBALT_MONGO_URI` : the MongoDB connection URI used to connect to your MongoDB database server (ex. `mongodb://localhost/cobalt`). This database will have Cobalt's datasets synced to it automatically when you run Cobalt.

## Usage 

To start your local instance:

```bash
$ cobalt
```

That's it! Cobalt should now be running on `localhost`. You can also specifiy a port to listen on via the `-p` command line argument (ex. `$ cobalt -p 4242`).

Use Cobalt as you normally would, under the new URL that is outputted during startup. No API key is required to authenticate requests on your local server.

#### Example
```
GET http://localhost:4242/1.0/buildings/008
```

#### Using Cobalt in an existing Express project

You can also create an instance of Cobalt in an existing Node.js project that uses [Express](http://expressjs.com/).

```js
var express = require('express');
var cobalt = require('cobalt-uoft');

var app = express();

var port = process.env.PORT || 4242;

// Serve the Cobalt APIs on the /cobalt URL prefix
app.use('/cobalt', cobalt.Server);

// Hello world
app.get('/', function(req, res) {
  res.status(200).send('Hello, world!');
});

app.listen(port, function() {
  console.log('Server running on port ' + port + '.');
});
```

###### Example
```
GET http://localhost:4242/cobalt/1.0/buildings/008
```

## Updating

```bash
npm update -g cobalt-uoft
```
