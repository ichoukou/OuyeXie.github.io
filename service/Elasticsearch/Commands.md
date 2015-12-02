check indices

```
curl "http://182.92.242.58:9200/_cat/indices"
```

delete indices

```
curl -X DELETE "http://localhost:9288/stocks_v9"
```

check alias

```
curl "http://182.92.242.58:9200/*/_alias/stocks"
```

```
curl "http://182.92.242.58:9200/stocks_v1/_alias/*"
```

delete alias

```
curl -XDELETE 'localhost:9288/stocks_v1448595514307/_alias/stocks_test'
```

check mapping

```
curl "http://182.92.242.58:9200/stocks_v1/_mapping/stock?pretty"
```

check health

```
curl 182.92.242.58:9200/_cat/health
```

```
curl 182.92.242.58:9288/_cat/health?v
```

empty search

```
curl 'http://localhost:9288/stocks_v2/_search?pretty=true'
```

fetch doc

```
curl 'http://localhost:9288/stocks_v2/stock/52152?pretty=true'
```

```
curl 'http://localhost:9288/stocks_v2/stock/52152?pretty'
```

DSL query

```
curl -X POST -d '{"query":{"bool":{"should":[{"match":{"symbol":{"query":"A","boost":2}}},{"match":{"name":"A"}}]}}}' "http://localhost:9288/stocks_v4/_search?pretty=true"
```

```
curl -X POST -d '{"query":{"match":{"symbol":{"query":"SZ300443"}}}}' "http://localhost:9288/stocks_v7/_search?pretty=true"
```