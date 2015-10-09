# How to expose elasticsearch to external java project

```
```
<div>
<code>
network.bind_host: 0.0.0.0

network.publish_host: 182.92.242.58 #this is my internet ip
</code>
</div>

# Command to start 

## with specific log level

```
./bin/elasticsearch -Des.logger.level=DEBUG >> /data/log/elasticsearch_20151004.log 2>& 1
```

## with specific memory config

```
./elasticsearch -f -Xmx2g -Xms2g -Des.index.storage.type=memory
```

如果是采用加-f的命令启动服务，则在当前界面可以按Ctrl+C关掉服务

### all JAVA_OPTS can be set in /etc/sysconfig/elasticsearch or even ./bin/elasticsearch.in.sh

```
ES_HEAP_SIZE=256m ./bin/elasticsearch -Des.logger.level=DEBUG >> /data/log/elasticsearch_20151004.log 2>& 1
```

<b>now I use this config to test search engine collapsing problem (linux scanning)</b>

# Reference

 - http://www.zihou.me/html/2014/01/16/9050.html
 - http://www.tuicool.com/articles/Nryu2i
