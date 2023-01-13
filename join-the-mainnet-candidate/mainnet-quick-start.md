---
description: Join the Taraxa network as a Validator!
---

# 🌱 Become a Validator

## Becoming a Validator on the Mainnet Candidate

We've launched our Mainnet Candidate network! You can now join the Mainnet Candidate as a validator.&#x20;

To become a validator, you need to do the following,&#x20;

1. Set up a validator node&#x20;
2. Register your validator node on the community site&#x20;
3. Solicit delegation from fellow stakers in Taraxa's online communities, or delegate your own tokens&#x20;
4. Check your node's status on the explorer&#x20;



## 1.  Set up a Validator Node&#x20;

Instructions relating to running a validator node on the Mainnet Candidate are mostly identical or highly similar than those for the [Testnet](../node-setup/testnet\_node\_setup/). More complete instructions & resources are coming soon, here are some quick technical instructions on how to get started right away.&#x20;

Here are some quick steps to get you started right away.&#x20;

###

### Install a node on the mainnet candidate on Linux

Node operations are basically the same as those on the [Testnet](../node-setup/testnet\_node\_setup/linux.md), here's how you can install a node on Linux.&#x20;

```
mkdir -p mainnet/config
cd mainnet
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml
docker-compose up -d
docker-compose logs
```

More instructions and scripts for other environments coming soon.&#x20;

###

### Find node's public address

It's the same command as the one on [Testnet](../node-setup/node\_address.md), except the container name is different. Instead of `taraxa_compose_node_1`, it's `mainnet_node_1`.&#x20;

```
docker exec mainnet_node_1 cat /opt/taraxa_data/conf/wallet.json
```

Per usual this name may be different in different environments, so to be sure you've got the right container name, just execute `docker ps.`&#x20;

###

### Get node proof of ownership&#x20;

It's the same command as the one on [Testnet](../node-setup/proof\_owership.md), except the container name is different. Instead of `taraxa_compose_node_1`, it's `mainnet_node_1`.&#x20;

```
docker exec mainnet_node_1 taraxa-sign sign --wallet /opt/taraxa_data/conf/wallet.json
```

Per usual this name may be different in different environments, so to be sure you've got the right container name, just execute `docker ps`



### Upgrade&#x20;

To update the node please run the following commands in the `mainnet` directory:

```
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```



## 2.  Register your validator node on the community site&#x20;

Here is a step-by-step guide on how to register your node on the community site,&#x20;

{% embed url="https://medium.com/taraxa-project/how-to-participate-in-taraxas-mainnet-candidate-a-step-by-step-guide-fb0c0f6ad71f" %}

A few key things to note,&#x20;

* Each validator node must have a minimum of 500,000 TARA in delegation, otherwise it will not be eligible to participate in consensus&#x20;
* Each validator node can have up to 80,000,000 TARA in delegation&#x20;
* Commissions like all rewards are awarded monthly, with cutoff at the 15th of each month, and rewards unlocked at \~20th of each month&#x20;



## 3.  Soliciting Delegation

As a validator, there's no self-delegation requirement, but it's often the easiest way to get started since the minimum threshold of 500,000 TARA delegation is relatively low.&#x20;

Validators often solicit delegation by advertising their nodes in our online communities, such as,&#x20;

* Taraxa's [Discord server](https://www.taraxa.io/discord)
* Taraxa's [Telegram group](https://www.taraxa.io/tg)
* Taraxa's [official Twitter](https://twitter.com/taraxa\_project)



## 4.  Check Your Node's Status&#x20;

Once you're up and running, you can check out your node's rankings in the [block production node list](https://explorer.mainnet.taraxa.io/nodes) on the explorer.&#x20;

