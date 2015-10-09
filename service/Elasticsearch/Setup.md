# How to expose elasticsearch to external java project

```
```
<div>
<code>
network.bind_host: 0.0.0.0

network.publish_host: 182.92.242.58 #this is my internet ip
</code>
</div>

# Command to start with specific log level

```
./bin/elasticsearch -Des.logger.level=DEBUG >> /data/log/elasticsearch_20151004.log 2>& 1
```