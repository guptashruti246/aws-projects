# Stale EBS Snapshot Cleanup using AWS Lambda

## Overview

This project demonstrates an AWS cost optimization use case by identifying stale EBS snapshots that are no longer associated with active EC2 instances.

An AWS Lambda function written in Python uses Boto3 to retrieve EBS snapshots owned by the account, compare them with active EC2 instances, and identify snapshots that are no longer required.

The Lambda function was configured and tested manually from the AWS Management Console to understand the snapshot lifecycle and cleanup process.

## Problem Statement

Amazon EBS snapshots incur storage costs even when they are no longer associated with active resources. As AWS environments grow, manually reviewing and deleting such snapshots becomes difficult and time-consuming.

This project demonstrates how AWS Lambda can be leveraged to identify stale snapshots and help optimize storage costs.

## Services Used

- AWS Lambda
- AWS IAM
- Amazon EC2
- Amazon EBS
- Boto3 (AWS SDK for Python)

## Implementation

### 1. Created Lambda Function

Configured an AWS Lambda function using Python runtime.

![Lambda Function](screenshots/lambda-function.png)

---

### 2. Configured IAM Role

Created and attached an IAM role with permissions required to:

- Describe EC2 instances
- Describe EBS snapshots
- Delete EBS snapshots

![IAM Role](screenshots/iam-role.png)

---

### 3. Added Lambda Code

Implemented Python code using Boto3 to:

- Retrieve EBS snapshots owned by the account
- Fetch active EC2 instances
- Compare snapshots against active instances
- Identify stale snapshots
- Delete snapshots that are no longer required

![Lambda Code](screenshots/lambda-code.png)

---

### 4. Tested the Lambda Function

Invoked the Lambda function manually using the Test feature in the AWS Console.

![Execution Success](screenshots/execution-success.png)

---

### 5. Verified Existing EBS Snapshots

Reviewed EBS snapshots associated with EC2 volumes to understand snapshot management and cleanup workflows.

![EBS Snapshots](screenshots/ebs-snapshots.png)

---

## Key Learnings

- Working with AWS Lambda and IAM roles
- Using Boto3 to interact with EC2 and EBS APIs
- Understanding EBS snapshot lifecycle management
- Exploring AWS cost optimization techniques
- Implementing serverless solutions for operational tasks

## Future Enhancements

Potential improvements include:

- Scheduling execution using EventBridge
- Sending notifications before snapshot deletion
- Tagging resources before cleanup
- Generating cost optimization reports

---

**Author**

Shruti Gupta

Junior AWS Administrator | Aspiring DevOps Engineer
