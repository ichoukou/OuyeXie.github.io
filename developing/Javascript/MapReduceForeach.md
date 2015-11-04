# Trick

<pre>
<code>
const users = await records.reduce(async (results, record) => {
    results = await results
    let user = await getUserById(record.user_id)
    results.push(user)
    return results
  }, []);
</code>
</pre>

# Reference

 - [如何形象地解释 JavaScript 中 map、foreach、reduce 间的区别？](http://www.zhihu.com/question/24927450)
 