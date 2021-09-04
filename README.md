## HOW TO START REDIS SERVER IN WSL :

Installing Redis :

```
> sudo apt-get update
> sudo apt-get upgrade
> sudo apt-get install redis-server
> redis-cli -v
```

Restart the Redis server to make sure it is running (!Important) :

```
> sudo service redis-server restart
```

Running Redis :

```
$ redis-cli
127.0.0.1:6379> set user:1 "Jane"
127.0.0.1:6379> get user:1
"Jane
```

<br>

## WHY WE USE REDIS :
```
To save key-val pair (JSON like object) in our local storage
```