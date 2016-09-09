 - [Java入门记(四)：容器关系的梳理（上）——Collection](http://www.cnblogs.com/wuyuegb2312/p/3867293.html)
 - [Java入门记(五)：容器关系的梳理（下）——Map](http://www.cnblogs.com/wuyuegb2312/p/4458468.html)
    - [解析WeakHashMap与HashMap的区别详解](http://www.jb51.net/article/36948.htm)
        - WeakHashMap，此种Map的特点是，当除了自身有对key的引用外，此key没有其他引用那么此map会自动丢弃此值
    - [深入理解WeakHashmap](http://mikewang.blog.51cto.com/3826268/880775/)
        - 引用对象的四种分类：
          1. 强引用（Strong Reference）
          2. 弱引用（Weak Reference）
          3. 软引用（Soft Reference）
          4. 幻象引用（Phantom Reference）
          
 - [Class EnumSet<E extends Enum<E>>](http://docs.oracle.com/javase/7/docs/api/java/util/EnumSet.html)
    - public abstract class EnumSet<E extends Enum<E>>
      extends AbstractSet<E>
      implements Cloneable, Serializable
 
 - [java - Fastest way to check if a byte array is all zeros](http://stackoverflow.com/questions/23824364/fastest-way-to-check-if-a-byte-array-is-all-zeros/23824753)
    - check answer 0
    
 - [How do I convert Double[] to double[]](http://stackoverflow.com/questions/1109988/how-do-i-convert-double-to-double)
    - check answer 64 (common.lang)
    
 - [java中的 Set转List](http://blog.csdn.net/linan0930/article/details/14214645)
    - List<String> list1 = new ArrayList<String>(set);
    - List<String> list2 = new ArrayList<String> ();  list2.addAll(set);  
    
 - [Set.toArray方法——用Set集合中的所有对象创建一个数组](http://book.2cto.com/201309/31817.html)
 
 - [java中数组与List相互转换的方法](http://blog.csdn.net/justfornn413/article/details/5348203)
    - String[] arr = (String[])list.toArray(new String[size]);
    
    - String[] arr = new String[] {"1", "2"};
    - List list = Arrays.asList(arr);
 
 - [JAVA数组初始化](http://wenwen.sogou.com/z/q69635729.htm)
    - string[] str = new string[]{1,2,3}       或       string[] str = {1,2,3}              二维数组初始化       int[][] a={{1,2,3},{2,3,4},{1,0}}
    
 - [java的数据类型有基本类型和引用类型。数组属于什么类型？ [问题点数：20分，结帖人OnlyOneLove]](http://bbs.csdn.net/topics/330044718)
    - 引用 Object
    
 - [How can I Initialize a static Map?](http://stackoverflow.com/questions/507602/how-can-i-initialize-a-static-map)

<pre>
import java.util.HashMap;
import java.util.Map;

public class Test {
    private static final Map<Integer, String> myMap = new HashMap<Integer, String>();
    static {
        myMap.put(1, "one");
        myMap.put(2, "two");
    }

    private static final Map<Integer, String> myMap2 = new HashMap<Integer, String>(){
        {
            put(1, "one");
            put(2, "two");
        }
    };
}
</pre>

 - [Java技巧之双括弧初始化](http://blog.csdn.net/ligaoyang/article/details/4410379)

 - [For initializing a map in Java 8](http://stackoverflow.com/questions/507602/how-can-i-initialize-a-static-map/37384773#37384773)
<pre>
import java.util.AbstractMap.*;
private static final Map<Integer, String> myMap = Stream.of(
            new SimpleEntry<>(1, "one"),
            new SimpleEntry<>(2, "two"),
            new SimpleEntry<>(3, "three"),
            new SimpleEntry<>(4, "four"),
            new SimpleEntry<>(5, "five"),
            new SimpleEntry<>(6, "six"),
            new SimpleEntry<>(7, "seven"),
            new SimpleEntry<>(8, "eight"),
            new SimpleEntry<>(9, "nine"),
            new SimpleEntry<>(10, "ten"))
            .collect(Collectors.toMap((se) -> se.getKey(), (se) -> se.getValue()));
</pre>

 - [Map 值增加的最高效的方法 —— 只一次搜索键](http://www.oschina.net/translate/most-efficient-way-to-increment-a-map-value-in-java-only-search-the-key-once)
 - [Map 按值排序 (Map sort by value) - Java](http://blog.csdn.net/srjklssj/article/details/6324880)
 - [TreeMap按照key排序](http://huangqiqing123.iteye.com/blog/1461163)
<pre>
Map<Double, List<String>> rankings = new TreeMap<>(new Comparator() {
            public int compare(Object o1, Object o2) {
                //如果有空值，直接返回0
                if (o1 == null || o2 == null)
                    return 0;
                return -String.valueOf(o1).compareTo(String.valueOf(o2));
            }
        });
</pre>

<pre>
package test.tool.gui.common;  
  
import java.util.Comparator;  
import java.util.TreeMap;  
  
public class Test {  
      
    public static void main(String[] args) {  
          
        //不指定排序器  
        TreeMap<String, String> treeMap1 = new TreeMap<String, String>();  
        treeMap1.put("2", "1");  
        treeMap1.put("b", "1");  
        treeMap1.put("1", "1");  
        treeMap1.put("a", "1");  
        System.out.println("treeMap1="+treeMap1);  
  
        //指定排序器  
        TreeMap<String, String> treeMap2 = new TreeMap<String, String>(new Comparator<String>(){  
  
            /* 
             * int compare(Object o1, Object o2) 返回一个基本类型的整型， 
             * 返回负数表示：o1 小于o2， 
             * 返回0 表示：o1和o2相等， 
             * 返回正数表示：o1大于o2。 
             */  
            public int compare(String o1, String o2) {  
              
                //指定排序器按照降序排列  
                return o2.compareTo(o1);  
            }     
        });  
        treeMap2.put("2", "1");  
        treeMap2.put("b", "1");  
        treeMap2.put("1", "1");  
        treeMap2.put("a", "1");  
        System.out.println("treeMap2="+treeMap2);  
    }  
} 

treeMap1={1=1, 2=1, a=1, b=1}  
treeMap2={b=1, a=1, 2=1, 1=1} 

</pre>

 - [Java的HashMap和HashTable](http://www.cnblogs.com/devinzhang/archive/2012/01/13/2321481.html)
    - Hashtable 中的方法是同步的，而HashMap中的方法在缺省情况下是非同步的。在多线程并发的环境下，可以直接使用Hashtable，但是要使用HashMap的话就要自己增加同步处理了。
    - Hashtable中，key和value都不允许出现null值。
    
 - [What's the simplest way to print a Java array?](http://stackoverflow.com/questions/409784/whats-the-simplest-way-to-print-a-java-array)
    - Arrays.toString(doubleArray)
    - Arrays.deepToString(deepArray)
    
 - [Java 7之集合类型 - Vector与Stack](http://www.2cto.com/kf/201402/280227.html)