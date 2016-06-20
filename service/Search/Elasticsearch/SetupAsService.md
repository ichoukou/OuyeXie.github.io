# How

## Install with apt

<pre>
<code>

wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -

echo "deb http://packages.elastic.co/elasticsearch/1.7/debian stable main" | sudo tee -a /etc/apt/sources.list.d/elasticsearch-1.7.list

sudo apt-get update && sudo apt-get install elasticsearch

</code>
</pre>

## Setup as service and start

<pre>
<code>

sudo update-rc.d elasticsearch defaults 95 10

sudo /etc/init.d/elasticsearch start

</code>
</pre>

The init script is placed at /etc/init.d/elasticsearch as you would expect it

The configuration file is placed at /etc/default/elasticsearch

The ES_HOME dir is /usr/share/elasticsearch/

CONF_DIR

Configuration file directory (which needs to include elasticsearch.yml and logging.yml files), defaults to /etc/elasticsearch

CONF_FILE

Path to configuration file, defaults to /etc/elasticsearch/elasticsearch.yml

## What I should do before launching

### copy data (indices) Or reindex (I prefer this)

### customize elasticsearch.yml, logging.yml and /etc/default/elasticsearch

<pre>
<code>

# Note, that for development on a local machine, with small indices, it usually
# makes sense to "disable" the distributed features:
#
index.number_of_shards: 1
index.number_of_replicas: 0

# Path to directory where to store index data allocated for this node.
#
#path.data: /path/to/data
path.data: /data/elasticsearch/data

# 
# Can optionally include more than one location, causing data to be striped across
# the locations (a la RAID 0) on a file level, favouring locations with most free
# space on creation. For example:
#
#path.data: /path/to/data1,/path/to/data2

# Path to temporary files:
#
#path.work: /path/to/work

# Path to log files:
#
#path.logs: /path/to/logs
path.logs: /data/elasticsearch/log 

# Set the bind address specifically (IPv4 or IPv6):
#
#network.bind_host: 192.168.0.1
network.bind_host: 0.0.0.0

# Set the address other nodes will use to communicate with this node. If not
# set, it is automatically derived. It must point to an actual IP address.
#
#network.publish_host: 192.168.0.1
network.publish_host: 182.92.242.58

# Set a custom port for the node to node communication (9300 by default):
#
#transport.tcp.port: 9300
#transport.tcp.port: 9300

# Enable compression for all communication between nodes (disabled by default):
#
#transport.tcp.compress: true

# Set a custom port to listen for HTTP traffic:
#
#http.port: 9200
http.port: 9288

</code>
</pre>

<pre>
<code>

#es.logger.level: INFO 
es.logger.level: DEBUG

</code>
</pre>


### install plugins

# Reference

 - https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-repositories.html
 - https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-service.html
