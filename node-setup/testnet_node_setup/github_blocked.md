---
description: Guide for bypassing blocked GitHub
---

# GitHub is blocked

GitHub is blocked in some countries. To bypass this we have two options:

## 1. VPN Extension

If you have VPN extension in your web browser activate your VPN extension and go to [this link](https://github.com/Taraxa-project/taraxa-ops).

![Download Taraxa Scripts](../../.gitbook/assets/15-download-scripts.png)

Click on "Download ZIP" under the "Code" menu and the download should start.

After the download is complete unzip the file and move the extracted directory to the following location based on your operating system.

For Windows: `Desktop`

For Mac: `Desktop`

For Linux: `Your home directory (~)`

You should now have a directory called `taraxa-ops-master` in the previous locations that contains another directory named `taraxa_compose`. If your OS named the parent directory differently rename it to `taraxa-ops-master`.

Now you can go back to the documentation for your operating system and run the same commands.

## 2. Without Docker Compose

If you still can't access GitHub you can run the Docker image manually without Docker Compose.

### Run node with Docker

The first steps is to create a taraxa directory somewhere on your computer.

For Windows:

```bash
cd .\Desktop\
mkdir taraxa
cd taraxa
mkdir data
mkdir conf
```

For Mac:

```bash
cd ~/Desktop
mkdir -p taraxa/data
mkdir -p taraxa/conf
cd taraxa
```

For Linux:

```bash
cd ~/
mkdir -p taraxa/data
mkdir -p taraxa/conf
cd taraxa
```

Now for creating the config file we have to run the following command:

```text
docker run --rm -v $(pwd):/opt/taraxa_data taraxa/taraxa-node:latest cli config node --network testnet --file /opt/taraxa_data/conf/testnet.json --prop-override db_path:/opt/taraxa_data/data
```

_NOTE: If Linux is complaining about permissions you can prefix these commands with `sudo`_

And now to start the node we can run the following commmands:

```text
docker run -d --name taraxa_compose_node_1 -it -p 10002:10002 -p 10002:10002/udp -p 7777:7777 -p 8777:8777 -v $(pwd):/opt/taraxa_data taraxa/taraxa-node:latest taraxad --conf_taraxa /opt/taraxa_data/conf/testnet.json

docker logs -f taraxa_compose_node_1
```

Now the node should start.

### Update node software

To update the node we can run the following:

```bash
docker rm -f taraxa_compose_node_1
```

OPTIONAL: If there was a protocol upgrade we also have to remove the data in order to re-sync.

For Mac and Linux:

```bash
rm -rf data
```

For Windows:

```bash
deltree /Y data
```

Continued:

```text
docker pull taraxa/taraxa-node:latest
docker run -d --name taraxa_compose_node_1 -it -p 10002:10002 -p 10002:10002/udp -p 7777:7777 -p 8777:8777 -v $(pwd):/opt/taraxa_data taraxa/taraxa-node:latest taraxad --conf_taraxa /opt/taraxa_data/conf/testnet.json
```

