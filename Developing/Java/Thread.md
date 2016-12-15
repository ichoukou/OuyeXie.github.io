# General

可以这样
class MyThread extends Thread{
    public void run(){
    System.out.println("Mythread 线程");
}
}
MyThread t = new Mythread();
t.start();

或者这样
Thread t = new Thread(new Runnabel(){
    public void run(){
        System.out.println("Mythread 线程");
}
});
t.start();

# Reference

 - [JAVA中Thread t = new Thread()](http://zhidao.baidu.com/link?url=EPlm6j0zv4yCRS2BL6mbgXq-fTMFOMwiKnBI8kCMNAuxp0v1HWfjgzkMtY79RJCpbZtjotb0boQ7Bh1fSBEP3a)
 - [并发队列ConcurrentLinkedQueue和阻塞队列LinkedBlockingQueue用法](http://www.cnblogs.com/linjiqin/archive/2013/05/30/3108188.html)
 - [Java四种线程池的使用](http://cuisuqiang.iteye.com/blog/2019372)
 
 - [java 多线程操作同一个变量](http://blog.csdn.net/jason_deng/article/details/17373227)
 - [Java synchronized详解](http://www.cnblogs.com/devinzhang/archive/2011/12/14/2287675.html)
 - [java笔记--关于线程同步（5种同步方式）](http://www.2cto.com/kf/201408/324061.html)
 - [Java多线程共享变量控制](http://www.2cto.com/kf/201504/389055.html)