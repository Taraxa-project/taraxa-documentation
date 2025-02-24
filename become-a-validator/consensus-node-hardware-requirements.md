# 🖥️ Consensus node hardware requirements

## Lite Consensus Node

Minimum system requirements for the Lite Consensus Node is,&#x20;

* 4 CPU
* 8GB Memory&#x20;
* 100GB SSD&#x20;

Most consensus nodes on the network are lite consensus nodes. The only difference between a lite node and a full node is that the lite node prunes historical state upon node restart (many community nodes periodically restar their lite nodes), while the full nodes keep everything.&#x20;

Beyond the state pruning, there is otherwise no difference between the full consensus node and the lite consensus node.&#x20;



## Full Consensus Node

Minimum system requirements for the Full Consensus Node is,&#x20;

* 4 CPU
* 8GB Memory&#x20;
* 1.5TB SSD&#x20;

The full node's state db grows very quickly, especially when transaction load is high. Over time the storage requirements will keep growing. We of course encourage you to run a full node if storage is not too big of a concern for you, just be aware that the disk requirement will keep growing.&#x20;

