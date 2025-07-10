---
title : "Introduction"
date: 2025-07-10 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
# 🏠 Workshop: Automatic Email Confirmation System with AWS

![S3](/images/3.buildanddeploy/workshop.drawio.png)

This workshop guides you in building an Automatic Email Confirmation System, deployed using a serverless architecture with core AWS services such as Lambda, API Gateway, S3, SES, IAM, CloudWatch, and CloudFormation. The system allows users to submit a form with an attached file (encoded in base64), the file will be stored in S3, and an automatic confirmation email will be sent to the user with a download link.

🔧 In this workshop, you will build a serverless system capable of:

- Receiving user input (including name, email, and a base64-encoded Excel file)

- Automatically decoding and storing the file in Amazon S3

- Creating a time-limited download link (presigned URL)

- Sending a confirmation email to the user via Amazon SES containing the download link

## 🎓 You will learn:

- How to build a real-world serverless system using Python and AWS

- How to handle multipart/form-data and base64 files in Lambda

- How to configure and use Amazon SES to send confirmation emails

- How to use the Serverless Framework to deploy AWS services

- How to manage environment variables, IAM permissions, and debug using CloudWatch

- Understand the serverless architecture and how to optimize it for performance and cost

## 💼 Workshop outcomes:

- Understand how to build a serverless system using AWS Lambda, API Gateway, S3, and SES

- Be able to handle and store base64 files, generate download links, and send confirmation emails automatically

- Deploy quickly using the Serverless Framework, manage environments and IAM permissions effectively

- Monitor, log, and handle errors efficiently with CloudWatch Logs

- Be ready to apply this model to real-world systems like submissions, file uploads, and email confirmations

---