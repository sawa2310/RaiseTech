# lesson04

## AWS上に新しくVPCを作成
![newVPC](img/lesson04-vpc.png)

### サブネット
![VPCsubnet](img/lesson04-vpc-subnet.png)

## EC2とRDSを構築

## EC2
![newEC2](img/lesson04-ec2.png)

### EC2のセキュリティグループ
![EC2-security](img/lesson04-ec2-security01.png)

## RDS
![newRDS](img/lesson04-newRDS.png)
### RDSの詳細とセキュリティグループ
![RDS-detail-01](img/lesson04-rds-detail01.png)
![RDS-detail-02](img/lesson04-rds-detail02.png)
![RDS-security](img/lesson04-rds-security.png)

## EC2からRDSへの接続をし、正常であることを確認
![EC2 connect to RDS](img/lesson04-ec2-rds-connect.png)

## 学び
・ RDSにパブリックのサブネットが接続できると、誰でもRDSを閲覧できてしまうので望ましくない。
<br>・ セキュリティグループが重複しないようにする
<br>・ ルールは許可のルールは必要最低限で書くのが基本
