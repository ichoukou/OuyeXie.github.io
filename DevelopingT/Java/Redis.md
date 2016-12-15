maven does not have to use the same version
 
 - [使用Jedis操作Redis](http://www.devnote.cn/article/352.html)
 - [jedis](https://github.com/xetorthio/jedis)
 - [Welcome to the jedis wiki!](https://github.com/xetorthio/jedis/wiki)
 - [using Jedis in a multithreaded environment](https://github.com/xetorthio/jedis/wiki/Getting-started)
    - You shouldn't use the same instance from different threads because you'll have strange errors. And sometimes creating lots of Jedis instances is not good enough because it means lots of sockets and connections, which leads to strange errors as well. A single Jedis instance is not threadsafe! To avoid these problems, you should use JedisPool, which is a threadsafe pool of network connections. You can use the pool to reliably create several Jedis instances, given you return the Jedis instance to the pool when done. This way you can overcome those strange errors and achieve great performance.
<pre>
<code>
You use it by:
/// Jedis implements Closable. Hence, the jedis instance will be auto-closed after the last statement.
try (Jedis jedis = pool.getResource()) {
  /// ... do stuff here ... for example
  jedis.set("foo", "bar");
  String foobar = jedis.get("foo");
  jedis.zadd("sose", 0, "car"); jedis.zadd("sose", 0, "bike"); 
  Set<String> sose = jedis.zrange("sose", 0, -1);
}
/// ... when closing your application:
pool.destroy();
If you can't use try-with-resource, you can still enjoy with Jedis.close().
Jedis jedis = null;
try {
  jedis = pool.getResource();
  /// ... do stuff here ... for example
  jedis.set("foo", "bar");
  String foobar = jedis.get("foo");
  jedis.zadd("sose", 0, "car"); jedis.zadd("sose", 0, "bike"); 
  Set<String> sose = jedis.zrange("sose", 0, -1);
} finally {
  if (jedis != null) {
    jedis.close();
  }
}
/// ... when closing your application:
pool.destroy();
</code>
</pre>