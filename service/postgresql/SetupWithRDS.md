# Problems with Aliyun

## default user

postgres (you have to create in console)

## login

before you can connect to the instance with command line, you have to add all ips you want into white list (124.207
.70.82 is Tech Temple Office)

## create database and user

when you try to create a new data base with owner who has no privilege to do so, you get:

```
ERROR:  must be member of role "shengupiao"
```

To work around:

```
psql -U postgres -h rdsd3u3px3pp86bw2a43.pg.rds.aliyuncs.com -p 3433 shengupiao
```

then create user:

```
create user shengupiao with password 'your password with single quotes around';
```

here is the trick, add shengupiao into postgres group:

```
grant shengupiao to postgres;
```

create db:

```
create database shengupiao owner shengupiao;
```

do not forget:

```
revoke shengupiao from postgres;
```

now everything should be set;