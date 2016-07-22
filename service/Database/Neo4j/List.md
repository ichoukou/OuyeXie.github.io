 - [How to push values to property array Cypher-Neo4j](http://stackoverflow.com/questions/21979782/how-to-push-values-to-property-array-cypher-neo4j)
    - c.id = c.id + 1111 
    - [check 9.3.4](http://neo4j.com/docs/developer-manual/current/#query-write)
    
 - [modifying an array property in cypher](https://groups.google.com/forum/#!topic/neo4j/bY5GXWYpM1k)
 
 - to make it work as a set:
    - match (a:Entity{id:'asdf'}) with a where not 'addd' in a.alias set a.alias = a.alias+'addd'
    - merge (a:Entity{id:'asdf'}) on create set a.alias=['lalala'] on match set a.alias = filter(x in a.alias where not x='addd')+'addd'