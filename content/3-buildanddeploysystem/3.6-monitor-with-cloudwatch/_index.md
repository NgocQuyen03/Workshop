---
title : "Monitor and Debug with CloudWatch Logs"
date: 2025-07-10
weight : 6
chapter : false
pre : " <b> 3.6. </b> "
---
🎯 Objective: Monitor activity and debug Lambda errors in practice.

💡 Tips & Tricks:

Use [INFO], [ERROR] prefixes to filter logs more easily

CloudWatch usually has a few seconds delay → refresh if you don't see logs yet

🪜 Steps:

Go to AWS Console → CloudWatch → Log groups

Find logs by Lambda function name (e.g., /aws/lambda/ses-mailer-dev-submitExcel)

![S3](/images/3.buildanddeploy/3.6-cloudwatch.png)

![S3](/images/3.buildanddeploy/3.6-cloudwatch-log.png)

Check the log lines:

- Input received

- Base64 decode success or error

- File upload success or error

- Email sending status

![S3](/images/3.buildanddeploy/3.6-cloudwatch-test.png)