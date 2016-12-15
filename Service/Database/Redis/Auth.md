# Setup

```
sudo nano /etc/redis/6379.conf
```

```
requirepass ##shengupio##
```

# Connect with commandline

```
redis-cli -a \#\#shengupio\#\#
```

```
redis-cli -a thereisnospoon
```

# Connect with then-redis

```
var db = redis.createClient({
  host: 'localhost',
  port: 6379,
  password: 'password'
})
```