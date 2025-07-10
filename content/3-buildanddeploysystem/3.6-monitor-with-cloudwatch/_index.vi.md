---
title : "Giám sát và debug với CloudWatch Logs"
date: 2025-07-10
weight : 6
chapter : false
pre : " <b> 3.6. </b> "
---
🎯 Mục tiêu: Theo dõi hoạt động và debug lỗi của Lambda trong thực tế.

💡 Tips & Tricks:

Dùng prefix [INFO], [ERROR] để lọc log dễ hơn

CloudWatch thường có độ trễ vài giây → F5 nếu chưa thấy log

🪜 Các bước thực hiện:

Vào AWS Console → CloudWatch → Log groups

Tìm log theo tên hàm Lambda (vd: /aws/lambda/ses-mailer-dev-submitExcel)

![S3](/images/3.buildanddeploy/3.6-cloudwatch.png)

![S3](/images/3.buildanddeploy/3.6-cloudwatch-log.png)

Kiểm tra các dòng log:

- Input nhận được

- Base64 decode thành công hay lỗi

- Upload file thành công hay lỗi

- Trạng thái gửi email

![S3](/images/3.buildanddeploy/3.6-cloudwatch-test.png)