# lesson04

## AWS上に新しくVPCを作成
![newVPC](img/img-lecture04/lesson04-vpc.png)

### サブネット
![VPCsubnet](img/img-lecture04/lesson04-vpc-subnet.png)

## EC2とRDSを構築

## EC2
![newEC2](img/img-lecture04/lesson04-ec2.png)

### EC2のセキュリティグループ
![EC2-security](img/img-lecture04/lesson04-ec2-security.png)

## RDS
![newRDS](img/img-lecture04/lesson04-newRDS.png)
### RDSの詳細とセキュリティグループ
![RDS-detail-01](img/img-lecture04/lesson04-rds-detail01.png)
![RDS-detail-02](img/img-lecture04/lesson04-rds-detail02.png)
![RDS-security](img/img-lecture04/lesson04-rds-security.png)

## EC2からRDSへの接続をし、正常であることを確認
![EC2 connect to RDS](img/img-lecture04/lesson04-ec2-rds-connect.png)

## 学び
・ RDSにパブリックのサブネットが接続できると、誰でもRDSを閲覧できてしまうので望ましくない。
<br>・ セキュリティグループが重複しないようにする
<br>・ ルールは許可のルールは必要最低限で書くのが基本
