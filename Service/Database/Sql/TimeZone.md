# How

```
create temporary table test(
    id int, 
    ts timestamp without time zone default (now() at time zone 'utc')
);
```

however, as far as I know, the way below can solve the problem instead:

```
created_at TIMESTAMP WITH TIME ZONE DEFAULT now()
```

# Reference
 - http://stackoverflow.com/questions/16609724/using-current-time-in-utc-as-default-value-in-postgresql