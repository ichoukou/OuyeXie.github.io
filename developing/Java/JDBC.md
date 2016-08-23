 - [Postgresql JDBC Driver](https://jdbc.postgresql.org/documentation/documentation.html)
    - [DatabaseMetaData: getSchemas() : DatabaseMetaData « java.sql « Java by API](http://www.java2s.com/Code/JavaAPI/java.sql/DatabaseMetaDatagetSchemas.htm)
    - [关于任意结果集resultset的遍历？](http://www.iteye.com/problems/61152)
    - [Why use PreparedStatement in Java JDBC – Example Tutorial](http://javarevisited.blogspot.com/2012/03/why-use-preparedstatement-in-java-jdbc.html)
 - transcaction
    - [JDBC之七——事物处理transaction ](http://blog.sina.com.cn/s/blog_885b4ace0100z92z.html)
    - [JDBC PreparedStatement example – Batch Update](http://www.mkyong.com/jdbc/jdbc-preparedstatement-example-batch-update/)
    - [Using Transactions](https://docs.oracle.com/javase/tutorial/jdbc/basics/transactions.html)
 - jsonb
    - [INSERTING JSON DATA INTO POSTGRES USING JDBC DRIVER](http://www.pateldenish.com/2013/05/inserting-json-data-into-postgres-using-jdbc-driver.html)
 - date
    - [JDBC中的date类型 ](http://blog.163.com/qiuzhixin_momo/blog/static/350708652011430102751595/)
 - crud 
    - [使用JDBC执行 select insert update delete](http://yuncode.net/code/c_53e113f867bb427)
 - connections
     - [JAVA: MySql: too many connection](http://stackoverflow.com/questions/11564000/java-mysql-too-many-connection)
        - Normally there is limited number of connections available for user. Additionally, establishing connections is costly operation. Therefore, if you experience performance problems you should start using connection pool, discussion about connection pools
        - Suggestion to increase number of connections is similar to advising a person with diarrhea to eat more food.
     - [com.mysql.jdbc.exceptions.jdbc4.MySQLNonTransientConnectionException: in mysql](http://stackoverflow.com/questions/1392304/com-mysql-jdbc-exceptions-jdbc4-mysqlnontransientconnectionexception-in-mysql/1392333#1392333)
        - I solved the problem by increasing number of connection (set @@global.max_connections = 1250;)
     - [在tomcat下配置jdbc连接池点滴](http://www.cnblogs.com/ventry/archive/2012/03/13/2394047.html)
     - up to date
        - [HikariCP](https://github.com/brettwooldridge/HikariCP)
        - [HikariCP —— 另外一款高性能的 JDBC 连接池](http://www.tuicool.com/articles/mMneMv)
     - out of date / outdated
        - [The DBCP Component](http://commons.apache.org/proper/commons-dbcp/)
        - [c3p0](https://github.com/swaldman/c3p0)
     - [best approach for returning connection objects to hikaricp pool](http://stackoverflow.com/questions/25367261/best-approach-for-returning-connection-objects-to-hikaricp-pool)   
        -As with most connection pools, Hikari doesn't give you an actual JDBC Connection when you ask for one. What it does instead is give you a proxy that implements the Connection interface. In the case of Hikari - it's a ConnectionProxy object.
        
 - Hibernate
    - [Hibernate ORM](http://hibernate.org/orm/)
        -Hibernate ORM enables developers to more easily write applications whose data outlives the application process. As an Object/Relational Mapping (ORM) framework, Hibernate is concerned with data persistence as it applies to relational databases (via JDBC). 
        
 - [Efficient way to Handle ResultSet in Java](http://stackoverflow.com/questions/7507121/efficient-way-to-handle-resultset-in-java)
<pre>
public List resultSetToArrayList(ResultSet rs) throws SQLException{
  ResultSetMetaData md = rs.getMetaData();
  int columns = md.getColumnCount();
  ArrayList list = new ArrayList(50);
  while (rs.next()){
     HashMap row = new HashMap(columns);
     for(int i=1; i<=columns; ++i){           
      row.put(md.getColumnName(i),rs.getObject(i));
     }
      list.add(row);
  }

 return list;
}
</pre>