# 🚩 Staking via community site

> To comply with recent SEC rulings, United States persons and persons from OFAC-sanctioned regions cannot receive token rewards from staking. All participants will be required to pass KYC to receive rewards.

You don't, however need to use the community site. You may perform all staking functions [directly on-chain by interacting with DPoS contract](staking-directly-on-chain.md).&#x20;

If you still wish to use the community site, please follow the steps below.&#x20;



### 0.  Register an account on the community site&#x20;

Navigate to the [community site](http://community.taraxa.io/) and register an account.&#x20;

<figure><img src="../.gitbook/assets/1. register.png" alt=""><figcaption></figcaption></figure>

### 1.  Pass KYC

To claim rewards (e.g., staking commission, yields) from the community site, you must pass KYC. It is in the [profile section](https://community.taraxa.io/profile).&#x20;

> DISCLAIMER: To comply with recent SEC rulings, United States persons and persons from OFAC-sanctioned regions cannot receive token rewards from running nodes. All participants will be required to pass KYC to receive rewards.

<figure><img src="../.gitbook/assets/2. kyc.png" alt=""><figcaption></figcaption></figure>

### 2.  Connect your wallet

Connect your wallet (upper-right corner). You may use any web3-enabled wallet that works with the Taraxa network, we recommend MetaMask.&#x20;

<figure><img src="../.gitbook/assets/9. profile (connect wallet).png" alt=""><figcaption></figcaption></figure>

### 3.  Delegate to a validator

Once your wallet is connected, navigate to the [community site's staking page](https://community.taraxa.io/staking) and select one ore more validators to delegate to.&#x20;

On this page you'll see a list of validators that have listed their nodes up for delegation. The "Avalailable for Delegation" shows you how much more delegation this specific node is able to take in. Each node can take on a total of 80 million TARA in delegation, beyond that no more delegation is possible for the specific node.&#x20;

_NOTE: the dev team is working to gather and display past uptime statistics (work in progress) so that you may make an informed choice on which validator to delegate your tokens to. Uptime is critical as it impacts the effective yield rate - i.e., if a node is not turned on, it does not earn any yields._&#x20;

<figure><img src="../.gitbook/assets/4. delegate to a node.png" alt=""><figcaption></figcaption></figure>

Minimum delegation per validator node is 1000 TARA.&#x20;

<figure><img src="../.gitbook/assets/5. delegation screen.png" alt=""><figcaption></figcaption></figure>

### 4.  Claim staking yields&#x20;

You may claim your staking yields by clicking the "Claim" button next to each of the nodes you've delegated to. You may claim your yields at anytime there are yields available to be claimed.&#x20;

<figure><img src="../.gitbook/assets/6. claim yields - staker.png" alt=""><figcaption></figcaption></figure>

### 5.  Re-delegate

Sometimes if the validator node you're delegating to is under-performing, shut down, or for whatever reason you no longer wish to delegate to that node anymore, you could shift your delegation to another validator node. This is called re-delegation.&#x20;

On the [staking page of the community site](https://community.taraxa.io/staking), you can see a button called "Shift delegation OUT" next to the validator nodes you have delegated to. This button helps you to move delegation OUT of that particular node and into another one.&#x20;

For example, let's say that a user is no longer happy with the validator node `0xC83e...`, and wants to shift delegation out of it, and INTO the validator node `0x94Ca...`&#x20;

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

The user will then click on the "Shift delegation OUT" button next to the node they're unhappy with, and you'll see a screen that asks them where you want to shift their delegation into. At the top left corner is the validator node to shift delegation OUT from, and at the bottom is a list of validator nodes, from which they'll be able to select one that they'd want to shift the delegation INTO.&#x20;

In this example, they pick the one `0x94Ca...` and click on the "Shift delegation IN" button next to the node.&#x20;

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>



Once the button is clicked, a confirmation screen will pop up that allows the user to specify how many tokens they'd like to shift over.&#x20;

<figure><img src="../.gitbook/assets/image (5) (2) (1).png" alt=""><figcaption></figcaption></figure>

Once the re-delegate button is clicked and the transaction is confirmed, the re-delegation has been completed.&#x20;

Make sure to confirm that the re-delegation has gone through properly, refresh the staking page.&#x20;

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

Here we see that indeed 500k TARA has been moved from validator node `0xC83e...`to `0x94Ca...` :tada:



### 6.  Un-delegate

You may choose to un-delegate your tokens from a validator node at any time, simply select the "Un-delegate" button next to the node.&#x20;

Here are a few things to remember when un-delegating,&#x20;

* Un-delegate initiates a removal of a defined amount of delegated tokens from the validator node
* Once you initiate un-delegation, there's a delay of 700,540 blocks (\~30 days) delay before you can claim your tokens
* If you simply wish to shift delegation from an under-performing node to one that performs better, you should consider using re-delegation which only has a few PBFT block delay (a few seconds)
* You can un-delegate, using the same wallet, from multiple validators simultaneously&#x20;
* You can NOT un-delegate, using the same wallet, from the same validator multiple times - you'd have to either cancel the un-delegation (at the top of the community staking page), or wait till the current un-stake delay has fully elapsed and execute a new un-stake



<figure><img src="../.gitbook/assets/7. undelegate.png" alt=""><figcaption></figcaption></figure>

###

