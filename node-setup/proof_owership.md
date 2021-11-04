---
description: Guide for getting proof of owership for node
---

# Get Proof of Owership via CLI

To find out your node's public address you can run the following command in a new terminal window while the node is running:

```text
docker exec taraxa_compose-node-1 taraxa-sign sign --wallet /opt/taraxa_data/conf/wallet.json
```

You should see an output similar to the following:

```text
0xXXXXXXXXXX
```