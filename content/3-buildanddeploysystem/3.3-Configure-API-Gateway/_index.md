---
title : "Configure API Gateway"
date: 2025-07-10
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---
🎯 Objective: Define the API endpoint to send requests from the client (Postman, website, etc.).

💡 Tips & Tricks:

Set private: true to require x-api-key
You can enable CORS if you will use it from the frontend (React, Vue, ...)

🪜 Steps:

Open the serverless.yml file

In the functions → submitExcel → events section:

```yaml
functions:
  submitExcel:
    handler: handler.lambda_handler
    events:
      - http:
          path: submit-excel
          method: post
          cors: true
          private: true
```

![S3](/images/3.buildanddeploy/3.3.png)

Declare apiKeys and usagePlan:

```yaml
apiGateway:
    apiKeySourceType: HEADER
    apiKeys:
      - name: SesMailerApiKey-${sls:stage}
        description: "API Key for Lambda to send SES"
        enabled: true
    usagePlan:
      throttle:
        rateLimit: 100
        burstLimit: 100
      quota:
        limit: 1000
        period: MONTH
```
![S3](/images/3.buildanddeploy/3.3-2.png)