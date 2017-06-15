# Deploy RabbitMQ cluster on AWS

#### From Tapgo .Inc \([http://tapgo.cc](http://tapgo.cc)\) 

# ![](/assets/rabbitmqlogo.png) + ![](/assets/AWSlogo_200x100.png)

官方推薦前3種建立 Cluster 方式

1. 手動使用 rabbitmqctl 指令
2. 定義 node config file
3. 使用 [rabbitmq-autocluster](https://github.com/aweber/rabbitmq-autocluster/) plugin
   1. 可以自動伸縮 Cluster 大小
   2. 使用 Container、consul、etcd2
   3. AWS 搭配 EC2 tag、Auto Scaling
4. docker-compose link 方式



