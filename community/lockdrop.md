---
description: Raising awareness
---

# Lockdrop

Taraxa's Lockdrop campaign is the first of many steps that go to support the successful launch and operation of the Taraxa mainnet. Here are all the details about the Lockdrop. 

## TLDR; 

* You can lock in ETH and receive TARA points as a reward in a Lockdrop round
* If you were referred by another participant, entering their address will net you both +5% rewards
* There will be 3 ETH locking periods: 3, 6, and 12 months, longer periods yield more rewards
* TARA points will be converted into TARA tokens when Taraxa's mainnet launches, which is expected in Q1 2021
* A maximum of 100 million TAR points will be dropped during the Lockdrop
* You can participate using the lockdrop dApp at [https://lockdrop.taraxa.io](https://lockdrop.taraxa.io)

## Purpose

Taraxa's Lockdrop campaign is designed to help raise awareness for the project in the wider community. A Lockdrop requires the participant to lock in ETH to receive TARA points, which are convertible into TARA tokens in the future, after the launch of Taraxa's main network.

We believe that, by asking the participants to put something at stake - i.e., the opportunity cost of their ETH's lockup - it will attract more genuinely interested members to join and support our community. In this respect, a Lockdrop is far superior to the traditional airdrop. 

The Lockdrop is just the first of many steps that culminate in Taraxa's mainnet launch. 

## Mechanics

Here's a step by step, part by part description of the mechanics of the Lockdrop. 

### Rounds 

The Lockdrop campaign will be conducted across many rounds. The exact number of rounds is yet to be determined, and will be dynamically adjusted based on community interest and feedback. 

Each round will have a fixed duration, announced at the beginning of the round. Once the time has elapsed the round will end. 



### Locking in ETH

Participants can choose to lock in ETH tokens into our Lockdrop contract via a [dApp](https://lockdrop.taraxa.io). There are three locking time ranges to choose from: 3, 6, and 12 months, with longer lockup times receiving more rewards. Once the locking time range has elapsed, the contract will allow the participant to withdraw their deposit. 

There is a minimum lockup of 1 ETH to participate.

The Lockdrop contract has been fully audited by [Certik](https://certik.io/),  you can find the [source code here](https://github.com/Taraxa-project/lockdrop-contracts) and the audit certification &lt;insert link here&gt; here. 



### Lockdrop rewards 

Participants who lock in their ETH will receive rewards in the form of TARA points, convertible into TARA tokens after the mainnet has been launched, which is expected in Q1 of 2021. Prior to that point, the TARA points are simply a set of tabulation inside a contract and are not transferable.  

The average yield of TARA points for locked ETH is set at 1,000, with an additional referral bonus of +5% \(of the referred TARA point reward\) for both the referrer as well as the referred, totaling a +10% reward for both together. This results in a 1,100 maximum average yield.  

Longer locking periods offer greater rewards, calculated as a weight multiplier. 

| Locking Period | Yield weight multiplier |
| :--- | :--- |
| 3 months | 1 |
| 6 months | 2 |
| 12 months | 4 |

Exact rewards are calculated at the end of each Lockdrop round, and the yield will be the same for each locking period. Here's a more detailed look on how rewards are calculated.

* _**totalETHLocked**_: total \# of ETH locked in
* _**rawETHPercent\_p**_: the raw percentage of ETH, for a given locking period 
* _**w\_p**_: the yield weight multiplier for a given locking period
* _**avgRewardYield**_: the overall average reward yield of locking in ETH
* _**rewardYield\_p**_: reward yield for a given locking period
* _**totalReward\_p**_: total rewards for a given locking period  

To calculate the reward yield for each locking period, we have, 

$$
normalizedWeight_p =(rawETHPercent_p*w_p) / sum(rawETHPercent_p*w_p)
$$

$$
totalRewards_p=normalizedWeight_p*avgRewardYield*totalETHLocked
$$

$$
rewardYield_p = totalRewards_p / (rawETHPercent_p*totalETHLocked)
$$

Let's look at a few examples to make this clearer.

**EXAMPLE 1: evenly distributed across 3 locking periods** _\(not real, for illustration only\)_

| Locking Period | ETH \# | ETH % | weighted | normalized | Rewards | Reward Yield |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3 | 1,000 | 33% | 33% | 14% | 428,571 | 429 |
| 6 | 1,000 | 33% | 67% | 29% | 857,143 | 857 |
| 12 | 1,000 | 33% | 133% | 57% | 1,714,286 | 1,714 |
| overall  | 3,000 | 100% |  | 100% | 3,000,000 | 1,000 |

**EXAMPLE 2: concentrated in 3 months locking period** _\(not real, for illustration only\)_

| Locking Period | ETH \# | ETH % | weighted | normalized | Rewards | Reward Yield |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3 | 2,999 | 99.97% | 99.97% | 99.87% | 2,996,004 | 999 |
| 6 | 0 | 0% | 0% | 0% | 0 |  |
| 12 | 1 | 0.03% | 0.13% | 0.13% | 3,996 | 3,996 |
| overall  | 3,000 | 100% |  | 100% | 3,000,000 | 1,000 |

There are several things to note between the two examples, 

* The reward yield is largely determined by the distribution of locked in ETH across the 3 locking periods
* Example 1 has a perfectly even distribution, with the the reward yield for a 3-month lock almost exactly 1/4 that of the 12-month lock 
* Example 2 has a lopsided distribution, with almost all the ETH but 1 locked into the 3-month period
* Because in each round, we keep the overall \(or average\) reward yield to 1,000, having almost all the ETH locked into a single period means that period's reward yield is going to be very close to 1,000, which is the case here, for the 3-month lock period it is 999
* So, if participants can collude and all deposit into the lowest locking period, they will maximize their overall reward yield
* But due to the reward weights, now that the 3-month period's reward is maximized, if someone just puts a single ETH into the 12-month locking period \(as they do in Example 2\), they also maximize their reward yield and get a 3,996 - creating a huge incentive for more participants to come into the 12-month locking period \(as well as the 6-month locking period, which will be ~2x of the 3-month\)

This mechanism therefore has built-in incentives to roughly even out the distribution across the periods. 



### Referral bonus 

We want to encourage community members to refer one another to join in the Lockdrop, and offer a +5% bonus to BOTH the referrer and the referred. 

The mechanics are simple. While locking in ETH, the participant can choose to enter an ETH address whose owner referred them to the Lockdrop. The address entered must be itself a participant of the Lockdrop, but need not be the current round - i.e., they could have participated in a prior Lockdrop round. 

For example, Alice referred Bob to the Lockdrop. Bob enters in Alice's ETH address while locking in his own ETH. At the end of the round, Bob has earned 1,000 TARA points, but since he entered a referral, he receives an additional 5%, or 50 TARA points, and Alice also receives an additional 50 TARA points as well.

 

## Lockdrop smart contract

Our Lockdrop contract has been fully audited by [Certik](https://certik.io/), a leader in blockchain security audits. 

You can find the Lockdrop contract here: &lt;insert github link here&gt; 

You can find Certik's audit certificate here: &lt;insert Certik audit report here&gt; 



## Next up: Testnet Staking!  

While TARA points can definitely be redeemed at mainnet launch for TARA tokens, the Lockdrop is a precursor to our testnet staking and eventually mainnet staking. 

Testnet staking will stake TARA points, while mainnet staking will stake TARA tokens. Just like in mainnet staking, testnnet staking will also yield staking interest, for those who operate nodes and those who delegate their TARA points to the node operators. 

We hope that testnnet staking will help build a community that will eventually take over the operations of the Taraxa network, by helping to stress-test both technical as well as the economic aspects of the network.  

## Legal compliance 

To comply with recent SEC rulings, United States persons cannot participate in the Lockdrop. 



