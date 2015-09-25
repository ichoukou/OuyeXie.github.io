# Commands:

```
db-migrate create add-indexes --sql-file
```

in the up file:

```
```
<div>
<code>
CREATE INDEX users_session_token_key ON users (session_token);

CREATE INDEX users_wx_openid_key ON users (wx_openid);

CREATE INDEX stock_symbol_key ON stock (symbol);
</code>
</div>


in the down file:

```
```
<div>
<code>
DROP INDEX users_session_token_key;

DROP INDEX users_wx_openid_key;

DROP INDEX stock_symbol_key;
</code>
</div>

to run:

```
db-migrate up -c 1
```

to run with different config file:

```
./node_modules/.bin/db-migrate create add-answer-history --sql-file --config config.json --env pg
```

```
./node_modules/.bin/db-migrate up --config config.json --env pg 
```

# References:

https://github.com/db-migrate/node-db-migrate