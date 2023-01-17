---
description: Using Taraxa on the Ledger hardware wallet
---

# Ledger

## Create a wallet on Ledger





## Ledger's Ethereum App works with Taraxa through Metamask

Because the Taraxa Network is ETH-compatible, the Ethereum App actually works fine with the Taraxa Network, but needs to work through Metamask.&#x20;

Here's how it works, it's pretty simple,&#x20;

* You have an ETH address on your Ledger hardware wallet, if you're new to Ledger you can check out their official [Getting Started](https://support.ledger.com/hc/en-us/sections/4404369606801-Getting-Started?docs=true) guides according to which hardware device you have
* Follow the [How to access your Ledger Ethereum (ETH) account via Metamask](https://support.ledger.com/hc/en-us/articles/4404366864657-Set-up-and-use-MetaMask-to-access-your-Ledger-Ethereum-ETH-account?docs=true) guide by following Ledger's official documentation&#x20;
* [Add the Taraxa network into Metamask](metamask.md)&#x20;
* Use Metamask to send / receive TARA, and it will be signed by your wallet on the Ledger ETH app

This works because the Taraxa network is compatible with Ethereum's address and cryptography, so when Metamask sends a request for signature for the Taraxa network to the Ledger's ETH app, everything just works.&#x20;

