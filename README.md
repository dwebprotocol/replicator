# @dswarm/replicator

Replicate data structures easily using dSwarm

## Install

```js
npm install @dswarm/replicator
```

## Usage

You data structure has to support a .replicate() stream, then you can replicate
them using the dSwarm replicator.

```js
const replicate = require('@dswarm/replicator')

const swarm = replicate(aDDatabase, {
  live: true // passed to .replicate
})

// swarm is a dSwarm instance that replicates the passed in instance
```

## API

#### `swarm = replicate(dataStructure, [options])`

Options include

```js
{
  bootstrap: [...], // optional set the DHT bootstrap servers
  live: bool, // passed to .replicate
  upload: bool, // passed to .replicate
  download: bool, // passed to .replicate
  encrypt: bool, // passed to .replicate
  discoveryKey: <buf>, // optionally set your own discovery key
  announce: true, // should the swarm announce you?
  lookup: true, // should the swarm do lookups for you?
  keyPair: { publicKey, secretKey }, // noise keypair used for the connection
  onauthenticate (remotePublicKey, done) // the onauthenticate hook to verify remote key pairs
}
```

## License

MIT
