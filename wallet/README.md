Start owner_api:

```
docker run -it --rm \
  -v `pwd`/keplerdata:/root/.kepler \
  --name kepler-owner-api \
  --network="host" \
  tychobrache/kepler-wallet:3.1.0-beta.2 \
  kepler-wallet -p foobar owner_api
```

- NOTE: the owner API is hard coded to bind on 127.0.0.1 for security reasons. This makes it impossible to access the port using docker's bridge network. Instead, use "host", to share the same IP stack as the host.
