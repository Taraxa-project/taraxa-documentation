---
description: Light-weight non-archival consensus node
---

# 🪶 Lite Consensus Node (beta)

If you don't wish to run a full archival node, you can choose to run a light-weight consensus node that has \~90% savings in disk space requirements. The Lite Consensus Node achieves the disk space savings by pruning the state DB and only keeping a set of the most recent Periods.&#x20;

> Lite node requires pruning, and you need to restart your lite node for pruning to start. It's recommended to set up a script to periodically restart the lite node to keep disk space usage to a mininum.&#x20;

Here are the [hardware requirements for a lite consensus node](../become-a-validator/consensus-node-hardware-requirements.md).&#x20;

Here's how you can set up a Lite Consensus Node.&#x20;



## 1.  Lite Consensus Node on the Taraxa Mainnet&#x20;

### 1.1  Set up a Lite Consensus Node on the Mainnet from scratch&#x20;

```bash
mkdir -p mainnet/config
cd mainnet
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.light.yml -O docker-compose.yml
docker-compose up -d
docker-compose logs
```



### 1.2  Turn an existing full node into a Lite Consensus Node on the Mainnet

```bash
cd mainnet
docker-compose down
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.light.yml -O docker-compose.yml
docker-compose up -d
docker-compose logs
```



### 1.3  Syncing from snapshot

Because the Taraxa network state has gotten very large, it takes quite a long time to sync. An alternative is to sync from a snapshot, which will drastically cut down on the amount of syncing time and can get  your node up & running much more quickly.&#x20;

Please read the guide on how to [sync from snapshot](syncing-from-snapshot.md), and due to the increased state, pruning can take a very long time as well, so please also be sure to read about the [lite node performance considerations](https://taraxa.gitbook.io/taraxa-network/node-setup/syncing-from-snapshot#light-node-performance-considerations) section on tactics to avoid pruning altogether.&#x20;







## 2.  Lite Consensus Node on the Taraxa Testnet &#x20;

### 2.1  Set up a Lite Consensus Node on the Testnet from scratch&#x20;

```bash
mkdir -p testnet/config
cd testnet
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.light.yml -O docker-compose.yml
docker-compose up -d
docker-compose logs
```



### 2.2  Turn an existing full node into a Lite Consensus Node on the Testnet

```bash
cd testnet
docker-compose down
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.light.yml -O docker-compose.yml
docker-compose up -d
docker-compose logs
```





## 3.  Node upgrade & reset &#x20;

### 3.1  Node Upgrade&#x20;

```bash
cd mainnet
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.light.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```

### 3.2  Node Reset

```bash
cd mainnet
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.light.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down -v
sudo docker-compose pull
rm -f config/mainnet.json
sudo docker-compose up -d
sudo docker-compose logs -f
```

