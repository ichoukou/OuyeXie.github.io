# Command

```
curl -X POST "http://localhost:9288/stocks_v4/_search?pretty=true"
```

```
curl -X POST -d '{"from":0,"size":1}' "http://localhost:9288/stocks_v4/_search?pretty=true"
```

```
curl -X POST -d '{"query":{"bool":{"should":[{"match":{"symbol":{"query":"A","boost":2}}},{"match":{"name":"A"}}]}}}' "http://localhost:9288/stocks_v4/_search?pretty=true"
```
