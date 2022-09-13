---
description: >-
  This document describes how to add Taraxa's native token, TARA, to a crypto
  exchange.
---

# Exchange Integration

### Node Setup

Taraxa Nodes are of three types:

```
1. Boot Nodes
2. Consensus Nodes
3. RPC Nodes
```

To connect to the Taraxa chain you can use either a **Consensus Node** or a **RPC Node**.

**Boot Nodes** don't have a RPC interface.

**Consensus Nodes** also participate in securing the network and need stake so we recommend setting up a couple of **RPC Nodes**.

#### Setting up your own node

The simplest way to set up a Taraxa Node inside your own infrastructure is to use the official [Docker Images](https://hub.docker.com/r/taraxa/taraxa-node/tags?page=1\&name=1.0) we provide for the mainnet version. Docker will also make sure that the node gets restarted if it crashes.

We highly recommend setting up more than one instance of the Taraxa Node for reliability.

#### Using our RPC endpoint

For testing purposes or a small number of requests you can also use our RPC endpoint:

[https://rpc.mainnet.taraxa.io](https://rpc.mainnet.taraxa.io)

### Interacting with the JSON-RPC endpoint

The Taraxa Chain is compatible with the Ethereum chain. That means that most default Ethereum RPC requests will work on Taraxa.

You can follow the Ethereum JSON-RPC documentation here:

[https://ethereum.org/en/developers/docs/apis/json-rpc/](https://ethereum.org/en/developers/docs/apis/json-rpc/)

The compatibility with Ethereum means that almost all tools from the Ethereum ecosystem work with Taraxa. You can use, for example, [Web3.js](https://web3js.org/), [ethers.js](https://docs.ethers.io/v5/) and [Web3.py](https://web3py.readthedocs.io/en/latest/) to connect to and interact with the Taraxa Network.

### Setting up Deposit Accounts

Setting up accounts for each user is pretty simple. You can use a variety of tools to generate the accounts. Depending on your security requirements, you may also want to use encrypted wallets / keyfiles.

{% tabs %}
{% tab title="Taraxad CLI" %}
```bash
$ taraxad --command account
"node_secret" : "907d6f3e84d54f069c98e082de4e0cad41d11b54bc722fd9463ab5cd8010792f"
"node_public" : "8a4a53f93004208866b23f4c324ea30b869abc718f0948c33bb6ff5bc4d06c5fb447fa320a57698ce4960f561a7dea2f0668f1b62b6e87539189d29cce917f65"
"node_address" : "b9b8648d29427494e39bb6ac2a3f221b4c14c8d2"
```
{% endtab %}

{% tab title="Web3.js" %}
```javascript
const Web3 = require('web3');
const main = () => {
    const web3 = new Web3(new Web3.providers.HttpProvider('https://rpc.mainnet.taraxa.io'));
    let { address, privateKey } = web3.eth.accounts.create(web3.utils.randomHex(32));
    console.log({
        node_address: address,
        node_secret: privateKey
    });
};
main();
```
{% endtab %}

{% tab title="ethers.js" %}
```javascript
const ethers = require('ethers');
const main = () => {
    const wallet = ethers.Wallet.createRandom();
    console.log({
        node_address: wallet.address,
        node_secret: wallet.privateKey,
    });
};
main();
```
{% endtab %}
{% endtabs %}



### Checking Deposits

Once you have a list of accounts that you need to watch, we can have a service that parses each block and checks for deposits to those addresses.

#### Example using ethers.js

```java
const { ethers } = require('ethers');
const { Level } = require('level');

const watch = [
  '0x44be58f80cdac2624c715a258bc20014293e1f1a',
  '0x2484d53cb5c6510eb1ef0e115fae17c9c6ae5610',
  '0x2bd434213eff7778ea7f93ab531b4b9bcaa5db5d',
  '0xb5da2ba8e72533396fd8af2462354b05640e29b7'
].map(address => ethers.utils.getAddress(address));

const main = async () => {
  const db = new Level('db', { valueEncoding: 'json' });
  const provider = new ethers.providers.JsonRpcProvider('https://rpc.mainnet.taraxa.io');

  provider.on('block', async (newBlockNumber) => {
    console.group(`Scanning new block #${newBlockNumber}...`);
    const { transactions } = await provider.getBlockWithTransactions(newBlockNumber);
    for (const transaction of transactions) {
      const from = ethers.utils.getAddress(transaction.from);
      const to = ethers.utils.getAddress(transaction.to);

      if (!watch.includes(from) && !watch.includes(to)) {
        continue;
      }

      const value = transaction.value.toString();

      await db.put(`transaction-${transaction.hash}`, {
        from,
        to,
        value
      });

      console.info(`- saved transaction ${transaction.hash}, from: ${from}, to: ${to}, value: ${value}`);
    }
    console.groupEnd();
  });
};

main();
```
