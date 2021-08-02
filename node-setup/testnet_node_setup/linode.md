---
description: Guide for running the Taraxa Node with Docker on Linode
---

# Linode

## 1. Register to Scaleway

You can use the following link to get $100 to test out their platform:

[https://www.linode.com?r=](https://www.linode.com?r=)

## 2. Create a API Token for Taraxa

You can create a API Token on this page:

[https://cloud.linode.com/profile/tokens](https://cloud.linode.com/profile/tokens)

Make a note of that key. We will use it in the next step.

_Note: If you are not sure which permissions need to be checked, you can assign all permissions._

## 3. Creating a Taraxa Node

{% hint style="danger" %}
If you are running this on Windows you will first need to install Windows Subsystem for Linux. You can use [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
{% endhint %}

Then you can download and run the node creation script using this command:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/one-click-Linode.sh)"
```

Now you should see a new droplet in your Linode account.

_NOTE: It takes a few minutes after the droplet starts to install the Taraxa Node software._

## 4. Connect to your instance

### 4.1 Using password

You can find the password in the log output by the script. It is randomly generated and a 12-digit password.

### 4.2 Using SSH key pair

* You can find your SSH public key on this page: [https://cloud.linode.com/profile/keys](https://cloud.linode.com/profile/keys).
* And you can find the new public key and private key in this directory: `~/.ssh/`.

  ```text
  ls -al .ssh/ | grep "taraxa"
  ```



Next, you can login your instance.

## 5. Check the logs

You can use the following commands to check if the node is up and running:

```bash
sudo docker ps

sudo docker logs -f taraxa_compose_node_1
```
