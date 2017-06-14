與 Cluster 相關的幾個 docker 服務

* **docker-machine** 來控制多台機器，除了 virtualbox，還可建立、管理 EC2、GCP、Azure
* **docker-swarm** 來整合多台機器，形成叢集
* **docker network** 將特定幾台機器，指定互相連接的方式 \(network level\)
* **docker service** 將 build 好的 docker image，部署到 N 台機器，且能夠即時伸縮 scale



這邊要建立 AWS machine，需先完成 awscli 安裝

安裝完成，直接下一下指令即可建立一個 hostname 為 aws-01 的 instance

```
$ docker-machine create aws-01 \
--driver amazonec2 \
--amazonec2-region ap-northeast-1 \
--engine-install-url https://experimental.docker.com
```

查詢是否執行中

```
$ docker-machine ls
```

![](/assets/螢幕快照 2017-06-14 下午2.53.45.png)

SSH 連入

```
$ docker-machine ssh aws-03
```

接著從 Step1 開始安裝，也能達到同樣結果



