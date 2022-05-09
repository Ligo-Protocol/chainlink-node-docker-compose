# How to use

1. Review `chainlink.env` and adapt accordingly. The committed environment file uses Kovan testnet. Also, the example uses a wss infura project url.

2. Build and run with docker-compose

* Build with default values, which you can adapt if needed inside the `Dockerfile`
```
docker-compose up --build
```

* First build with your own build args and then run:

```
$ docker-compose build --build-arg API_USER_EMAIL=my@test.com

$ docker-compose up
```

3. Browse to `localhost:6688` and log in with your credentials.

Default credentials:
- username: `"admin@admin.com"`
- password: `Admin@123`
- wallet password: `Admin@123`

4. Go to keys from the menu and Send some ether to your Regular node address. 

# Deploy Oracle.sol and fulfill Node request

1. Open [Oracle.sol](https://remix.ethereum.org/#url=https://docs.chain.link/samples/NodeOperators/Oracle.sol) 

2. Compile, In Deploy and Run tab select "Injected Web3"

3. Select Oracle.sol contract in menu and in Deploy copy the Kovan address link:

```
0xa36085F69e2889c224210F603D836748e7dC0088
```
4. Deploy with the kovan link address and confirm the metamask transaction

5. Check Keys tab in Chainklink node and copy the Regular node address. (If chainlink node isn't running yet check [this](https://github.com/Ligo-Protocol/chainlink-node-docker-compose/blob/main/README.md) link.)

6. Paste it in `SetFullfillmentPermission` function with your node address and value as `true`.

7. Recheck your node address in `getAuthorizationStatus` function to see if it is true.


# How to run a job in the node

1. Run your [External Adapter](https://github.com/Ligo-Protocol/external-adapter-js). 

2. From the menus on the top, go to Bridge and create a bridge.

* Give any name for the bridge (You will need it later in job spec).
* Check your localhost ip using ```ipconfig``` as docker struggles to understand localhost. 
* There must be your 'wlp6s0' or similar with 'inet' value as your IP address.
* Set it as the Bridge link. I have set it as http://192.168.254.120/8080 where the external adapter is running.

3. Copy paste the [odometer_job.txt](https://github.com/Ligo-Protocol/chainlink-node-docker-compose/blob/main/odometer_job.txt) as the job spec code for test. OR Follow https://docs.chain.link/docs/fulfilling-requests/ for setting a job request

4. Go through https://docs.chain.link/docs/jobs/ for your preferred job type. (No need to go through this if working with odometer_job.txt)

7. Change the bridge name to that you made earlier (default=hackathon).

8. Change Oracle address on top and bottom of the job spec to the oracle you deployed. If not deployed yet, check above 'Deploy Oracle.sol and fulfill Node request' section.

9. Recheck your Oracle address and bridge name, then Run the job.

