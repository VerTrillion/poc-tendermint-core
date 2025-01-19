# poc-tendermint-core

## How to start Cluster of Nodes
1. Initialize the cluster by running the following command
    ```shell
    docker run -it --rm -v "./docker/volumes:/tendermint" tendermint/tendermint testnet
    ```
2. Get the node id of each node in the cluster
    ```shell
    docker run -it --rm -v "./docker/volumes/mytestnet/node0:/tendermint" tendermint/tendermint show_node_id
    docker run -it --rm -v "./docker/volumes/mytestnet/node1:/tendermint" tendermint/tendermint show_node_id
    docker run -it --rm -v "./docker/volumes/mytestnet/node2:/tendermint" tendermint/tendermint show_node_id
    docker run -it --rm -v "./docker/volumes/mytestnet/node3:/tendermint" tendermint/tendermint show_node_id
    ```
3. Use result of step 2. to edit `NODE0_ID`, `NODE1_ID`, `NODE2_ID`, and `NODE3_ID` in `start-cluster.sh` file
4. Run this script to start cluster 
    ```shell
    docker compose -p tendermint-testnet up -d
    ```
