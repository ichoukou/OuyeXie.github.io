# Commend

```
select cast('2015-10-01 00:00:00' as datetime) as new_date from user;
```

```
INSERT OVERWRITE TABLE user_meta PARTITION (ds='20160101')
SELECT 'u1' AS user_id
    , concat('age', '\003', '18') AS tags
FROM dual;
```


# Commons

 - [数据生命周期管理](数据生命周期管理)
    - 数据生命周期管理：设置表的生命周期，可以及时删除临时中间表，否则随着业务规模扩大，数据会膨胀很快。
 - shards
 - hublifecycle
    - 创建ODPS表的时候带上shards和hublifecycle参数，表示表可以在Datahub服务上使用，在这里我们把结果表也写入Datahub服务。Datahub服务会自动把写入的数据同步到ODPS表中。
 - lifecycle指明此表的生命周期
    - ODPS提供数据生命周期管理功能，方便用户释放存储空间，简化回收数据的流程。
    days 参数为生命周期时间，只接受正整数。单位：天；
    如果表table_name是非分区表，自最后一次数据被修改开始计算，经过days天后数据仍未被改动，则此表无需用户干预，
    
    将会被ODPS自动回收(类似drop table操作)。在ODPS中，每当表的数据被修改后，表的LastDataModifiedTime将会被更新，因此，
    
    ODPS会根据每张表的LastDataModifiedTime以及lifecycle的设置来判断是否要回收此表。如果table_name是分区表，
    
    则根据各分区的LastDataModifiedTime判断该分区是否该被回收。关于LastDataModifiedTime的介绍请参考 查看表信息 。
    
    不同于非分区表，分区表的最后一个分区被回收后，该表不会被删除。生命周期只能设定到表级别，不能再分区级设置生命周期。创建表时即可指定生命周期。
 - insert
    - insert overwrite/into用于将计算的结果保存目标表中。insert into与insert overwrite的区别是， insert into会向表或表的分区中追加数据，而insert overwrite则会在向表或分区中插入数据前清空表中的原有数据
    - 需要注意的是，在进行insert更新数据操作时，源表与目标表的对应关系依赖于在select子句中列的顺序，而不是表与表之间列名的对应关系， 下面的SQL语句仍然是合法的：
    - 向某个分区插入数据时，分区列不可以出现在select列表中：

# Reference

 - [ODPS简介](https://help.aliyun.com/document_detail/odps/summary/summary.html?spm=5176.docodps/summary/welcome.6.89.Fs1Hug)
 - [ODPS技术架构及应用实践](http://www.csdn.net/article/2014-10-20/2822184)
 - [数据格式规范](https://help.aliyun.com/document_detail/shujia/RE/dataspec/datauploadspec.html?spm=5176.docshujia/RE/startup/re-startup-pre2.6.263.8I7AGp)