# Economic Model

## 6. Economics

Note: this is a _**preliminary outline**_ of the overall intent for the Taraxa network's economics. These designs will be finalized at network launch via the governance process by stakeholders from the community, and they are subject to alterations via the same process.

### 6.1 Token Supply

The overall Taraxa token supply is 253 – 1 = 9007199254740991 tokens, with all tokens minted in the genesis block at network launch. This number was chosen because it is the largest safe integer in javascript.

This number may seem big, but we are simply expanding the number of tokens into its smallest units. For example, BTC has a total supply of 21 million tokens, but each BTC token is divisible into a further 100 million Satoshis, which means the effective supply is 2100000000000000 total Satoshis, which is approximately 250.899311, which is on the same order of magnitude \(within 1dB\) as Taraxa’s tokens.

### 6.2 Token Distribution

The target tokens distribution will be as follows,

| Distribution | % |
| :--- | ---: |
| Private sales | 24.1% |
| Public sales | 23.4% |
| Team | 15% |
| Block rewards | 15% |
| Foundation | 20% |
| Community grants | 2.5% |

* **Private sales** took place and has ended in 2018. 
* **Public sales** refer to the tokens that the foundation will inject into the market to fund ongoing development and ecosystem support. 
* Taraxa’s founding **team** members are committed to the long-term success of the network and will hold their token allocations for an extended period. 
* **Block rewards** are incentives offered to early Taraxa node operators to bootstrap the network. The total reward is capped and will be doled out until it runs out. 
* The **Foundation** intends to keep a certain number of tokens to continue contributing to the Taraxa ecosystem and to participate in the decentralized network operations. 
* **Community grants** are given out over time to incentivize positive contributions to the Taraxa ecosystem. This could range from bug bounties, to community building, or applications development. 

### 6.3 Token Utility

**Transaction Fees**

Token holders may use the token to initiate and pay for the cost of processing transactions, these transaction fees are paid to the validators of the network. More on transaction fees in the Rewards section.   
  


**Validator Eligibility**

Token holders may choose to stake their tokens via bonding to become an eligible validator of the network, responsible for processing the network’s transactions and maintaining the network’s overall security and integrity.

To become a validator, a fixed number of Taraxa tokens will need to be staked. Since the total token supply in the network is fixed, the maximum number of validators is also fixed. These rules will be set at network launch and are subject to change per stakeholders’ voting.   
  


**DApp Storage**

Token holders may choose to stake their tokens via bonding to receive a corresponding amount of storage on the network. This is meant to reflect the ongoing operational cost of validators having to replicate and store the full state \(and potentially the full state history\) of the network and discourage users from wantonly storing an excessive amount of data onto the network.

Each staked Taraxa token will correspond to a fixed number of bytes of eligible storage on the Taraxa network, governed by a \(token : storage\) ratio. Although the maximum number of tokens in the Taraxa network is capped, the maximum storage will be increased by the network automatically reducing the ratio should the staking rate go beyond the targeted staking rate \(see the Staking section\).

### 6.4 Staking

Staking is a mechanism for stakeholders to signal their commitment to help maintain and grow the Taraxa network, and they are rewarded \(see Rewards section\) accordingly. To stake, the stakeholder needs to bond Taraxa tokens for a period, in return gaining additional weight in voting in governance-related decisions and become eligible to participate in the Taraxa network’s consensus process and earning rewards.   
  


**Staking Period**

For simplicity, the staking period will be based on a fixed timeframe to be determined at network launch. The actual timeframe \(as all time-related metrics\) are governed by the number of Periods elapsed on the Taraxa network.

At network launch there may a special set of launch nodes that have a longer staking period with greater rewards. Details are to be determined.   
  


**Staking via Bonding**

Bonding of Taraxa tokens is needed in staking in order to provide stable expectations for eligibility. To bond a token is to lock a token into a fixed period of time \(as determined by the number of Periods on chain\), during which the bonded token is not tradeable or usable – besides granting the privileges in validation eligibility and access to current state storage on the network.   
  


**Stake Delegation**

Not everyone who wishes to help secure the Taraxa network wishes to deal with the actual operational details of running a node. These stakeholders can choose to bond their stake and then delegate it to another entity to operate a node on its behalf. How the proceeds from the stake are divide are negotiated between the stakeholder and the node operator.   
  


**Stake Alterations**

When a stakeholder wishes to bond or withdraw \(at the end of the staking period\) his / her stake, there is a buffer period \(e.g., a few days\) before such changes take effect. Since the staking amount is fixed, fractional stake alterations aren’t possible. The reasoning behind this buffer period is two-fold.

The first consideration is security. Because staking endows critical privileges on the network, namely the right to validate transactions, it is critical that the network has full understanding for eligibility. The network and the community need to be given ample time to note any such changes and be confident in their determination of any changes in eligibility resulting from the staking alterations.

The second consideration is economic. When large quantities of tokens are either added or removed from the staking pool, it could have an impact on the secondary markets for both the tokens themselves as well as the storage rentals \(i.e., those with bonded stakes could rent out the storage they’re entitled to DApp developers\). Having a buffer period will give the community ample notice to react to the change.   
  


**Target Staking Rate**

The network will have a target staking rate the entire token supply to be determined at network launch. This is the “desired” number of tokens in the overall supply that is locked into stake, leaving the remaining tokens used for fees on the network. Having a target staking rate is meant to encourage the community to stake their coins and help secure the network.

The target staking rate will be significantly higher than 50%, the exact number will be determined at network launch.

To incentivize the community to reach the target staking rate, a progressively increasing block reward will be doled out, reaching a maximum reward per block at the target staking rate. To put it simply, if the current staking rate is less than the target staking rate, the block reward is given by a linearly increasing line trending upward until it reaches the target staking rate, beyond which the reward remains constant \(flat line\).   
  


**Storage Scaling**

As the network starts to exceed the target staking rate, the amount of available storage on the network will be dynamically adjusted to expand the maximum available storage. Exceeding the target staking rate triggers a decrease in the \(token / storage\) ratio.

The idea behind this increase is that, because the community would have no increasing marginal incentive to stake beyond the target staking rate as far as block reward is concerned, then such an increase is most likely driven by a lack of storage as demanded by increasing DApp activity on the network. Hence maximum storage is increased to address this scarcity.

The mechanism is simple: the ratio will be decreased to trigger an exponential increase in the maximum amount of storage available on the network. For staking ranges less than the target staking rate, the maximum storage is constant \(flat line\).

### 6.5 Rewards

Rewards in Taraxa are made up of three components: block rewards, transaction fees, and storage rental.   
  


**Block Rewards**

Block rewards are meant to incentivize stakeholders to help secure the network by participating in validation by driving up the overall network’s staking rate. This is especially important in the early days of the network where fees may not meet node operators’ ROI expectations.

Within any given Period, each block receives the same quantity of tokens as block rewards, as determined by the target staking rate at the end of each Period. See target staking rate for more details.

Block rewards are dispersed to staked validators following the successful completion of these activities,

* Proposing valid blocks in the Block DAG
* Proposing valid consensus blocks on the PBFT chain

Since all participation are randomly with fairness guaranteed by a combination of VRF and VDF, all eligible staked nodes operating in good faith will have an equal chance of being rewarded.   
  


**Transaction Fees**

Taraxa will make use of the same first-price auction mechanism currently being used in BTC, ETH, and almost all other blockchain systems.

The primary criticism against the fees in classic systems such as BTC and ETH are that, they are 1\) too high, and 2\) too volatile. However, these symptoms are primarily driven not by the pricing mechanism itself, but rather by the throughput limitations of these networks. To put it simply, if the system is not at its maximum throughput limit, the block proposer has no incentive to prioritize between which pending transactions to include in a block – they’d simply place all available \(and eligible\) pending transactions into the next block.

As a sidebar, this isn’t entirely true in practice, as the network propagation speed consideration during competitive mining could adversely impact inclusion as well. In the Taraxa network however, there is no competition between the staking nodes so this adverse incentive should not exist.

Because of the very low maximum throughput in systems such as BTC and ETH, these networks are almost always operating at their maximum throughput, forcing users into constantly paying premiums to be included in blocks earlier, driving up both fee prices as well as fee volatility. In a far higher-throughput system such as Taraxa, we expect this to be far less of a consideration.

Just like block rewards, fees are going to be dispersed to staked validators for the same following the successful completion of these activities,

* Proposing valid blocks in the Block DAG
* Proposing valid consensus blocks on the PBFT chain

**Storage Rental**

Since staked tokens not only grants eligibility to become a validator, it also grants rights to store a certain amount of data on the network, those who have staked tokens could lease this privilege to DApp developers and generate rental income.

This incidentally creates an additional stream of income for those who have staked tokens to become validators. Storage lessors and renters could easily be matched on a secondary market to ensure pricing efficiency.   
  


**No Slashing**

Taraxa will not implement a slashing or punishment mechanisms at this moment.

It is incredibly difficult to design economic incentive schemes that properly motivate players in a system to behave in ways that are deemed constructive. As a rule, such mechanisms need to be as simple as possible, as more complexity creates more opportunities to game these mechanisms.

Reward mechanisms are already difficult to design and get “right”, punishment mechanisms are even harder, as a faulty punishment mechanism generating false positives is far more likely to incite a backlash and inject vitriol into the ecosystem.

At this point in time, we believe the lack of a reward should be sufficient “punishment” without the need to add further complexity.

## 

