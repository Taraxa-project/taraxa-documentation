---
description: A guide to all the ways you can run  a node in a Taraxa public testnet
---

# Node Setup

### Requirements

* A Mac or Linux shell environment 
* curl with ssl support

## One Liner Deploy Script

### 

### Digital Ocean

#### Pre-requisite Step A: Create a Digital Ocean Account <a id="pre-requisite-step-a-create-a-digital-ocean-account"></a>

Follow these instructions to [signup for a Digital Ocean account](https://www.digitalocean.com/docs/getting-started/sign-up/)

#### Pre-requisite Step B: Generate an API Key <a id="pre-requisite-step-b-generate-an-api-key"></a>

You need a Digital Ocean API token. Follow [here](https://www.digitalocean.com/docs/api/create-personal-access-token/) to get it.

You may export your token as the env var `DIGITALOCEAN_ACCESS_TOKEN` or simply provide it when script asks for it.

**One Liner Install For Digital  Ocean**

```
bash -c "$(curl -fsSL https://taraxa.io/one-click-DO.sh)"
```

{% hint style="info" %}
 Each run of this script will generate a Droplet on Digital Ocean running a Taraxa node. You will receive an email to the address used in your Digital Ocean registration with login credentials. The Taraxa node runs as a docker image, and the script on the instance will contact the Taraxa faucet to request coins to be sent to your node.
{% endhint %}



