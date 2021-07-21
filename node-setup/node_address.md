---
description: Guide for getting your node's public address
---

# Find Node's Public Address

To find out your node's public address you can run the following command in a new terminal window while the node is running:

```text
docker exec taraxa_compose_node_1 cat /opt/taraxa_data/conf/wallet.json
```

You should see an output similar to the following:

```text
{
	"node_address" : "49a303283915277ec9c8cb87f50368d2be41f38b",
	"node_public" : "af27e45a6e234f28e5a37fb482de35062b2088975edf98ec21f7e0eb798faf0439175b8f0f3f501fd60d160dbb86e6f7082658baa659c5fdaafe49065f444fb9",
	"node_secret" : "d62a1297fe2fcd0fd2e531be2028897071a3b3da0608a04ca3b97d6495964c0f",
	"vrf_public" : "a295f401c788316268de7b768c97a59c4f408eaa91dc723af6e4111cec106717",
	"vrf_secret" : "50d9ea4b7f92ac3632434b3334fe7a52793086b9b62014d0517dca0e369336bea295f401c788316268de7b768c97a59c4f408eaa91dc723af6e4111cec106717"
}
```

The public address is the first field in the output. In this case `49a303283915277ec9c8cb87f50368d2be41f38b`

When registering this address on our community account you should add a `0x` prefix before it. Example:

`0x49a303283915277ec9c8cb87f50368d2be41f38b`

{% hint style="danger" %}
Don't share your private key or config file with others. They can be used to take control of your wallet.

We will never ask you to provide any sensitive information.
{% endhint %}

