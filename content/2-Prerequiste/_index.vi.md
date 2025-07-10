---
title : "Các bước chuẩn bị"
date: 2025-07-10 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---
## 1. Yêu cầu hệ thống

- Python 3.11

- Node.js ≥ 16

- AWS CLI

- Tài khoản AWS có quyền tạo và cấu hình Lambda, API Gateway, S3, SES

- Docker Desktop (dùng để đóng gói dependencies cho Lambda)

- IDE: Visual Studio Code (hoặc bất kỳ editor bạn thích)

## 2. Cài đặt công cụ cần thiết

### Cài AWS CLI

#### macOS
```bash
brew install awscli
```
#### Ubuntu
```bash
sudo apt install awscli
```
#### Windows
Tải từ AWS CLI
Cấu hình AWS CLI
```bash
aws configure
```
Nhập:
Access key, secret key
Region: ap-southeast-1
Format: json
Cài Node.js & npm
macOS
```bash
brew install node
```
Ubuntu
```bash
sudo apt install nodejs npm
```
Cài Serverless Framework
```bash
npm install -g serverless
```
Cài Docker (nếu chưa có) để hỗ trợ đóng gói thư viện Python
Tạo virtual environment Python
```bash
python3 -m venv .venv
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows
```
## 3. Tạo cấu trúc dự án và cài thư viện cần thiết
Tạo thư mục dự án và khởi tạo serverless
```bash
mkdir ses-mailer
cd ses-mailer
sls create --template aws-python --path .
```
Tạo các file cấu trúc
- handler.py — chứa logic nhận form, giải mã base64, lưu S3 và gửi email SES

- serverless.yml — cấu hình service, môi trường, IAM, API Gateway
requirements.txt — chứa các thư viện:
```nginx
boto3
requests_toolbelt
```
.env — định nghĩa biến môi trường:
```ini
S3_BUCKET=my-upload-bucket
SES_SENDER_EMAIL=your-verified@email.com
```
## 4. Cài đặt thư viện Python

Cài đặt:  
```bash
pip install -r requirements.txt
```