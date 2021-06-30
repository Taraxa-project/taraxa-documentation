---
description: Guide for running the Taraxa Node with Docker on Hetzner
---

# Hetzner

## 1. Register to Hetzner

You can use the following link to get Euro 20 to test out Hetzner Cloud:

[https://hetzner.cloud/?ref=c0rOjmxysd7i](https://hetzner.cloud/?ref=c0rOjmxysd7i)

## 2. Create a Project API access token

First, create a project in the [Hetnzer Cloud Console](https://console.hetzner.cloud/)
Then select the project and create an API access token in the Security menu under API Tokens tab. 

Make a note of that key. We will use it in the next step.

## 3. Creating a Taraxa Node

{% hint style="danger" %}
If you are running this on Windows you will first need to install Windows Subsystem for Linux. You can use [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
{% endhint %}

Export your Hetzner Cloud access token to your environment so that the node creation script can access it without prompting you for it:

```bash
export HCLOUD_TOKEN=your_api_key
```

Then you can download and run the node creation script using this command:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/one-click-Hetzner.sh)"
```

Now you should see a new server in your Hetzner Cloud Console and you should receive an email with the login details.

_NOTE: It takes a few minutes after the droplet starts to install the Taraxa Node software._

## 4. Check the logs

You can use the following commands inside the created server to check if the node is up and running:

```bash
sudo docker ps

sudo docker logs -f taraxa_compose_node_1
```

