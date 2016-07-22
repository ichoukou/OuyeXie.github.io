# Reference
 - [docs](http://flask.pocoo.org/docs/0.10/)
 - [Flask 的 request 和 response 对象](http://my.oschina.net/lionets/blog/410973)
 - [DEBUG模式下flask开多一个线程来监视项目的变化](https://segmentfault.com/q/1010000000446372)
 - [How to debug a Flask app](http://stackoverflow.com/questions/17309889/how-to-debug-a-flask-app)
 - [How to know what version of Flask is installed on the server [Python]](http://code.runnable.com/Uh-p2A7SSQIsAAAz/how-to-know-what-version-of-flask-is-installed-on-the-server-for-python)
 - [Deployment Options](http://flask.pocoo.org/docs/0.11/deploying/)
    - While lightweight and easy to use, Flask’s built-in server is not suitable for production as it doesn’t scale well and by default serves only one request at a time. Some of the options available for properly running Flask in production are documented here.
    - [wsgi](http://baike.baidu.com/link?url=vk7E43Eu_G1ck4VFZF-znTAgKNkJ1ZY3NGXjhLUpyQiLFfdeAoCjf2jiv7CCOeQ_5Cqu1wYfa32lybatSwHQV_)
    - [来了解一下WSGI这个概念](http://www.nowamagic.net/academy/detail/1330310)
    - [The Flask Mega-Tutorial, Part XVII: Deployment on Linux (even on the Raspberry Pi!)](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xvii-deployment-on-linux-even-on-the-raspberry-pi)
# Error
 - [Error when logging failure to parse request obscures real error](https://github.com/mitsuhiko/werkzeug/issues/832)
    - AttributeError: 'WSGIRequestHandler' object has no attribute 'environ'