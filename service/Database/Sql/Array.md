# Command

```
UPDATE users SET roles=array_append(roles, 'admin') WHERE id = 1;
```

```
UPDATE users SET roles=ARRAY[]::text[] WHERE id = 1;
```

```
select * from topics where array['t', 'f'] <@ tags;
```

# Reference

 - http://my.oschina.net/Kenyon/blog/133974