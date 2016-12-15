 - [What are 5 mistakes to avoid when using Redis?](https://www.quora.com/What-are-5-mistakes-to-avoid-when-using-Redis)

 - [Storing and Querying Objects in Redis](http://tylerstroud.com/2014/11/18/storing-and-querying-objects-in-redis/)
  
 - [Redis key design](http://stackoverflow.com/questions/24847539/redis-key-design)
 - [Redis key naming conventions?](http://stackoverflow.com/questions/6965451/redis-key-naming-conventions)
 - [Can I use redis as caching server for mysql where I need a minimum of 5 lakh hits per day. If yes how I can I do?](https://www.quora.com/Can-I-use-redis-as-caching-server-for-mysql-where-I-need-a-minimum-of-5-lakh-hits-per-day-If-yes-how-I-can-I-do)
    - The key could be an MD5 of the mysql query and when looking up, you can do an MD5 of the select query and see if the same is previously cached.