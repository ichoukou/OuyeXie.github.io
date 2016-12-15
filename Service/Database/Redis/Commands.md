# Command

to start:

```
redis-server [&]
```

to connect:

```
redis-cli
```

```
redis-cli -a "##shengupiao##"
```

to list all keys:

```
keys *
```

to get database info:

```
info
```

to switch database:

```
select 0/1/...
```

to clear a database or the server

```
flushdb
```

```
flushall
```

```
//删除当前数据库中的所有Key
flushdb
//删除所有数据库中的key
flushall
```

list connection info

```
CLIENT LIST
```

get string 

```
get key
```

delete key

```
del key
```

type of value

```
type key
```

获取在哈希中的所有值

```
HVALS key 
```

由索引返回一个成员范围的有序集合。

```
ZRANGE key start stop [WITHSCORES] 
```

移除有序集 key 中的一个或多个成员，不存在的成员将被忽略

```
ZREM key member [member ...]
```

返回列表 key 中指定区间内的元素，区间以偏移量 start 和 stop 指定

```
LRANGE key start stop
```

LASTSAVE Return the UNIX TIME of the last DB save executed with success

```
lastsave
(integer) 1468556816
```

EXPIRE key seconds

!!!seconds!!!

```
redis> SET mykey "Hello"
OK
redis> EXPIRE mykey 10
(integer) 1
redis> TTL mykey
(integer) 10
redis> SET mykey "Hello World"
OK
redis> TTL mykey
(integer) -1
```

TTL key
Returns the remaining time to live of a key that has a timeout. 

```
redis> TTL mykey
(integer) 10
```

批量删除Key
注：keys 指令可以进行模糊匹配，但如果 Key 含空格，就匹配不到了，暂时还没发现好的解决办法。

```
redis-cli -a password keys "*" | xargs redis-cli -a password del
```

# Reference

 - http://www.jb51.net/article/57826.htm
 - [Redis 命令参考](http://doc.redisfans.com)
 - http://www.cmky.net/?p=203
 - [删除redis所有KEY](http://ssuupv.blog.163.com/blog/static/1461567220135610456193/)
 - [http://redis.io/commands](http://redis.io/commands)