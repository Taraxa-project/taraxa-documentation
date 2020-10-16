---
description: Building a sustainable community
---

# Lockdrop

Taraxa's Lockdrop campaign is the first of many steps that go to support the successful launch and operation of the Taraxa mainnet. Here are all the details about the Lockdrop. 

## TLDR; 

* Current round is: Round 1, which starts on &lt;insert date&gt; 
* You can participate &lt;here - insert link&gt;
* You can lock in ETH and receive TARA points as a reward
* If you were referred by another participant, entering his address will net you both +5% rewards
* There will be 3 ETH locking periods: 3, 6, and 12 months, longer periods yield more rewards
* The TARA points will be converted into TARA tokens when Taraxa's mainnet launches, which is expected in Q1 2021

## Purpose

Taraxa's Lockdrop campaign is designed to help raise awareness for the project in the wider community. A Lockdrop requires the participant to lock in ETH to receive TARA points, which are convertible into TARA tokens in the future, after the launch of Taraxa's main network.

We believe that, by asking the participants to put something at stake - i.e., the opportunity cost of their ETH's lockup - it will attract more genuinely interested members to join and support our community. In this respect, a Lockdrop is far superior to the traditional airdrop. 

The Lockdrop is just the first of many steps that culminate in Taraxa's mainnet launch. 

## Mechanics

Here's a step by step, part by part description of the mechanics of the Lockdrop. 

### Rounds 

The Lockdrop campaign will be conducted across many rounds. The exact number of rounds is yet to be determined, and will be dynamically adjusted based on community interest and feedback. 

Each round will have a maximum cap on the number of ETH that can be locked. After the cap has been reached, that round will automatically close, the locked ETH tabulated, and the rewards calculated and reflected in the Lockdrop contract. 

### 

### Locking in ETH

Participants can choose to lock in ETH tokens into our Lockdrop contract via a web interface &lt;here - insert link&gt;. There are three locking time ranges to choose from: 3, 6, and 12 months, with longer lockup times receiving more rewards. Once the locking time range has elapsed, the contract will automatically release the ETH tokens back to the participant. 

There is a minimum lockup of 1 ETH to participate.

The Lockdrop contract has been fully audited by Quantstamp,  you can find the source code &lt;insert link here&gt; here and the audit certification &lt;insert link here&gt; here. 



### Lockdrop rewards 

Participants who lock in their ETH will receive rewards in the form of TARA points, convertible into TARA tokens after the mainnet has been launched, which is expected in Q1 of 2021. Prior to that point, the TARA points are simply a set of tabulation inside a contract and are not transferable.  

The average ratio between TARA points and locked ETH is set at 1,000, with an additional referral bonus of +5% \(of the referred TARA point reward\) for both the referrer as well as the referred, totaling a +10% reward for both together. This results in a 1,100 maximum average ratio of TARA points to locked ETH in rewards. 

Longer locking periods offer greater rewards, calculated as a weight multiplier. 

| Locking Period | Contribution weight multiplier |
| :--- | :--- |
| 3 months | 1 |
| 6 months | 2 |
| 12 months | 4 |

Exact rewards are calculated at the end of each Lockdrop round, and the ratio will be the same for each locking period. Here's a more detailed look on how rewards are calculated.

* _**totalETHLocked**_: total \# of ETH locked in
* _**rawETHPercent\_p**_: the raw percentage of ETH, for a given locking period 
* _**w\_p**_: the contribution weight multiplier for a given locking period
* _**avgRewardRatio**_: the overall average reward ratio of locking in ETH
* _**rewardRatio\_p**_: reward ratio for a given locking period
* _**totalReward\_p**_: total rewards for a given locking period  

To calculate the reward ratio for each locking period, we have, 

$$
normalizedWeight_p =(rawETHPercent_p*w_p) / sum(rawETHPercent_p*w_p)
$$

$$
totalRewards_p=normalizedWeight_p*avgRewardRatio*totalETHLocked
$$

$$
rewardRatio_p = totalRewards_p / (rawETHPercent_p*totalETHLocked)
$$

Let's look at a few examples to make this clearer.

**EXAMPLE 1: evenly distributed across 3 locking periods** _\(not real, for illustration only\)_

| Locking Period | ETH \# | ETH % | weighted | normalized | Rewards | Reward Ratio |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3 | 1,000 | 33% | 33% | 14% | 428,571 | 429 |
| 6 | 1,000 | 33% | 67% | 29% | 857,143 | 857 |
| 12 | 1,000 | 33% | 133% | 57% | 1,714,286 | 1,714 |
| overall  | 3,000 | 100% |  | 100% | 3,000,000 | 1,000 |

\*\*\*\*

**EXAMPLE 2: mostly concentrated in 6 months locking period** _\(not real, for illustration only\)_

| Locking Period | ETH \# | ETH % | weighted | normalized | Rewards | Reward Ratio |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3 | 100 | 3% | 3% | 2% | 49,180 | 492 |
| 6 | 2,800 | 93% | 187% | 92% | 2,754,098 | 984 |
| 12 | 100 | 3% | 13% | 7% | 196,721 | 1,967 |
| overall  | 3,000 | 100% |  | 100% | 3,000,000 | 1,000 |

### 

### 

### Rounds 

The Lockdrop campaign will be conducted across many rounds. The exact number of rounds is yet to be determined, and will be dynamically adjusted based on community interest and feedback. 

Each round will have a maximum cap on the number of ETH that can be locked. After the cap has been reached, that round will automatically close, the locked ETH tabulated, and the rewards calculated and reflected in the Lockdrop contract. 



### Rounds 

The Lockdrop campaign will be conducted across many rounds. The exact number of rounds is yet to be determined, and will be dynamically adjusted based on community interest and feedback. 

Each round will have a maximum cap on the number of ETH that can be locked. After the cap has been reached, that round will automatically close, the locked ETH tabulated, and the rewards calculated and reflected in the Lockdrop contract. 



### Rounds 

The Lockdrop campaign will be conducted across many rounds. The exact number of rounds is yet to be determined, and will be dynamically adjusted based on community interest and feedback. 

Each round will have a maximum cap on the number of ETH that can be locked. After the cap has been reached, that round will automatically close, the locked ETH tabulated, and the rewards calculated and reflected in the Lockdrop contract. 







## Lockdrop contract

xx





## Legal compliance 

To comply with recent SEC rulings, United States persons cannot participate in the Lockdrop. 



