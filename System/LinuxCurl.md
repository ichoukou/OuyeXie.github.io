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
curl -l -H "Content-type: application/json" -X POST -d '[[{"deleted":[],"new":[{"actor":"user:13","verb":"like","object":"answer:1","target":"answer","time":"2014-12-15T17:20:37.258","foreign_id":null,"id":"af781804-847e-11e4-8080-80012fb97b9e"}],"published_at":"2014-12-15T17:20:37.263518+00:00","feed":"user:16"}],[{"deleted":["38f81366-847f-11e4-9c94-0cc47a024be0"],"new":[],"published_at":"2014-12-15T17:20:37.263518+00:00","feed":"flat:1"}]]' "http://123.57.211.81:3011/stream_callback"
```

```
curl -l -H "Content-type: application/json" -X POST -d '[[{"deleted":[],"new":[{"actor":"user:13","verb":"like","object":"answer:160","target":"answer","time":"2014-12-15T17:20:37.258","foreign_id":null,"id":"af781804-847e-11e4-8080-80012fb97b9e"}],"published_at":"2014-12-15T17:20:37.263518+00:00","feed":"user:16"}],[{"deleted":["38f81366-847f-11e4-9c94-0cc47a024be0"],"new":[],"published_at":"2014-12-15T17:20:37.263518+00:00","feed":"flat:1"}]]' "http://127.0.0.1:3011/stream_callback"
```

```
curl -l -H "Content-type: application/json" -X POST -d '[{"feed":"notification:16","deleted":[],"published_at":"2015-12-17T03:24:44.473757+00:00","unseen":7,"new":[{"activities":[{"actor":"users:16","verb":"like","object":"answers:161","target":"answer","time":"2015-12-17T03:24:44.397887","foreign_id":"user_like_answer_activities:43","id":"b7a31c76-a46d-11e5-8080-80017155b7ee","to":["notification:16"],"origin":null}],"group":"14895_answer_answers:161_03","activity_count":1,"created_at":"2015-12-17T03:24:44.397887","updated_at":"2015-12-17T03:24:44.397887","actor_count":1,"verb":"like","is_seen":false,"id":"b7a31c76-a46d-11e5-8080-80017155b7ee","is_read":false}],"unread":7}]' "http://127.0.0.1:3011/stream_callback"
```

# Reference

 - http://blog.csdn.net/iefreer/article/details/8280345
 - [How to send a header using a HTTP request through a curl call?](http://stackoverflow.com/questions/356705/how-to-send-a-header-using-a-http-request-through-a-curl-call)
 - [wget/curl查看请求响应头信息](http://www.tuicool.com/articles/A7BRny)