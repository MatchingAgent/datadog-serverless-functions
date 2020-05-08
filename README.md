# forked from DataDog/datadog-serverless-functions
[logs_monitoring](https://github.com/MatchingAgent/datadog-serverless-functions/tree/master/aws/logs_monitoring) をカスタマイズして使用するのが目的です  
`Datadog Forwarder` 以外の使用は想定していません  

## 変更点
Datadog Forwarder Lambdaに設定されるIAMポリシー
```
- Effect: Allow
  Action:
  - s3:GetObject
  Resource: 'arn:aws:s3:::*'
```
を削除して使用しています

## 運用
### リソースの作成
[aws/logs_monitoring/template.yaml](https://github.com/MatchingAgent/datadog-serverless-functions/blob/master/aws/logs_monitoring/template.yaml)をAWSコンソールからCloudFormationに入力してリソースの作成を行いました  

### Fowarder Lambdaのトリガーの設定
作成さた `tapple-datadog-forwarder-Forwarder` というLambdaにAWSコンソールからトリガーの追加を行っています  
subscribeするCloudWatch Log Groupを追加したい場合はコンソールから設定してください  
