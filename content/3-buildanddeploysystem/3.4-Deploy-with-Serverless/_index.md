---
title : "Deploy the System to AWS"
date: 2025-07-10
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---
🎯 Objective: Deploy all source code, configuration, and resources to AWS using the Serverless Framework.

💡 Tips & Tricks:

- Always use .env and the serverless-dotenv-plugin to manage environment variables

- If deployment is slow or times out → check your internet connection or region

🪜 Steps:

Add plugins to serverless.yml:

```yaml
plugins:
  - serverless-python-requirements
  - serverless-dotenv-plugin
```
![S3](/images/3.buildanddeploy/3.4.png)

Create a .env file:
```bash
S3_BUCKET=auto-confirm-dev-bucket

SES_SENDER_EMAIL=your_verified@email.com
```
![S3](/images/3.buildanddeploy/3.1-s3-6.png)

Deploy with the command:
```bash
sls deploy
```

Record:
- The API endpoint after deployment
- The API key if needed