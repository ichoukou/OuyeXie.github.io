# Introduction

- connect browser

 http://localhost:7474/browser/
 
- connect server

 :server connect
 
- delete all

    - We can delete all nodes with relationships,
    
```
MATCH (n) DETACH DELETE n
```

    - simple command to delete all nodes and relationships:
    
```
MATCH (n) OPTIONAL MATCH (n)-[r]-() DELETE n,r
```

- retrieve all with directions

```
MATCH (n)-[r]->() RETURN n,r LIMIT 100
```

```
MATCH (n)-[r]->(m) RETURN n,r,m
```

 - [Match nodes without labels](http://stackoverflow.com/questions/24247505/match-nodes-without-labels)
 
```
MATCH (n) WHERE size(labels(n)) = 0 RETURN n
```

 - [Neo4j: Match multiple labels (2 or more)](http://stackoverflow.com/questions/20003769/neo4j-match-multiple-labels-2-or-more)
 
```
MATCH n WHERE n:Male OR n:Female RETURN n
```

 - [Excluding label names in simple Neo4j Query](http://stackoverflow.com/questions/32817075/excluding-label-names-in-simple-neo4j-query)

```
MATCH (n) WHERE NOT n:Label1 AND NOT n:Label2 RETURN n
```

 - search recommendation

```
MATCH (n)-[:invest]-(x)-[:invest]-(m) WHERE n.code = "80129233" AND m.code = "80366877" RETURN n,x,m
```

 - delete relationship related
 
```
MATCH (a)-[r:Similarity]-(b) DELETE r
```

 - fetch data accordingly
 
```
match (a:Investor)-[r:Invest]->(b) return a,count(r),max(r.amount) order by a.amount DESC limit 100
match (a:Investor{code:'80000007'})-[r:Invest]->(b) return a,r.amount,b order by r.amount DESC limit 100
```

```
match (a:Investor)-[r:Invest]->(b) where r.publishint>=20160101 return a,count(r),max(r.rpayamt) order by a.rpayamt20160101 DESC limit 200
match (a:Investor)-[r:Invest]->(b) where r.publishint>=20160101 return a,r.rpayamt,r.publishdate order by a.rpayamt20160101 DESC, r.rpayamt DESC limit 10000
```

# Tools

 - Tableau
    - [tableau-neo4j-wdc](https://github.com/ralfbecher/tableau-neo4j-wdc/blob/master/docu/Neo4jWdc-Docu.pdf)
    - [Neo4j + Tableau Visual Analytics - GraphConnect SF 2015](http://www.slideshare.net/neo4j/neo4j-tableau-visual-analytics-graphconnect-sf-2015)
    - [The ability to create network graphs is not functionality built into the product](http://kb.tableau.com/articles/issue/creating-network-graph?lang=zh-cn)
    
# Reference

 - [Neo4j Documentation](http://neo4j.com/docs/) 
     - [The Neo4j Developer Manual v3.0](http://neo4j.com/docs/developer-manual/current/)
        - [collect](http://www.ttlsa.com/nosql/how-to-neo4j-cypher-query-language/)
        - [percentile](http://www.2cto.com/database/201210/162822.html)
     - [Cypher Query Language](http://neo4j.com/docs/developer-manual/current/#cypher-query-lang)
     - [Graph Visualization with Neo4j](http://neo4j.com/graph-visualization-neo4j/)
     - [Using Neo4j from Java](http://neo4j.com/developer/java/)
 - [How to delete/create databases in Neo4j?](http://stackoverflow.com/questions/4498523/how-to-delete-create-databases-in-neo4j)
 - [Neo4J get node by ID](http://stackoverflow.com/questions/22369520/neo4j-get-node-by-id)
 - [Adding relationship to existing nodes with Cypher](http://stackoverflow.com/questions/20456002/adding-relationship-to-existing-nodes-with-cypher)