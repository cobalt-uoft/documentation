# Self hosting

Using the hosted version of Cobalt works well but may not be ideal as there is a network latency along with occasional rate limiting during peak hours. To avoid these issues, you can self host Cobalt on your own server.

## Requirements

Ensure that the following software has been installed on your server:

* [Node.js](https://nodejs.org/) ^0.12.7 ([nvm](https://github.com/creationix/nvm) recommended)
* [MongoDB](https://www.mongodb.org/) ^3.0.2

## Installation

Download the latest release of Cobalt from the [GitHub repository](https://github.com/cobalt-uoft/cobalt/releases).

Unzip the download where you would like to keep your Cobalt source code. Open a command line and `cd` to that directory.

Install the rest of Cobalt's dependencies via `npm`:

```
npm install
```

Before you can start Cobalt, you'll need to set the following environment variables (refer to [this guide](http://www.schrodinger.com/kb/1842) if you're unsure how to set new environment variables).

* `COBALT_PORT` : The port at which you would like to deploy Cobalt (ex. `4242`)
* `COBALT_MONGO_URI` : the MongoDB connection URI used to connect to your MongoDB database server (ex. `mongodb://localhost/cobalt`)

Ensure that you are connected to the internet when running Cobalt for the first time so that it can retrieve the latest datasets. To start your local instance:

```
npm start
```

That's it! Cobalt should now be running on `localhost` at whichever port you specified in the `COBALT_PORT` environment variable.

## Usage

You can now use Cobalt as you normally would, under the new URL that is outputted during startup. No API key is required to authenticate requests on your local server.

## Updating

Updating Cobalt is as simple as downloading any new release and repeating the steps in the Installation section of this page.
