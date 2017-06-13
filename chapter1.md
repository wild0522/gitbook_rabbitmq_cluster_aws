# 安裝 rabbitMQ

on Ubuntu 16.04

```
$ sudo -s

$ echo 'deb http://www.rabbitmq.com/debian/ testing main' | sudo tee /etc/apt/sources.list.d/rabbitmq.list

$ wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -

$ apt-get update

$ apt-get install rabbitmq-server

$ rabbitmq-plugins enable rabbitmq_management
```

測試

```
$ rabbitmqctl status
```

基本指令

啟動

```
$ service rabbitmq-server start

$ rabbitmqctl start_app #node用
```

停止

```
$ service rabbitmq-server stop

$ rabbitmqctl stop_app #node用
```



