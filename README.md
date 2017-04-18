# Firebase Admin Node.js SDK

## Install

```
npm install firebase-admin-proxy --save
```

## Extends Options
```js
const caw = require("caw");
const https = require("https");

// Your Proxy
const firebaseAgent = caw("http://127.0.0.1:8118", {
  protocol: "https",
});

admin.initializeApp({
  credential: admin.credential.cert(serviceAccount),
  databaseURL: "https://YOURAPP.firebaseio.com",
  agent: firebaseAgent, // proxy agent
  logging_enabled: true, // open logging info
});
```
If `logging_enabled` is open, your console will print out a similar log:
```
p:0: Browser went online.
p:0: Listen called for /users default
p:0: Making a connection attempt
p:0: Auth token refreshed
getToken() completed. Creating connection.
c:0:0: Connection created
c:0:0:0 Websocket connecting to wss://YOURAPP.firebaseio.com/.ws?v=5
c:0:0:0 Websocket connected.
c:0:0: Reset packet received.  New host: XXXXX.firebaseio.com
c:0:0: Shutting down all connections
c:0:0:0 WebSocket is being closed
c:0:0:0 Websocket connection was disconnected.
c:0:0:1 Websocket connecting to wss://XXXXX.firebaseio.com/.ws?v=5&ns=YOURAPP
c:0:0:1 Websocket connected.
c:0:0: Realtime connection established.
p:0: connection ready
```
Find `YOURAPP.firebaseio.com` and `XXXXX.firebaseio.com` real ID and add them to the hosts file.

## Table of Contents

 * [Overview](#overview)
 * [Installation](#installation)
 * [Documentation](#documentation)
 * [Release Notes](#release-notes)
 * [Acknowledgments](#acknowledgments)
 * [License](#license)


## Overview

[Firebase](https://firebase.google.com) provides the tools and infrastructure
you need to develop your app, grow your user base, and earn money. The Firebase
Admin Node.js SDK provides admin (second-party) access to several Firebase
services.

For more information, visit the
[Firebase Admin SDK setup guide](https://firebase.google.com/docs/admin/setup/).


## Installation

The Firebase Admin Node.js SDK is available on npm as `firebase-admin`:

```bash
$ npm install --save firebase-admin
```

To use the module in your application, `require` it from any JavaScript file:

```js
var admin = require("firebase-admin");
```

If you are using ES2015, you can `import` the module instead:

```js
import * as admin from "firebase-admin";
```


## Documentation

* [Setup Guide](https://firebase.google.com/docs/admin/setup/)
* [Database Guide](https://firebase.google.com/docs/database/admin/start/)
* [Authentication Guide](https://firebase.google.com/docs/auth/admin/)
* [Cloud Messaging Guide](https://firebase.google.com/docs/cloud-messaging/admin/)
* [API Reference](https://firebase.google.com/docs/reference/admin/node/)


## Release Notes

Release Notes for the Firebase Admin Node.js SDK are available
[here](https://firebase.google.com/support/release-notes/admin/node/).


## Acknowledgments

Thanks to the team at [Casetext](https://casetext.com/) for transferring
ownership of the `firebase-admin` npm module over to the Firebase team
and for their longtime use and support of the Firebase platform.


## License

The Firebase Admin Node.js SDK is covered by the
[Terms of Service for Firebase Services](https://firebase.google.com/terms/).
