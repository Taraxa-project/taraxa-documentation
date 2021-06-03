---
description: Guide for running the Taraxa Node with Docker on Digital Ocean
---

# Digital Ocean

## 1. Register to Digital Ocean

You can use the following link to get $100 in credits:

[https://m.do.co/c/4143d5ec5500](https://m.do.co/c/4143d5ec5500)

## 2. Create a Personal access token

You can follow this guide to create a personal access token/key:

[https://docs.digitalocean.com/reference/api/create-personal-access-token/](https://docs.digitalocean.com/reference/api/create-personal-access-token/)

Make a note of that key. We will use it in the next step.

## 3. Creating a Taraxa Node

{% hint style="danger" %}
If you are running this on Windows you will first need to install Windows Subsystem for Linux. You can use [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
{% endhint %}

Export your Digital Ocean access token to your environment so that the node creation script can access it without prompting you for it:

```bash
export DIGITALOCEAN_ACCESS_TOKEN=your-token
```

Then you can download and run the node creation script using this command:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/one-click-DO.sh)"
```

Now you should see a new droplet in your Digital Ocean account and you should receive an email with the login details.

_NOTE: It takes a few minutes after the droplet starts to install the Taraxa Node software._

## 4. Check the logs

You can use the following commands to check if the node is up and running:

```bash
sudo docker ps

sudo docker logs -f taraxa_compose_node_1
```

