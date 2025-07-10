+++
title = "Dọn dẹp tài nguyên  "
date = 2025-07-10
weight = 6
chapter = false
pre = "<b>4. </b>"
+++

## Dọn dẹp tài nguyên AWS sau Workshop

Sau khi hoàn tất workshop, bạn nên dọn dẹp các tài nguyên không còn sử dụng để tránh phát sinh chi phí và giữ tài khoản AWS gọn gàng, an toàn.

### Gỡ bỏ các tài nguyên Serverless đã triển khai

Nếu bạn sử dụng Serverless Framework để triển khai Lambda, S3, API Gateway:

Thực hiện lệnh:
```bash
sls remove
```
Lệnh này sẽ xóa toàn bộ các tài nguyên mà Serverless Framework đã tạo, bao gồm:

- AWS Lambda function

- API Gateway

- IAM role

- Log group (CloudWatch)

- S3 bucket (chỉ nếu được tạo qua serverless.yml)

### Xoá các tài nguyên còn lại (nếu có)

Một số tài nguyên bạn có thể đã tạo thủ công hoặc không nằm trong serverless.yml, hãy kiểm tra và xoá thủ công:

S3 buckets: Kiểm tra kỹ và xóa nội dung trong bucket trước khi xóa bucket.

SES identities:

- Vào AWS SES chọn Identities
- Sau đó chọn email muốn xóa chọn Delete.
![S3](/images/3.buildanddeploy/4-delete-mail.png)
- Chọn Confirm để hoàn tất việc xóa
![S3](/images/3.buildanddeploy/4-delete-mail-2.png)
CloudWatch log groups:

- Vào AWS CloudWatch ở thanh bên trái chọn Logs → log group.
- Chọn log group muốn xóa chọn Actions → Delete log group(s)
![S3](/images/3.buildanddeploy/4-delete-cloudw.png)
- Chọn Confirm để xóa.
![S3](/images/3.buildanddeploy/4-delete-cloudw2.png)

IAM roles và policies (nếu tạo thủ công):

- Trên thanh tìm kiếm chọn IAM
- Chọn Roles còn xóa rồi chọn Delete
![S3](/images/3.buildanddeploy/4-delete-role.png)
- Nhập lại tên Role sau đó chọn Delete
![S3](/images/3.buildanddeploy/4-delete-role-confirm.png)
Bước xóa Policies cũng thực hiện tương tự

API Key (nếu có tạo trong API Gateway):
- Trên thanh công cụ tìm API Gateway
![S3](/images/3.buildanddeploy/4-apigateway.png)
- Chọn API Keys
- Chọn API Keys muốn xóa
- Chọn Actions → Chọn Delete
![S3](/images/3.buildanddeploy/4-delete-apikeys.png)
- Chọn Delete để xóa.
![S3](/images/3.buildanddeploy/4-confirm.png)

### Xoá môi trường phát triển cục bộ (tuỳ chọn)

Xoá thư mục dự án (todo-serverless hoặc tên khác).

Deactivate & xoá virtual environment:

Windows:
- .venv\Scripts\deactivate
- rmdir /S /Q .venv

macOS/Linux:
- deactivate
- rm -rf .venv

### Kiểm tra hoá đơn và tài nguyên tồn đọng

- Vào Billing > Cost Explorer → Kiểm tra xem có dịch vụ nào đang tính phí.

- Vào AWS Resource Explorer hoặc Trusted Advisor → Xem tài nguyên còn hoạt động.

📌 Gợi ý:

Nếu workshop chỉ mang tính thử nghiệm, bạn nên xóa cả tài khoản sandbox hoặc tạo Billing Alert để tránh phí phát sinh.