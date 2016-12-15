 - [java中compareTo和compare方法之比较](http://www.cnblogs.com/yueliming/archive/2013/05/22/3092576.html)
    compareTo(Object o)方法是java.lang.Comparable<T>接口中的方法，当需要对某个类的对象进行排序时，该类需要实现Comparable<T>接口的，必须重写public int compareTo(T o)方法，比如MapReduce中Map函数和Reduce函数处理的 <key,value>,其中需要根据key对键值对进行排序，所以，key实现了WritableComparable<T>接口，实现这个接口可同时用于序列化和反序列化。WritableComparable<T>接口(用于序列化和反序列化)是Writable接口和Comparable<T>接口的组合；
    compare(Object o1,Object o2)方法是java.util.Comparator<T>接口的方法，它实际上用的是待比较对象的compareTo(Object o)方法。
    
 public class User implements Comparable<Object>{
     int id;
     String name;
        
     @Override
     public int compareTo(Object o) {
         if(this ==o){
             return 0;            
         }
         else if (o!=null && o instanceof User) {   
             User u = (User) o; 
             if(id<=u.id){
                 return -1;
             }else{
             return 1;
         }
     }else{
         return -1;
     }
 }
 
 private static final Comparator<User> COMPARATOR = new Comparator<User>() {
        public int compare(User o1, User o2) {
            return o1.compareTo(o2);//运用User类的compareTo方法比较两个对象       
       }
    };