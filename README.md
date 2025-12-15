# planio-serverless-task-platform

flowchart LR
  U[User (Browser)] -->|HTTP GET| S3[Amazon S3\nStatic Website Hosting\nPlanio Frontend]
  S3 -->|HTTPS REST calls (/tasks)| APIGW[Amazon API Gateway\nHTTP API]
  APIGW -->|Invoke| L[AWS Lambda\nPlanioHandler]
  L -->|CRUD| DDB[Amazon DynamoDB\nPlanioTasks]
  L -->|Logs| CW[Amazon CloudWatch Logs]
