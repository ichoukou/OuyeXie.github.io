 - [Chinese](http://lodashjs.com/docs/)
 - [Latest](https://lodash.com/docs)
 - [Lodash 4.0.0 更新文档](http://www.tuicool.com/articles/mAfqIrv)
 - [You Might Not Need Underscore](https://www.reindex.io/blog/you-might-not-need-underscore/)
 - [FP Guide](https://github.com/lodash/lodash/wiki/FP-Guide)
 
 - groupBy
 
<pre>
import _ from 'lodash'
console.log(_.groupBy([{code:1,value:2},{code:1,value:3},{code:2,value:4}],'code'))

{ '1': [ { code: 1, value: 2 }, { code: 1, value: 3 } ],
  '2': [ { code: 2, value: 4 } ] }
</pre>

 - memoize (watch out typing)
    - Creates a function that memoizes the result of func. If resolver is provided, it determines the cache key for storing the result based on the arguments provided to the memoized function. By default, the first argument provided to the memoized function is used as the map cache key. The func is invoked with the this binding of the memoized function. 
    - _.memoize(func, [resolver])

var result = func.apply(this, args); will return a promise, so it is OK to await from outside the function in order to get the correct result

<pre>
function memoize(func, resolver) {
  if (typeof func != 'function' || (resolver && typeof resolver != 'function')) {
    throw new TypeError(FUNC_ERROR_TEXT);
  }
  var memoized = function() {
    var args = arguments,
        key = resolver ? resolver.apply(this, args) : args[0],
        cache = memoized.cache;

    if (cache.has(key)) {
      return cache.get(key);
    }
    var result = func.apply(this, args);
    memoized.cache = cache.set(key, result);
    return result;
  };
  memoized.cache = new (memoize.Cache || MapCache);
  return memoized;
}
</pre>