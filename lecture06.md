# lecture06

## 課題

1. 最後にAWSを利用した日の記録をCloudTrailから探し出して、イベント名と含まれている内容3つをピックアップ
2. CloudWatchアラームを使って、ALBのアラームを設定し、メール通知をしてみる
3. AWS利用料の見積を作成
4. マネージメントコンソールから現在の利用料を確認して報告


# 1. CloudTrail

![CLoudTrail](img/img-lecture06/L-06-CloudTrail.png)

* イベント名：ConsoleLogin
* ユーザー名：test-IAM1
* イベント時間：1月24,2024,15:11:22(UTC+09:00)
* イベントソース：signin.amazonaws.com

# 2. CloudWatch

### CloudWatchの設定

![ALB-detail](img/img-lecture06/ALB-detail.png)

![アクション.png](img/img-lecture06/アクション.png)

### 異常時

![ALB異常時](img/img-lecture06/ALB異常時.png)

![CloudWatch異常時](img/img-lecture06/CloudWatch-異常時.png)

### 正常時

![ALB正常時](img/img-lecture06/ALB正常時.png)

![CloudWatch正常時](img/img-lecture06/CloudWatch-正常時.png)

# 3. AWS利用料の見積

見積りを取得するには、以下のリンクを使用する必要がある。このリンクの有効期間は 1 年間。

[見積 2024/01/26](https://calculator.aws/#/estimate?id=876729dffa7c17e219c5655d668950b93b7f2ed8)

リンクに有効期限があるためスクリーンショットも掲載

![見積スクショ1](img/img-lecture06/見積１.png)

![見積スクショ2](img/img-lecture06/見積2.png)

# 4. 現在の利用料

* 12月利用料
![12月利用料](img/img-lecture06/12月利用料.png)

* EC2利用料
![EC2利用料](img/img-lecture06/EC2利用料.png)