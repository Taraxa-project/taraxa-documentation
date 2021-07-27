---
description: Guide for running the Taraxa Node with Docker on Google Cloud
---

# Google Cloud

## 1. Create a Google Cloud account

Go to [http://cloud.google.com] and sign up. You can use your existing Google account. If you have not used Google Cloud before, you get $300 worth of credits for 90 days. You need to fill in your billing details to be able to run a node.

Use [http://console.cloud.google.com] to manage all your services. The Console can be a bit hard to navigate so it's a good idea to take a moment to familiarize yourself with the layout before proceeding. 

## 2. Check your Billing Details

To run a node in Google Cloud, make sure you have a billing account set up. Using the left menu navigate to Billing and you should see a table with a billing account name and id and some usage details.

## 3. Create the node

{% hint style="danger" %}
If you are running this on Windows you will first need to install Windows Subsystem for Linux. You can use [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
{% endhint %}

Download the node install script like so:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/one-click-GC.sh)"
```

Before running the script, if you have already set up a Google Cloud project you would like to use, you can use an environment variable USE_PROJECT_ID and provide the project's id there.

```bash
export USE_PROJECT_ID=<projects-id>
```

You should get a Google Cloud login window in your browser after running the script. Login to proceed and click Allow when prompted.

The script will run for a while and will set you up with a new project consisting of a  Compute Engine VM instance in random region, with proper firewall.

There might be a few errors regarding component updates - you can ignore them if running the script in Fedora/Debian-based Linux - these are related to manual installation procedure in other distros/macOS. If there are critical errors, the script will exit.

If successful, you should see some instructions for login. You should use the gcloud method first to generate ssh keys.

If you cannot run gcloud from terminal, try <HOME>/google-cloud-sdk/bin/gcloud - in distros where a package manager is not utilized (also macOS), the gcloud SDK is installed manually there. You can add the directory to your path for easier access (or run install.sh in <HOME>/google-cloud-sdk/)

Login via gcloud

```bash
gcloud compute ssh <compute-engine-id>
```

Login via ssh

```bash
ssh -i ~/.ssh/google_compute_engine <your-nodes-ip>
```

## 4. Check your node

```bash
sudo docker ps
```

## 5. Further tweaks

The node is running under root account.  You might want to change that for easier access and security reasons.  To do so, first, set the root password.

```bash
sudo passwd root
```

Now you can change into root.  Make note of your current user before with whoami.

```bash
whoami
su
```

If you want to continue as is, all good. Save your root password and your done.  If you'd rather move your node under your account, read on.

Change into root home and move your node to your personal home

```bash
cd /root
cd ./taraxa-ops/taraxa_compose
docker-compose down
cd /root
mv -R taraxa-ops /home/<your-user-account>
exit
```

Once back in your user account, start the node

```bash
cd ~/taraxa-ops/taraxa_compose
sudo docker-compose up -d
```

You should be good to go!
