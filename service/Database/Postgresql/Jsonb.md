# How to query within jsonb:

```
select * from users where wx_info @> '{"nickname":"Seth"}';
```

@> means "Does the left JSON value contain within it the right value?"

# Reference:

 - http://www.postgresql.org/docs/9.4/interactive/functions-json.html#FUNCTIONS-JSONB-OP-TABLE