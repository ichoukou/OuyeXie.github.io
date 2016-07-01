 - [Chinese](http://lodashjs.com/docs/)
 - [Latest](https://lodash.com/docs)
 - [Lodash 4.0.0 更新文档](http://www.tuicool.com/articles/mAfqIrv)
 - [You Might Not Need Underscore](https://www.reindex.io/blog/you-might-not-need-underscore/)
 
 - groupBy
 
<pre>
import _ from 'lodash'
console.log(_.groupBy([{code:1,value:2},{code:1,value:3},{code:2,value:4}],'code'))

{ '1': [ { code: 1, value: 2 }, { code: 1, value: 3 } ],
  '2': [ { code: 2, value: 4 } ] }
</pre>