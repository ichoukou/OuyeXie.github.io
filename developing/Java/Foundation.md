# Memory

 - 主内存与工作内存

Java内存模型中规定了所有的变量都存储在主内存中，每条线程还有自己的工作内存（可以与前面将的处理器的高速缓存类比），线程的工作内存中保存了该线程使用到的变量到主内存副本拷贝，线程对变量的所有操作（读取、赋值）都必须在工作内存中进行，而不能直接读写主内存中的变量。不同线程之间无法直接访问对方工作内存中的变量，线程间变量值的传递均需要在主内存来完成

这里的主内存、工作内存与Java内存区域的Java堆、栈、方法区不是同一层次内存划分。

共享内存又称为堆内存，指的就是线程之间共享的内存，包含所有的实例域、静态域和数组元素。每个线程都有一个私有的，只对自己可见的内存，称之为本地内存。

 - 内存间交互操作
 - 重排序
 - 同步机制
 介绍volatile、synchronized和final
 
 对于volatile修饰的变量，jvm虚拟机只是保证从主内存加载到线程工作内存的值是最新的
 
 JAVA中Volatile的作用：强制每次都直接读内存，阻止重排序，确保voltile类型的值一旦被写入缓存必定会被立即更新到主存
 Volatile被正确使用的理想条件包括如下两点：
 1 对变量的写操作不依赖当前值。
 2 变量没有包含在具有其他变量的不变式中。
 
 - 原子性、可见性与有序性

# Thread

# GC

 - GC eden
 - finalize

# NIO

# Spring

# Mybatis

# References

 - [Java内存模型](http://www.cnblogs.com/nexiyi/p/java_memory_model_and_thread.html)
 - [Java Memory Model](http://tutorials.jenkov.com/java-concurrency/java-memory-model.html)
 - [java中volatile关键字的含义](http://www.cnblogs.com/aigongsi/archive/2012/04/01/2429166.html)
 - [Java杂谈5——关键字final与volatile](http://www.cnblogs.com/yahokuma/p/3684413.html)
 - [如何使用 volatile, synchronized, final 进行线程间通信](https://segmentfault.com/a/1190000004487149)
 - [Java synchronized详解](http://www.cnblogs.com/devinzhang/archive/2011/12/14/2287675.html)
 - [Java 多线程（六） synchronized关键字详解](http://www.cnblogs.com/mengdd/archive/2013/02/16/2913806.html)
 - [java虚拟机内存模式。栈和堆](http://rainyear.iteye.com/blog/1735121)
 - [Java 内存模型及GC原理](http://blog.csdn.net/ithomer/article/details/6252552)
 - [java并发之原子性与可见性(一)](http://blog.csdn.net/maosijunzi/article/details/18315013)
 - [深入理解Java虚拟机笔记---原子性、可见性、有序性](http://www.tuicool.com/articles/ru6vUvn)
 - [Java 内存模型及GC原理](http://blog.csdn.net/ithomer/article/details/6252552)
 - [Java中finalize()用法](http://blog.csdn.net/shanghui815/article/details/6787855)
 - [深入理解java的finalize](http://www.iteye.com/topic/484934)
 - [Java NIO系列教程（一） Java NIO 概述](http://ifeve.com/overview/)
 - [Java NIO系列教程（十二） Java NIO与IO](http://ifeve.com/java-nio-vs-io/)
    - we have more in this series
 - [Java NIO原理图文分析及代码实现 ](http://weixiaolu.iteye.com/blog/1479656)
    - I have source code
 - [贪吃的jetty被撑死了 NIO](http://blog.csdn.net/jiafu1115/article/details/39989321)
 - [MyBatis学习总结(一)——MyBatis快速入门](http://www.cnblogs.com/xdp-gacl/p/4261895.html)