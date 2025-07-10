---
title : "Viết logic xử lý Lambda"
date: 2025-07-10 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
🎯 Mục tiêu: Viết function Lambda để xử lý form từ người dùng, lưu file, tạo link tải và gửi email.

💡 Tips & Tricks:

- Dữ liệu file từ Postman sẽ là dạng multipart/form-data → cần parse thủ công

- base64 không phải lúc nào cũng hợp lệ – nên kiểm tra trước khi decode

🪜 Các bước thực hiện:

Tạo file handler.py trong dự án

Cài thư viện:
```bash
- pip install requests_toolbelt boto3 -t .
```
![S3](/images/3.buildanddeploy/3.2-lambda.png)

Xử lý lambda_handler(event, context):

- Parse multipart/form-data từ body

- Decode nội dung file từ base64

- Gửi lên S3 bằng boto3

- Tạo presigned URL

- Gửi email qua SES (boto3)

In log chi tiết (name, email, filename, trạng thái upload/email)

![S3](/images/3.buildanddeploy/3.2-lambda-3.png)