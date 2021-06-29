---
description: Guide for running the Taraxa Node with Docker on Vultr
---

# Vultr

## 1. Register to Vultr

You can use the following link to get $100 to test out their platform:

[https://www.vultr.com/?ref=8908059-6G](https://www.vultr.com/?ref=8908059-6G)

## 2. Create a Personal access token

You can find a personal access token on this page:

[Vultr API KEY](https://my.vultr.com/settings/#settingsapi)

Make a note of that key. We will use it in the next step.

## 3. Creating a Taraxa Node

{% hint style="danger" %}
If you are running this on Windows you will first need to install Windows Subsystem for Linux. You can use [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
{% endhint %}

Export your Vultr access token to your environment so that the node creation script can access it without prompting you for it:

```bash
export VULTR_API_KEY=your_api_key
```

Then you can download and run the node creation script using this command:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/one-click-Vultr.sh)"
```

Now you should see a new droplet in your Vultr account and you should receive an email with the login details.

_NOTE: It takes a few minutes after the droplet starts to install the Taraxa Node software._

## 4. Check the logs

You can use the following commands to check if the node is up and running:

```bash
sudo docker ps

sudo docker logs -f taraxa_compose_node_1
```

