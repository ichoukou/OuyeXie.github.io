#  Mac 

## Install

```
brew install postgresql
```

## Setup

### Server

```
initdb /data/postgresql/db
```

```
pg_ctl -D /data/postgresql/db -l /data/postgresql/db-log start
```
### Check

```
lsof -P -i TCP
```

### Client & Database & User

```
psql -d postgres
```

```
postgres=# \?
```

```
postgres=# \conninfo
```

```
postgres=# \password ouyexie
```

(optional)
```
postgres=# CREATE USER dbuser WITH PASSWORD 'password';
```

```
postgres=# CREATE DATABASE ouyexie OWNER ouyexie;
```

```
postgres=# GRANT ALL PRIVILEGES ON DATABASE ouyexie to ouyexie;
```

```
postgres=# \q
```

### Table

```
psql
```
<div>
<code>
ouyexie=# \c  
You are now connected to database "ouyexie" as user "ouyexie".  
ouyexie=# CREATE TABLE user_tbl(name VARCHAR(20), signup_date DATE);  
CREATE TABLE  
ouyexie=# INSERT INTO user_tbl(name, signup_date) VALUES('张三', '2013-12-22');  
INSERT 0 1  
ouyexie=# SELECT * FROM user_tbl;  
 name | signup_date   
------+-------------  
 张三 | 2013-12-22  
(1 row)  

ouyexie=# UPDATE user_tbl set name = '李四' WHERE name = '张三';  
UPDATE 1  
ouyexie=# DELETE FROM user_tbl WHERE name = '李四' ;  
DELETE 1  
ouyexie=# ALTER TABLE user_tbl ADD email VARCHAR(40);  
ALTER TABLE  
ouyexie=# ALTER TABLE user_tbl ALTER COLUMN signup_date SET NOT NULL;  
ALTER TABLE  
ouyexie=# ALTER TABLE user_tbl RENAME COLUMN signup_date TO signup;  
ALTER TABLE  
ouyexie=# ALTER TABLE user_tbl DROP COLUMN email;  
ALTER TABLE  
ouyexie=# ALTER TABLE user_tbl RENAME TO backup_tbl;  
ALTER TABLE  
ouyexie=# DROP TABLE IF EXISTS backup_tbl;  
DROP TABLE  
</code>
</div>

# FAQ

## psql: FATAL:  Peer authentication failed for user "shengupiao"

http://blog.sina.com.cn/s/blog_581df0be0101ju3o.html

local   all             postgres                                trust

local   all             all                                     md5

## psql: FATAL:  no pg_hba.conf entry for host "124.207.70.82", user "shengupiao", database "shengupiao", SSL on

http://blog.csdn.net/luweifeng1983/article/details/3980141

host    all             all             127.0.0.1/0            md5

# Reference

[1] http://www.ruanyifeng.com/blog/2013/12/getting_started_with_postgresql.html