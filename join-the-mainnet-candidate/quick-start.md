# Quick start

We've launched our Mainnet Candidate network!

The vast majority of instructions relating to the node are identical or highly similar than those for the [Testnet](broken-reference). More complete instructions & resources are coming soon, here are some quick technical instructions on how to get started right away.&#x20;



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
docker exec mainnet_node_1 taraxa-sign sign --wallet /opt/taraxa_data/conf/wallet.jsonPer usual this name may be different in different environments, so to be sure you've got the right container name, just execute docker ps. 
```

Per usual this name may be different in different environments, so to be sure you've got the right container name, just execute `docker ps.`&#x20;



### Upgrade & Reset&#x20;

We'll publish upgrade and reset instructions soon.&#x20;

