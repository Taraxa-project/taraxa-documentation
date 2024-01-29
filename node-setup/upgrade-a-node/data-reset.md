---
description: Wipes the node's data and start over with the latest version.
---

# 🔁 Reset Node

### How to reset your node's data

The mainnet as a network will never be reset. However, sometimes your individual node's state may have been corrupted - e.g., you were too late to a major upgrade, then you might want to reset your node and re-index.&#x20;

The testnet is reset pretty frequently. We use the testnet to deploy new features that we'll be stress-testing before making it to the mainnet.&#x20;

{% tabs %}
{% tab title="Windows" %}
Mainnet&#x20;

Download the latest docker-compose file: [https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose\_mainnet/docker-compose.yml](https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose\_mainnet/docker-compose.yml)

```bash
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down -v
docker-compose pull
del config\mainnet.json
docker-compose up -d
docker-compose logs -f// Some code
```



Testnet

Download the latest docker-compose file: [https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose/docker-compose.yml](https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose/docker-compose.yml)

```bash
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down -v
docker-compose pull
del config\testnet.json
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Mac" %}
Mainnet

```bash
cd ~/Desktop/taraxa-ops-master/taraxa_compose
curl -0 https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml > docker-compose-new.yml && mv docker-compose-new.yml docker-compose.yml
docker-compose down -v
docker-compose pull
rm -f config/mainnet.json
docker-compose up -d
docker-compose logs -f
```



Testnet

```bash
cd ~/Desktop/taraxa-ops-master/taraxa_compose
curl -0 https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.yml > docker-compose-new.yml && mv docker-compose-new.yml docker-compose.yml
docker-compose down -v
docker-compose pull
rm -f config/testnet.json
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Linux" %}
Mainnet

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down -v
sudo docker-compose pull
rm -f config/mainnet.json
sudo docker-compose up -d
sudo docker-compose logs -f
```



Testnet

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down -v
sudo docker-compose pull
rm -f config/testnet.json
sudo docker-compose up -d
sudo docker-compose logs -f
```
{% endtab %}
{% endtabs %}

