---
title: kafka:安装与启动
date: 2021-09-06 01:50:21
tags:  
categories: Kafka
---
### kafka配置文件在docker下的设置

将 `listeners` 设为 `PLAINTEXT://[::1]:9092`

### kafka启动

##### 启动zookeeper

 ```shell
 bin/zookeeper-server-start.sh config/zookeeper.properties
 ```
##### 启动kafka

```shell
bin/kafka-server-start.sh config/server.properties
```
##### 启动kafka生产者

```shell
bin/kafka-topics.sh --create --topic test --bootstrap-server [::1]:9092
```
##### 启动kafka消费者

```shell
bin/kafka-console-consumer.sh --topic test --from-beginning --bootstrap-server [::1]:9092 
```

