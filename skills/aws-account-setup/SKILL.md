---
name: aws-account-setup
description: Set up and configure a new AWS account with basic security and billing controls
version: 1.0.0
metadata:
  skill_forge:
    domain: "aws"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [aws, cloud, account-setup, security]
    category: cloud
---

# AWS Account Setup and Configuration

## When to Use
When you need to create and configure a new AWS account for cloud computing services with proper security and billing controls in place.

## Prerequisites
- Valid email address
- Credit card or debit card for billing
- Phone number for verification
- Basic understanding of cloud computing concepts

## Procedure
1. Navigate to AWS signup: `https://aws.amazon.com/`
2. Click "Create an AWS Account"
3. Enter email address and account name
4. Choose account type (Personal or Professional)
5. Complete billing information and phone verification
6. Select support plan (Basic is free for getting started)
7. Set up root account MFA: Go to IAM → Security credentials → Multi-factor authentication
8. Create IAM admin user: `aws iam create-user --user-name admin-user`
9. Attach admin policy: `aws iam attach-user-policy --user-name admin-user --policy-arn arn:aws:iam::aws:policy/AdministratorAccess`
10. Create access keys for programmatic access: `aws iam create-access-key --user-name admin-user`
11. Set up billing alerts in CloudWatch for cost monitoring
12. Configure AWS CLI with new credentials: `aws configure`

## Verification
- Log into AWS Console with IAM user (not root)
- Run `aws sts get-caller-identity` to confirm CLI access
- Check billing dashboard shows current usage
- Verify MFA is enabled on root account

## Pitfalls
- Never use root account for daily operations
- Don't skip MFA setup - accounts without MFA are vulnerable
- Set billing alerts early to avoid unexpected charges
- Store access keys securely, never commit to version control
- AWS Free Tier has usage limits - monitor to avoid charges

## Sources
- https://aws.amazon.com/
- https://en.wikipedia.org/wiki/Amazon_Web_Services
- https://skillbuilder.aws/
- https://www.linkedin.com/company/amazon-web-services
- https://www.aws.org/