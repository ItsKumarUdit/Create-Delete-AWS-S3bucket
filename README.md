TITLE: Create and Delete S3 Buckets using AWS Console and AWS CLI

This document explains how to create two S3 buckets using the AWS Management Console and delete them using the AWS Command Line Interface (CLI).

PART 1: CREATE TWO S3 BUCKETS USING AWS MANAGEMENT CONSOLE

Step 1: Sign in to AWS

Go to https://aws.amazon.com/
Click “Sign in to the Console” and log in with your credentials.

Step 2: Open the S3 Service

In the AWS Management Console, type “S3” in the search bar.
Click on “S3” under the Storage category.

Step 3: Create the First Bucket

Click “Create bucket”.
Enter a unique bucket name, for example: my-demo-bucket-udit-1
Choose a region, e.g., Asia Pacific (Mumbai) – ap-south-1.
Keep other settings default.
Scroll down and click “Create bucket”.

Step 4: Create the Second Bucket
Click “Create bucket” again.
Enter a second unique bucket name, for example: my-demo-bucket-udit-2
Choose the same region (ap-south-1).
Click “Create bucket”.

Both buckets are now successfully created in your S3 console.

PART 2: DELETE THE SAME BUCKETS USING AWS CLI

Step 1: Install AWS CLI
For Windows:
Visit https://aws.amazon.com/cli/

Download the AWS CLI MSI Installer (64-bit).
Run the installer and complete setup.

Open Command Prompt and verify installation using:
aws --version

For Linux or macOS:
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip
" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version

Step 2: Configure AWS CLI
Run the command:
aws configure

Then enter the following details:
AWS Access Key ID [None]: <your-access-key>
AWS Secret Access Key [None]: <your-secret-key>
Default region name [None]: ap-south-1
Default output format [None]: json

Access Key ID: Your IAM user key (acts as a username)

Secret Access Key: Your private key (acts as a password)

Default region: The region where your buckets are located (ap-south-1)

Output format: json (recommended)

Step 3: Verify Buckets
List all S3 buckets in your account using:
aws s3 ls

Example output:
2025-10-25 10:12:34 udit-123
2025-10-25 10:13:10 udit-789

Step 5: Delete the Buckets
Delete both buckets using:
aws s3 rb s3://udit-123 --force
aws s3 rb s3://udit-789 --force

The “--force” flag deletes the bucket along with its contents.

Step 6: Confirm Deletion
Check that the buckets are deleted by listing all buckets again:
aws s3 ls

If the deletion was successful, the buckets will not appear in the list.

SUMMARY

Step 1 - Create first bucket (AWS Console)
Step 2 - Create second bucket (AWS Console)
Step 3 - List all buckets (AWS CLI) → aws s3 ls
Step 4 - Remove bucket contents (AWS CLI) → aws s3 rm s3://bucket --recursive
Step 5 - Delete buckets (AWS CLI) → aws s3 rb s3://bucket --force
Step 6 - Verify deletion (AWS CLI) → aws s3 ls

IMPORTANT NOTES

Bucket names must be globally unique.
Always empty a bucket before deleting (or use --force).
Use the same AWS region for creation and deletion (e.g., ap-south-1).
Never share or upload your AWS Access Key and Secret Key to GitHub.

AUTHOR INFORMATION
Name: Udit
Branch: B.Tech CSE
Topic: AWS S3 Bucket Creation and Deletion using Console and CLI

REFERENCES
AWS CLI Documentation: https://docs.aws.amazon.com/cli/latest/userguide/
Amazon S3 User Guide: https://docs.aws.amazon.com/AmazonS3/latest/userguide/
