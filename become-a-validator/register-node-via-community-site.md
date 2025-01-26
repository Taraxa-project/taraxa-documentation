# 🚩 Register node via community site

> To comply with recent SEC rulings, United States persons and persons from OFAC-sanctioned regions cannot receive token rewards from running nodes. All participants will be required to pass KYC to receive rewards.

You don't, however need to use the community site. You may [register a node by directly interacting with the on-chain DPoS contract](register-node-directly-on-chain.md).&#x20;



If you still wish to use the community site, please follow the steps below.&#x20;



### 0.  IMPORTANT: wallet used to register a node is the owner of that node

Validator node registration is an on-chain transaction. The wallet you use to register a node is the "owner" of that node. This means once a node is registered, the "owner wallet" is now required to,&#x20;

* Change the validator node's commission rate
* Claim commission rewards earned by the validator node

A single owner wallet can register multiple validator nodes and become their owner, this makes it easy to manage multiple validator nodes in aggregate.&#x20;

**Please safeguard your validator nodes' owner wallet!**&#x20;



### 1.  Register an account on the community site&#x20;

Navigate to the [community site](http://community.taraxa.io/) and register an account.&#x20;

<figure><img src="../.gitbook/assets/1. register.png" alt=""><figcaption></figcaption></figure>

### 2.  Pass KYC

To claim rewards (e.g., staking commission, yields) from the community site, you must pass KYC. It is in the [profile section](https://community.taraxa.io/profile).&#x20;

_A reminder, you can skip the community site and directly_ [_register your node on-chain by interacting with the DPoS contract_](register-node-directly-on-chain.md)_._&#x20;

<figure><img src="../.gitbook/assets/2. kyc.png" alt=""><figcaption></figcaption></figure>

### 3.  Register your validator node&#x20;

Navigate to the [run a node](https://community.taraxa.io/node) section of the community site and select "Register a Mainnet Node".&#x20;

<figure><img src="../.gitbook/assets/3. register a validator.png" alt=""><figcaption></figcaption></figure>

You'll see a node registration prompt asking for several pieces of node-specific information.&#x20;

<figure><img src="../.gitbook/assets/3. enter node details.png" alt=""><figcaption></figcaption></figure>

Here are instructions on how to find the node's,&#x20;

* [Public address](https://docs.taraxa.io/node-setup/node\_address)
* [Proof of ownership](../node-setup/proof\_owership.md)
* [VRF key](../node-setup/vrf\_key.md)

Note that, the container name is different from the testnet. In the mainnet, instead of `taraxa_compose_node_1`, it's `mainnet_node_1`.&#x20;

Also note that Public address, Proof of ownership, and VRF Key need to start with `0x`. You must manually prepend `0x` to each value.

Per usual this name may be different in different environments, so to be sure you've got the right container name, just execute `docker ps`.&#x20;

### 4.  Setting the commission

The last entry to registering a node is setting its commission, which is the portion of the staking yield that goes to the node operator. You can enter a range of value between 0 to 100.&#x20;

Here are some [information on commissions](https://docs.taraxa.io/faq/mainnet-candidate#c0e0). This is a purely economic decision on the part of the validator operators, it's advisable to review how much commission other validators are charging first by going to the [delegation section](https://community.taraxa.io/delegation) of the community site.&#x20;

### 5.  Self-delegation requirement

Once you click "Submit" in the node registration pop-up, the on-chain transaction will require that the operator delegate 1000 TARA to their own validator node - so make sure you have enough in the wallet to complete the on-chain registration of the validator node.&#x20;

This self-delegation requirement is not meant to be a financial burden, but purely to guard against spamming.&#x20;
