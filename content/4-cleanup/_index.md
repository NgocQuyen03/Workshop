+++
title = "Clean up AWS resources"
date = 2025-07-10
weight = 6
chapter = false
pre = "<b>4. </b>"
+++

## Clean up AWS resources after the Workshop

After completing the workshop, you should clean up unused resources to avoid incurring costs and keep your AWS account tidy and secure.

### Remove deployed Serverless resources

If you used the Serverless Framework to deploy Lambda, S3, API Gateway:

Run the command:
```bash
sls remove
```
This command will delete all resources created by the Serverless Framework, including:

- AWS Lambda function

- API Gateway

- IAM role

- Log group (CloudWatch)

- S3 bucket (only if created via serverless.yml)

### Delete remaining resources (if any)

Some resources may have been created manually or are not in serverless.yml, so check and delete them manually:

S3 buckets: Carefully check and delete the contents in the bucket before deleting the bucket.

SES identities:

- Go to AWS SES and select Identities
- Then select the email you want to delete and choose Delete.
![S3](/images/3.buildanddeploy/4-delete-mail.png)
- Click Confirm to complete the deletion
![S3](/images/3.buildanddeploy/4-delete-mail-2.png)
CloudWatch log groups:

- Go to AWS CloudWatch, in the left sidebar select Logs → log group.
- Select the log group you want to delete, choose Actions → Delete log group(s)
![S3](/images/3.buildanddeploy/4-delete-cloudw.png)
- Click Confirm to delete.
![S3](/images/3.buildanddeploy/4-delete-cloudw2.png)

IAM roles and policies (if created manually):
- In the search bar, select IAM
- Select Roles to delete, then choose Delete
![S3](/images/3.buildanddeploy/4-delete-role.png)
- Enter the Role name again, then choose Delete
![S3](/images/3.buildanddeploy/4-delete-role-confirm.png)
Deleting Policies is similar

API Key (if created in API Gateway):
- In the toolbar, search for API Gateway
![S3](/images/3.buildanddeploy/4-apigateway.png)
- Select API Keys
- Select the API Keys you want to delete
- Choose Actions → Delete
![S3](/images/3.buildanddeploy/4-delete-apikeys.png)
- Click Delete to remove.
![S3](/images/3.buildanddeploy/4-confirm.png)

### Delete local development environment (optional)

Delete the project folder (todo-serverless or another name).

Deactivate & delete the virtual environment:

Windows:
- .venv\Scripts\deactivate
- rmdir /S /Q .venv

macOS/Linux:
- deactivate
- rm -rf .venv

### Check billing and remaining resources

- Go to Billing > Cost Explorer → Check if any services are still incurring charges.

- Go to AWS Resource Explorer or Trusted Advisor → See if there are any active resources.

📌 Suggestion:

If the workshop is just for testing, you should also delete the sandbox account or set up a Billing Alert to avoid unexpected charges.