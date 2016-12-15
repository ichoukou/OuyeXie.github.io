# General

 HBase 不同于一般的关系数据库,它是一个适合于非结构化数据存储的数据库.所谓非结构化数据存储就是说HBase是基于列的而不是基于行的模式，这样方面读写你的大数据内容。
 
 HBase是介于Map Entry(key & value)和DB Row之间的一种数据存储方式。就点有点类似于现在流行的Memcache，但不仅仅是简单的一个key对应一个 value，你很可能需要存储多个属性的数据结构，但没有传统数据库表中那么多的关联关系，这就是所谓的松散数据。
 
 当在生产环境中运行HBase时，它在HDFS上部运行，数据基于行键通过HDFS，如果你所有的行键都是以user-开头，那么很有可能你大部分数据都被分配一个节点上（违背了分布式数据的初衷），因此，你的行键应该是有足够的差异性以便分布式地通过整个部署。
 
# Reference

 - [HBase 超详细介绍](http://blog.csdn.net/frankiewang008/article/details/41965543)
 - [HBase的特征和优点](http://blog.jobbole.com/83614/)