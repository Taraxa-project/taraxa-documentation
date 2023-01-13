---
description: Join the Taraxa network as a Validator!
---

# 🌱 Become a Validator

We've launched our Mainnet Candidate network! You can now join the Mainnet Candidate as a validator.&#x20;

Instructions relating to running a validator node are mostly identical or highly similar than those for the [Testnet](broken-reference). More complete instructions & resources are coming soon, here are some quick technical instructions on how to get started right away.&#x20;



### Install a node on the mainnet candidate on Linux

Node operations are basically the same as those on the Testnet, here's how you can install a node on Linux.&#x20;

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

It's the same command as the one on testnet, except the container name is different. Instead of `taraxa_compose_node_1`, it's `mainnet_node_1`.&#x20;

```
docker exec mainnet_node_1 cat /opt/taraxa_data/conf/wallet.json
```

Per usual this name may be different in different environments, so to be sure you've got the right container name, just execute `docker ps.`&#x20;

###

### Get node proof of ownership&#x20;

It's the same command as the one on testnet, except the container name is different. Instead of `taraxa_compose_node_1`, it's `mainnet_node_1`.&#x20;

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

