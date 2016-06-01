# Introduction

- connect browser

 http://localhost:7474/browser/
 
- connect server
 :server connect
 
- delete all

    - We can delete all nodes with relationships,
```
MATCH (n)
DETACH DELETE n
```
    - simple command to delete all nodes and relationships:
```
MATCH (n)
OPTIONAL MATCH (n)-[r]-()
DELETE n,r
```
 
# Reference
 
 - [Cypher Query Language](http://neo4j.com/docs/developer-manual/current/#cypher-query-lang)
 - [Graph Visualization with Neo4j](http://neo4j.com/graph-visualization-neo4j/)
 - [Using Neo4j from Java](http://neo4j.com/developer/java/)
 - [How to delete/create databases in Neo4j?](http://stackoverflow.com/questions/4498523/how-to-delete-create-databases-in-neo4j)
 - [Neo4J get node by ID](http://stackoverflow.com/questions/22369520/neo4j-get-node-by-id)
 - [Adding relationship to existing nodes with Cypher](http://stackoverflow.com/questions/20456002/adding-relationship-to-existing-nodes-with-cypher)