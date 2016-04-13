# General

Tornado is a Python web framework and asynchronous networking library, originally developed at FriendFeed. By using non-blocking network I/O, Tornado can scale to tens of thousands of open connections, making it ideal for long polling, WebSockets, and other applications that require a long-lived connection to each user.

# Comparison

 - flask
 
    相对来说，flask比较简单，flask用的几个核心库都是相同的作者开发的，有保证，如果想入门，从flask入门比较不错。而且，flask的资料也非常多，Github有很多使用flask的开源项目。
    
    Tornado大了一点说其实应该算是一个异步框架和Web框架，Web框架是其中的一部分功能；flask则更加简单一些，就是一个Web框架。tornado的并发处理比flask强。
    
    就简单灵活易用来说，用flask是比较合适的。另外一点flask的文档和扩展都比tornado要好。


# Reference

 - http://www.tornadoweb.org/en/stable/