# ⚙ Set up validator node

Instructions relating to running a validator node on the Mainnet are mostly identical or highly similar than those for the [Testnet](../node-setup/testnet\_node\_setup/).  Here's how you can install a node on Linux.&#x20;

```bash
mkdir -p mainnet/config
cd mainnet
wget https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml
docker-compose up -d
docker-compose logs
```

