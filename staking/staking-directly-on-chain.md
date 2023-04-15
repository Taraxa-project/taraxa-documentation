# ⛓ Staking directly on-chain

You can delegate to validator nodes by directly communicating with the on-chain DPoS contract and skip the community site altogether.&#x20;

Here are instructions on how to do this.&#x20;



### 1.  Upload the DPoS contract Solidity interface into Remix

Go to [Remix](https://remix.ethereum.org/), and upload Taraxa's DPoS contract's Solidity interface.&#x20;

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

In the pop-up, paste in the following link to the Taraxa DPoS contract Solidity interface,&#x20;

```
https://raw.githubusercontent.com/Taraxa-project/taraxa-evm/master/taraxa/state/dpos/solidity/dpos_contract_interface.sol
```

After it's been uploaded you should be able to see it in the IDE on the right side,&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### 2.  Compile the interface&#x20;

Make sure the interface file is selected,&#x20;

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Go into the compiler section by clicking on the icon on the left side. Once you're in the section, double check the big blue compile button indeed says "Compile dpos\_contract\_interface.sol".&#x20;

If the Compile button doesn't say that, that means the interface file wasn't selected in the file explorer section as indicated above, please go back and make sure the right file is selected.&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Click the Compile button. Once it has been compiled you should see a green checkmark on the compiler icon on the left sidebar, and additional options will show up below the compile button.&#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### 3.  Set up the interface&#x20;

After compilation, make sure you log into Metamask and switch the network to Tarxa Mainnet. If you aren't sure how to do that, please check out the [wallet guide on adding Taraxa networks into Metamask](../become-a-validator/register-node-directly-on-chain.md).&#x20;

_**Remember:** whatever wallet you use to register the validator node, this wallet is the_ [_owner of that node_](staking-directly-on-chain.md#0.-important-wallet-used-to-register-a-node-is-the-owner-of-that-node)_._&#x20;

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

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Go ahead and click the "At Address" button, and it should show up under "Deployed Contracts".&#x20;

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Go ahead and expand the interface by clicking on the chevron ">" and you'll see a list of all the commands you can send to the contract.&#x20;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

