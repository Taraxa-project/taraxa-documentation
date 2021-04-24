---
description: Guide for running the Taraxa Node with Docker on Linux
---

# Linux

## 1. Install Docker

Open a terminal window and run the following commands to install Docker:

```bash
wget -O get-docker.sh https://get.docker.com 
sudo sh get-docker.sh
sudo apt install -y docker-compose
rm -f get-docker.sh
```

![Install Docker](../../.gitbook/assets/1-install.png)

## 2. Download the Taraxa Docker Compose File

```bash
cd ~/Desktop
mkdir taraxa
cd taraxa
wget -O docker-compose.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/docker-compose.yml
```

![Download Scripts](../../.gitbook/assets/2-scripts.png)

## 3. Start the Taraxa Node

```bash
cd ~/Desktop/taraxa
sudo docker-compose up
```

![Start Node](../../.gitbook/assets/3-docker-start.png)

The node will start after Docker pulls the latest Taraxa Node image.

![Start Node](../../.gitbook/assets/4-taraxa.png)

## 4. Update the Taraxa Node

From time to time we will release new versions of the node software. Try to keep it up to date using the following commands:

```bash
cd ~/Desktop/taraxa
wget -O docker-compose.yml https://raw.githubusercontent.com/Taraxa-project/taraxa-ops/master/scripts/docker-compose.yml
sudo docker-compose stop
sudo docker-compose rm -f
sudo docker-compose pull
sudo docker-compose up
```

