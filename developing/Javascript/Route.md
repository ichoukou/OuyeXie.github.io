# Description

<pre>
<code>
var routes = (  
  <Routes location="hash">
    <Route path="/" handler={App}>
      <Route path="books" name="bookList" handler={Books}>
          <Route path=":bookId" name="book" handler={Book}/>
      </Route>
      <Route path="movies" name="movieList" handler={Movies}>
          <Route path=":movieId" name="movie" handler={Movie}/>
      </Route>
      <DefaultRoute handler={Welcome}/>
    </Route>
  </Routes>
);

和之前的路由对象类似，需要嵌套的路由直接进行嵌套即可（完全就是字面意思嘛），但是注意到我们的<Route>的path变成了一个奇怪的形式，「:bookId」和「:movieId」是什么意思？熟悉express的同学应该对这样的路由形式不会陌生，这定义了路由接受的一个参数，简单的说 /moview/:movieId 定义了一个规则，当访问 /moviews/123 的时候，程序会自动把 123 提取出来当做名为 movieId 的参数。
</code>
</pre>

<pre>
<code>
router.param(['id', 'page'], function (req, res, next, value) {
  console.log('CALLED ONLY ONCE with', value);
  next();
})

app.get('/user/:id/:page', function (req, res, next) {
  console.log('although this matches');
  next();
});

app.get('/user/:id/:page', function (req, res) {
  console.log('and this matches too');
  res.end();
});
On GET /user/42/3, the following is printed:

CALLED ONLY ONCE with 42
CALLED ONLY ONCE with 3
although this matches
and this matches too
</code>
</pre>

# React Router

http://undefinedblog.com/react-router-0-13-3/

# Reference

 - http://undefinedblog.com/react-router/
 - http://www.expressjs.com.cn/4x/api.html#router
 - [A modern JavaScript router in 100 lines](http://krasimirtsonev.com/blog/article/A-modern-JavaScript-router-in-100-lines-history-api-pushState-hash-url)
 - [sammy.js](http://sammyjs.org/docs/routes)
 - [React Router](https://github.com/rackt/react-router/blob/0.13.x/docs/guides/overview.md)