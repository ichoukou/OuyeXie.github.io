 - [How to get a count for each type of an index in elasticsearch?](http://stackoverflow.com/questions/17557580/how-to-get-a-count-for-each-type-of-an-index-in-elasticsearch)
    - url "localhost:9200/test-idx/_search?search_type=count" -d '{
          "aggs": {
              "count_by_type": {
                  "terms": {
                      "field": "_type"
                  }
              }
          }
      }'
      
 - [Elasticsearch document count returned by _stats versus _count](http://stackoverflow.com/questions/29267733/elasticsearch-document-count-returned-by-stats-versus-count)
    - Actually, the docs.count you get back from the Indices stats API also includes the count of nested documents present in the index so it will always be greater or equals than the count you get back from the Count API, which only returns the count of top-level documents, i.e. documents that would be returned from a search query. So, judging by the numbers you posted, it looks like your index contains documents with fields whose type is nested in the mapping. Sounds correct?