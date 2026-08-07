# Real-Time-Leaderboard-on-AWS-with-DynamoDB
<img width="1728" height="1117" alt="Screenshot 2026-07-31 at 2 30 43 AM" src="https://github.com/user-attachments/assets/d1e01c78-2581-49a5-977d-89cb49aeb1c3" />

<h2> **IAM Roles** </h2>

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

<img width="1727" height="727" alt="image" src="https://github.com/user-attachments/assets/bd5a887b-5a96-4c03-8f89-537a23552d2f" />

<img width="1720" height="785" alt="image" src="https://github.com/user-attachments/assets/268b25da-7fc1-4d33-bfae-c57dafbd9b7c" />


<h2> **Goal: Add DynamoDB read permissions to the role.** </h2>

Step 1: Click on LambdaExecutionRole.

Step 2: Go to the Permissions tab.

Step 3: Click Add permissions → Attach policies.

Step 4: Search for and select: AmazonDynamoDBReadOnlyAccess

Step 5: Click Add permissions.

Verify:

The role now has two policies attached:
AWSLambdaBasicExecutionRole
AmazonDynamoDBReadOnlyAccess

<img width="1362" height="540" alt="image" src="https://github.com/user-attachments/assets/135cad95-ed81-4225-8e70-44b513974d07" />

Goal: Review the role's trust and permissions policies.

Step 1: Click on LambdaExecutionRole.

Step 2: Go to Trust relationships tab.

Step 3: Verify the trust policy shows:

Service: lambda.amazonaws.com

Effect: Allow

Action: sts:AssumeRole

Step 4: Go back to Permissions tab.

Step 5: Verify both policies are listed:

AWSLambdaBasicExecutionRole (for CloudWatch Logs)
AmazonDynamoDBReadOnlyAccess (for DynamoDB reads)

Observations:

Role can only be assumed by Lambda service
Role can write logs and read DynamoDB
Role cannot write to DynamoDB or access other services

<img width="572" height="356" alt="image" src="https://github.com/user-attachments/assets/b64f2404-5e27-47f3-ace7-3bc7760af847" />


<h2> AWS Lambda </h2>

Serverless compute service that runs code without provisioning servers. You upload code, set memory and timeout, and Lambda handles the rest.

Key Concepts:

Function: Your code that runs in response to events
Runtime: Programming language environment (Python, Node.js, Java, etc.)
Handler: Entry point function that Lambda invokes
Environment Variables: Key-value pairs accessible to your function
Timeout: Maximum execution time (default 3 seconds, max 15 minutes)
What You'll Build:

Task 1: Create a Lambda function
Task 2: Add environment variables
Task 3: Test the function
