# Software Upgrade

### Upgrade your node's software

From time to time we will release new versions of the node software. Try to keep it up to date using the following commands _for your host operating system_:

{% tabs %}
{% tab title="Windows" %}
```bash
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down
docker-compose pull
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Mac" %}
```bash
cd ~/Desktop/taraxa-ops-master/taraxa_compose
curl -0 https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.yml > docker-compose-new.yml && mv docker-compose-new.yml docker-compose.yml
```

{% hint style="danger" %}
GitHub is blocked in some countries. If you can't run the previous command please refer to the [GitHub is blocked](https://github.com/Taraxa-project/taraxa-documentation/tree/f4ee57d43b23f5ad4a2212fa5ec90254d9181f92/node-setup/testnet_node_setup/node-setup/github_blocked.md) document.
{% endhint %}

```bash
docker-compose down
docker-compose pull
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Linux" %}
From time to time we will release new versions of the node software. Try to keep it up to date using the following commands:

```bash
cd ~/taraxa-ops-master/taraxa_compose
wget -O docker-compose-new.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/taraxa_compose/docker-compose.yml && mv docker-compose-new.yml docker-compose.yml
```

{% hint style="danger" %}
GitHub is blocked in some countries. If you can't run the previous command please refer to the [GitHub is blocked](https://github.com/Taraxa-project/taraxa-documentation/tree/f4ee57d43b23f5ad4a2212fa5ec90254d9181f92/node-setup/testnet_node_setup/node-setup/github_blocked.md) document.
{% endhint %}

```bash
sudo docker-compose down
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Sometimes during breaking protocol changes we will advise you to [reset your node's data.](data-reset.md) Don't worry, we will let you know when that is required.
{% endhint %}

### 

## 

