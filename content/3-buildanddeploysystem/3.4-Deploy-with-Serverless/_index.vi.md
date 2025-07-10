---
title : "Triển khai hệ thống lên AWS"
date: 2025-07-10
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---
🎯 Mục tiêu: Đưa toàn bộ mã nguồn, cấu hình và tài nguyên lên AWS bằng Serverless Framework.

💡 Tips & Tricks:

- Luôn dùng .env và plugin serverless-dotenv-plugin để quản lý biến môi trường

- Nếu deploy chậm hoặc bị lỗi timeout → kiểm tra internet hoặc region

🪜 Các bước thực hiện:

Cài plugin vào serverless.yml:

```bash
plugins:
  - serverless-python-requirements
  - serverless-dotenv-plugin
```
![S3](/images/3.buildanddeploy/3.4.png)
Tạo file .env:
```bash
S3_BUCKET=auto-confirm-dev-bucket

SES_SENDER_EMAIL=your_verified@email.com
```
![S3](/images/3.buildanddeploy/3.1-s3-6.png)

Triển khai bằng lệnh:
```bash
sls deploy
```
Ghi lại:

- API endpoint sau khi deploy

- API key nếu cần