---
description: Join the Taraxa network as a Validator!
---

# 🌱 Become a Validator

## Becoming a Validator on the Mainnet

We've launched our Mainnet network! You can now join the Mainnet Candidate as a validator.&#x20;

To become a validator, you need to do and be aware of the following,&#x20;

1. [Set up a validator node](mainnet-quick-start.md#1.-set-up-a-validator-node)&#x20;
2. [Register your validator node](mainnet-quick-start.md#2.-register-your-validator-node-on-the-community-site-optional) on the community site (optional)&#x20;
3. [Solicit delegation](mainnet-quick-start.md#3.-soliciting-delegation)
4. [Node upgrade](mainnet-quick-start.md#4.-node-upgrade)



## 1.  Set up a Validator Node&#x20;

Instructions relating to running a validator node on the Mainnet are mostly identical or highly similar than those for the [Testnet](../node-setup/testnet\_node\_setup/).  Here's how you can install a node on Linux.&#x20;

```
mkdir -p mainnet/config
cd mainnet
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml
docker-compose up -d
docker-compose logs
```





## 2.  Register your validator node on the community site (optional)

_Registration on the community site is optional._&#x20;

The community site is simply a thin-layer user interface to interact with the on-chain DPoS contract, making it easier for TARA holders to find and delegate to validator nodes.&#x20;

Anyone may interact with that contract at anytime through their own node via RPC calls (instructions coming soon), and anyone can deploy the community site on their own - the site has always been [open source](https://github.com/Taraxa-project/taraxa-platform).&#x20;



### >> Register an account on the community site&#x20;

Navigate to the [community site](http://community.taraxa.io/) and register an account.&#x20;

<figure><img src="../.gitbook/assets/1. register.png" alt=""><figcaption></figcaption></figure>

### >> Pass KYC

To claim rewards (e.g., staking commission, yields) from the community site, you must pass KYC. It is in the [profile section](https://community.taraxa.io/profile).&#x20;

> DISCLAIMER: To comply with recent SEC rulings, United States persons and persons from OFAC-sanctioned regions cannot receive token rewards from running nodes. All participants will be required to pass KYC to receive rewards.

<figure><img src="../.gitbook/assets/2. kyc.png" alt=""><figcaption></figcaption></figure>

### >> Register your validator node&#x20;

Navigate to the [run a node](https://community.taraxa.io/node) section of the community site and select "Register a Mainnet Node".&#x20;

<figure><img src="../.gitbook/assets/3. register a validator.png" alt=""><figcaption></figcaption></figure>

You'll see a node registration prompt asking for several pieces of node-specific information.&#x20;

<figure><img src="../.gitbook/assets/3. enter node details.png" alt=""><figcaption></figcaption></figure>

Here are instructions on how to find the node's,&#x20;

* [Public address](https://docs.taraxa.io/node-setup/node\_address)
* [Proof of ownership](../node-setup/proof\_owership.md)
* [VRF key](../node-setup/vrf\_key.md)

Note that, the container name is different from the testnet. In the mainnet, instead of `taraxa_compose_node_1`, it's `mainnet_node_1`.&#x20;

Per usual this name may be different in different environments, so to be sure you've got the right container name, just execute `docker ps`.&#x20;

### >> Setting the commission

The last entry to registering a node is setting its commission, which is the portion of the staking yield that goes to the node operator. You can enter a range of value between 0 to 100.&#x20;

Here are some [information on commissions](https://docs.taraxa.io/faq/mainnet-candidate#c0e0). This is a purely economic decision on the part of the validator operators, it's advisable to review how much commission other validators are charging first by going to the [delegation section](https://community.taraxa.io/delegation) of the community site.&#x20;

### >> Self-delegation requirement

Once you click "Submit" in the node registration pop-up, the on-chain transaction will require that the operator delegate 1000 TARA to their own validator node - so make sure you have enough in the wallet to complete the on-chain registration of the validator node.&#x20;

This self-delegation requirement is not meant to be a financial burden, but purely to guard against spamming.&#x20;



## 3.  Soliciting Delegation

Each validator node must have a minimum of 500,000 TARA in delegation, otherwise it will not be eligible to participate in consensus. You may delegate this to your own node, or more commonly solicit delegation from the Taraxa community.&#x20;

Here are a few social channels where the Taraxa community congregates, &#x20;

* Taraxa's [Discord server](https://www.taraxa.io/discord)
* Taraxa's [Telegram group](https://www.taraxa.io/tg)
* Taraxa's [official Twitter](https://twitter.com/taraxa\_project)



## 4.  Node Upgrade

The development team will release regular technical updates. To update the node please run the following commands in the `mainnet` directory:

```
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```

