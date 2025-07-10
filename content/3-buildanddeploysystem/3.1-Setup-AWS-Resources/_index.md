---
title : "Create Required AWS Resources"
date: 2025-07-10
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---
🎯 Objective: Prepare the necessary AWS resources for the system to run smoothly.

💡 Tips & Tricks:

If you are in Vietnam, choose the ap-southeast-1 (Singapore) region to reduce latency.

🪜 Steps:

### Create an S3 bucket:

- Go to AWS Console and search for S3

![S3](/images/3.buildanddeploy/3.1-s3.png)

- Click Create Bucket

![S3](/images/3.buildanddeploy/3.1-s3-2.png)

- Bucket name: lambda-file-ses
- Leave the rest as default, then scroll to the bottom and click Create

![S3](/images/3.buildanddeploy/3.1-create-bucket.png)
![S3](/images/3.buildanddeploy/3.1-create-bucket-1.png)
![S3](/images/3.buildanddeploy/3.1-s3-3.png)

### Create a verified email in Amazon SES:

- Go to AWS Console and search for SES

![S3](/images/3.buildanddeploy/3.1-s3-4.png)

- In the Identities section, select Create Identities

- Add your email and wait until the Status Identity changes to Verified

![S3](/images/3.buildanddeploy/3.1-s3-5.png)

- After creating, you will receive an email to verify via the provided link

### Record the information:
```bash
S3_BUCKET = bucket name
SES_SENDER_EMAIL = verified email
```
![S3](/images/3.buildanddeploy/3.1-s3-6.png)

### Grant permissions to Lambda:

Check that your serverless.yml has the following permissions:

- ses:SendEmail
- s3:PutObject, GetObject
- logs:CreateLogGroup
- ec2:CreateNetworkInterface

![S3](/images/3.buildanddeploy/3.1-s3-7.png)