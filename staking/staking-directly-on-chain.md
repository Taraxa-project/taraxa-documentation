# ⛓ Staking directly on-chain

You can delegate to validator nodes by directly communicating with the on-chain DPoS contract and skip the community site altogether.&#x20;

Here are instructions on how to do this.&#x20;



### 1.  Upload the DPoS contract Solidity interface into Remix

Go to [Remix](https://remix.ethereum.org/), and upload Taraxa's DPoS contract's Solidity interface.&#x20;

<figure><img src="../.gitbook/assets/image (13) (2).png" alt=""><figcaption></figcaption></figure>

In the pop-up, paste in the following link to the Taraxa DPoS contract Solidity interface,&#x20;

```
https://raw.githubusercontent.com/Taraxa-project/taraxa-evm/master/taraxa/state/dpos/solidity/dpos_contract_interface.sol
```

After it's been uploaded you should be able to see it in the IDE on the right side,&#x20;

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

### 2.  Compile the interface&#x20;

Make sure the interface file is selected,&#x20;

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Go into the compiler section by clicking on the icon on the left side. Once you're in the section, double check the big blue compile button indeed says "Compile dpos\_contract\_interface.sol".&#x20;

If the Compile button doesn't say that, that means the interface file wasn't selected in the file explorer section as indicated above, please go back and make sure the right file is selected.&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Click the Compile button. Once it has been compiled you should see a green checkmark on the compiler icon on the left sidebar, and additional options will show up below the compile button.&#x20;

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

### 3.  Set up the interface&#x20;

After compilation, make sure you log into Metamask and switch the network to Tarxa Mainnet. If you aren't sure how to do that, please check out the [wallet guide on adding Taraxa networks into Metamask](../become-a-validator/register-node-directly-on-chain.md).&#x20;

_**Remember:** whatever wallet you use to register the validator node, this wallet is the_ [_owner of that node_](staking-directly-on-chain.md#0.-important-wallet-used-to-register-a-node-is-the-owner-of-that-node)_._&#x20;

Once you've switched your Metamask to the Taraxa Mainnet, go to the "Deploy & Run Transactions" section in Remix.&#x20;

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

At the top, change "Environment" to "Injected Provider - Metamask". Once you've done that, make sure to double-check that&#x20;

* The network ID is indeed [Taraxa's network ID](../wallet/taraxas-network-connection-details.md) in the "Custom network" tag  under the Environment dropdown, and&#x20;
* The wallet under "Account" is the wallet you want to use. Make sure you use the wallet that contains the TARA you wish to delegate.&#x20;
* The right compiled interface from the previous step is loaded. Look at the "Contract (Compiled by Remix)" section and make sure the filename is the same as the one in the file explorer.&#x20;

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

Next, we tell Remix where the DPoS contract is located. Go the "At Address" field towards the bottom of the screen, and enter the following address. This is where Taraxa's precompiled DPoS contract is located.&#x20;

```
0x00000000000000000000000000000000000000fe
```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Go ahead and click the "At Address" button, and it should show up under "Deployed Contracts".&#x20;

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Go ahead and expand the interface by clicking on the chevron ">" and you'll see a list of all the commands you can send to the contract.&#x20;

<figure><img src="../.gitbook/assets/image (5) (2).png" alt=""><figcaption></figcaption></figure>

### 4.  Verifying the validator node

Before you delegate to a validator node, let's make sure it has actually been registered in the DPoS contract. We're going to do this by calling the `getValidator` function on the validator you wish to delegate to.&#x20;

For example, if I wanted to delegate to a validator node whose public address is: `0xd423413a6b4bb11e584d7de3acce40d95da6c3b1`, we simply enter this address into the function.&#x20;

<figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>

We click on the "call" button to send the query to the DPoS contract, and we get the return value below the call. Here's how to interpret it.&#x20;

* First, the returned value at the bottom is not an error! Which means the validator has been registered.&#x20;
* If the returned value is an error, :octagonal\_sign: DO NOT :octagonal\_sign: delegate to this address. This node either does not exist at all, or it has not been registered.&#x20;
* Part of the returned value is an 256-bit unsigned integer that indicates the current delegation (see underlined number in the screenshot above). Note that, all values on the blockchain are stored as unsigned 256-bit integers, so there are no decimals, that's why the numbers look so big because they need to also represent 10^18 decimal places as part of the integer value. Just take this number and remove 18 zeros from the end, and you'll see that, in this example, this validator node has 1000 TARA delegated to it. Since 1000 TARA is a required self-delegation from the node owner, that means this node has not received any delegation since registration.&#x20;
* Since the minimum delegation required to participate in consensus is 500,000 TARA, that means in this example, this node is not yet eligible to participate in consensus. If the validator node has passed the minimum threshold, then you can also check it on the explorer to see its past block production history.&#x20;

### 5.  Delegating to the validator&#x20;

After verifying the validator node indeed exists on the network, we can now delegate to it by calling the `delegate` function.&#x20;

First, we enter the number of TARA to be delegated into the node. Within the "Deploy & Run Transactions" section of Remix, navigate back towards the top and you'll see a "Value" field. This field defines how many tokens will be transferred to the contract in this transaction.&#x20;

Set the following,&#x20;

* Value to whatever you wish to delegate, in this example we're going to use 1000 since it's the minimum delegation amount.&#x20;
* Unit to "Ether", this may be confusing but since Remix isn't aware of the Taraxa Network's token name, it calls all tokens for EVM-compatible networks "Ether", don't worry, it's sending TARA (since you're on the Taraxa Network)

Next, we enter the validator node's public address into the `delegate` function below. &#x20;

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

After pressing the "transact" button, the output is seen on the right side in Remix's console.&#x20;

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

If the transaction is successful, you should see a green checkmark at the top-left corner. If you expand the output, you'll that the "status" has a successful output, and in the "va" field you should see the exact amount (with 18 extra zeros at the end) that you delegated.&#x20;

Let's verify that the delegation has indeed worked, by calling the `getValidator` function on the validator node again.&#x20;

&#x20;

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Now it has 2000 TARA delegation (once again, reminder there are 18 extra zeros after the number), which is exactly 1000 TARA more than before we started.&#x20;

:tada: Everything worked!&#x20;



### 6.  Claiming staking yields

To claim staking yields, use the `claimRewards` function. Make sure the wallet connected is the wallet used to stake.&#x20;

Note that, you'll need to claim rewards from every validator you delegated to.&#x20;

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

In our example, since the validator only has 2000 TARA delegation, it isn't eligible to participate in consensus yet so the reward claimed was 0, which is expected.&#x20;



### 7.  Re-delegating your stake

If for whatever reason, you want to move your delegation from one node to another - e.g., if the original node you delegated to has shut down, you can use the `reDelegate`  function.&#x20;

Just enter the public addresses for the validator node you want to remove delegation from, to, and the amount (remember to add 18 zeros at the end of this!), and press "transact".&#x20;

<figure><img src="../.gitbook/assets/image (7) (2).png" alt=""><figcaption></figcaption></figure>

You should always verify the results by using the `getValidator` function as usual.&#x20;

### 8.  Un-delegating your stake

You can also remove your delegation and return the staked TARA back into your wallet by using the     `unDelegate` function. Note that, after calling the unDelegate function, it'll take \~30 days for the delegated tokens to unlock.&#x20;

After the time has elapsed and tokens unlocked, you can claim the tokens via the `confirmUndelegate` function, which requires that you enter the same validator node's public address again.&#x20;



<figure><img src="../.gitbook/assets/image (4) (3).png" alt=""><figcaption></figcaption></figure>

