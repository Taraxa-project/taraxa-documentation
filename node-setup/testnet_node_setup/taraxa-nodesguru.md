---
Description: Guide for running the Taraxa Node with Docker on Vscale/Vultr/DigitalOcean/Webtropia/Contabo platforms.
---

# Vscale

## 1. Register to Vscale

[https://vscale.io/](Vscale.io)

## 2. Create a server

Click "Create Server", choose wanted configuration (4vCPU and 6GB RAM should be enough), login with Termius/PuTTY/MobaXTerm/etc.

## 3. Installing a Taraxa Node

```wget -q -O taraxa.sh https://api.nodes.guru/taraxa.sh && chmod +x taraxa.sh && sudo /bin/bash taraxa.sh```

Choose you wanted option (for example option 1 – simply installing the node) and wait for installation to complete.

## 4. Check the logs

You can use the following commands to check if the node is up and running:

```bash
sudo docker ps

sudo docker logs -f taraxa_compose_node_1
```
