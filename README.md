# Tyk tourist

## Start redis

```
docker-compose up -d tyk-redis
```

## Start mongo

```
docker-compose up -d tyk-mongo
```

## Start tyk-gateway

```
docker-compose up -d tyk-gateway
```

## Start and bootstrap tyk-dashboard

```
docker-compose up -d tyk-dashboard
./bootstrap.sh 0.0.0.0
```

```
http://your-host:3000
```

When we visit this url, we can see a page need a licensee, we can apply the licensee from tyk. Then we can use the username/password login the tyk-dashboard.

## Setup first api

- in dashboard, it is easy to new an api, I set the api name as "test".
- visit, http://your-host:8080/test/get, it return "error": "Authorization field missing".

