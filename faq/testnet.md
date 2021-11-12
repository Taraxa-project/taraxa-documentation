---
description: All your burning questions about Taraxa's testnet.
---

# Testnet

## What errors should I NOT be concerned about?&#x20;

The blockchain network exists in a constant state of flux where a lot of things are "going wrong" constantly. But the beauty of a successful blockchain network is that it can handle and fix these inconsistencies and errors gracefully. Many of the errors you see displayed from the node should not concern you because they're temporary, and the node understands them and knows how to handle them.&#x20;

Here's a list of commonly seen "errors" that you should NOT be concerned about,&#x20;

* [ERROR: Vote sortition failed](testnet.md#error-vote-sortition-failed.)
* [ERROR: Received NewBlock xxx has missing pivot or/and tips](testnet.md#error-received-newblock-xxx-has-missing-pivot-or-and-tips)
* [ERROR: DagBlockValidation failed](testnet.md#error-dagblockvalidation-failed)

## Is incentivized testnet live?&#x20;

We have an ongoing incentivized testnet, please check out this [step by step guide](https://taraxa.io/run\_node) to participate!&#x20;

## How do I run a node?

Please see our [node operation instructions](https://www.taraxa.io/run\_node).

We recommend everyone who wants to run a node join our [Discord server](https://www.taraxa.io/discord) and look for the #node-operations channel.

## Is there a testnet?

Yes, you can look at the testnet through our [explorer](https://explorer.testnet.taraxa.io). It is a test network so occasionally it will go down or get wiped, please join our [Discord server](https://www.taraxa.io/discord) for the latest information.

## How do I tell if my node has been synced?&#x20;

Either go to the dashboard, which is located at your node's IP at port :3000, or you can look in the CLI log outputs and look for the `---- tl;dr ----` section, first line should tell you the node's sync status.&#x20;

## Why does my node's sync percentage go down?&#x20;

This is normal.&#x20;

Your node determines its synchronization progress by asking the nodes it's connected to. Sometimes, and this often happens after a network recovers from a crash, the node is only connected to peers that aren't 100% synced themselves. But when the node connects to a new peer who is either fully synced or has made more sync progress than its existing (or previous) peers, the node adjusts and re-calculates its sync progress.&#x20;

We recommend comparing your node's synchronization status against the network progress on the explorer to get a better sense of where your node actually is.&#x20;

## How do I update / reset my node?&#x20;

Here are the instructions to [update](../node-setup/upgrade-a-node/software-upgrade.md#upgrade-your-nodes-software) or [reset ](../node-setup/upgrade-a-node/data-reset.md)the node.&#x20;

## Why is my node shown as inactive on the community site?&#x20;

A node is considered active only if it has been [fully synced](testnet.md#undefined) as well as producing blocks. If it's not then it shows up as inactive on the community site.&#x20;

A block-producing node should also show up on the [node list](https://explorer.testnet.taraxa.io/nodes) in the explorer.&#x20;

## I received TARA on my node after registration, what does that mean?&#x20;

TARA tokens on the testnet are not real tokens, so please don't try to send those out (it won't work), and please do not send any tokens from another chain (e.g., ETH) into the testnet - it won't work and you'll lose your tokens.&#x20;

The tokens are sent to your node as part of the faucet to generate some transaction traffic on the network, and that later on we will run community-driven stress tests which will require that everyone has some testnet tokens to send around.&#x20;

## Why is my node eating up so much CPU / RAM? &#x20;

Our recommended system setup is 4-core CPU, 8GB RAM, and 50GB disk.&#x20;

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

`"db_max_snapshots" : 0`

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



