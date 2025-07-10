---
title : "Preparation Steps"
date: 2025-07-10 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

## 1. System Requirements

- Python 3.11
- Node.js ≥ 16
- AWS CLI
- AWS account with permissions to create and configure Lambda, API Gateway, S3, SES
- Docker Desktop (for packaging Lambda dependencies)
- IDE: Visual Studio Code (or any editor you prefer)

## 2. Install Required Tools

### Install AWS CLI

#### macOS
```bash
brew install awscli
```
#### Ubuntu
```bash
sudo apt install awscli
```
#### Windows
Download from AWS CLI
Configure AWS CLI
```bash
aws configure
```
Enter:
Access key, secret key
Region: ap-southeast-1
Format: json

Install Node.js & npm
macOS
```bash
brew install node
```
Ubuntu
```bash
sudo apt install nodejs npm
```
Install Serverless Framework
```bash
npm install -g serverless
```
Install Docker (if not already installed) to support packaging Python libraries

Create a Python virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows
```

## 3. Create Project Structure and Install Required Libraries
Create the project folder and initialize serverless
```bash
mkdir ses-mailer
cd ses-mailer
sls create --template aws-python --path .
```
Create the following files:
- handler.py — contains logic to receive the form, decode base64, save to S3, and send SES email
- serverless.yml — service configuration, environment, IAM, API Gateway
- requirements.txt — contains libraries:
```nginx
boto3
requests_toolbelt
```
- .env — defines environment variables:
```ini
S3_BUCKET=my-upload-bucket
SES_SENDER_EMAIL=your-verified@email.com
```

## 4. Install Python Libraries

Install:
```bash
pip install -r requirements.txt
```