---
description: A guide to all the ways you can run  a node in a Taraxa public testnet
---

# Node Setup

## Super Easy To Run a Node

You can either run  a node:

* Via deploy to a host in the cloud
* On  any machine with Docker installed

## One Liner Deploy Script To The Cloud

{% hint style="info" %}
### Requirements

* A Mac or Linux shell environment 
* curl with ssl support
{% endhint %}

### 

### Digital Ocean

{% hint style="info" %}
**Prerequisites**: Follow these instructions to [signup for a Digital Ocean account](https://www.digitalocean.com/docs/getting-started/sign-up/). You need a Digital Ocean [API token](https://www.digitalocean.com/docs/apis-clis/api/create-personal-access-token/). You may export your token as the env var `DIGITALOCEAN_ACCESS_TOKEN` or simply provide it when script asks for it.
{% endhint %}

#### **One Liner Install For Digital  Ocean**

```
bash -c "$(curl -fsSL https://taraxa.io/one-click-DO.sh)"
```

{% hint style="success" %}
Each run of this script will generate a Droplet on Digital Ocean running a Taraxa node. You will receive an email to the address used in your Digital Ocean registration with login credentials. The Taraxa node runs as a docker image.

 
{% endhint %}

## Running using Docker Compose

**Step 1:** Download the [docker-compose.yml](https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/docker-compose.yml) file to your machine that has Docker installed.

**Step 2:** Start the node

```bash
docker-compose up
```

{% hint style="info" %}
You can also start the node as  a detached background service:

```
docker-compose up -d
```

To view  the logs you then use the docker logs command:

```
docker logs taraxa-node -f
```
{% endhint %}

