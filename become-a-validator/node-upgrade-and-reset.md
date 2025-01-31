# 🛠️ Node upgrade & reset

### The instructions below are for Full Taraxa nodes. Here are the [instructions for Lite Taraxa nodes](../node-setup/lite-consensus-node-beta.md).&#x20;

##

## 1.  Node Upgrade

The development team will release regular technical updates. To update the node please run the following commands in the `mainnet` directory:

```bash
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```



## 2.  Node Reset

The mainnet as a network will never be reset. However, sometimes your individual node's state may have been corrupted - e.g., you were too late to a major upgrade, then you might want to reset your node and re-index. &#x20;

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down -v
sudo docker-compose pull
rm -f config/mainnet.json
sudo docker-compose up -d
sudo docker-compose logs -f
```

