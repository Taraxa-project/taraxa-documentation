---
description: Dev release nodes for mainnet node post-conversion
---

# 🔢 Node Release Notes

## v1.8.0 - Aspen Hardfork PART TWO on Mainnet

_`Hardfork at block 8,572,000 on Mainnet`_

{% hint style="info" %}
This completes the Aspen hardfork!
{% endhint %}

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.8.0`&#x20;

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/pull/2668](https://github.com/Taraxa-project/taraxa-node/pull/2668)&#x20;

**Release Highlights:**&#x20;

**Token Economic Improvements**

* Aspen Hardfork, implements the community approved [TIP-2](https://github.com/Taraxa-project/TIP/blob/main/TIP-2/TIP-2%20-%20Cap%20TARA's%20Total%20Supply.md) which caps the max Taraxa token supply to 12 billion going forward.  The first part of the hardfork (v1.7.2 at block 8,118,000) created the necessary data retention to ensure light-nodes will be able to smoothly upgrade in the final hardfork.

## v1.7.2 - Aspen Hardfork PART ONE on Mainnet

_`Hardfork at block 8,118,000 on Mainnet`_

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.7.2`&#x20;

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/pull/2713](https://github.com/Taraxa-project/taraxa-node/pull/2713) (v1.7.2)

[https://github.com/Taraxa-project/taraxa-node/pull/2675](https://github.com/Taraxa-project/taraxa-node/pull/2675) (v.1.7.0)

_NOTE: v.1.7.0 contains the Aspen Hardfork, but v1.7.2 contains a critical bug-fix for node inter-communication during the upgrade process._\


**Release Highlights:**&#x20;

**Token Economic Improvements**

* Aspen Hardfork, when complete will implement the community approved [TIP-2](https://github.com/Taraxa-project/TIP/blob/main/TIP-2/TIP-2%20-%20Cap%20TARA's%20Total%20Supply.md) which will cap the max Taraxa token supply to 12 billion going forward. Hardfork PART ONE creates the necessary data retention to ensure light-nodes will be able to smoothly upgrade in Aspen Hardfork PART TWO which will follow shortly after Aspen Hardfork part one.\

* Another significant improvement in Aspen Hardfork PART ONE is that block rewards for DAG block production will be tied more directly to stake by rewarding DAG blocks on their possessing low VDF difficulty level, which is solely determined by VRF sortition tied to stake. It will no longer be based also on unique transaction inclusion. Under the previous system nodes could game unique transaction inclusion, or were rewarded based on proximity to transaction creators, or by using significant CPU hardware to somewhat outpace the VDF calculations of others.

##

## v1.5.1 - Magnolia Hardfork on Mainnet



_`Hardfork at block 5,730,000 on Mainnet`_

This hardfork will take effect at PBFT block height: 5,730,000.&#x20;



**Features:**

* **Parallel Execution of State Pruning**: Enhanced efficiency by enabling parallel execution during state pruning.
* **Improved Tracing API**: Upgraded tracing API for better performance and usability.
* **State Root Verification on Syncing**: Ensured data integrity through state root verification during syncing processes.
* **Transaction Pool Overflow Improvements**: Addressed transaction pool overflow issues for improved stability.
* **Sync-Gossip Transition Improvement**: Optimized the transition between syncing and gossip protocols.
* _LOG.old Files Cleanup on Database Start_\*: Initiated cleanup of old log files on database startup for a cleaner DB environment.
* **Syncing Optimizations**: Implemented optimizations for a smoother syncing process.
* **Removal of Existing Transactions Check**: Streamlined operations by removing checks for existing transactions.
* **Reduced Prune Memory Usage**: Optimized memory usage during pruning processes.
* **Added RPC Methods for Faster Indexing**: Introduced new RPC methods to expedite the indexing process.
* **Optimized Peer Cache Memory Usage**: Improved memory utilization within the peer cache.
* **Improved Performance of Vote Weight Calculation**: Enhanced efficiency in vote weight calculation.
* **Improved Ping Timeout Handling on Discovery**: Optimized handling of ping timeouts during the discovery process.
* **Handled Batch Requests via WebSocket Interface**: Enabled handling of batch requests through the WebSocket interface.
* **Improved Light Node History Deletion**: Enhanced the process of history deletion in light nodes.

**Fixes:**

* **Corrected Reward Votes Initialization**: Fixed the initialization process of reward votes for accurate tallying.
* **Usage of All Passed Gas on Reverts**: Resolved an issue with unused gas on reverts.
* **Period Data Transactions Order**: Corrected the ordering of period data transactions.
* **Resolved Ignorance of PBFT Size Check on Syncing**: Fixed an issue where PBFT size check was being ignored during syncing.
* **Fixed Syncing of DAG Blocks**: Addressed syncing issues of DAG blocks for improved data consistency.

**Hard Fork (HF) Features:**

* **Process Rewards in Batches Every N Blocks**: Implemented batch processing of rewards every N blocks for efficiency.
* **Jailing of Validator on Double Voting**: Introduced a penalty mechanism for validators engaged in double voting by jailing them.

**Github:**

* [https://github.com/Taraxa-project/taraxa-node/releases/tag/v1.5.1](https://github.com/Taraxa-project/taraxa-node/releases/tag/v1.5.1)



## v1.4.0

_`Hardfork at block 3091000 on Mainnet`_

**Docker image:**&#x20;

`docker pull taraxa/taraxa-node:v1.4.0`&#x20;

**Github:** &#x20;

[https://github.com/Taraxa-project/taraxa-node/pull/2548](https://github.com/Taraxa-project/taraxa-node/pull/2548)



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
