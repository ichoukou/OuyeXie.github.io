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

### make sure data and log dir can be read and written by user elasticsearch

drwxrwxr-x 2 elasticsearch elasticsearch 4096 Jul 14 18:18 data
drwxrwxr-x 2 elasticsearch elasticsearch 4096 Jul 14 18:18 log

### copy data (indices) Or reindex (I prefer this)

### customize elasticsearch.yml, logging.yml and /etc/default/elasticsearch

 - 1.7

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

 - 2.3
 
<pre>
# ======================== Elasticsearch Configuration =========================
#
# NOTE: Elasticsearch comes with reasonable defaults for most settings.
#       Before you set out to tweak and tune the configuration, make sure you
#       understand what are you trying to accomplish and the consequences.
#
# The primary way of configuring a node is via this file. This template lists
# the most important settings you may want to configure for a production cluster.
#
# Please see the documentation for further information on configuration options:
# <http://www.elastic.co/guide/en/elasticsearch/reference/current/setup-configuration.html>
#
# ---------------------------------- Cluster -----------------------------------
#
# Use a descriptive name for your cluster:
#
# cluster.name: my-application
cluster.name: elasticsearch
#
# ------------------------------------ Node ------------------------------------
#
# Use a descriptive name for the node:
#
# node.name: node-1
#
# Add custom attributes to the node:
#
# node.rack: r1
#
# ----------------------------------- Paths ------------------------------------
#
# Path to directory where to store the data (separate multiple locations by comma):
#
# path.data: /path/to/data
path.data: /data/elasticsearch/data
#
# Path to log files:
#
# path.logs: /path/to/logs
path.logs: /data/elasticsearch/log 
#
# ----------------------------------- Memory -----------------------------------
#
# Lock the memory on startup:
#
# bootstrap.mlockall: true
#
# Make sure that the `ES_HEAP_SIZE` environment variable is set to about half the memory
# available on the system and that the owner of the process is allowed to use this limit.
#
# Elasticsearch performs poorly when the system is swapping the memory.
#
# ---------------------------------- Network -----------------------------------
#
# Set the bind address to a specific IP (IPv4 or IPv6):
#
# network.host: 192.168.0.1
#network.host: 123.56.89.3
network.host: 0.0.0.0
#
# Set a custom port for HTTP:
#
# http.port: 9200
#
# For more information, see the documentation at:
# <http://www.elastic.co/guide/en/elasticsearch/reference/current/modules-network.html>
#
# --------------------------------- Discovery ----------------------------------
#
# Pass an initial list of hosts to perform discovery when new node is started:
# The default list of hosts is ["127.0.0.1", "[::1]"]
#
# discovery.zen.ping.unicast.hosts: ["host1", "host2"]
#
# Prevent the "split brain" by configuring the majority of nodes (total number of nodes / 2 + 1):
#
# discovery.zen.minimum_master_nodes: 3
#
# For more information, see the documentation at:
# <http://www.elastic.co/guide/en/elasticsearch/reference/current/modules-discovery.html>
#
# ---------------------------------- Gateway -----------------------------------
#
# Block initial recovery after a full cluster restart until N nodes are started:
#
# gateway.recover_after_nodes: 3
#
# For more information, see the documentation at:
# <http://www.elastic.co/guide/en/elasticsearch/reference/current/modules-gateway.html>
#
# ---------------------------------- Various -----------------------------------
#
# Disable starting multiple nodes on a single system:
#
# node.max_local_storage_nodes: 1
#
# Require explicit names when deleting indices:
#
# action.destructive_requires_name: true
</pre>

### install plugins

# Reference

 - https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-repositories.html
 - https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-service.html
