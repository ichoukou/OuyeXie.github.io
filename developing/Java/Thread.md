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

 - [](http://zhidao.baidu.com/link?url=EPlm6j0zv4yCRS2BL6mbgXq-fTMFOMwiKnBI8kCMNAuxp0v1HWfjgzkMtY79RJCpbZtjotb0boQ7Bh1fSBEP3a)