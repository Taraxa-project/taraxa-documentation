---
description: A step-by-step guide on how to use Taraxa's Ficus Root Bridge.
---

# ↔️ Bridge usage guide

The [Ficus Root Bridge](https://bridge.taraxa.io/) is live! Here's a guide on how to use it. In this step by step guide we use an example bridging from Taraxa to Ethereum. Bridging from Ethereum to Taraxa follow the exact same steps, just with the source and destination networks reversed.&#x20;

### 1. Select your source and destination&#x20;

Go the [Ficus Root Bridge](https://bridge.taraxa.io/), pick your your source and destination networks. In the screenshot below, we're bridging from the Taraxa network into the Ethereum network.&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### 2. Connect your wallet&#x20;

#### 2.1 Click on Connect Wallet &#x20;

Once you selected your source & destination networks, you should connect your wallet. Click on the "Connect Wallet" button and the web3 plugin (e.g., Metamask) should pop-up.&#x20;

Make sure that your wallet is connected to the source network. In this example, we're bridging from Taraxa to Ethereum, so the Metamask plugin should be connected to the Taraxa mainnet.&#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### 2.2 Pick the wallet address you want to connect &#x20;

Once the wallet is open, select which address you want to connect to from the list of addresses.&#x20;

<figure><img src="../.gitbook/assets/2.2. Connect wallet - address.png" alt=""><figcaption></figcaption></figure>

#### 2.3 Give permission to connect &#x20;

<figure><img src="../.gitbook/assets/2.3. Connect wallet - confirm.png" alt=""><figcaption></figcaption></figure>



#### 2.4 Confirm that your wallet is connected

Once connected, you should see your wallet address show up on the upper-right corner. Please confirm that this is indeed the right wallet address you want to use.&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>



### 3. Start the bridging transfer

Click on "Begin new transfer" to start bridging from the connected wallet.&#x20;

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### 4. Asset selection&#x20;

#### 4.1 Select the asset you want to bridge over

In the dropdown menu, select the asset you want to bridge over. Please make sure that you have the selected assets in your wallet.&#x20;

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### 4.2 Confirm asset balance&#x20;

Once the asset is selected, you can see the asset's balance in your connected wallet at the bottom-right corner of the UI, make sure that number matches with what you think is in the wallet. You can also see there there's a bridging fee.&#x20;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### 5. Enter amount to bridge

Having selected the assets you wish to bridge, now enter the amount you want to bridge over. Make sure you leave enough to cover the bridging fees.&#x20;

In this example we've selected to bridge over 200 TARA from the Taraxa network to the Ethereum network.&#x20;

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

### 6. Note the bridging fees

The bridging fee goes to cover the cost of transferring and verifying on-chain state proofs that make the bridge possible. Since gas costs on Ethereum are so high, these state proofs tend to cost quite a bit of gas. The Taraxa dev team will continue to work on optimizations to try to bring down this cost.&#x20;

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### 7. Start bridging &#x20;

Click the Continue button to start bridging.&#x20;

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### 8.  Bridging summary and transaction delay&#x20;

Once you start bridging, a summary will appear with all the details of the bridging transaction. You can confirm,&#x20;

* Source & destination network
* Asset
* Amount
* Bridging delay&#x20;

As of this writing, it takes \~4 hours to bridge from Taraxa to Ethereum, and \~18 minutes to bridge from Ethereum to Taraxa.&#x20;

The reason there's a delay is due to the fact that we need to give sufficient time for the respective networks to reach finality. In the case for Ethereum, the official finality timeframe is actually much longer than 18 minutes, but this is typically how long dApps wait. In the case of Taraxa, finality is actually just under 3.7 seconds.&#x20;

Bridging from Taraxa to Ethereum takes far longer than bridging from Ethereum to Taraxa, this is driven again by the extremely high gas fees on Ethereum. Just transferring, storing, and verifying state changes is an extremely expensive operation, so when the Relayer transfers over Taraxa's state changes to Ethereum, we'd like to do it not so frequently to keep costs under control. But since gas costs on Taraxa are next to nothing, the Relayer can store Ethereum's state onto Taraxa much more frequently.&#x20;

The bridging delays may be shorter than what's aforementioned, if your transaction falls into the same delay window as a previous transaction that was earlier than yours.&#x20;

The dev team will continue to work on finding optimizations to reduce this delay, but ultimately there will always be an asymmetry simply because the gas costs on Ethereum are so astronomically high.&#x20;

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### 9. Confirm the transaction

#### 9.1 Click on "Confirm" to proceed

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

#### 9.2 Confirm transaction in wallet

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

#### 9.3 Wallet submitting the transaction&#x20;

<figure><img src="../.gitbook/assets/9.1. Pop-up confirmation submit.png" alt=""><figcaption></figcaption></figure>

#### 9.4 Wallet successfully submitted transaction&#x20;

<figure><img src="../.gitbook/assets/9.1. Pop-up confirmation submitted.png" alt=""><figcaption></figcaption></figure>

#### 9.5 Bridge UI confirming the transaction's success&#x20;

<figure><img src="../.gitbook/assets/9.2. Pop-up confirmation - link.png" alt=""><figcaption></figcaption></figure>

### 10. Confirming your transaction in explorers & wallet&#x20;



#### 10.1 Confirming in explorers&#x20;

Once your transaction is completed, the bridged assets will arrive into the target wallet automatically after the requisite delay has elapsed. As an example, we can check on the first bridging transaction from Taraxa to Ethereum. Here are the transactions,&#x20;

* [Transaction on Taraxa initiating the bridging transfer](https://mainnet.explorer.taraxa.io/tx/0x025cb96a7245d1005c5c43eaa9bdc480bfe3bd2cd1b0c2b57d33638f2cb59fb9)
* [Transaction on Ethereum that automatically credits the bridging transfer](https://etherscan.io/tx/0xe78526ad0a805849dafd0da87be1520aacc1342b56328893875d20f60c7b1a4b)&#x20;

You can see that there's an \~4 hour delay between the two transactions.&#x20;



#### 10.2 Add to your wallet&#x20;

You should also add the bridged token to your wallet.&#x20;



For example, if you have just bridged over TARA coins from the Taraxa network to the Ethereum network, you should add the TARA-on-ETH token address to your wallet.&#x20;

Go to the [On-chain contracts](on-chain-contracts.md) section of the guide, find the target (i.e., where you're transferring to) contract address, and add it into your wallet (e.g., Metamask). In this example the address we're looking for is the TARA Token on ETH address, add that as a custom token and you will see the balance pop up.&#x20;

As a reference, here is the [official guide on how to add a custom token in Metamask](https://support.metamask.io/managing-my-tokens/custom-tokens/how-to-display-tokens-in-metamask/#how-to-add-a-custom-token).&#x20;





That's it! You now know how to use the [Ficus Root Bridge](https://bridge.taraxa.io/) to bridge assets between Taraxa and Ethereum!&#x20;

