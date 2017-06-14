使用兩項 awscli 指令達成半自動 add Node

* run-instances --user-data
* describe-instances --filters



運作流程

1. 找出 tag:Name 相同者，第一筆的 Private DNS
2. 使用這個 hostname 來與 Cluster 串連



Shell Script

[https://github.com/wild0522/awscli\_add\_rabbitmq\_node](https://github.com/wild0522/awscli_add_rabbitmq_node)







