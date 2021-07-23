---
description: What / how / why's of Taraxa's public ledger
---

# Layer-1 Tech

## What's special about Block DAG? 

We chose to implement Block DAG because it is the only technology stack that can massively scale throughput and minimize latency without sacrificing security and decentralization. A super simple explanation of how this is possible is that Block DAG allows many blocks to be proposed simultaneously while making no sacrifices in security, while a single-chain topology can only admit one block at a time. 

More details: 

* Taraxa Architecture \(core section of the Whitepaper\): [https://docs.taraxa.io/tech-whitepaper/taraxa-architecture](https://docs.taraxa.io/tech-whitepaper/taraxa-architecture)
* More readable Medium articles on Taraxa's consensus: [https://medium.com/taraxa-project/tagged/taraxa-tech](https://medium.com/taraxa-project/tagged/taraxa-tech) 

## I thought DAG doesn't have blocks / DAG can't handle double-spend / DAG is feeless / ...? 

We have encountered so many misconceptions about what a directed acyclic graph \(DAG\) is that we wrote an article specifically to address them here: [https://medium.com/taraxa-project/debunking-misconceptions-about-dag-150fcc6c6e7](https://medium.com/taraxa-project/debunking-misconceptions-about-dag-150fcc6c6e7). 

Simply put, DAG is simply a data structure and different projects use it differently. People often confuse the consensus architecture with this simple data structure.  







