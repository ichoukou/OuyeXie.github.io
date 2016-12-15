# How to query within jsonb:

```
select * from users where wx_info @> '{"nickname":"Seth"}';
```

@> means "Does the left JSON value contain within it the right value?"

```
select * from users where wx_info ？ 'nickname';
```

jsonb also has an existence operator, which is a variation on the theme of containment: it tests whether a string (given as a text value) appears as an object key or array element at the top level of the jsonb value.

# Reference:

 - http://www.postgresql.org/docs/9.4/interactive/functions-json.html#FUNCTIONS-JSONB-OP-TABLE
 - https://www.postgresql.org/docs/9.4/static/datatype-json.html