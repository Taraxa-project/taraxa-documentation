---
description: Instructions for faster syncing by use of a recent snapshot
---

# 🔀 Syncing From Snapshot

## What are Snapshots?&#x20;

Snapshots are versions of the Taraxa network's overall state.&#x20;

The Taraxa network has an extremely high throughput, and hence a very large historical state. New nodes joining the network could have a very hard time syncing and catching up with the rest of the network if they start from scratch. So snapshots of the latest network state (with some delay) are provided so that new nodes won't have to start from scratch, and also making syncing a lite node much more painless.&#x20;



## Latest Snapshots&#x20;

Snapshots are provided for the Mainnet and Testnet through an API, which returns the latest image file paths in JSON. We have stopped providing full node snapshots as the data egress charges are pretty high, we'll update if we find an affordable alternative.&#x20;

Here are some examples,&#x20;

### Mainnet&#x20;

LITE node snapshot

```
curl "https://snapshots.taraxa.io/api?network=mainnet" -s | jq -r '.light.url'
```

### Testnet

LITE node snapshot

```
curl "https://snapshots.taraxa.io/api?network=testnet" -s | jq -r '.light.url'
```



## Installing Snapshot On Local Machine

Follow the these steps:

1. Download the snapshot (link above)
2. Uncompress the snapshot archive
3. Stop the node process
4. Replace **`state_db`** and **`db`** folders into the data folder for your node. (Default path is `~/.taraxa/data` or as specified in your node config.)
5. Restart your node to begin syncing from the block height of your snapshot.

Congrats you are all done and node will sync faster than having started from the beginning!

##

## Installing Snapshot On Dockerized Node

Follow the these steps:

1. Download the snapshot (link above)
2. Uncompress the snapshot archive
3. Open a terminal and navigate to the location containing the renamed snapshot state\_db and db folders.
4. Run the following commands in the terminal to copy them into your dockerized container: \`

```bash
docker cp ./db $(docker ps --format "{{.Names}}" | grep mainnet | grep node):/opt/taraxa_data/data/db/db_new
docker cp ./state_db $(docker ps --format "{{.Names}}" | grep mainnet | grep node):/opt/taraxa_data/data/db/state_db_new
docker-compose down
docker run --rm -it -v $(docker volume ls | awk '{print $2}' | grep -i mainnet):/data alpine ash -c "cd /data/db; mv db db_bk; mv state_db state_db_bk; mv db_new db; mv state_db_new state_db"
docker-compose up -d
docker-compose logs -f
```

Congrats you are all done and node will sync faster than having started from the beginning!

