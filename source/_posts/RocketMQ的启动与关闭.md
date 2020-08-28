---
title: RocketMQ的启动与关闭
date: 2020-08-28 23:48:14
tags:
- RabbitMQ
- 后端
categories: 后端
---

### 1.1. 运行Name Server

```sh
nohup sh bin/mqnamesrv &
# 查看运行日志
tail -f ~/logs/rocketmqlogs/namesrv.log
```
 
### 1.2. 运行Broker

```sh
# 通过-c参数指定配置文件 
nohup sh bin/mqbroker -n localhost:9876 -c conf/broker.conf &

# 查看运行日志
tail -f ~/logs/rocketmqlogs/broker.log
```

### 1.3. 停止服务的方式

如果需要停止RocketMQ的服务，在生产环境不建议直接用kill，应该使用以下命令

```sh
sh bin/mqshutdown broker
sh bin/mqshutdown namesrv
```

### 1.4. 运行RocketMQ Console

```sh
nohup java -jar  -Dserver.port=8090  -Drocketmq.config.namesrvAddr=localhost:9876  -Drocketmq.config.isVIPChannel=true /usr/local/rocketmq-console/rocketmq-console-ng-2.0.0.jar &
# 停止
netstat -lnpt|grep java
kill pid
```