 - [Java中的继承与组合](http://www.importnew.com/12907.html)
    - 继承机制是有缺点的：子类依赖于父类的实现细节，如果父类产生了变更，子类的后果将不堪设想
    - 如果存在一种IS-A的关系（比如Bee“是一个”Insect），并且一个类需要向另一个类暴露所有的方法接口，那么更应该用继承的机制。
    - 如果存在一种HAS-A的关系（比如Bee“有一个”attack功能），那么更应该运用组合。