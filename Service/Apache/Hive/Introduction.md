 - [初始Hive —— 深入浅出学Hive ](http://sishuok.com/forum/blogPost/list/6220.html)
    - [Hive QL](http://sishuok.com/forum/blogPost/list/0/6227.html)
        - [Hive的insert操作](http://blog.csdn.net/yeruby/article/details/23039009)
        
 - [Hive入门指南](http://blog.csdn.net/zhoudaxia/article/details/8842576)
    - data type （2）复杂类型：
                   Structs： structs内部的数据可以通过DOT（.）来存取，例如，表中一列c的类型为STRUCT{a INT; b INT}，我们可以通过c.a来访问域a。
                   Maps（Key-Value对）：访问指定域可以通过['element name']进行，例如，一个Map M包含了一个group->gid的k-v对，gid的值可以通过M['group']来获取。
                   Arrays：array中的数据为相同类型，例如，假如array A中元素['a','b','c']，则A[1]的值为'b'。
                   
 - [GettingStarted](https://cwiki.apache.org/confluence/display/Hive/GettingStarted)