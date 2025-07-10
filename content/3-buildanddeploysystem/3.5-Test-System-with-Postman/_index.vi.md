---
title : "Kiểm thử hệ thống bằng Postman"
date: 2025-07-10
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---
🎯 Mục tiêu: Gửi dữ liệu mô phỏng để kiểm tra toàn bộ luồng từ upload → gửi email.

💡 Tips & Tricks:

Sử dụng form-data (không phải raw body) khi test multipart/form-data

Kiểm tra kỹ file base64 nếu dùng mã hoá → cần đảm bảo không bị lỗi khi decode

🪜 Các bước thực hiện:

Mở Postman → New → POST Request

URL: {API_ENDPOINT}/submit-excel

![S3](/images/3.buildanddeploy/3.5-postman.png)


Headers:

x-api-key: <API_KEY>

Content-Type: multipart/form-data (Postman tự tạo)

Body → raw:

name: Nguyễn Văn A

email: a@example.com

file: file Excel bất kỳ (Postman tự mã hoá thành multipart)

![S3](/images/3.buildanddeploy/3.5-postman-2.png)

Gửi request → kiểm tra email

Nếu thành công:

![S3](/images/3.buildanddeploy/3.5-postman-sendmail.png)

Nhận email xác nhận có link tải

![S3](/images/3.buildanddeploy/3.5-postman-nhanmail.png)

File đã có trên S3