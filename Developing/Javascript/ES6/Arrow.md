# Features

1.对 this 的关联。函数内置 this 的值，取决于箭头函数在哪儿定义，而非箭头函数执行的上下文环境。

2.new 不可用。箭头函数不能使用 new 关键字来实例化对象，不然会报错。

3.this 不可变。函数内置 this 不可变，在函数体内整个执行环境中为常量。

4.没有arguments对象。更不能通过arguments对象访问传入参数。只能使用显式命名或其他ES6新特性来完成。

# Complement

1.对箭头函数进行typeof操作会返回“function”。

2.箭头函数仍是Function的实例，故而instanceof的执行方式与传统函数一致。

3.call/apply/bind方法仍适用于箭头函数，但就算调用这些方法扩充当前作用域，this也依旧不会变化。

箭头函数与传统函数最大的不同之处在，禁用new操作。

The yield keyword may not be used in an arrow function's body (except when permitted within functions further nested within it).  As a consequence, arrow functions cannot be used as generators.

# Reference
 - http://it.010lm.com/a/biancheng/JavaScript/71147.html
 - https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/arrow_functions