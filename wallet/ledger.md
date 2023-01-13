---
description: Using Taraxa on the Ledger hardware wallet
---

# Ledger

## Ledger's Ethereum App works with Taraxa through Metamask

Because the Taraxa Network is ETH-compatible, the Ethereum App actually works fine with the Taraxa Network, but needs to work through Metamask.&#x20;

Here's how it works, it's pretty simple,&#x20;

* You have an ETH address on your Ledger hardware wallet&#x20;
* [Connect your Ledger hardware wallet into Metamask](https://www.ledger.com/academy/security/the-safest-way-to-use-metamask) by following Ledger's official documentation&#x20;
* [Add the Taraxa network into Metamask](metamask.md)&#x20;
* Use Metamask to send / receive TARA, and it will be signed by your wallet on the Ledger ETH app

This works because the Taraxa network is compatible with Ethereum's address and cryptography, so when Metamask sends a request for signature for the Taraxa network to the Ledger's ETH app, everything just works.&#x20;

