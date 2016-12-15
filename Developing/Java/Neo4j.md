 - [Using Neo4j from Java](http://neo4j.com/developer/java/)
    - Using Neo4j’s Embedded Java API, As a JVM developer you are also on the bright side when it comes to inserting large amounts of data into Neo4j. With its non-transactional, highly-concurrent batch-insertion APIs it can ingest billions of nodes and relationships in just minutess.

 - [java连接neo4j之内嵌式](http://www.cnblogs.com/visoncheng/p/4136187.html)
 
 - [Java实现Neo4j数据库的相关操作](http://blog.csdn.net/ace_luffy/article/details/8788707)
 
 - [Neo4j图数据库应用开发之一：Neo4j Java 工具包](http://www.2cto.com/database/201512/452677.html)
 
 - [Optimizing high volume batch inserts into Neo4j using REST](http://stackoverflow.com/questions/19839469/optimizing-high-volume-batch-inserts-into-neo4j-using-rest)
 
 - [Interface Session](http://alpha.neohq.net/docs/java-driver/org/neo4j/driver/v1/Session.html)
 - [Interface Session](http://neo4j.com/docs/api/java-driver/current/index.html?org/neo4j/driver/v1/Session.html)
    - Session objects are not thread safe, if you want to run concurrent operations against the database, simply create multiple sessions objects.
    
 - Exception
    - [Resolve issue where pooled connections could leak if exception occurred](https://github.com/neo4j/neo4j-java-driver/pull/167)
        - That'll bubble up to the application layer - but this is good, if the pool rejects the connection return, that's a fatal problem that should get reported to the user. IllegalStateException happens whenever the pool state is corrupted, so this is good.
        
 - [release notes](https://github.com/neo4j/neo4j-java-driver/releases)
 
 - [changelog](https://github.com/neo4j/neo4j-java-driver/wiki/1.1-changelog#110-m01)