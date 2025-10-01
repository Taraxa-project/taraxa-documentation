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

##

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

##

## Snapshot Management

The Taraxa node automatically downloads the latest blockchain snapshot on first start to speed up synchronization. The snapshot-puller container handles this process before the node starts.

### Default Behavior

By default, the snapshot-puller will:

* Check if the data directory already exists and has content
* If data exists, skip snapshot download and use existing data
* If data directory is empty, download the latest snapshot for your network and node type

### Configuration Options

You can customize the snapshot behavior using environment variables in your docker-compose.yml:

#### Network Selection

```
environment:
  - NETWORK=mainnet  # Options: mainnet (default) or testnet
```

#### Node Type

```
environment:
  - NODE_TYPE=light  # Options: light (default) or full
```

#### Custom Snapshot URL

To use a specific snapshot instead of the latest:

```
environment:
  - SNAPSHOT_URL=https://storage.googleapis.com/taraxa-snapshot/mainnet-light-db-block-19951895-20250723-044758.tar.gz
```

#### Force Fresh Snapshot Download

If you have a corrupted database or want to start fresh, use the `DELETE_DATA` flag to remove existing data and download a new snapshot:

```
environment:
  - DELETE_DATA=true  # Options: true or false (default)
```

**Warning:** Setting `DELETE_DATA=true` will permanently delete all existing blockchain data in your data directory before downloading a fresh snapshot.

##

## Light Node Performance Considerations

When running a light node (with `--light` flag), the initial pruning can take a significant amount of time as it processes and prunes historical data. If you don't want to wait for the long initial sync, you can:

1. Run your node **without** the `--light` flag (full node mode)
2. Periodically use `DELETE_DATA=true` to remove old data and download a fresh snapshot

This approach allows you to save disk space by regularly refreshing with the latest snapshot instead of maintaining full historical data, while avoiding the long sync times associated with light node initialization.

### Example Configurations

#### Standard Light Node Configuration

```
snapshot-puller:
  image: alpine:latest
  volumes:
    - ./data:/opt/taraxa_data/data
    - ./snapshot-init.sh:/snapshot-init.sh:ro
  environment:
    - NETWORK=mainnet
    - NODE_TYPE=light
    - DELETE_DATA=false
  command: /bin/sh /snapshot-init.sh
```

#### Periodic Snapshot Refresh (Alternative to Light Node)

For users who want to save space without waiting for light node sync:

```
snapshot-puller:
  image: alpine:latest
  volumes:
    - ./data:/opt/taraxa_data/data
    - ./snapshot-init.sh:/snapshot-init.sh:ro
  environment:
    - NETWORK=mainnet
    - NODE_TYPE=full
    - DELETE_DATA=true  # Set to true when you want to refresh with latest snapshot
  command: /bin/sh /snapshot-init.sh

node:
  # Run without --light flag for faster startup
  # Manually refresh snapshot periodically by setting DELETE_DATA=true and restarting
```

**Important:** After the snapshot is downloaded and your node is confirmed to be running successfully, it is **highly advisable to set `DELETE_DATA=false`**. Only switch it back to `true` when you intentionally want to force delete the data and download a fresh snapshot. Leaving `DELETE_DATA=true` permanently could result in unintended data loss on container restarts.
