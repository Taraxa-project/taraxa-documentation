# 🛠 Node upgrade & reset

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

Sometimes you need to wipe your node and restart the whole thing, e.g., maybe your state db is corrupted. This is how you'd reset your node.&#x20;

To fully reset a node and remove all of its data (including keys!), here are the commands.&#x20;

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down -v
sudo docker-compose pull
rm -f config/mainnet.json
sudo docker-compose up -d
sudo docker-compose logs -f
```

