# Description

bind方法会创建一个新函数,称为绑定函数.当调用这个绑定函数时,绑定函数会以创建它时传入bind方法的第一个参数作为this,传入bind方法的第二个以及以后的参数加上绑定函数运行时本身的参数按照顺序作为原函数的参数来调用原函数

# Code

this._onReplace.bind(this)

# Function Bind Syntax

let log = ::console.log

# Related To

getChildContext

call apply (function is invoked) bind (return a function without calling it)

call([thisObj[,arg1[, arg2[,   [,.argN]]]]]) 

apply([thisObj[,argArray]]) 

# Reference

 - http://my.oschina.net/blogshi/blog/265415
 - http://segmentfault.com/a/1190000002891125#articleHeader2
 - https://www.tildedave.com/2014/11/15/introduction-to-contexts-in-react-js.html
 - http://blog.csdn.net/xxb2008/article/details/7862956
 - http://www.cnblogs.com/cosiray/p/4512969.html
 - http://uule.iteye.com/blog/1158829