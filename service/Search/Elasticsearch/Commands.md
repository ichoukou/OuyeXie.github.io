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
curl "http://127.0.0.1:9200/*/_alias/*"
```

```
curl "http://182.92.242.58:9200/*/_alias/stocks"
```

```
curl "http://182.92.242.58:9200/stocks_v1/_alias/*"
```

delete alias

```
curl -X DELETE 'localhost:9288/stocks_v1462848181683/_alias/stocks'
```

add alias

```
curl -X PUT 'localhost:9288/stocks_v1462856285284/_alias/stocks'
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

```
curl -X POST -d '{
                     "query": {
                       "function_score": {
                         "query": {
                           "bool": {
                             "should": [
                               {
                                 "match": {
                                   "symbol": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 20
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "name": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 1
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "country": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 0.1
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "exchange": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 0.1
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "pinyin": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 0.5
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "pinyinParts": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 0.5
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "initial": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 0.5
                                   }
                                 }
                               },
                               {
                                 "match": {
                                   "initialParts": {
                                     "query": "bidu",
                                     "operator": "and",
                                     "boost": 0.5
                                   }
                                 }
                               }
                             ]
                           }
                         },
                         "field_value_factor": {
                           "field": "setypeScore",
                           "modifier": "square",
                           "missing": 1,
                           "factor": 1
                         },
                         "max_boost": 2
                       }
                     }
                   }
'  "http://182.92.242.58:9288/stocks/stock/_search?pretty=true"
```