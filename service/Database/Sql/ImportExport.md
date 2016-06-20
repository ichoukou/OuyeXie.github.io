# Command

dump from shengupiao and then restore into shengupiao1 ()

```
pg_dump -h 127.0.0.1 -t stock -U shengupiao shengupiao  | psql -h 127.0.0.1 -U shengupiao shengupiao1
```

dump and restore separately (data only) -a

```
pg_dump -h 127.0.0.1 -t investors -a -U shengupiao shengupiao > investors
psql -h rdsd3u3px3pp86bw2a43.pg.rds.aliyuncs.com -p 3433 -U shengupiao shengupiao < investors
```

pg_restore can also be used

# Reference

 - http://www.postgresql.org/docs/9.4/interactive/backup-dump.html