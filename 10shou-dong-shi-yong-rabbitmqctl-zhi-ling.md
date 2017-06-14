使用 rabbitmqctl 指令來串 Cluster

其中有幾個前提

1. Cluster 中，每一台的 .erlang.cookie 必須要相同
2. 知道 其他台的 hostname \(command line 左邊的 root@**ip-111-222-333-444**\)
   1. AWS hostname 預設為 private ip
3. 同個 security group



