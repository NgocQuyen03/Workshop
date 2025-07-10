---
title : "Tạo tài nguyên AWS cần thiết"
date: 2025-07-10
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---
🎯 Mục tiêu: Chuẩn bị các tài nguyên cần thiết trên AWS để hệ thống hoạt động trơn tru.

💡 Tips & Tricks:

Nếu bạn ở Việt Nam, chọn region ap-southeast-1 (Singapore) để giảm độ trễ

🪜 Các bước thực hiện:

### Tạo bucket S3:

- Vào AWS Console tìm S3

![S3](/images/3.buildanddeploy/3.1-s3.png)

- Chọn Create Bucket

![S3](/images/3.buildanddeploy/3.1-s3-2.png)

- Bucket name: lambda-file-ses
- Các phần còn lại không chỉnh gì sau đó kéo xuống cuối trang nhấn

![S3](/images/3.buildanddeploy/3.1-create-bucket.png)
![S3](/images/3.buildanddeploy/3.1-create-bucket-1.png)
![S3](/images/3.buildanddeploy/3.1-s3-3.png)
### Tạo email verified trong Amazon SES:

- Vào AWS Console tìm SES

![S3](/images/3.buildanddeploy/3.1-s3-4.png)

- Sau đó vào phần Identities chọn Create Identities

- Add mail vào và chờ đến khi Status Identity chuyển sang Verified

![S3](/images/3.buildanddeploy/3.1-s3-5.png)

- Sau khi tạo sẽ có 1 mail gửi đến để xác nhận email qua đường link được gửi

### Ghi lại thông tin:
```bash
S3_BUCKET = tên bucket

SES_SENDER_EMAIL = email vừa verify
```
![S3](/images/3.buildanddeploy/3.1-s3-6.png)

### Gán quyền cho Lambda:

Kiểm tra serverless.yml đã có quyền:

- ses:SendEmail

- s3:PutObject, GetObject

- logs:CreateLogGroup

- ec2:CreateNetworkInterface

![S3](/images/3.buildanddeploy/3.1-s3-7.png)