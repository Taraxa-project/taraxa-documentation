# ⚙ Set up validator node

## Full Consensus Node

Instructions relating to running a validator node on the Mainnet are mostly identical or highly similar than those for the [Testnet](../node-setup/testnet\_node\_setup/).  Here's how you can install a node on Linux.&#x20;

```bash
mkdir -p mainnet/config
cd mainnet
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml
docker-compose up -d
docker-compose logs
```



## Lite Consensus Node (beta)

You could also choose to run a lite-version of the consensus nodes, with \~90% SSD savings. It operates exactly the same as a full node, but prunes most of the historical states, keeping just a few recent Periods.&#x20;

Please follow the [instructions on light consensus nodes](../node-setup/lite-consensus-node-beta.md#1.-lite-consensus-node-on-the-taraxa-mainnet).&#x20;



