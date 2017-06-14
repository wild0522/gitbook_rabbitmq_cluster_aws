# 安裝 rabbitMQ

先裝第一台\(node0\)，之後的 node 也是相同安裝流程

on Ubuntu 16.04

```
ubuntu@ip-172-5-5-100 # sudo -s

root@ip-172-5-5-100 # echo 'deb http://www.rabbitmq.com/debian/ testing main' | sudo tee /etc/apt/sources.list.d/rabbitmq.list

root@ip-172-5-5-100 # wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -

root@ip-172-5-5-100 # apt-get update

root@ip-172-5-5-100 # apt-get install rabbitmq-server

root@ip-172-5-5-100 # rabbitmq-plugins enable rabbitmq_management
```

新增 user \(每個節點都可登入\)

```
root@ip-172-5-5-100 # rabbitmqctl add_user 帳號 密碼
root@ip-172-5-5-100 # rabbitmqctl set_user_tags 帳號 administrator
root@ip-172-5-5-100 # rabbitmqctl set_permissions -p / 帳號 ".*" ".*" ".*"
```

登入 Management

[http://public\_ip:15672](http://public_ip:15672)

* 輸入剛剛建立的帳號、密碼![](/assets/螢幕快照 2017-06-14 下午12.22.53.png)



