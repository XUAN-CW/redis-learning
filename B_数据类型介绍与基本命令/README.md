---
title: 数据类型介绍与基本命令
date: 2021-09-12 01:42:12
tags: 
categories: 
id: 1631382132365210900
---

# 数据库

## 简单介绍

1. redis 单机默认有 16 个数据库（可通过修改配置文件改变数据库的数量）
2. redis 集群就没有数据库的概念，或者说就一个数据库
3. 数据库下标从零开始，默认使用零号数据库

## 常用命令

[select](https://redis.io/commands/select) : Change the selected database for the current connection

[flushdb](https://redis.io/commands/flushdb) : Remove all keys from the current database

[flushall](https://redis.io/commands/flushall) : Remove all keys from all databases

# 官方数据类型介绍

 https://redis.io/topics/data-types 

# 命令介绍

这里我就不废话了，官方文档写得很清楚，Filter by group 查看自己想看的部分就行。由于外网访问不便，查询功能还没来得及加载出来，所以我在本地缓存了一份 [命令介绍](assets\references\Command reference – Redis.html) 















