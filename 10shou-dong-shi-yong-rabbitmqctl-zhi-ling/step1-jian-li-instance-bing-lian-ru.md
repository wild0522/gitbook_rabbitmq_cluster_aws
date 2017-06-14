先建立一台 instance，可使用 AWS web 建立，或 使用 awscli

以 awscli 為例

```
aws ec2 run-instances \
--image-id ami-xxxxxxxx \
--key-name xxxx \
--instance-type t2.nano \ 
--subnet-id subnet-xxxxxxxx \ 
--security-group-ids sg-xxxxxxxx \ 
--count 1
```

若有需要，可帶 user-data 執行 shell \(\*.即使是絕對路徑，前面還是要加 **file:// 這個 prefix**\)

```
--user-data file://rabbitmq-user-data.sh #建立後，執行
```

相關參數

* **instance-type** [https://aws.amazon.com/tw/ec2/instance-types/](https://aws.amazon.com/tw/ec2/instance-types/)
* **image-id** 可到 ami 建立後取得
* **key-name** 到 key Pairs 建立後取得
* **subnet-id** 到Elastic IPs-&gt;Network interface ID -&gt;Subnet ID
* **vpc-id** 到 security group 建立後取得
* **zone** 為 Dashboard -&gt;Avilability zone 最後一個字

### 登入 instance

可在 EC2 列表中-&gt;點擊該 instance-&gt; Connect ，會有說明![](/assets/螢幕快照 2017-06-14 上午11.59.35.png)步驟

1. 將之前建立 key-pairs 時，下載的的 \*.pem 檔，調整權限 chomd 400
2. 使用以下指令連入

```
ssh -i "yours.pem" ubuntu@your_public_dns

ex. ssh -i "aws-03.pem" ubuntu@ec2-52-199-229-182.ap-northeast-1.compute.amazonaws.com
```



