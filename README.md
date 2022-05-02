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

4. Browse to `localhost:6688` and log in with your credentials.

Default credentials:
- username: `"admin@admin.com"`
- password: `Admin@123`
- wallet password: `Admin@123`

