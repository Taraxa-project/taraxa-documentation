# Governance

## 7. Governance

For the Taraxa network to remain healthy and viable in the long-term, it must be adaptable and responsive to the network stakeholders’ demands over time. To that end we propose the following governance model, and welcome feedback from the broader community. For the avoidance of doubt, the right to vote does not entitle Taraxa token holders to vote on the operation and management of the Foundation, its affiliates, or their assets, and does not constitute any equity interest in any of these entities.\


**Council**

Since voter turnout is a persistent problem in almost all electoral systems – including decentralized ecosystems – a council will be elected to represent the interests of passive stakeholders in the Taraxa network. These Council Members may determine features and/or parameters of Taraxa as well as protocol improvements and new product development, or even changes to the governance process itself.

The size of the council will increase as the network size increases. The size of the council will be determined at network launch, starting with a relatively smaller number and then scaling upward as the network matures.\


**Councils’ Purview**

The council will vote on decisions that impact all aspects of the Taraxa network, including anything from code upgrades to adjustments to the reward mechanism. These changes will eventually be encoded into each node’s codebase that will automatically enact approved decisions.\


**Council Election**

The council will be elected via a single transferable vote (STV) system, with the number of votes determined by the number of Taraxa tokens held by each voter with a bonding time modifier (see below). This is a widely used voting system to achieve proportional representation through ranked voting for multi-seat organizations. Here’s a simple description of the STV system with a Droop quota.&#x20;

_Premises_

* N seats are available
* V valid votes are cast
* T is the minimum threshold of votes necessary to win any given seat, with T = ceil (valid votes cast / (seats to fill + 1))

_Voting steps_

1. Council candidates nominate themselves
2. Stakeholders cast their votes for their most preferred N candidates ranking from most to least preferred
3. Starting from all stakeholders’ first choice votes
4. Any candidate receiving votes greater than T is elected into the council
5. The elected candidates’ received votes in excess of T are transferred to those voter’s next choice
6. If no candidate receives votes in excess of T, eliminate the candidate with the least number of votes and transfer those votes to the voter’s next preferred candidate
7. Repeat steps 4-6 until we have either elected a candidate for every seat, or the number of remaining seats equal to the number of remaining candidates – in which case those remaining candidates are elected

**Council Member Terms**

Each council member has a term of approximately 12 weeks. In actual implementation, the term will be determined by counting the number of periods that have elapsed. As the network grows and council expands, we will try to stagger the terms to make sure only a portion of the council members are up for reelection at any given election cycle.\


**Proposals** Any users holding Taraxa tokens may make proposals, but for a proposal to be heard by the council, it needs to reach at least a minimum percentage (to be determined at network launch) of the entire Taraxa token supply.
