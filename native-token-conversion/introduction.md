---
description: What is the conversion and how does it work?
---

# 💡 Introduction

## What is the Native Token Conversion?&#x20;

As of this writing, the Taraxa token is still an [ERC-20 contract](https://etherscan.io/address/0xf001937650bb4f62b57521824b2c20f5b91bea05) residing on the Ethereum blockchain. The goal is to eventually convert the ERC-20 tokens into the native tokens residing on the Taraxa blockchain.



## How will the conversion work?&#x20;

Technically, the conversion is pretty simple. But the technical process must be done in coordination with the exchanges that the TARA token is currently listed on, since otherwise all deposits and withdrawals will be disabled on these exchanges.&#x20;

Here's a quick overview of the mechanics of the conversion,&#x20;

1. Coordinate with the exchanges on a specific date & time when the conversion will take place&#x20;
2. Disable the ERC-20 contract on Ethereum
3. Record the exact ETH block where the contract has been disabled, this is the cutoff block height&#x20;
4. Mirror the ERC-20 and staking contract balances at the cutoff block height&#x20;
5. All staked tokens will be returned to the stakers' wallets on Mainnet, a re-delegation process must take place after the conversion&#x20;
6. New community site will be deployed&#x20;
7. Place these resulting balances inside the genesis block of the Mainnet&#x20;
8. Reset the Mainnet with the updated genesis block&#x20;
9. Deploy updated network statistics endpoints
10. Deploy community site claims contract&#x20;
11. Notify Mainnet validators to reset their nodes to the new version&#x20;

###

## Where are in the process?&#x20;

You can [track the status here](conversion-status.md).&#x20;
