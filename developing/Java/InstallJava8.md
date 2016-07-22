# How to do it

```
```
<div>
<code>

1、下载JDK

从官网下载jdk8

jdk-8u5-linux-x64.tar.gz

2、解压

$ tar -zxvf jdk-8u5-linux-x64.tar.gz

解压出来是一个jdk1.8.0_51文件夹

3、将文件夹移动到安装目录

$ sudo mv jdk1.8.0_51 /usr/local/

4、配置环境变量

$ sudo gedit /etc/profile

export JAVA_HOME=/usr/local/jdk1.8.0_51 

export PATH=$JAVA_HOME/bin:$JAVA_HOME/jre/bin:$PATH 

export CLASSPATH=$CLASSPATH:.:$JAVA_HOME/lib:$JAVA_HOME/jre/lib

5、更改默认配置选项 ,依次执行如下命令

sudo update-alternatives  --install  /usr/bin/java java /usr/local/jdk1.8.0_51/bin/java 300

sudo update-alternatives  --install  /usr/bin/javac javac /usr/local/jdk1.8.0_51/bin/javac 300

and next:

sudo update-alternatives  --install  /usr/bin/jar jar /usr/local/jdk1.8.0_51/bin/jar 300

sudo update-alternatives  --install  /usr/bin/javah javah /usr/local/jdk1.8.0_51/bin/javah 300

sudo update-alternatives  --install  /usr/bin/javap javap /usr/local/jdk1.8.0_51/bin/javap 300

</code>
</div>

# install from ppa (not tested)

<pre>
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
java -version
</pre>

# Reference

- http://my.oschina.net/u/1407116/blog/227084
- https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-service.html