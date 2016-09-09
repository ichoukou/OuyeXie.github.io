# Error
 
 - Error: Ready check failed: NOAUTH Authentication required. / (error) NOAUTH Authentication required.
   - restart redis (```/etc/init.d/redis-6379 restart```)
   - kill and start (```rm /var/run/redis_6379.pid```)
 - 在redis 中存储中文，读取会出现乱码（其实不是乱码，只是不是我们存的中文显示）
    - http://www.cnblogs.com/lyl6796910/p/3879284.html
    - redis-cli --raw