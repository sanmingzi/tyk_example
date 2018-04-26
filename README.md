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

## Conclusion

I will give up the tyk, there are so many reasons.

- It seems that the tyk of CE version save the api definition under the folder "apps". I try to use the tyk-dashboard to save it to mongo, but I do not know whether it is right.
- There are two database(redis/mongo) used by tyk, I do not know where the api definition saved, and where the other data saved.
- I do not know the structure of tyk-gateway and tyk-dashboard until now. I think the tyk-gateway is the core service, but sometimes it is depends on tyk-dashboard.
- The auth design is not simple. When I setup my first api, I can not visit it if I did not have a key.
- The design of auth key in tyk is anti-human, when you create a key, you can not see it at the key list. The only way you can see it is search the key by it's value.
- The api of tyk-gateway is complex.
- The UI of tyk-dashboard is complex.
- I see there are apis in tyk-dashboard, but I do not understand the significance of it.
