---
title : "Cấu hình API Gateway"
date: 2025-07-10
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---
🎯 Mục tiêu: Định nghĩa API endpoint để gửi yêu cầu từ client (Postman, website...).

💡 Tips & Tricks:

Đặt private: true để yêu cầu x-api-key

Có thể bật CORS nếu sẽ dùng từ frontend (React, Vue,...)

🪜 Các bước thực hiện:

Mở file serverless.yml

Trong phần functions → submitExcel → events:

```bash
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

Khai báo apiKeys và usagePlan:

```bash
apiGateway:
    apiKeySourceType: HEADER
    apiKeys:
      - name: SesMailerApiKey-${sls:stage}
        description: "API Key cho Lambda gửi SES"
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