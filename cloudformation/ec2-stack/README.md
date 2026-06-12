# AWS CloudFormation - EC2 Stack

## Project Objective

This project demonstrates how to launch an EC2 instance using AWS CloudFormation (Infrastructure as Code).

Instead of manually creating resources in the AWS Console, infrastructure was deployed using a YAML template.

## Services Used

* AWS CloudFormation
* Amazon EC2

## Files

* `ec2-basic.yaml` → CloudFormation template
* `screenshots/` → Deployment screenshots

## Steps Performed

1. Created a CloudFormation YAML template.
2. Uploaded the template in AWS CloudFormation.
3. Created a stack.
4. Automatically deployed an EC2 instance.

## Challenges Faced

### 1. Invalid AMI ID Error

**Issue:** Stack creation failed due to an invalid AMI ID.

**Cause:** AMI IDs are region-specific.

**Fix:** Updated the template with the correct AMI ID for `ap-south-1`.

### 2. Free Tier Instance Type Error

**Issue:** `t2.micro` was not eligible.

**Fix:** Changed the instance type to `t3.micro`.

## Outcome

Successfully deployed an EC2 instance using Infrastructure as Code (IaC) with AWS CloudFormation.
