 - [5.5. Parameters](http://neo4j.com/docs/developer-manual/current/#cypher-intro)
    - Cypher supports querying with parameters. This means developers don’t have to resort to string building to create a query. In addition to that, it also makes caching of execution plans much easier for Cypher.
      
    - Parameters can be used for literals and expressions in the WHERE clause, for the index value in the START clause, index queries, and finally for node/relationship ids. Parameters can not be used as for property names, relationship types and labels, since these patterns are part of the query structure that is compiled into a query plan.