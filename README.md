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

# How to run a job in the node

1. Run your [External Adapter](https://github.com/Ligo-Protocol/external-adapter-js). 

2. From the menus on the top, go to Bridge and create a bridge.

* Give any name for the bridge
* Check your localhost ip using ```ipconfig``` as docker struggles to understand localhost. 
* There must be your 'wlp6s0' or similar with 'inet value' as your IP address.
* Set it as the Bridge link. I have set it as http://192.168.254.120/8080 where the external adapter is running.

3. Follow https://docs.chain.link/docs/fulfilling-requests/ for setting a job request. Or copy paste the odometer_job.txt(uploading soon) for test.

4. Go through https://docs.chain.link/docs/jobs/ for your preferred job type. (Non need to go through this if working with odometer_job.txt)

7. Mention the bridge name that you made earlier in the job.

8. Recheck your Oracle address and bridge name, then Run the job.

