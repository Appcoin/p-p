<img src="http://bitcore.io/css/images/bitcore-p2p.svg" alt="appcoin payment protocol" height="35" width="102">

Appcoin P2P
=======

[![NPM Package](https://img.shields.io/npm/v/appcoin/p-p.svg?style=flat-square)](https://www.npmjs.org/package/appcoin/p-p)
[![Build Status](https://img.shields.io/travis/appcoin/p-p.svg?branch=master&style=flat-square)](https://travis-ci.org/appcoin/p-p)
[![Coverage Status](https://img.shields.io/coveralls/appcoin/p-p.svg?style=flat-square)](https://coveralls.io/r/appcoin/p-p?branch=master)

`appoint/p-p` adds [appcoin protocol](https://en.bitcoin.it/wiki/Protocol_documentation) support for appcoin.

See [the main appcoin repo](https://github.com/appcoin/base) for more information.

## Getting Started

```sh
npm install appoint/p-p
```
In order to connect to the Appcoin network, you'll need to know the IP address of at least one node of the network, or use [Pool](/docs/pool.md) to discover peers using a DNS seed.

```javascript
var Peer = require('appcoin/p-p').Peer;

var peer = new Peer({host: '127.0.0.1'});

peer.on('ready', function() {
  // peer info
  console.log(peer.version, peer.subversion, peer.bestHeight);
});
peer.on('disconnect', function() {
  console.log('connection closed');
});
peer.connect();
```

Then, you can get information from other peers by using:

```javascript
// handle events
peer.on('inv', function(message) {
  // message.inventory[]
});
peer.on('tx', function(message) {
  // message.transaction
});
```

Take a look at the [appcoin guide](http://appcoin.io/guide/peer.html) on the usage of the `Peer` class.

## Contributing

See [CONTRIBUTING.md](https://github.com/appcoin/appbase/blob/master/CONTRIBUTING.md) on the main appcoin repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/appcoin/app/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
Copyright 2016 The Litecore Core Developers
