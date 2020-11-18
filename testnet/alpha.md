---
description: Taraxa Alpha Testnet
---



# Block Explorer

 Check out our alpha testnet via the [Taraxa Block Explorer](https://explorer.testnet.taraxa.io/).

![](../.gitbook/assets/image%20%281%29.png)

<br>

# Ethereum compatible JSON RPC interface

To connect to the Taraxa Alpha Testnet, use the following options:
1. https: https://rpc.testnet.taraxa.io
2. websocket: wss://ws.rpc.testnet.taraxa.io

<br>

# Creating a wallet

- [Taraxa Sandbox](https://sandbox.testnet.taraxa.io) - For the testnet, Taraxa provides a web-based wallet called the sandbox.  The sandbox wallet provides 10 addresses that can be used for sending/receiving TARA, contract deployment, and staking.
- [MetaMask](https://metamask.io/) - MetaMask browser extention also works with Taraxa Alpha Testnet. Just use custom RPC, and set the token name to TARA, and use the block explorer above.

<br>


# Using the Faucet

Taraxa testnet includes a faucet. The faucet will send small amount of testnet TARA every few seconds, to the last 5000 addresses that were added.


<br>

# Development

### Libraries

- Web3 - Because of the Ethereum-compatible RPC interface, most Ethereum libraries like Web3.js, Web3.py, Ethers.js, etc will work for sending and receiving TARA and interacting with contracts.
- [TaraxaJS](https://github.com/Taraxa-project/taraxa-js) - To access custom RPC functionality using JavaScript, try TaraxaJS (based on Axios)
- [TaraxaPy](https://github.com/Taraxa-project/taraxa-py) - To access custom RPC functionality using Python, try TaraxaPy