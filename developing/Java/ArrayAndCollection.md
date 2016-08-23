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
 - [Java TreeMap的排序（转）](http://blog.sina.com.cn/s/blog_530fe9870100l5oy.html)
<pre>
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
</pre>
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

 - [Java的HashMap和HashTable](http://www.cnblogs.com/devinzhang/archive/2012/01/13/2321481.html)
    - Hashtable 中的方法是同步的，而HashMap中的方法在缺省情况下是非同步的。在多线程并发的环境下，可以直接使用Hashtable，但是要使用HashMap的话就要自己增加同步处理了。
    - Hashtable中，key和value都不允许出现null值。