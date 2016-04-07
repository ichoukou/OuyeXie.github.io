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

返回列表 key 中指定区间内的元素，区间以偏移量 start 和 stop 指定

```
LRANGE key start stop
```

# Reference

 - http://www.jb51.net/article/57826.htm
 - [Redis 命令参考](http://doc.redisfans.com)
 - http://www.cmky.net/?p=203
 - [删除redis所有KEY](http://ssuupv.blog.163.com/blog/static/1461567220135610456193/)