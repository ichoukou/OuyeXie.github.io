# Get all Routes between two nodes neo4j

<pre>
start a=node(19038), b=node(20926) match p=(a)-[r*2..3]-(b) where not((a)--(b)) with p, relationships(p) as rcoll return p, reduce(totalAmount=0.0, x in rcoll| totalAmount + toFloat(x.amount)) as t order by t DESC

start a=node(19038), b=node(20926) match p=(a)-[r*2..3]-(b) where not((a)--(b)) with p, relationships(p) as rcoll return p, length(rcoll) as t order by t DESC

MATCH p=(a:Main {code:'80446036'})-[r:Invest*1..3]-(b:Main) RETURN p, length(p) as l order by l ASC

MATCH p=(a:Main {code:'80092742'})-[r:Invest*1..4]-(b:Main {code:'80092743'}) RETURN p, length(p) as l order by l DESC
</pre>

# Reference
 
 - http://stackoverflow.com/questions/14814124/get-all-routes-between-two-nodes-neo4j
 
 - [Thoughts on Software Development neo4j/Cypher: Finding the shortest path between two nodes while applying predicates](http://www.markhneedham.com/blog/2012/05/12/neo4jcypher-finding-the-shortest-path-between-two-nodes-while-applying-predicates/)