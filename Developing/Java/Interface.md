 - [java 接口 实现和继承关系](http://blog.csdn.net/lyflower/article/details/4204449)
    - java允许一个接口继承多个父接口，也允许一个类实现多个接口
 - [java接口可以继承多个接口](http://blog.sina.com.cn/s/blog_67d247c40100tr39.html)
    - 接口全都是抽象方法继承谁都无所谓，所以接口可以继承多个接口。
 - [java接口继承接口有意义吗？](http://bbs.csdn.net/topics/390757448/)
    - 比如在项目中需要N个接口，他们都要实现一些常用的功能，这样你就可以只写一个接口，然后让你的其他接口都这个接口。
    
 - Error:(20, 40) java: reference to a is ambiguous, both variable a in test.Interface1 and variable a in test.Interface2 match
 
<pre>
<code>
package test;

interface Interface1 {
	public static final int a = 1;
	public static final int b = 11;

	public void print ();
}

interface Interface2 {
	public static final int a = 2;
	public static final int c = 22;

	public void print ();
}

public class TestInterface implements Interface1, Interface2{

	public void print () {
		System.out.println(this.a);
		System.out.println(this.b);
		System.out.println(this.c);
	}
	public static void main(String[] args) {
		TestInterface testInterface = new TestInterface();
		testInterface.print();
	}
}
</code>
</pre>