 - 深入理解java虚拟机
    - bookmark 4.2.7 (20160909)
    - bookmark 154 (20160928)
    - bookmark 173 (20161018)
    - bookmark 211(page) (20161020)
    - bookmark 195 (20161021)
    - bookmark 239 (20161027)
    - bookmark 279 (20161028)
        - JEE->JBOSS, OSGi
    - bookmark 302 (20161103)
    - bookmark 329 (20161103)
    - bookmark 355 (20161104)
    - bookmark 403 (20161107)
    - done
    
 - [How to find a Java thread running on Linux with ps -axl?](http://stackoverflow.com/questions/9934517/how-to-find-a-java-thread-running-on-linux-with-ps-axl)
    - jps
    - jstack
    
# Configurations

 - [-D](https://zhidao.baidu.com/question/196052852.html)
    - java已有默认系统属性，通过：System.getProperties().list(System.out);查看。可以使用java -D修改这些属性，也可以创建自己的程序属性，如：java -Djava.io.tmpdir=d:\，修改临时文件存放目录
    
 - [-d32 and -d64](http://wenku.baidu.com/link?url=ucdBju4EMFKviI7yL6JuFeztzjpmT63FdfdHQSunUM87-UEUBxkVyFfnmXuuK_HRTOcmgwqMeFDwekEE-0qvFc9qXzMRdzrqtcgqJQPLybS)
    - java命令中用-d32和-d64来表明程序运行在32位或者64位环境。如果JVM本身不支持该参数，会报告错误。当前仅有java hotspot server VM支持64位模式。选择 "-server"选项必须使用-d64；"-client"选项会忽略使用-d64；如果没有指定-d32或者-d64，则默认运行在32位模式。除非仅有64位系统。
 
 - [-XX:InitialCodeCacheSize and -XX:ReservedCodeCacheSize](http://ifeve.com/useful-jvm-flags-part-4-heap-tuning/)
    - -XX:InitialCodeCacheSize and -XX:ReservedCodeCacheSize

 - [-XX:+UseCompressedOops](http://javarevisited.blogspot.tw/2012/06/what-is-xxusecompressedoops-in-64-bit.html)
    - -XX:+UseCompressedOops JVM command line option is one of the most talked options of 64 bit JVM. Though 64 bit JVM allows you to specify larger Java heap sizes it comes with a performance penalty by using 64 bit OOPS. Ordinary object pointers also known as OOPS which is used to represent Java objects in Virtual Machine has an increased width of 64 bit than smaller 32 bit from earlier 32 bit JVM. because of increased size of OOPS, fewer OOPS can be stored in CPU cache registers which effectively reduced CPU cache efficiency. -XX:+UseCompressedOops enables the use of compressed 32 bit OOPS in 64 bit JVM which effectively compensate performance penalty imposed by 64 bit JVM without scarifying heap size advantage offered by them. You should use -XX:+UseCompressedOops if maximum heap size specified by -Xmx is less than 32G.

 - [-Xss](http://www.cnblogs.com/redcreen/archive/2011/05/04/2037057.html) 
    - 每个线程的堆栈大小 JDK5.0以后每个线程堆栈大小为1M,以前每个线程堆栈大小为256K.更具应用的线程所需内存大小进行 调整.在相同物理内存下,减小这个值能生成更多的线程.但是操作系统对一个进程内的线程数还是有限制的,不能无限生成,经验值在3000~5000左右一般小的应用， 如果栈不是很深， 应该是128k够用的 大的应用建议使用256k。这个选项对性能影响比较大，需要严格的测试。（校长）和threadstacksize选项解释很类似,官方文档似乎没有解释,在论坛中有这样一句话:"”-Xss is translated in a VM flag named ThreadStackSize”一般设置这个值就可以了。
    
 - [-ea](http://developer.51cto.com/art/201009/227526.htm)
    - 上述JVM启动参数就用来设置jvm是否启动断言机制（从JDK1.4开始支持），缺省时jvm关闭断言机制。用-ea可打开断言机制，不加<packagename>和classname时运行所有包和类中的断言，如果希望只运行某些包或类中的断言，可将包名或类名加到-ea之后。
    
 - [-Dsun.io.useCanonCaches=false](http://stackoverflow.com/questions/7479198/canonical-file-path-in-java-optimization-problem)
    - Try disabling Java's canonicalization cache. This can be done by setting the system properties sun.io.useCanonCaches and sun.io.useCanonPrefixCache to false.
    - So by default, the cache canonicalization is on, but when you specify the VM arg -Dsun.io.useCanonCaches=false, the cache is never used.
      Getting back to the puzzler, the first call to TESTDIR_SYMLINK.getCanonicalPath() always returns the path to the symlink, while the second call returns either the cached value (the path to the symlink) or the up-to-date resolved symlink, but only when -Dsun.io.useCanonCaches=false is specified.
        - http://konigsberg.blogspot.tw/2009/10/answer-to-symbolic-puzzler.html
    
 - [-Djava.net.preferIPv4Stack=true](http://www.micmiu.com/lang/java/java-net-ipv4-ipv6/)
    - 在实际的运用中有以下几种办法可以实现指定获取IPv4的地址
         
 - [-XX:+UseCodeCacheFlushing](http://ifeve.com/useful-jvm-flags-part-4-heap-tuning/)
    - 如果代码缓存不断增长，例如，因为热部署引起的内存泄漏，那么提高代码的缓存大小只会延缓其发生溢出。为了避免这种情况的发生，我们可以尝试一个有趣的新参数：当代码缓存被填满时让JVM放弃一些编译代码。通过使用-XX:+UseCodeCacheFlushing 这个参数，我们至少可以避免当代码缓存被填满的时候JVM切换到interpreted-only 模式。不过，我仍建议尽快解决代码缓存问题发生的根本原因，如找出内存泄漏并修复它。
    
 - [-XX:+UseConcMarkSweepGC](http://www.cnblogs.com/redcreen/archive/2011/05/04/2037057.html)
    - 使用CMS内存收集
 
 - [-XX:SoftRefLRUPolicyMSPerMB=50](http://www.cnblogs.com/redcreen/archive/2011/05/05/2038331.html)
    - 这个参数我认为可能有点用，官方解释是softly reachable objects will remain alive for some amount of time after the last time they were referenced. The default value is one second of lifetime per free megabyte in the heap，我觉得没必要等1秒；
 
 - [-XX:MinHeapFreeRatio=40](http://www.blogjava.net/bitbit/archive/2009/11/30/304247.html)
    - GC后，如果发现空闲堆内存占到整个预估堆内存的40%，则放大堆内存的预估最大值，但不超过固定最大值。(什么是预估堆内存？见 -XX:MaxHeapFreeRatio 处的描述)
 
 - [-XX:MaxHeapFreeRatio=70](http://www.blogjava.net/bitbit/archive/2009/11/30/304247.html)
    - GC后，如果发现空闲堆内存占到整个预估堆内存的70%，则收缩堆内存预估最大值。
      什么是预估堆内存？
      预估堆内存是堆大小动态调控的重要选项之一。
      堆内存预估最大值一定小于或等于固定最大值(-Xmx指定的数值)。
      前者会根据使用情况动态调大或缩小，以提高GC回收的效率。
 
 - [-Xincgc](http://blog.csdn.net/witsmakemen/article/details/38585919)
    - 第四种为Incremental Low Pause GC，适用于要求缩短因GC造成程序停滞的时间。这种GC可以在Young区回收的同时，回收一部分Old区对象。-Xincgc参数启动该GC