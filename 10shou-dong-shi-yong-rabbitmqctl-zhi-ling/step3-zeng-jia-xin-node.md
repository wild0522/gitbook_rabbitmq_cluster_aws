先在 Master 機器，取得 erlang.cookie

```
root@ip-172-5-5-100 # cat /var/lib/rabbitmq/.erlang.cookie
PCNVWAZRZYQUUQYSYXIK
```

依照 Step 1,2 再建立一台 instance

將 Master 的 cookie 寫入 node1

```
root@ip-172-5-5-101 # echo "PCNVWAZRZYQUUQYSYXIK" > /var/lib/rabbitmq/.erlang.cookie
```

重新啟動 rabbitMQ \(重要！\)

```
root@ip-172-5-5-101 # service rabbitmq-server restart
```

脫離

```
root@ip-172-5-5-101 # rabbitmq-server -detached
```

先關閉 node1 服務

```
root@ip-172-5-5-101 # rabbitmqctl stop_app
```

將 node1 加到 master

@後面為 master 的 hostname

```
root@ip-172-5-5-101 # rabbitmqctl join_cluster rabbit@ip-172-5-5-100

#Clustering node 'rabbit@ip-172-5-5-101' with 'rabbit@ip-172-5-5-100'
```

啟動服務

```
root@ip-172-5-5-101 # rabbitmqctl start_app
```

到 master 機器，查看是否成功

```
root@ip-172-5-5-101 # rabbitmqctl cluster_status
```

若成功，running\_nodes 會多出一台

再到 Management 網頁，應該會多出一台 Node![](/assets/螢幕快照 2017-06-14 下午12.46.18.png)後面要再在增加 Node，也是相同流程

