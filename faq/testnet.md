---
description: All your burning questions about Taraxa's testnet.
---

# Testnet & Node

## What errors should I NOT be concerned about?&#x20;

The blockchain network exists in a constant state of flux where a lot of things are "going wrong" constantly. But the beauty of a successful blockchain network is that it can handle and fix these inconsistencies and errors gracefully. Many of the errors you see displayed from the node should not concern you because they're temporary, and the node understands them and knows how to handle them.&#x20;

Here's a list of commonly seen "errors" that you should NOT be concerned about,&#x20;

* [ERROR: Vote sortition failed](testnet.md#error-vote-sortition-failed.)
* [ERROR: Received NewBlock xxx has missing pivot or/and tips](testnet.md#error-received-newblock-xxx-has-missing-pivot-or-and-tips)
* [ERROR: DagBlockValidation failed](testnet.md#error-dagblockvalidation-failed)
* [ERROR: Incorrect node version](testnet.md#error-incorrect-node-version-0-our-node-version-xxxxx-host-xxxxx-will-be-disconnected)
* [ERROR: RangeError \[ERR\_HTTP\_INVALID\_STATUS\_CODE\]: Invalid status code: undefined](testnet.md#rangeerror-err\_http\_invalid\_status\_code-invalid-status-code-undefined)

## Is incentivized testnet live?&#x20;

We have an ongoing incentivized testnet, please check out this [step by step guide](https://taraxa.io/run\_node) to participate!&#x20;

## How do I run a node?

Please see our [node operation instructions](https://www.taraxa.io/run\_node).

We recommend everyone who wants to run a node join our [Discord server](https://www.taraxa.io/discord) and look for the #node-operations channel.

## Is there a testnet?

Yes, you can look at the testnet through our [explorer](https://explorer.testnet.taraxa.io). It is a test network so occasionally it will go down or get wiped, please join our [Discord server](https://www.taraxa.io/discord) for the latest information.

## How do I report a problem?&#x20;

First, join [Taraxa's Discord server](https://www.taraxa.io/discord) for technical discussions.&#x20;

Always try include the following information when you're reporting a problem,&#x20;

* Your node's public address (see [how to get your node's public address](../node-setup/node\_address.md))&#x20;
* Your system resources: CPU (# of cores), RAM, Disk&#x20;
* Are you running this on a dedicated or a shared machine
* If it's in the cloud, the cloud service provider, and your instance's physical location (e.g., Frankfurt - Germany)&#x20;
* Screenshot the error message, or better yet the logs (see [how to get the logs](testnet.md#undefined))&#x20;
* System resource consumption screenshot - e.g., a time-series of CPU or RAM utilization
* Anything out of the ordinary you were doing right before this error occurred, e.g., tried to import a previous state\_db.&#x20;

Thanks for all your feedback!&#x20;

## How do I download the node's logs when reporting a problem?&#x20;

Here's the command to generate logs from the node,&#x20;

`docker logs taraxa_compose_node_1 > logs`

Note that, the container is not always called `taraxa_compose_node_1` on every environment. If this doesn't wrok, please check to make sure - use `docker ps` to see a list of all your containers and figure out exactly what the name of your container is.&#x20;

If the node has been running for a while, the log file might be too big, so it's a good idea just to get the latest few log entries, say 50,000,  you can try this,&#x20;

`docker logs --tail 50000 taraxa_compose_node_1 > logs`

Now that you have the `logs` file, just send it to the dev team along with your problem report. Thanks!&#x20;

## How do I tell if my node has been synced?&#x20;

Either go to the dashboard, which is located at your node's IP at port :3000, or you can look in the CLI log outputs and look for the `---- tl;dr ----` section, first line should tell you the node's sync status.&#x20;

## Why does my node's sync percentage go down?&#x20;

This is normal.&#x20;

Your node determines its synchronization progress by asking the nodes it's connected to. Sometimes, and this often happens after a network recovers from a crash, the node is only connected to peers that aren't 100% synced themselves. But when the node connects to a new peer who is either fully synced or has made more sync progress than its existing (or previous) peers, the node adjusts and re-calculates its sync progress.&#x20;

We recommend comparing your node's synchronization status against the network progress on the explorer to get a better sense of where your node actually is.&#x20;

## How do I know if my node is producing blocks?&#x20;

There are several ways to tell,&#x20;

* Go to your node's IP at port :3000, and see "Synced - Participating in consensus", or if you see that in your node's logs `STATUS: GOOD. NODE SYNCED AND PARTICIPATING IN CONSENSUS`
* Go to the [explorer's node page](https://explorer.testnet.taraxa.io/nodes) and see if your address is listed, note it's paginated so you may not be on the first page
* Search for your node's public address on the [explorer](https://explorer.testnet.taraxa.io) and see how many blocks (if any) it has produced
* Go to the [community site's node list](https://community.taraxa.io/node) and see if your node is listed active

Several things to note,&#x20;

* Sometimes the explorer is reset and that will cause you to not see the node list or the community site node list, the most reliable way to tell is to look at your local node and see if it is participating in consensus&#x20;
* You will often see messages like `PARTICIPATING IN CONSENSUS BUT NO NEW FINALIZED BLOCKS`, `PBFT STALLED, POSSIBLY PARTITIONED. NODE HAS NOT RESTARTED SYNCING`, or `STUCK. NODE HAS NOT RESTARTED SYNCING,` these happen from time to time and not necessarily specific to your node

## What if my node is not producing any blocks at all and just says "Synced"?&#x20;

If your node is 100% synced but has not produced any block, please make sure that your node is properly registered on the community site's node page.&#x20;

If it has already been registered and still it's producing no block at all, then try deleting your node from the community site and add it back in again.&#x20;

## How do I update / reset my node?&#x20;

Here are the instructions to [update](../node-setup/upgrade-a-node/software-upgrade.md#upgrade-your-nodes-software) or [reset ](../node-setup/upgrade-a-node/data-reset.md)the node.&#x20;

## Why is my node shown as inactive on the community site?&#x20;

A node is considered active only if it has been [fully synced](testnet.md#undefined) as well as producing blocks. If it's not then it shows up as inactive on the community site.&#x20;

A block-producing node should also show up on the [node list](https://explorer.testnet.taraxa.io/nodes) in the explorer.&#x20;

## I received TARA on my node after registration, what does that mean?&#x20;

TARA tokens on the testnet are not real tokens, so please don't try to send those out (it won't work), and please do not send any tokens from another chain (e.g., ETH) into the testnet - it won't work and you'll lose your tokens.&#x20;

The tokens are sent to your node as part of the faucet to generate some transaction traffic on the network, and that later on we will run community-driven stress tests which will require that everyone has some testnet tokens to send around.&#x20;

## Why is my node eating up so much CPU / RAM? &#x20;

Our recommended system setup is 4-core CPU, 16GB RAM, and 200GB disk.&#x20;

Currently in the network, CPU and RAM consumption is very high during syncing. A faster, less resource-intensive sync is on the roadmap.&#x20;

Our node currently also seems to eat up much more memory than intended, and node optimization is definitely on the roadmap after the mainnet candidate release.&#x20;

## Why is my node eating up so much disk space?&#x20;

At the current stage we only have a FULL node implementation, which means the node stores the entirety of the blockchain's history. For a full node, our space consumption is comparable to other blockchain networks such as Ethereum.&#x20;

What will permanently solve this problem is create a light node, which only stores the current state, and prunes (deletes) the historical transactional data. This is on the roadmap.&#x20;

For now, you can ameliorate this problem by disabling and deleting some snapshots if you'd like. The node generates and stores many network snapshots (for testing purposes) which could take up a lot of memory, and we're going to update it later on to stop generating them.&#x20;

If you would like to save disk space, you can do two things.&#x20;

**Step 1: please go to the config file**

`/taraxa-ops-master/taraxa_compose/config/testnet.json`

Inside this file, set,&#x20;

`"`db\_snapshot\_each\_n\_pbft\_block`" : 0`

IMPORTANT: Now restart the node or just restart the entire machine. If you don't this change won't take effect.&#x20;

**Step 2: remove the snapshots from your existing node**

On a Linux system the db files are located here,&#x20;

`./var/lib/docker/volumes/taraxa_compose_data/_data/db/`

The only files you need to keep are `db` and `state_db`. The rest you can just clear out.&#x20;

If you're on a different system, you can try searching for the file `state_db` and see where it's located.&#x20;

## My node gets killed when it runs out of disk space!&#x20;

The most common problem we're seeing is that the node runs out of disk space. We're working to update our one-click install scripts to help with this problem - e.g., attaching a disk volume to the machine on VPS.&#x20;

In the meantime please increase the disk allocation on your own.&#x20;

## ERROR: No such container: taraxa\_compose\_node-1

This happens when you're trying to access the node's container (e.g., when trying to produce the prove-you-own-your-node signature), but the container's name is wrong.&#x20;

Different operating systems name these containers slightly differently. When you see this the best thing to do is to try&#x20;

`docker container ls`

and see what your node's container is actually called.&#x20;

Of course, if you are running multiple nodes then they're likely sequentially numbered, listing all the containers will also help to find the one you're looking for.&#x20;

## ERROR: Vote sortition failed.&#x20;

Typically speaking you don't need to worry about this error.&#x20;

This means that your node has received a vote that it deems invalid. This doesn't mean something's wrong with your node, likely it indicates something's wrong with the node that generated the invalid vote.&#x20;

## ERROR: Received NewBlock xxx has missing pivot or/and tips

Typically speaking you don't need to worry about this error.&#x20;

It indicates that the node has received a DAG block, but the node is missing its parents - i.e., other DAG blocks it's pointing to. Since there's no guarantee the order in which packets arrive over the network, a node could easily see a specific block before it sees the parent. In fact, when this happens, the node will proactively request from its peers the missing parent blocks.&#x20;

## ERROR: DagBlockValidation failed&#x20;

Typically speaking you don't need to worry about this error.

The reason for this happening is the same as the error about [missing pivots or tips](testnet.md#error-received-newblock-xxx-has-missing-pivot-or-and-tips), and the node should naturally recover.&#x20;

## ERROR: Incorrect node version: 0, our node version xxxxx, host xxxxx will be disconnected&#x20;

You don't need to worry about this error.

We added a versioning system, and nodes that have different versions will not connect to each other as peers. This message is your node encountering another node that's a different version, so it has decided to disconnect that node from its peers.&#x20;

This design choice may be revisited later, as we progress towards mainnet we may have to take backwards compatibility into consideration.&#x20;

## RangeError \[ERR\_HTTP\_INVALID\_STATUS\_CODE]: Invalid status code: undefined

You don't need to worry about this error.

It's actually from the node status app and it happens when the app starts before the actual node and can't get data from it.

