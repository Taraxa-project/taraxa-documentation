---
description: Light-weight non-archival consensus node
---

# 🪶 Lite Consensus Node (beta)

If you don't wish to run a full archival node, you can choose to run a light-weight consensus node that has \~90% savings in disk space requirements. The Lite Consensus Node achieves the disk space savings by pruning the state DB and only keeping a set of the most recent Periods.&#x20;

Here's how Taraxa's Lite Consensus Node stacks up against other PoS Layer-1s' consensus nodes.&#x20;

<figure><img src="../.gitbook/assets/Picture1 (1) (1).png" alt=""><figcaption></figcaption></figure>

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





##

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





