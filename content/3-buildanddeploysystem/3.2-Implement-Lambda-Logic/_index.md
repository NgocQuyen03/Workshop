---
title : "Write Lambda Processing Logic"
date: 2025-07-10 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
🎯 Objective: Write a Lambda function to process user forms, save files, generate download links, and send emails.

💡 Tips & Tricks:

- File data from Postman will be in multipart/form-data format → needs to be parsed manually

- base64 is not always valid – you should check before decoding

🪜 Steps:

Create a handler.py file in your project

Install libraries:
```bash
pip install requests_toolbelt boto3 -t .
```
![S3](/images/3.buildanddeploy/3.2-lambda.png)

Handle lambda_handler(event, context):

- Parse multipart/form-data from the body

- Decode the file content from base64

- Upload to S3 using boto3

- Generate a presigned URL

- Send email via SES (boto3)

Log details (name, email, filename, upload/email status)

![S3](/images/3.buildanddeploy/3.2-lambda-3.png)