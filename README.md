# Real-Time-Leaderboard-on-AWS-with-DynamoDB
<img width="1728" height="1117" alt="Screenshot 2026-07-31 at 2 30 43 AM" src="https://github.com/user-attachments/assets/d1e01c78-2581-49a5-977d-89cb49aeb1c3" />

IAM Roles

IAM roles are identities that AWS services assume to perform actions on your behalf. Unlike users, roles are for temporary access and are assumed by AWS services.

Key Concepts:

Trust Policy: Defines which AWS services can assume the role
Permissions Policy: Defines what actions the role can perform
Service Role: A role assumed by AWS services like Lambda, EC2, or DynamoDB
Common Use Cases:

Lambda functions accessing DynamoDB
EC2 instances accessing S3
Services writing logs to CloudWatch
What You'll Build:

Task 1: Create an IAM role for Lambda
Task 2: Attach permissions to the role
Task 3: Verify the role configuration
