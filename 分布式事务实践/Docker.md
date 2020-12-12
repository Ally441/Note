## Docker

##### Docker介绍

- 是一种轻量级容器（Docker是使用操作系统级别的虚拟化技术，然后对进程、文件系统、网络等资源进行分装和隔离，让别人看上去是一个独立系统，所以叫容器）
- 与虚拟机的异同(Docker是直接在操作系统把一部分进程、文件系统、网络等隔离，让人觉得是一个独立系统)
- 使用方便

1. Docker镜像—docker资源库
2. Docker容器—Dockerfile
3. Docker服务—docker-compose
4. Docker集群—swam、Kubernetes

Docker解决了什么问题？

- 我本地运行没问题，上服务器有问题(Docker解决运行环境不一致带来的问题)
- 系统好卡，哪个哥们又写死循环了？！(Linux多个用户，当一个用户写了死循环导致占用CPU等资源，可以使用Docker)
- 双11来了，服务器撑不住啦！

Docker核心技术：

1. docker镜像
2. docker容器
3. docker仓库

###### Docker镜像

就是一系列的文件(运行程序文件、运行环境文件等)。Docker 镜像是由文件系统叠加而成(是一种文件的存储形式)。最底端是一个文件引 导系统，即 bootfs，这很像典型的 Linux/Unix 的引导文件系统。Docker 用户几乎永远不会和 引导系统有什么交互。实际上，当一个容器启动后，它将会被移动到内存中，而引导文件系 统则会被卸载，以留出更多的内存供磁盘镜像使用。Docker 容器启动是需要一些文件的， 而这些文件就可以称为 Docker 镜像。

###### Docker容器

本质就是一个进程

###### Docker仓库

​	构造Docker镜像主要是在其他服务器上使用，把镜像上传到Docker仓库，其他服务器从Docker仓库获取Docker镜像

- Docker仓库url:hub.docker.com ；国内url:  c.163.com



docker镜像：

- docker pull [OPTIONS] NAME[:TAG]   从仓库拉取镜像

- docker images 显示本机有哪些镜像

- docker run 运行镜像

  ![image-20201115160516649](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201115160516649.png)

  ###### Docker网络

  - 网络类型
    - Bridge
    - Host
    - None
  - 端口映射

  ![image-20201115170902583](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201115170902583.png)

###### 制作自己的镜像

- Dockerfile
- docker build

###### Docker安装MySQL

**安装： `docker run --name mysql1 mysql.mysql-server:5.7`**

**运行：**`docker start  mysql1`











