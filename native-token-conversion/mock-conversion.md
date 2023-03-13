# ⚗ Mock Conversion

## WARNING: Technical Understanding Required!

This mock conversion document was prepared for the exchanges to conduct pre-conversion testing. However if you're someone who's technically-inclined then you're more than welcome to try this out yourself.&#x20;

If you find these instructions hard to understand or follow, then it's probably best to just wait for the actual conversion.&#x20;



## Test the Conversion Before It Happens

The native token conversion is a big event for the Taraxa ecosystem. While the [conversion mechanism](https://docs.taraxa.io/native-token-conversion/introduction#how-will-the-conversion-work) is designed to minimize risk and the amount of work end users have to endure, it's nevertheless a good idea to try out the conversion for yourself prior to the actual conversion so you know what to expect.&#x20;

The latest testnet reset occurred on March 1, 2023 (see [Discord announcement](https://discord.com/channels/419749122556297216/909881217216827402/1080473001138597938)), which mirrored the TARA ERC-20 contract at the **`cutoff ETH block height: 16720500`**.&#x20;



## Goals of the Mock Conversion&#x20;

There are two simple goals of the mock conversion. Everyone should try to,&#x20;

**🪙  Verify your wallet's balance at the stated block height on the testnet, and**&#x20;

**🔐  Verify your wallet's ownership by issuing a few transactions on the testnet**

Let's get into a step by step example.&#x20;



## **🪙**  Example 1/2: Verify your Balance&#x20;

### STEP 1: Verify what your balance should be

Alice has a wallet on the ETH network which holds some TARA tokens. She knows that during the native token conversion, all of her TARA holdings will be mirrored onto Taraxa's native Layer-1 network, but she doesn't know exactly how that works. Let's go through step by step on how she can take advantage of this Mock Conversion event to help familiarize herself with the upcoming native token conversion.&#x20;

Alice's wallet address is `0xb2781265b0905123bed40d4d0fb08a4bff28702a` , we can see that by block height `16720500`, Alice has a balance of `1,289,181` TARA ERC-20 tokens on the Ethereum network. As of this writing, you can [check this balance](https://etherscan.io/token/0xf001937650bb4f62b57521824b2c20f5b91bea05?a=0xb2781265b0905123bed40d4d0fb08a4bff28702a) yourself on Etherscan, note that the [last transaction](https://etherscan.io/tx/0xafe359ff311b82c34903007635b6319cf94f10a447979709f87e215741248d05) occurred on ETH block `16690828`, which is earlier than the block cutoff of `16720500`.&#x20;

Note that, if unlike Alice, you've made additional TARA transactions after ETH block `16720500`, then you'll need to manually account for them, or "roll back" these transactions in your calculations.  Just find the transactions that took place after the cutoff and reverse them in your calculations.&#x20;

Alice has also participated in staking. As of this writing, she has `86,074,923` TARA tokens staked in the staking contract. If you have staked, you can check this in the [community site's staking section.](https://community.taraxa.io/staking)&#x20;

After the conversion, Alice's balance in her wallet should be her wallet balance + her staking balance, which in this case is: `1,289,181 + 86,074,923 =`` `**`87,364,104`** tokens.&#x20;



### STEP 2: Verify the balance on the Testnet&#x20;

Now Alice will go to the Testnet that was recently reset, and see if her balance was correctly mirrored over from Step #1.&#x20;

On the explorer, she visits her address's page,&#x20;

[https://testnet.explorer.taraxa.io/address/b2781265b0905123bed40d4d0fb08a4bff28702a](https://testnet.explorer.taraxa.io/address/b2781265b0905123bed40d4d0fb08a4bff28702a)&#x20;

and the balance is exactly what you'd expect from Step #1 - as of this writing.&#x20;

🥳 Alice has verified her balance!&#x20;



## **🔐**  Example 2/2: Verify your Ownership

Now that Alice has confirmed that she has the correct balance on the Testnet, next she will try to confirm that she truly OWNS this wallet.&#x20;

To do that, she can try to send some coins to other addresses from this wallet by doing the following.&#x20;

1. Follow the [wallet guide](../wallet/) and connect her wallet to the Testnet
2. Make sure that the [custom network details](https://docs.taraxa.io/wallet/taraxas-network-connection-details#taraxa-testnet-connection-details) are those of the Taraxa Testnet!&#x20;
3. Once connected, Alice can simply send some coins to any address, since this is the Testnet and this is a mock conversion, the tokens aren't real and she won't lose anything.&#x20;
4. ➡️ MAKE SURE Taraxa Testnet is selected in the wallet. ⬅️
5. If Alice is able to successfully make a transaction, that means she does indeed has ownership over her wallet!&#x20;

🥳 Alice has verified her ownership!&#x20;

