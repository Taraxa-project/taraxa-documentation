---
description: Deploying Smart Contracts on Taraxa via Remix
---

# Remix

Here's a step-by-step example to deploy a simple contract onto Taraxa's mainnet via [Remix](https://remix.ethereum.org/).&#x20;



* Go to [Remix](https://remix.ethereum.org/), you'll see the IDE

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* Let's start with one of the pre-populated default contracts in the Remix IDE, `1_Storage.sol`.&#x20;

<figure><img src="../../.gitbook/assets/image (4) (2).png" alt=""><figcaption></figcaption></figure>

* We'll compile with version 0.8.3

<figure><img src="../../.gitbook/assets/image (13) (1).png" alt=""><figcaption></figcaption></figure>

* Let's deploy, change the Environment to "Injected Provider - Metamask" and make sure that you're on the Taraxa Mainnet network on Metamask. If you don't know how, here's how you can [add Taraxa into Metamask](../../wallet/metamask.md).&#x20;

<figure><img src="../../.gitbook/assets/image (6) (3).png" alt=""><figcaption></figcaption></figure>

* Make sure you have some TARA in your wallet, Confirm the Metamask transaction prompt (wallet address redacted).&#x20;

<figure><img src="../../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

* Check out the console output inside the Remix IDE, looks like the contract was successfully deployed! (wallet address & transaction hash redacted)&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

* You can find the deployed contract address on the bottom left side of the Deploy & Run Transactions panel in the Remix IDE.&#x20;

<figure><img src="../../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

* We can also confirm this in the [explorer](https://explorer.mainnet.taraxa.io/), we can look up the transaction ID in the explorer and make sure the deployed contract address is the same. (certain details redacted)&#x20;

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

* Let's try interacting with the contract via the Remix IDE, let's store a number into the contract by calling the `store()` function, and of course confirm the transaction on Metamask. (certain details redacted).&#x20;

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* From the Remix IDE console output, it looks like the transaction went through, and calling the `retrieve()` function correctly recalls the stored number. Everything checks out!&#x20;

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

🎊🎊 That's it, you're done! You've successfully deployed a smart contract onto Taraxa. 🎊🎊
