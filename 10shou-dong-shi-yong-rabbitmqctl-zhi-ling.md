使用 rabbitmqctl 指令來串 Cluster

其中有幾個前提

1. Cluster 中，每一台的 .erlang.cookie 必須要相同
   1. 可以自己指定任意字串
2. 知道 其他台的 hostname \(command line 左邊的 root@**ip-111-222-333-444**\)
   1. AWS hostname 預設為 private ip
   2. 只要知道任意一個 node，就可以加入 Cluster
3. 同個 security group

Port

* **EPMD:** 4369
* **AMQP**: 5671-5672
* **clustering**: 25672
* **http:** 15672

Filepath \([link](https://www.rabbitmq.com/relocate.html)\)

* /var/lib/rabbitmq/  **\#persistent data like the messages or queues**
* /etc/rabbitmq/rabbitmq.config **\#config**
* /var/lib/rabbitmq/mnesia/rabbit@ip-000-000-000-000 **\#Database directory**
* /var/log/rabbitmq/ip-000-000-000-000.log  **\#Log file**
* /var/log/rabbitmq/ip-000-000-000-000.log  **\#SASL Log file**
* /var/lib/rabbitmq/.erlang.cookie **\#elang.cookie**



