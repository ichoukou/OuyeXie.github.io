 - [python with关键字用法](http://blog.sina.com.cn/s/blog_76e94d210100vybf.html)
    - 数据库的连接好像也可以和with一起使用，我在一本书上看到以下内容：
      conn = sqlite.connect("somedb")
      with conn:
          conn.execute("insert into sometable values (?,?)",("foo","bar"))
      在这个例子中，commit()是在所有with数据块中的语句执行完毕并且没有错误之后自动执行的，如果出现任何的异常，将执行rollback()
      操作，再次提示异常
 - [with-statement](http://initd.org/psycopg/docs/usage.html#with-statement)