#### Q1.Node statistics not available

![](/assets/螢幕快照 2017-06-14 下午12.53.10.png)該 node 需啟用 management

```
$ rabbitmq-plugins disable rabbitmq_management
```

#### Q2.Error: Mnesia is still running...

```
$ rabbitmqctl stop_app
```

#### Q3.Error: unable to connect to nodes \[rabbit@xxxxxxx\]: nodedown

* 請檢查 Master 的 hostname 是否正確
* 4369 port 是否開啟
* 有可能 hostname 找不到，則須在 /etc/hosts 加入對應 ip

```
vi /etc/hosts
xxxxxxx 111.222.333.444 #master_hostname master_ip
```



