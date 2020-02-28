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

# datadog-serverless-functions

This repository contains our serverless functions that process streams and send data to datadog

- For AWS, [go here](./aws/README.md)
- For Azure, [go here](./azure/README.md)
