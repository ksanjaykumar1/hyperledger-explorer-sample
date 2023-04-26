## How to Setup
1. Copy entrie crypto artifact directory (organizations/) from your fabric network 
    ```bash
    sudo cp -r ../fabric-samples/test-network/organizations/ .
    ```
    Note: the reason behind sudo is in some instance copying of private key fails due to file permission
2. Replace your admin's private key file name in connection-profile/test-network.json , the private key is found in organizations/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp/keystore
3. Command to start up the network is
  ```shell
    $ docker-compose up -d
    ```

## Clean up

* To stop services without removing persistent data, run the following:

    ```shell
    $ docker-compose down
    ```

* In the docker-compose.yaml, two named volumes are allocated for persistent data (for Postgres data and user wallet). If you would like to clear these named volumes up, run the following:

    ```shell
    $ docker-compose down -v
    ```
Note: If explorer network setup fails then make sure to delete the Postgres (pgdata) and wallet (walletstore) volume before starting starting the network from start. If you recreate the fabric network from start then make sure to replace the organisation files i.e crypto artifacts and private in test-network.json 