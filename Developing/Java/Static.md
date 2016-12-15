 - [Java中的static关键字解析](http://www.cnblogs.com/dolphin0520/p/3799052.html)
 
    static关键字还有一个比较关键的作用就是 用来形成静态代码块以优化程序性能。static块可以置于类中的任何地方，类中可以有多个static块。在类初次被加载的时候，会按照static块的顺序来执行每个static块，并且只会执行一次。
 
    static是不允许用来修饰局部变量
    
 - [static class 静态类（Java](http://blog.sina.com.cn/s/blog_605f5b4f0100zbps.html)
 
    public static class SimpleImmutableEntry<K,V>
            implements Entry<K,V>, java.io.Serializable
    
    一般情况下，如果一个内部类不是被定义成静态内部类，那么在定义成员变量或者成员方法的时候，是不能够被定义成静态成员变量与静态成员方法的。也就是说，在非静态内部类中不可以声明静态成员。如现在在一个student类中定义了一个内部类age，如果没有将这个类利用static关键字修饰，即没有定义为静态类，那么在这个内部类中如果要利用static关键字来修饰某个成员方法或者成员变量是不允许的。在编译的时候就通不过。故程序开发人员需要注意，只有将某个内部类修饰为静态类，然后才能够在这个类中定义静态的成员变量与成员方法。这是静态内部类都有的一个特性。也正是因为这个原因，有时候少了这个静态的内部类，很多工作就无法完成。或者说要绕一个大圈才能够实现某个用户的需求。这也是静态的内部类之所以要存在的一个重要原因。
    
    后注：经过大家的指正，现声明：非静态内部类也可以定义静态成员但需要同时有final关键词修饰，静态方法鉴于无法用final修饰，仍必须是在静态内部类 或者非内部类中定义。
        BY JAVADOC (Reports methods declared final and static. When a static method is overridden in a subclass it can still be accessed via the super class, making a final declaration not very necessary. Declaring a static method final does prevent subclasses from defining a static method with the same signature.)
    静态内部类的使用限制:
        一是静态成员(包括静态变量与静态成员)的定义
        二是在成员的引用上，有比较大的限制
        三是在创建静态内部类时不需要将静态内部类的实例绑定在外部类的实例上
    
 - [Java关键字final、static使用总结](http://lavasoft.blog.51cto.com/62575/18771/)
    
    4、static和final一块用表示什么
            static final用来修饰成员变量和成员方法，可简单理解为“全局常量”！
            对于变量，表示一旦给值就不可修改，并且通过类名可以访问。
            对于方法，表示不可覆盖，并且可以通过类名直接访问。