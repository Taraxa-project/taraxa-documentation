---
description: List of critical on-chain bridge-related contracts and addresses.
---

# 📜 On-chain contracts

The dev team is publishing all on-chain contracts critical to the operation of the bridge to maximize transparency as well as to minimize risk of fraud.&#x20;



## Bridge infrastructure contracts&#x20;

These contracts are part of the core [Ficus Root Bridge](https://bridge.taraxa.io/) infrastructure. They are upgradable so from time to time the code they point to may change, but these addresses will stay the same.&#x20;



On the Ethereum network,&#x20;

* ETH\_bridge: 0x359CF536b1fd6248ebAd1449E1B3727caB33A01d&#x20;
* TARA\_client: 0xcDF14446F78ea7EBCaa62Fdb0584e4D2e536B999&#x20;

On the Taraxa network,&#x20;

* TARA\_bridge: 0xe126E0BaeAE904b8Cfd619Be1A8667A173b763a1&#x20;
* ETH\_client: 0x7157233800c3c1f2ac8b12Cefe2cBE796C04446B&#x20;
* BeaconLightClient: 0x97Eb8E024bE036eCdb25aDf842C5D6241189FB53&#x20;



## Asset contracts deployed by the core dev team

The Ficus Root Bridge is fully permissionless, which means anyone can deploy asset connector contracts and register them with the bridge contracts. But since these deployments are completely permissionless and anonymous, there is no way for anyone to know if the asset connectors are fraudulent.&#x20;

Here we publish a list of asset connector contracts that are deployed by the core Taraxa development team for maximum transparency. This list will grow over time as the core development team deploy more.&#x20;



On the Ethereum network,&#x20;

* TARA token on ETH: `0x2F42b7d686ca3EffC69778B6ED8493A7787b4d6E`

On the Taraxa network,&#x20;

* ETH token on TARA: `0x39b1fC930C43606af5C353e90a55db10bCaF4087`
* USDT (Tether) token on TARA: `0x69D411CbF6dBaD54Bfe36f81d0a39922625bC78c`



