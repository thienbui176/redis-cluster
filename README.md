# Redis Cluster in Docker on osx

Using port from 7500 ~ 75xx

### start the redis cluster

```run
docker-compose up -d
```

### Các file docker-compose v3, 09,08,09, 06-07 dùng để test thêm node

### connect to cluster

```
redis-cli -c -p 7500
```

### to stop the cluster

```
docker-compose down
```

### to install redis-cli

```
brew install redis-cli
```

### example output in cli

```
○ → redis-cli -c -p 7500 -a myredis
127.0.0.1:7500> set foo bar
-> Redirected to slot [12182] located at 127.0.0.1:7002
OK
127.0.0.1:7002> set hello world
-> Redirected to slot [866] located at 127.0.0.1:7500
OK
127.0.0.1:7500> get foo
-> Redirected to slot [12182] located at 127.0.0.1:7002
"bar"
127.0.0.1:7002> get hello
-> Redirected to slot [866] located at 127.0.0.1:7500
"world"
```
