# Conf

<pre>

[program:stream]

command=main.py

autostart=true

autorestart=true

directory=/data/stream/gs/shengupiao-python/shengupiao-stream

user=ouyexie

redirect_stderr=true

stdout_logfile=/data/log/stream.log

</pre>

# Reference

 - http://www.jb51.net/article/55285.htm
 - http://blog.csdn.net/xiaoguaihai/article/details/44750073
 - http://blog.csdn.net/imzoer/article/details/8742729
 - [error when start](http://vv15.pbhz.com/2015/10/unlink-supervisor-1)