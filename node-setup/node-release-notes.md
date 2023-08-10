---
description: Dev release nodes for mainnet node post-conversion
---

# 🔢 Node Release Notes

## v1.4.0

_`Hardfork at block 3067000 on Mainnet`_

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.4.0`&#x20;

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/pull/2544](https://github.com/Taraxa-project/taraxa-node/pull/2544)



**Release Highlights:**&#x20;

**DPOS Contract**

* Fixes a critical security vulnerability where a call to DPOS contract could cause a persisting error in the state readout for a validator.
* Removes the depth limit on contract call enabling other contracts to interact with the DPOS contract

## v1.3.2

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.3.2`&#x20;

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/pull/2539](https://github.com/Taraxa-project/taraxa-node/pull/2539)



**Release Highlights:**&#x20;

**RPC**

* Added batch RPC request support via websockets

## v1.3.1

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.3.1`&#x20;

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/commit/24e6c310b3168dc93b5d4095556eb41544f13e8b](https://github.com/Taraxa-project/taraxa-node/commit/24e6c310b3168dc93b5d4095556eb41544f13e8b)



**Release Highlights:**&#x20;

**RPC**

* RPC changes to increase indexer performance
* Update EVM submodule with added `getTotalDelegation` method to DPOS contract

**Consensus**

* Disconnect nodes that send multiple PBFT votes (ie. equivocate) in same step in network layer
* Properly rebroadcast blocks that local node has voted for

## v1.3.0

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.3.0-rc.10253`

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/compare/master...release/v1.3.0](https://github.com/Taraxa-project/taraxa-node/compare/master...release/v1.3.0)  &#x20;



**Release Highlights:**&#x20;

**Storage**

* [Remove duplicated columns from db](https://github.com/Taraxa-project/taraxa-node/commit/9a4f4afcc7517a2a46bf09c50f666fad0b64c88f)
* [Change how we process db versions changes](https://github.com/Taraxa-project/taraxa-node/commit/bda00c5d70b7c6f403b03a25f71c1772c5343c83)
* [Feature: implement db migrations](https://github.com/Taraxa-project/taraxa-node/commit/8d85640ad145e8efb17b0f64ddc56059dec502e3)
* [Feature: add transaction hashes migration](https://github.com/Taraxa-project/taraxa-node/commit/377bf9a24d70eb10bcefa2bcc453d889be344767)
* [Fix to update db version only if rebuild\_db or all migrations was applied](https://github.com/Taraxa-project/taraxa-node/commit/3a985ec594828d01bbd2480e0da7cd2c452fa76e)

#### Syncing

* [Check state root during syncing](https://github.com/Taraxa-project/taraxa-node/commit/e78e5193062809067a21d79eb7c33fae3be78075)
* [Fix setting reward votes period on node startup and sync init](https://github.com/Taraxa-project/taraxa-node/commit/d557974786196d80b7e961fd9011da9fbb60179e)
* [Fix to not broadcast votes that were not processed](https://github.com/Taraxa-project/taraxa-node/commit/35ffa41fa44c0e6ee4ce601bedbb1514a698808b)
* [Fix request vote syncing only if packet sender is vote author](https://github.com/Taraxa-project/taraxa-node/commit/5aac615aa0b918a6a9ee107555e809262ae06065)
* [Save nodes own votes and re-gossip them for faster sync](https://github.com/Taraxa-project/taraxa-node/commit/89cebc490e7d45f3ff508fcb1d3c47e49c9a3e4d)

#### Consensus

* [Correct check for duplicate reward votes](https://github.com/Taraxa-project/taraxa-node/commit/e4cd97cf08ad1804eeefcebb0f6f25dce53c3cec)
* [Fixed exponential backoff behavior in event of partition](https://github.com/Taraxa-project/taraxa-node/commit/52ff614d7fab942d019bb36329478e0515050cc9)

#### EVM

* [Fixed gas estimation for transactions with calls to internal contract methods](https://github.com/Taraxa-project/taraxa-node/commit/903ec6deff92c67145a491e6cf201cfb3e3a10d5)
* [Fixed use of all passed gas \[sic\] on reverts](https://github.com/Taraxa-project/taraxa-node/commit/9b1756293e0dbfc931fd11ad630072a1184c47e6)
* [Updated evm submodule with correct address in dpos\_contract logs](https://github.com/Taraxa-project/taraxa-node/commit/bbd34eebc6b178db1de0afe93de68dc485248f23)

#### RPC

* [Implemented EIP-1898](https://github.com/Taraxa-project/taraxa-node/commit/80b8f12d7473cdbd897bba690b19c43501fca7c3)

#### Improved Tracing

* [Implemented trace\_replayTransaction](https://github.com/Taraxa-project/taraxa-node/commit/0f6abd5fad871c1ea504f7f548132162740942f5)
* [Added support for tracing blocks](https://github.com/Taraxa-project/taraxa-node/commit/c7ecdb98892409388e6bba2b138c9972defaaa70)

#### Light Node

* [Prune state db initiated manually from command line](https://github.com/Taraxa-project/taraxa-node/commit/e295ed3bbf99e857a1c3f67382a9da69a6d1a93b)
