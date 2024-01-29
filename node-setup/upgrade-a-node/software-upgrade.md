---
description: Upgrade the node to the latest version without erasing any local data.
---

# ⬆ Upgrade Node

### Upgrade your node's software

From time to time we will release new versions of the node software. Try to keep it up to date using the following commands for your host operating system.&#x20;

The difference between Mainnet and Testnet scripts are in the YAML files, please make sure you're following the right instructions for the network your node is on.&#x20;

{% tabs %}
{% tab title="Windows" %}
Mainnet&#x20;

Download the latest docker-compose file: [https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose\_mainnet/docker-compose.yml](https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose\_mainnet/docker-compose.yml)

```bash
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down
docker-compose pull
docker-compose up -d
docker-compose logs -f
```



Testnet

Download the latest docker-compose file: [https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose/docker-compose.yml](https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa\_compose/docker-compose.yml)

```bash
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down
docker-compose pull
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Mac" %}
Mainnet

```bash
cd ~/Desktop/taraxa-ops-master/taraxa_compose
curl -0 https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml > docker-compose-new.yml && mv docker-compose-new.yml docker-compose.yml
docker-compose down
docker-compose pull
docker-compose up -d
docker-compose logs -f
```



Testnet

```bash
cd ~/Desktop/taraxa-ops-master/taraxa_compose
curl -0 https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.yml > docker-compose-new.yml && mv docker-compose-new.yml docker-compose.yml
docker-compose down
docker-compose pull
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Linux" %}
Mainnet

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose_mainnet/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```



Testnet

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```
{% endtab %}
{% endtabs %}







{% hint style="danger" %}
GitHub is blocked in some countries. If you can't run the previous command please refer to the [GitHub is blocked](https://github.com/Taraxa-project/taraxa-documentation/tree/f4ee57d43b23f5ad4a2212fa5ec90254d9181f92/node-setup/testnet\_node\_setup/node-setup/github\_blocked.md) document.
{% endhint %}

{% hint style="info" %}
Sometimes during breaking protocol changes we will advise you to [reset your node's data.](data-reset.md) Don't worry, we will let you know when that is required.
{% endhint %}
