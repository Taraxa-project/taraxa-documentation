---
description: Instructions for faster syncing by use of a recent snapshot
---

# 🔀 Syncing From Snapshot

_**Current latest snapshot hosted by Taraxa dev team is here:**_

{% embed url="https://storage.googleapis.com/taraxa-snapshot/snapshot.tar.gz" %}
Full Node
{% endembed %}

{% embed url="https://storage.googleapis.com/taraxa-snapshot/ln_snapshot_18938414.tar.gz" %}
Light node
{% endembed %}

## Installing Snapshot On Local Machine

Follow the these steps:

1. Download the snapshot (link above)
2. Uncompress the snapshot archive
3. Stop the node process
4. Replace **`state_db`** and **`db`** folders into the data folder for your node. (Default path is `~/.taraxa/data` or as specified in your node config.)
5. Restart your node to begin syncing from the block height of your snapshot.

Congrats you are all done and node will sync faster than having started from the beginning!

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

