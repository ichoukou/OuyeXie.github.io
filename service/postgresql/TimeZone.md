# How

```
create temporary table test(
    id int, 
    ts timestamp without time zone default (now() at time zone 'utc')
);
```

# Reference
 - http://stackoverflow.com/questions/16609724/using-current-time-in-utc-as-default-value-in-postgresql