---
description: Building on Taraxa is easy as pie.
---

# 🚀 Quickstart

## Building on Taraxa's EVM-compatible Network = super easy

Hi! Thanks for checking out Taraxa's Layer-1 network. Here are a few quick links to get you started right away.&#x20;

* [Create a wallet](../wallet/) using tools you're already familiar with such as Metamask and Ledger
* Get some testnet tokens on the faucet on the Taraxa Explorer \[WIP]&#x20;
* [Connecting to the Taraxa network](connect-to-taraxas-network.md) via our dev deployed RPC endpoint, or running a node of your own&#x20;
* [Deploying a smart contract](smart-contracts-wip.md) is super easy, all ETH-compatible tools just work&#x20;
* [Taraxa RPC specifications](taraxa-rpc-specs.md) highlights Taraxa's near-100% compatibility with ETH's RPC specs, with a few minor quirks & exceptions

Let's get building!&#x20;



## A step-by-step example

To show how easy it is to develop on Taraxa and its ETH-compatibility, let's start with a simple step-by-step example. We're going to deploy a simple contract onto Taraxa's mainnet via [Remix](https://remix.ethereum.org/).&#x20;



* Go to [Remix](https://remix.ethereum.org/), you'll see the IDE

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* Let's start with one of the pre-populated default contracts in the Remix IDE, `1_Storage.sol`.&#x20;

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

* We'll compile with version 0.8.3

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

* Let's deploy, change the Environment to "Injected Provider - Metamask" and make sure that you're on the Taraxa Mainnet network on Metamask. If you don't know how, here's how you can [add Taraxa into Metamask](../wallet/metamask.md).&#x20;

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* Make sure you have some TARA in your wallet, Confirm the Metamask transaction prompt (wallet address redacted).&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

* Check out the console output inside the Remix IDE, looks like the contract was successfully deployed! (wallet address & transaction hash redacted)&#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* You can find the deployed contract address on the bottom left side of the Deploy & Run Transactions panel in the Remix IDE.&#x20;

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* We can also confirm this in the [explorer](https://explorer.mainnet.taraxa.io/), we can look up the transaction ID in the explorer and make sure the deployed contract address is the same. (certain details redacted)&#x20;

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

* Let's try interacting with the contract via the Remix IDE, let's store a number into the contract by calling the `store()` function, and of course confirm the transaction on Metamask. (certain details redacted).&#x20;

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* From the Remix IDE console output, it looks like the transaction went through, and calling the `retrieve()` function correctly recalls the stored number. Everything checks out!&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

🎊🎊 That's it, you're done! You've successfully deployed a smart contract onto Taraxa. 🎊🎊

