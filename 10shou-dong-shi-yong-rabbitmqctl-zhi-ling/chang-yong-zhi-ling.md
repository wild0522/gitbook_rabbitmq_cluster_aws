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

查看 Cluster 清單

```
$ rabbitmqctl cluster_status
```

查權限清單\( 指定hostpath\)

```
$ rabbitmqctl list_permissions [-p VHostPath]
```

查單一 User

```
$ rabbitmqctl list_user_permissions User
```

清除 User 的權限 \(帳號還會在\)

```
$ rabbitmqctl clear_permissions [-p VHostPath] User
```

刪除已離線的 node

```
$ rabbitmqctl forget_cluster_node rabbit@hostname
```



