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