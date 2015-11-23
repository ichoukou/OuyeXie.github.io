check indices

```
curl "http://182.92.242.58:9200/_cat/indices"
```

check alias

```
curl "http://182.92.242.58:9200/*/_alias/stocks"
```

```
curl "http://182.92.242.58:9200/stocks_v1/_alias/*"
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