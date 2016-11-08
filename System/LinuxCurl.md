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

```
curl -b 'gr_user_id=1ccc9957-54eb-405c-812a-c0d1b54d5c69; _uab_collina=147331730005340124077473; _umdata=6AF5B463492A874D8EAC0027A4CE562049B919081BA2637789A0FBB4F612AFF0297FA9B00F9065D0E3786C4B83A30CBB18753A3C20AC84EFD5BD8548CEA51788F1D13A53D57A4E0D287CBAA57B2CE3814A8B51291C76D9EDD0FF37A156C67FCB0C89DB8EB63A09AC; PHPSESSID=se6s2hrlnqe2g7pu4v6ubhkth3; CNZZDATA1254842228=1204001312-1471310346-http%253A%252F%252Fwww.qichacha.com%252F%7C1477901063; gr_session_id_9c1eb7420511f8b2=de860864-d2df-4870-92d0-a5082a33b941' "http://www.qichacha.com/cms_map?keyNo=057373f0a21eea7b5f56ec3a983d3d3e&upstreamCount=4&downstreamCount=4"
```

# Reference

 - http://blog.csdn.net/iefreer/article/details/8280345
 - [How to send a header using a HTTP request through a curl call?](http://stackoverflow.com/questions/356705/how-to-send-a-header-using-a-http-request-through-a-curl-call)
 - [wget/curl查看请求响应头信息](http://www.tuicool.com/articles/A7BRny)
 - [Linux curl命令详解](http://www.linuxdiyf.com/linux/2800.html)
    - -b/--cookie <name=string/file>    cookie字符串或文件读取位置