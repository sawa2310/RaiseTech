# lecture12

## 課題
    ・CircleCI のサンプルコンフィグが正しく動作するようにリポジトリに組み込む。

### CircleCIのサンプルコンフィグを実行

今回使用したサンプルコンフィグ（[config.yml](https://github.com/MasatoshiMizumoto/raisetech_documents/blob/main/aws/samples/circleci/config.yml)）

![cfn-lint](img/img-lecture12/cfn-lint.png)

### cfn-lintでエラーが発生した部分を修正

修正内容
|  ファイル名  |  説明  |
| ---- | ---- |
|  ALB.yml  |  24行目<br>`GroupName: !Sub ${AWS::StackName}-sg` を削除  |
|  EC2.yml  |  12~14行目<br>`PJPrefix:<br>Type: String<br> Default: cfn` を削除  |
|  RDS.yml  |  55行目<br>`AvailabilityZone: ap-northeast-1c` を<br>`AvailabilityZone: !Select<br>- 1 #c<br>- Fn::GetAZs: !Ref AWS::Region` に修正  |
|  VPC.yml  |  98、120行目(修正前)<br>`AvailabilityZone: "ap-northeast-1a"` を<br>`AvailabilityZone: !Select<br>- 0  # a<br>- Fn::GetAZs: !Ref AWS::Region` に修正  |
|  VPC.yml  |  109.131行目(修正前)<br>`AvailabilityZone: "ap-northeast-1c"` を<br>`AvailabilityZone: !Select<br>- 1  # c<br>- Fn::GetAZs: !Ref AWS::Region` に修正  |

### 修正後
![cfn-lint-success](img/img-lecture12/cfn-lint-success.png)
![CircleCi-success](img/img-lecture12/CircleCI-success.png)

