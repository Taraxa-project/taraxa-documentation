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

### 5.  Un-delegate

You may choose to un-delegate your tokens from a validator node at any time, simply select the "Un-delegate" button next to the node.&#x20;

Note that there is an \~30 day delay between when you request an un-delegation and when you actually receive the tokens.&#x20;



<figure><img src="../.gitbook/assets/7. undelegate.png" alt=""><figcaption></figcaption></figure>

### 6.  Re-delegate (UI coming soon)

There's also a built-in function on the on-chain DPoS contract to switch nodes for your delegation, which only has a 5-block delay (< 20 seconds). This functionality exists but has not yet bee incorporated into the community site's UI, it's coming soon!&#x20;

In the meantime you can always [access the re-delegate and all other DPoS contract functions directly on-chain](staking-directly-on-chain.md).&#x20;
