 - [Graph DB neo4j Installation on Ubantu](http://blog.csdn.net/robinsonmhj/article/details/18336847)
 - [Using the Debian repository](http://debian.neo4j.org/?_ga=1.227761949.1259482207.1464684579)
    - https://github.com/neo4j/neo4j/issues/7031
 - [Standalone Neo4j Server Setup on Ubuntu 14.04](http://www.codiply.com/blog/standalone-neo4j-server-setup-on-ubuntu-14-04/)
 - [2.3. Single instance install](http://neo4j.com/docs/operations-manual/current/#single-instance-install)

# Finally, I chose to install from source (why? java 8 dependency)

 - [Installing Neo4j](http://neo4j.com/download-thanks/?edition=community&release=3.0.1&flavour=unix&_ga=1.259627530.1259482207.1464684579)
    - bin/neo4j start
    - See /data/neo4j/logs/neo4j.log for current status. This means that current working dir is /data/neo4j
    - edit neo4j.conf (for 0.0.0.0 interfaces) and restart (bin/neo4j restart)