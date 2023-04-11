---
description: Everything you want to know about Taraxa's Mainnet!
---

# 🌱 Mainnet

## Is the Mainnet live?  <a href="#f7c9" id="f7c9"></a>

Yes, you can see it on the [mainnet explorer](https://explorer.mainnet.taraxa.io/) right now.&#x20;

## &#x20;<a href="#c0e0" id="c0e0"></a>

## How does **S**taking work on the Mainnet ? <a href="#c0e0" id="c0e0"></a>

**Delegation is required**

In addition to staking into the contract, staked tokens must now be delegated to an active node on the Taraxa Mainnet network to earn yields, otherwise it earns nothing. This is a key economic mechanism in classic DPOS consensus to counter Sybil attacks.

After a Staker stakes TARA, they will need to select a node from a list of available nodes and delegate that stake into the node. Once a node has received the minimum necessary delegation, it will begin participating in consensus and earning yields.



**Need to pay commission to the delegated node**

Staking Yields (rewarded in the form of Block Rewards) and Transaction Fees now have to be split between the Staker and the Node Operator. How much commission a Node Operator charges is up to him, and whether or not the Staker selects the Node Operator is up to the Staker, making it a purely market-driven activity.



**Pick a node that has the maximum expected yield**

Not all consensus nodes are equal. Due to varying commitment, skill level, and resource allocation (e.g., does the Node Operator meet minimum resource requirements of a node), different nodes will have varying levels of expected yield. We encourage Stakers to be vigilant in switching away from low-yielding consensus nodes into high-yielding ones to help improve the reliability of the network — and of course earn a higher yield 😃

## &#x20;<a href="#dac8" id="dac8"></a>

## How does running a node work on the Mainnet? <a href="#dac8" id="dac8"></a>

**Consensus eligibility from delegation**

Nodes will now need to receive delegated staking from Stakers in order to participate in consensus. There will be a minimum and a maximum delegation for consensus eligibility,

* Min delegation for a node to join consensus: **500k tokens**
* Max delegation per consensus node: **80mn tokens**

There is a minimum requirement because any consensus node needs to get some sort of community recognition before it can participate in consensus. There is a maximum because we want to avoid excessive centralization and single-point of failure that could result in too many tokens being delegated into a single node.



**Define a commission for your node**

Each Node Operator will need to define a commission rate for every node they decide to operate, which is the percentage of overall Period Rewards (Block Rewards + Transaction Fees) that the node operator charges the Stakers. This is a purely market-driven decision, so please check out what other nodes are charging before you decide your own node’s commission rate.\


## How is commission calculated? <a href="#2fe0" id="2fe0"></a>

The commission is a percent of the overall yield earned by the node. If a node is charging say 5% commission, and it is earning 20% annualized yield, then the commission is 5% of that 20% yield, which is 1% of the overall delegation, annualized.&#x20;

Here's a simple example,&#x20;

* A node has 10mn tokens delegated, it earns 20% on that per year, or 2mn tokens per year
* This node has a 5% commission, so the node operator gets 5% of 2mn, which is 100k tokens per year&#x20;
* The remaining 95% of the yield, 1.9mn tokens per year, goes to the staker(s) who delegated the tokens to the node

## Can I register a Testnet node into the Mainnet network?  <a href="#2fe0" id="2fe0"></a>

No.&#x20;

The Testnet and the Mainnet are two different networks, with two different code bases. You cannot register a node from one codebase into another, and you cannot run a node from one codebase in the other's network.&#x20;

## Are Node Operators required to self-delegate? <a href="#2fe0" id="2fe0"></a>

There is a 1000 TARA self-delegation requirement for node operators. This self-delegation requirement is not meant to be a financial burden, but purely to guard against spamming.&#x20;

## How many nodes will there be in the Mainnet? <a href="#7a2a" id="7a2a"></a>

You can find a real time accounting of the network on [Taraxa's website](https://taraxa.io/node/).&#x20;

Since consensus nodes are driven by delegated stake, the number of nodes will depend on how many tokens are staked in the network.

## Do I need to unstake to claim my staking yields?  <a href="#b168" id="b168"></a>

You do NOT need to unstake in order to claim your rewards. Just claim your rewards on the community site's [redeem section](https://community.taraxa.io/redeem).&#x20;

## Will there still be a testnet? <a href="#b168" id="b168"></a>

YES! New features will still need to be tested before being deployed on the mainnet, so there’s always a need for a testnet.

Furthermore, the testnet will provide a good proving ground and a “bench” for potential Node Operators on the mainnet, so as staking increases, there’ll be a continuous supply of new nodes.

Top block producing awards on the testnet will also continue on until further notice.\


##
