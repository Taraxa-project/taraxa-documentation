# ⛓ Register node directly on-chain

You can register a validator node by directly communicating with the on-chain DPoS contract and skip the community site altogether.&#x20;

Here are instructions on how to do this.&#x20;



### 0.  IMPORTANT: wallet used to register a node is the owner of that node

Validator node registration is an on-chain transaction. The wallet you use to register a node is the "owner" of that node. This means once a node is registered, the "owner wallet" is now required to,&#x20;

* Change the validator node's commission rate
* Claim commission rewards earned by the validator node

A single owner wallet can register multiple validator nodes and become their owner, this makes it easy to manage multiple validator nodes in aggregate.&#x20;

**Please safeguard your validator nodes' owner wallet!**&#x20;



### 1.  Upload the DPoS contract Solidity interface into Remix

Go to [Remix](https://remix.ethereum.org/), and upload Taraxa's DPoS contract's Solidity interface.&#x20;

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

In the pop-up, paste in the following link to the Taraxa DPoS contract Solidity interface,&#x20;

```
https://raw.githubusercontent.com/Taraxa-project/taraxa-evm/master/taraxa/state/dpos/solidity/dpos_contract_interface.sol
```

After it's been uploaded you should be able to see it in the IDE on the right side,&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### 2.  Compile the interface&#x20;

Make sure the interface file is selected,&#x20;

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Go into the compiler section by clicking on the icon on the left side. Once you're in the section, double check the big blue compile button indeed says "Compile dpos\_contract\_interface.sol".&#x20;

If the Compile button doesn't say that, that means the interface file wasn't selected in the file explorer section as indicated above, please go back and make sure the right file is selected.&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Click the Compile button. Once it has been compiled you should see a green checkmark on the compiler icon on the left sidebar, and additional options will show up below the compile button.&#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### 3.  Set up the interface&#x20;

After compilation, make sure you log into Metamask and switch the network to Tarxa Mainnet. If you aren't sure how to do that, please check out the [wallet guide on adding Taraxa networks into Metamask](register-node-directly-on-chain.md).&#x20;

_**Remember:** whatever wallet you use to register the validator node, this wallet is the_ [_owner of that node_](register-node-directly-on-chain.md#0.-important-wallet-used-to-register-a-node-is-the-owner-of-that-node)_._&#x20;

Once you've switched your Metamask to the Taraxa Mainnet, go to the "Deploy & Run Transactions" section in Remix.&#x20;

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

At the top, change "Environment" to "Injected Provider - Metamask". Once you've done that, make sure to double-check that&#x20;

* The network ID is indeed [Taraxa's network ID](../wallet/taraxas-network-connection-details.md) in the "Custom network" tag  under the Environment dropdown, and&#x20;
* The wallet under "Account" is the wallet you want to use, since setting up a validator node will require gas fees but also a 1000-TARA minimum self-delegation, so make sure the wallet connected has sufficient funds
* The right compiled interface from the previous step is loaded. Look at the "Contract (Compiled by Remix)" section and make sure the filename is the same as the one in the file explorer.&#x20;

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

Next, we tell Remix where the DPoS contract is located. Go the "At Address" field towards the bottom of the screen, and enter the following address. This is where Taraxa's precompiled DPoS contract is located.&#x20;

```
0x00000000000000000000000000000000000000fe
```

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

Go ahead and click the "At Address" button, and it should show up under "Deployed Contracts".&#x20;

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Go ahead and expand the interface by clicking on the chevron ">" and you'll see a list of all the commands you can send to the contract.&#x20;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### 4.  Set the self-delegation value&#x20;

When a new validator node is registered, there's a 1000 TARA self-delegation requirement. This means 1000 TARA will need to be delegated from the registration wallet, or the owner wallet, to the DPoS contract.&#x20;

Within the "Deploy & Run Transactions" section of Remix, navigate back towards the top and you'll see a "Value" field. This field defines how many tokens will be transferred to the contract in this transaction.&#x20;

Set the following,&#x20;

* Value to 1000, since we're self-delegating 1000 TARA
* Unit to "Ether", this may be confusing but since Remix isn't aware of the Taraxa Network's token name, it calls all tokens for EVM-compatible networks "Ether", don't worry, it's sending TARA (since you're on the Taraxa Network)

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

Once these values are set let's move to the next step.&#x20;



### 5.  Register a validator node

Now we register a validator. Let's run a few tests first. Assume that the validator is completely new (hence we're registering one), let's see if the network thinks it is an eligible validator.&#x20;

As an example, assume the validator's public address is:  `0xd423413a6b4bb11e584d7de3acce40d95da6c3b1`.

Let's try calling `getValidator`, with the node's public address,&#x20;

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

On the right side, we get an error as returned value, "Validator does not exist", which is expected since this is a brand new node.&#x20;

Now let's register this node by calling the `registerValidator` function.&#x20;

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

The function takes 6 arguments, we're going to enter the first 4 and leave the last two blank, since the last two really has no impact on the node's function or economics, and are simply informational.&#x20;

Here are instructions on how to find the node's,&#x20;

* [Public address](https://docs.taraxa.io/node-setup/node\_address) which goes into the "validator" field
* [Proof of ownership](../node-setup/proof\_owership.md) which goes into the "proof" field
* [VRF key](../node-setup/vrf\_key.md) which goes into the "vrf\_key" field, don't forge to add a `0x` in front of the wallet's output

The commission field takes in an integer that is 100 multiplied by the commission percentage, here are a few examples of how a commission percentage is translated into the parameter entered into the `registerValidator` function,&#x20;

* 0.01% commission -> 1&#x20;
* 1% commission -> 100
* 10% commission -> 1000
* 100% commission -> 10000

We get all the information and enter it into the fields, **BUT DON'T PRESS TRANSACT YET**.&#x20;

<figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>

Press the "transact" button and check for the results in the console, located the bottom-right side of the page. If the transaction is successful, you should see a green checkmark at the top, the status message indicating the transaction has been successfully executed.&#x20;

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### 6.  Confirm validator's registration

Let's confirm the validator's registration by calling the `getValidator` function again. Simply enter the validator node's public address into the function's parameter input field and press "call".&#x20;

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Two things to note here,&#x20;

* The returned value at the bottom is not an error, which means the validator has been registered&#x20;
* Part of the returned value is an 256-bit unsigned integer that indicates the current delegation (see underlined number in the screenshot above). Since we just registered the node with a 1000 TARA delegation, we'd expect that there would be 1000 \* 10^18 wei delegated to this node, and indeed that is what it is (count the zeros :smile:)&#x20;

:tada::tada: You have just registered a validator node.&#x20;

