---
description: Guide for getting your node's public address
---

# Getting the node's public address

To find out your node's public address you can run the following command while the node is running:

```
docker exec taraxa_compose_node_1 ./cli/taraxa account --file /opt/taraxa_data/conf/testnet.json
```

You should see an output similar to the following:
```
address: 0x949367e6a7ce6e838e13e3b897d431102a6d4d12
address w/ checksum: 0x949367E6a7CE6e838E13E3B897d431102a6d4D12
public key: 0xeea99819bad45c93292a200b085eb809bbdecb8521a4baca777e06811362fb2d9b92334db0793b473cfd5ccd1cbaa8a5fffea6f09baf308629866f6828677d91
private key: 0x7be85127ed7934374019f34efc714f62ec6d3d45776a8a6137720a57e96c4140
```

The public address is the first field in the output. In this case `0x949367e6a7ce6e838e13e3b897d431102a6d4d12`

{% hint style="danger" %}
Don't share your private key or config file with others.
They can be used to take control of your wallet.

We will never ask you to provide any sensitive information.
{% endhint %}