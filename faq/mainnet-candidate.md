# Mainnet Candidate

## What’s the purpose of the Mainnet Candidate?&#x20;

The Mainnet Candidate is meant to be a candidate network to be able to host native TARA tokens and become a fully-featured decentralized network. The primary goals of the Mainnet Candidate phase are,

* Deploy true community staking-based consensus
* Harden the network’s security, reliability, and performance
* Receive native TARA token conversion from ETH

## Is the Mainnet Candidate live?  <a href="#f7c9" id="f7c9"></a>

Yes, you can see it on the [mainnet candidate explorer](https://explorer.mainnet.taraxa.io) right now.&#x20;

## Will yields change on the Mainnet Candidate? <a href="#f7c9" id="f7c9"></a>

Staking Yields will be still be a fixed 20% annualized basis.

We will solicit the community for comments with regards to the implementation of a long-term dynamic yield curve prior to Native Token Conversion.

## How does **S**taking work on the Mainnet Candidate? <a href="#c0e0" id="c0e0"></a>

**Delegation is required**

In addition to staking into the contract, staked tokens must now be delegated to an active node on the Taraxa Mainnet Candidate network to earn yields, otherwise it earns nothing. This is a key economic mechanism in classic DPOS consensus to counter Sybil attacks.

After a Staker stakes TARA, they will need to select a node from a list of available nodes and delegate that stake into the node. Once a node has received the minimum necessary delegation, it will begin participating in consensus and earning yields.

****

**Need to pay commission to the delegated node**

Staking Yields (rewarded in the form of Block Rewards) and Transaction Fees now have to be split between the Staker and the Node Operator. How much commission a Node Operator charges is up to him, and whether or not the Staker selects the Node Operator is up to the Staker, making it a purely market-driven activity.

****

**Pick a node that has the maximum expected yield**

Not all consensus nodes are equal. Due to varying commitment, skill level, and resource allocation (e.g., does the Node Operator meet minimum resource requirements of a node), different nodes will have varying levels of expected yield. We encourage Stakers to be vigilant in switching away from low-yielding consensus nodes into high-yielding ones to help improve the reliability of the network — and of course earn a higher yield 😃

## How does running a node work on the Mainnet Candidate? <a href="#dac8" id="dac8"></a>

**Consensus eligibility from delegation**

Nodes will now need to receive delegated staking from Stakers in order to participate in consensus. There will be a minimum and a maximum delegation for consensus eligibility,

* Min delegation for a node to join consensus: **1mn tokens**
* Max delegation per consensus node: **10mn tokens**

There is a minimum requirement because any consensus node needs to get some sort of community recognition before it can participate in consensus. There is a maximum because we want to avoid excessive centralization and single-point of failure that could result in too many tokens being delegated into a single node.

****

**Define a commission for your node**

Each Node Operator will need to define a commission rate for every node they decide to operate, which is the percentage of overall Period Rewards (Block Rewards + Transaction Fees) that the node operator charges the Stakers. This is a purely market-driven decision, so please check out what other nodes are charging before you decide your own node’s commission rate.\


## Are Node Operators required to self-delegate? <a href="#2fe0" id="2fe0"></a>

_No_, Node Operators are NOT required to own tokens to delegate to the nodes they operate. We wish to maximize the potential pool of Node Operators.

This policy may of course change based on community feedback and how it impacts overall network quality.

## How many nodes will there be in the Mainnet Candidate? <a href="#7a2a" id="7a2a"></a>

Since consensus nodes are driven by delegated stake, the number of nodes will depend on how many tokens are staked in the network.

As of this writing, there are \~248 million TARA tokens staked, so this will enable a minimum of 25 consensus nodes. As staking grows, so will the number of consensus nodes in the network.

The development team will initially maintain 9 consensus nodes across the world, and 9 boot nodes to bootstrap the network and help improve latency. The delegated stake for these nodes will come from the Foundation.

## Will there still be a testnet? <a href="#b168" id="b168"></a>

YES! New features will still need to be tested before being deployed on the mainnet, so there’s always a need for a testnet.

Furthermore, the testnet will provide a good proving ground and a “bench” for potential Node Operators on the mainnet, so as staking increases, there’ll be a continuous supply of new nodes.

Top block producing awards on the testnet will also continue on until further notice.\


## When is Native Token Conversion?&#x20;

Native token conversion depends on many factors that are beyond the developer team's control, the biggest of which is exchange adoption. The developer team will be working closely with the exchanges per the Taraxa Foundation's instructions to make sure that we meet all their internal security hurdles.&#x20;

The developer team will publish a roadmap as soon as timelines become clear.&#x20;

##
