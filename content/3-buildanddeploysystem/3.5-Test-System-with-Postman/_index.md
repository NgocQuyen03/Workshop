---
title : "Test the System with Postman"
date: 2025-07-10
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---
🎯 Objective: Send simulated data to test the entire flow from upload → email sending.

💡 Tips & Tricks:

Use form-data (not raw body) when testing multipart/form-data

Check the base64 file carefully if using encoding → make sure it can be decoded without errors

🪜 Steps:

Open Postman → New → POST Request

URL: {API_ENDPOINT}/submit-excel

![S3](/images/3.buildanddeploy/3.5-postman.png)

Headers:

x-api-key: <API_KEY>

Content-Type: multipart/form-data (Postman will set this automatically)

Body → raw:

name: Nguyen Van A

email: a@example.com

file: any Excel file (Postman will encode as multipart)

![S3](/images/3.buildanddeploy/3.5-postman-2.png)

Send the request → check your email

If successful:

![S3](/images/3.buildanddeploy/3.5-postman-sendmail.png)

Receive a confirmation email with a download link

![S3](/images/3.buildanddeploy/3.5-postman-nhanmail.png)

The file is now in S3