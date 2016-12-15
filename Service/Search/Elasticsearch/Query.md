 - size
    - [From / Size](https://www.elastic.co/guide/en/elasticsearch/reference/1.7/search-request-from-size.html)
        - "from" : 0, "size" : 20,
   
 - bool
    - [Elasticsearch difference between MUST and SHOULD bool query](http://stackoverflow.com/questions/28768277/elasticsearch-difference-between-must-and-should-bool-query)
    
 - terms
    - [Terms Query](https://www.elastic.co/guide/en/elasticsearch/reference/1.7/query-dsl-terms-query.html)
<pre>
{
  bool: {
    should: [
      {
        term: {
          setype: '103'
        }
      },
      {
        term: {
          setype: '104'
        }
      }
    ],
    minimum_should_match : 1
  }
}
    equals:
{
    terms : {
       setype: [ '103', '104' ],
       minimum_should_match: 1
    }
}
</pre>