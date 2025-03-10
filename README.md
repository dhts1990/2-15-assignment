# 2-15-assignment

## 1. Authorizing EC2 to Retrieve Secrets
To allow an EC2 instance to retrieve secrets from AWS Secrets Manager:
1. Create an **IAM Role** and attach it to the EC2 instance.
2. Attach the following **IAM Policy** to grant access to the secret.
3. Use AWS CLI to retrieve the secret.

## 2. IAM Policy for Secrets Manager
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "secretsmanager:GetSecretValue",
            "Resource": "arn:aws:secretsmanager:us-east-1:123456789012:secret:prod/cart-service/credentials-*"
        }
    ]
}


