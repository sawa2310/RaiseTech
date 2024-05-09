# lecture12

## 課題
    ・CircleCI のサンプルコンフィグが正しく動作するようにリポジトリに組み込む。

### CircleCIのサンプルコンフィグを実行

今回使用したサンプルコンフィグ（[config.yml](https://github.com/MasatoshiMizumoto/raisetech_documents/blob/main/aws/samples/circleci/config.yml)）

![cfn-lint](img/img-lecture12/cfn-lint.png)

### cfn-lintでエラーが発生した部分を修正

<table>
  <caption>修正内容</caption>
  <thead>
    <tr>
      <th>ファイル名</th> <th>説明</th>
    </tr>
  </thead>
  <tr>
    <td> ALB.yml </td>
     <td>24行目
     <br>`GroupName: !Sub ${AWS::StackName}-sg` を削除 </td>
  </tr>
  <tr>
    <td> EC2.yml </td>
     <td>12~14行目
      <br>`PJPrefix: 
      <br>Type: String
      <br> Default: cfn` を削除 </td>
  </tr>
  <tr>
    <td> RDS.yml </td>
     <td>55行目 
      <br>`AvailabilityZone: ap-northeast-1c` を
      <br>`AvailabilityZone: !Select
      <br>- 1 #c
      <br>- Fn::GetAZs: !Ref AWS::Region` に修正 </td>
  </tr>
  <tr>
    <td> VPC.yml </td>
     <td>98、120行目(修正前)
      <br>`AvailabilityZone: "ap-northeast-1a"` を 
      <br>`AvailabilityZone: !Select
      <br>- 0  # a
      <br>- Fn::GetAZs: !Ref AWS::Region` に修正 </td>
     <td>109.131行目(修正前)
      <br>`AvailabilityZone: "ap-northeast-1c"` を 
      <br>`AvailabilityZone: !Select
      <br>- 1  # c
      <br>- Fn::GetAZs: !Ref AWS::Region` に修正 </td>
  </tr>
</table>

### 修正後
![cfn-lint-success](img/img-lecture12/cfn-lint-success.png)
![CircleCi-success](img/img-lecture12/CircleCI-success.png)

