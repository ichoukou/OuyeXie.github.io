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

post json
```
curl -l -H "Content-type: application/json" -X POST -d '[[{"deleted":[],"new":[{"actor":"user:1","verb":"like","object":"answer:1","target":"answer","time":"2014-12-15T17:20:37.258","foreign_id":null,"id":"af781804-847e-11e4-8080-80012fb97b9e"}],"published_at":"2014-12-15T17:20:37.263518+00:00","feed":"user:2"}],[{"deleted":["38f81366-847f-11e4-9c94-0cc47a024be0"],"new":[],"published_at":"2014-12-15T17:20:37.263518+00:00","feed":"flat:1"}]]' "http://123.57.211.81:3011/stream_callback"
```

# Reference

 - http://blog.csdn.net/iefreer/article/details/8280345