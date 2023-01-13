---
description: Wipes the node's data and start over with the latest version.
---

# 🔁 Reset Node

### How to reset your node's data

During the testing period, we will also make changes on the protocol level and you will have to re-sync all the data. Don't worry, we will let you know. To remove the current data and do a full re-sync you have to run the following commands:

{% tabs %}
{% tab title="Windows" %}
You need to download the latest `docker-compose.yml` file from our Github repo: [https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose/docker-compose.yml](https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose/docker-compose.yml)

```
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down -v
docker-compose pull
del config\testnet.json
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Mac" %}
```
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
```
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

### Checking that the reset worked
