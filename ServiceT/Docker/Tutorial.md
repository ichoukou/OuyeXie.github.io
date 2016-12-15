# Setup

<pre>
on a ali cloud machine

# uname -r
  3.13.0-32-generic

# apt-key list
  pub   4096R/2C52609D 2015-07-14
  uid                  Docker Release Tool (releasedocker) <docker@docker.com>

# sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
  Executing: gpg --ignore-time-conflict --no-options --no-default-keyring --homedir /tmp/tmp.CmNUclmHsN --no-auto-check-trustdb --trust-model always --keyring /etc/apt/trusted.gpg --primary-keyring /etc/apt/trusted.gpg --keyring /etc/apt/trusted.gpg.d/apt.postgresql.org.gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
  gpg: requesting key 2C52609D from hkp server p80.pool.sks-keyservers.net
  gpg: key 2C52609D: "Docker Release Tool (releasedocker) <docker@docker.com>" not changed
  gpg: Total number processed: 1
  gpg:              unchanged: 1
  
# sudo nano /etc/apt/sources.list.d/docker.list
  deb https://get.daocloud.io/docker/apt-repo ubuntu-trusty main

!!!!!!!!!SOMETHING ALREADY IN!!!!!!!!!
# ps aux | grep docker
  root       699  0.0  0.5 301808  2776 ?        Ssl  Aug25  37:49 /usr/bin/docker daemon

!!!!!!!!!DOCKER ALREADY RUNNING ON ALI CLOUD ECS!!!!!!!!!

</pre>

Continue with this [TUTORIAL](https://docs.docker.com/engine/installation/ubuntulinux/) if you are using none ali cloud machine.

# Notes

 - Because the Docker daemon uses Linux-specific kernel features, you can’t run Docker natively in OS X. Instead, you must use docker-machine to create and attach to a virtual machine (VM). This machine is a Linux VM that hosts Docker for you on your Mac.
 - Docker是目前最热门的虚拟化工具，阿里云的ECS默认支持其使用的。但由于Docker配置复杂，建议客户使用镜像市场中已经配置好的镜像生成Docker环境
 - docker stop会向容器发送一个SIGTERM信号，然后过一段时间再发送SIGKILL信号. docker kill会向容器发送一个信号（SIGKILL或者其他信号, docker kill相当于快速地强制关闭容器。但是关闭容器并非是docker kill的唯一功能，向容器发送信号也是很有用的功能。
 
# Concepts

 - In a Docker installation on Linux, your physical machine is both the localhost and the Docker host. In networking, localhost means your computer. The Docker host is the computer on which the containers run.
 - On a typical Linux installation, the Docker client, the Docker daemon, and any containers run directly on your localhost. This means you can address ports on a Docker container using standard localhost addressing such as localhost:8000 or 0.0.0.0:8376.
 
# Using

<pre>
# sudo docker info
  Containers: 0
  Images: 0
  Storage Driver: aufs
   Root Dir: /var/lib/docker/aufs
   Backing Filesystem: extfs
   Dirs: 0
   Dirperm1 Supported: false
  Execution Driver: native-0.2
  Logging Driver: json-file
  Kernel Version: 3.13.0-32-generic
  Operating System: Ubuntu 14.04.1 LTS
  CPUs: 1
  Total Memory: 488.5 MiB
  Name: iZ25faivxbmZ
  ID: G3JW:E6DU:CQYA:FO7H:XD25:QSNX:T572:OB3T:AKS3:TJBE:XAQ4:KUQM
  WARNING: No swap limit support
  
# sudo docker images
  REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
  
# sudo docker pull ubuntu

# sudo docker images
  REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
  ubuntu              latest              d55e68e6cc9c        7 days ago          187.9 MB
  
# docker run -i -t ubuntu /bin/bash       
  The -i flag starts an interactive container. The -t flag creates a pseudo-TTY that attaches stdin and stdout.
 
  To detach the tty without exiting the shell, use the escape sequence Ctrl-p + Ctrl-q. The container will continue to exist in a stopped state once exited. To list all containers, stopped and running, use the docker ps -a command.
  
#sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
  5dd882d662cc        ubuntu              "/bin/bash"         5 minutes ago       Up 4 minutes                            focused_bohr

# sudo docker attach 5dd882d662cc

EXIT with commandline "exit" this time

# sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                     PORTS               NAMES
  5dd882d662cc        ubuntu              "/bin/bash"         14 minutes ago      Exited (0) 7 seconds ago                       focused_bohr

# sudo docker rm 5dd882d662cc

# sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

# sudo docker create ubuntu:latest
  791ab1b9ae99d12fb329ba6f9a1ae7ad195c7d0d6492987dadd6728c5e1b7c0a
# sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
  791ab1b9ae99        ubuntu:latest       "/bin/bash"         5 seconds ago       Created                                 desperate_cray

# sudo docker start 791ab1b9ae99
  791ab1b9ae99

# sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED              STATUS                     PORTS               NAMES
  791ab1b9ae99        ubuntu:latest       "/bin/bash"         About a minute ago   Exited (0) 2 seconds ago                       desperate_cray

!!!!!!!!!WE CANNOT START, DID NOT CREATE CORRECTLY!!!!!!!!!

# sudo docker create -i -t ubuntu:latest /bin/bash
  b655d4769eb4671b1358c8df39bc92b0f42a376405104c89550c15c3a90c45d9

# sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
  b655d4769eb4        ubuntu:latest       "/bin/bash"         5 seconds ago       Created                                 cocky_mclean

# sudo docker start b655d4769eb4
  b655d4769eb4
  
# sudo docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
  b655d4769eb4        ubuntu:latest       "/bin/bash"         26 seconds ago      Up 4 seconds                            cocky_mclean

# sudo docker attach b655d4769eb4

!!!!!!!!!WORK NOW!!!!!!!!!

Now I want to bind host port 6000 to container's 22

# sudo docker create -i -t -p 0.0.0.0:6000:22 ubuntu:latest /bin/bash
  c624122e3790b172965d0767c155dff7bc27830aa7beed6ab648b718ca32d079
# sudo docker start c624122e3790

Try from my local machine 

# ssh 182.92.242.58 -p 6000
  ssh: connect to host 182.92.242.58 port 6000: Operation timed out
  
!!!!!!!!!!NO SSH SERVER IN CONTAINER!!!!!!!!!!

Then what? Install? Check this out: 
 - http://snoopyxdy.blog.163.com/blog/static/601174402014720113318508/
 - http://blog.csdn.net/kongxx/article/details/38395305
 - http://blog.sina.com.cn/s/blog_600e56a60102vwjc.html

</pre>

follow https://docs.docker.com/engine/userguide/basics/

# 

# Reference

 - https://github.com/docker/docker
 - https://docs.docker.com/engine/installation/
 - https://docs.docker.com/engine/installation/ubuntulinux/
 - [Video training](https://training.docker.com/self-paced-training)
 - [Using](https://docs.docker.com/engine/userguide/basics/)
 - [Ecs fundamental](https://help.aliyun.com/knowledge_detail/6504165.html?spm=5176.7114037.1996646101.21.5EJWlK&pos=11)
 - [In ecs preactice](http://oss.aliyuncs.com/aliyun_portal_storage/help/ecs/ECS%20Docker实践.pdf?spm=5176.775974866.0.0.94EdVN&file=ECS%20Docker实践.pdf)
 - [Docker hub](https://hub.docker.com)
 - [Ali docker hub](https://help.aliyun.com/knowledge_detail/5974865.html)
 - [Dao hub](https://www.daocloud.io/product/daohub)
 - [Kill vs stop](http://it.taocms.org/03/7132.htm)
 - [Useful commands](http://segmentfault.com/a/1190000000751601)
