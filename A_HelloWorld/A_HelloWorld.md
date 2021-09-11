---
title: hello_redis
date: 2021-09-12 01:03:24
tags: 
- redis
- docker
categories: 
id: 1631379804811362200
---



# 官方资料

## 官网

1. 项目地址: https://github.com/redis/redis
2. redis 官网: https://redis.io/ 
3. 文档: https://github.com/redis/redis-doc 
4. github项目及其相关项目: https://github.com/redis 

## 资料

1. redis 命令摘要: [commands.json](http://htmlpreview.github.io/?https://github.com/redis/redis-doc/blob/master/commands.json) 
2. 文档: [网站源码](https://github.com/redis/redis-io) 
3. 命令: [在线浏览](https://redis.io/commands) | [md文件](https://github.com/redis/redis-doc/tree/master/commands) 

# docker 安装

##  下载

```sh
docker pull redis:6.2.3
```

## 安装与启动

### 创建目录

```sh
# 在/usr/local目录下创建docker目录
mkdir /usr/local/docker
cd /usr/local/docker
# 再在docker目录下创建redis目录
mkdir redis && cd redis
# 创建数据存储目录data
mkdir data
```

### redis.conf

将官网 [redis.conf](https://github.com/redis/redis/blob/unstable/redis.conf) 文件配置复制下来进行 [修改](assets\references\docker安装redis.html)，这里我改好了，上传 [redis.conf](assets/data) 到 `/usr/local/docker/redis` 即可

### 启动

```sh
docker run -itd --restart=always -p 6379:6379 --name redis -v a/usr/local/docker/redis/redis.conf:/etc/redis/redis.conf -v /usr/local/docker/redis/data:/data -d redis:6.2.3 redis-server /etc/redis/redis.conf --appendonly yes
```

## 简单使用

进入容器后查看版本信息、进行简单的插入与查询

```shell
root@ubuntu-bionic:~# docker exec -it redis /bin/bash
root@4ca8a673bf21:/data# redis-cli -v 
redis-cli 6.2.3
root@4ca8a673bf21:/data# redis-cli
127.0.0.1:6379> set k1 vi 
OK
127.0.0.1:6379> get k1
"vi"
127.0.0.1:6379> 
```

