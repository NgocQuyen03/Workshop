---
title : "Giới thiệu"
date: 2025-07-10 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
# 🏠 Workshop: Hệ thống Gửi Email Xác Nhận Tự Động bằng AWS

![S3](/images/3.buildanddeploy/workshop.drawio.png)

Workshop này hướng dẫn bạn xây dựng một hệ thống Gửi Email Xác Nhận Tự Động, được triển khai theo kiến trúc serverless sử dụng các dịch vụ chủ lực của AWS như Lambda, API Gateway, S3, SES, IAM, CloudWatch và CloudFormation. Hệ thống cho phép người dùng gửi một biểu mẫu kèm file (được mã hóa base64), hệ thống sẽ lưu trữ file vào S3 và tự động gửi email xác nhận đến người dùng với liên kết tải file.

🔧 Trong workshop, bạn sẽ xây dựng một hệ thống serverless có khả năng:

- Nhận dữ liệu từ người dùng (bao gồm tên, email và file Excel được mã hóa base64)

- Tự động giải mã và lưu file vào Amazon S3

- Tạo liên kết tải file (presigned URL) có thời hạn

- Gửi email xác nhận đến người dùng qua Amazon SES, trong đó chứa liên kết tải file

## 🎓 Bạn sẽ học được:

- Cách xây dựng hệ thống serverless thực tế bằng Python và AWS

- Kỹ năng xử lý multipart/form-data và file base64 trong Lambda

- Cách cấu hình và sử dụng Amazon SES để gửi email xác nhận

- Kỹ năng sử dụng Serverless Framework để triển khai dịch vụ AWS

- Quản lý biến môi trường, quyền IAM và debug bằng CloudWatch

- Hiểu được kiến trúc serverless và cách tối ưu cho hiệu suất và chi phí

## 💼 Kết quả sau workshop:

- Hiểu cách xây dựng hệ thống serverless sử dụng AWS Lambda, API Gateway, S3 và SES.

- Xử lý và lưu trữ file dạng base64, tạo link tải và gửi email xác nhận tự động.

- Sử dụng Serverless Framework để triển khai nhanh, quản lý môi trường và phân quyền IAM.

- Theo dõi, ghi log và xử lý lỗi hiệu quả với CloudWatch Logs.

- Sẵn sàng áp dụng mô hình cho các hệ thống thực tế như nộp đơn, tải file, gửi email xác nhận.

---