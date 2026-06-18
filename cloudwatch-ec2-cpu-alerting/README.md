# EC2 CPU Monitoring and Alerting using CloudWatch and SNS

## Project Overview

This project demonstrates how to monitor an Amazon EC2 instance using Amazon CloudWatch and configure automated email notifications through Amazon SNS when CPU utilization exceeds a defined threshold.

The objective of this project is to gain hands-on experience with AWS monitoring, alerting, and notification mechanisms commonly used in production environments.

---

## Project Type

AWS Monitoring & Alerting Mini Project

---

## AWS Services Used

- Amazon EC2
- Amazon CloudWatch
- Amazon SNS

---

## Architecture

```text
EC2 Instance
     │
     ▼
CloudWatch Metrics
     │
     ▼
CloudWatch Alarm
     │
     ▼
SNS Topic
     │
     ▼
Email Notification
```

---

## Implementation Steps

### Step 1: Launch EC2 Instance

An Amazon EC2 instance was launched to monitor its CPU utilization.

Screenshot:

![EC2 Instance](screenshots/01-ec2-instance.png)

---

### Step 2: Create SNS Topic

An Amazon SNS topic was created to receive notifications from CloudWatch alarms.

Screenshot:

![SNS Topic](screenshots/02-sns-topic-created.png)

---

### Step 3: Subscribe an Email Endpoint

An email subscription was added to the SNS topic and confirmed successfully.

Screenshot:

![Subscription Confirmed](screenshots/03-email-subscription-confirmed.png)

---

### Step 4: Select EC2 CPU Metric

Navigated to CloudWatch Metrics and selected the EC2 CPUUtilization metric.

Path:

CloudWatch → Metrics → EC2 → Per-Instance Metrics → CPUUtilization

Screenshot:

![CPU Metric](screenshots/04-cloudwatch-metric-selected.png)

---

### Step 5: Configure CloudWatch Alarm

Configured a CloudWatch alarm with a static threshold for CPU utilization and associated it with the SNS topic.

Example Configuration:

- Metric: CPUUtilization
- Threshold Type: Static
- Condition: Greater than threshold
- Threshold Value: 70%
- Evaluation Period: 1 datapoint within 5 minutes

Screenshot:

![Alarm Configuration](screenshots/05-cloudwatch-alarm-configuration.png)

---

### Step 6: Create and Verify Alarm

Created the alarm and verified that it was successfully deployed.

Screenshot:

![Alarm Created](screenshots/06-alarm-created.png)

---

### Step 7: Alarm Triggered

Verified that the CloudWatch alarm changed its state from **OK** to **ALARM**, confirming that monitoring and alerting were functioning correctly.

Screenshot:

![Alarm Triggered](screenshots/07-alarm-state-triggered.png)

---

### Step 8: Receive Email Notification

Received an email notification through Amazon SNS after the alarm entered the ALARM state.

Screenshot:

![Email Notification](screenshots/08-email-notification-received.png)

---

## Key Learnings

- Understanding CloudWatch Metrics
- Creating and managing CloudWatch Alarms
- Configuring Amazon SNS Topics
- Managing SNS Email Subscriptions
- Monitoring EC2 performance metrics
- Implementing basic alerting and notification workflows
- Understanding AWS observability fundamentals

---

## Future Enhancements

- CloudWatch Dashboards
- Slack Notifications
- Lambda-based Auto Remediation
- Integration with AWS Systems Manager
- Monitoring additional EC2 metrics such as Memory and Disk Utilization

---

## Author

Shruti Gupta

AWS Administrator | Aspiring DevOps Engineer
