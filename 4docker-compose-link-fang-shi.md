使用 [harbur](https://github.com/harbur)/[**docker-rabbitmq-cluster**](https://github.com/harbur/docker-rabbitmq-cluster)

```
$ git clone https://github.com/harbur/docker-rabbitmq-cluster.git
$ cd cd docker-rabbitmq-cluster
```

build image 

```
$ docker build -t harbur/rabbitmq-cluster .
```

Run

```
$ docker-compose up -d
```

連到 Management 查看 node 狀況，應該可以看到 3 台

[http://localhost:15672](http://localhost:15672)



#### 增加 Node

```
$ nano docker-compose.yml
```

最下方再增加 rabbit4

```
rabbit4:
  image: harbur/rabbitmq-cluster
  hostname: rabbit4
  links:
    - rabbit1
    - rabbit2
    - rabbit3
  environment:
    - ERLANG_COOKIE=abcdefg
    - CLUSTER_WITH=rabbit1
  ports:
    - "5675:5672"
```

Build

```
$ docker build -t harbur/rabbitmq-cluster .
```

Run \(不會影響到已經在執行的 node\)

```
$ docker-compose up -d rabbit4
```

連到 Management 查看 node 狀況，應該變成 4 台

[http://localhost:15672](http://localhost:15672)

