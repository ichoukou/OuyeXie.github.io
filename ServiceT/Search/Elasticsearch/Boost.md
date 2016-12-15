# Tutorial

 - https://www.elastic.co/search?q=boost&section=Docs%2FElasticsearch%2FReference%2F1.7
 
 - [query time boosting](http://es.xiaoleilu.com/170_Relevance/20_Query_time_boosting.html)
 - [index time boosting](https://www.elastic.co/guide/en/elasticsearch/reference/1.7/mapping-core-types.html)
 - [mapping](http://blog.csdn.net/an74520/article/details/13772619)
 
 - [Function Score Query](https://www.elastic.co/guide/en/elasticsearch/reference/1.7/query-dsl-function-score-query.html)
 - [function score chinese version](http://blog.csdn.net/dm_vincent/article/details/42201721)
 
# FAQ

 - script_score the script could not be loaded scripts of type [inline], operation [search] and lang [groovy] are disabled
    - add following to /etc/elasticsearch/elasticsearch.yml
    # enable dynamic script
      script.groovy.sandbox.enabled: true
      script.inline: on
      script.indexed: on
      script.search: on
      script.engine.groovy.inline.aggs: on