# 🌐 AWS VPC Architecture: Bastion Host, NAT Gateway, ALB & Python Application

## 📌 Overview

This project demonstrates a production-style AWS VPC architecture implementing secure networking, controlled access, and application load balancing.

The setup includes:
- Public and Private Subnets
- Bastion Host for secure SSH access
- NAT Gateway for outbound internet access
- Application Load Balancer (ALB)
- Target Group for backend EC2 instances
- Python web server hosted on EC2 instances

This simulates a real-world multi-tier web application architecture used in production environments.

---

## 🏗️ Architecture Design

### 🔹 Core Components

- Custom VPC
- Public Subnets (2 AZs)
- Private Subnets (2 AZs)
- Internet Gateway (IGW)
- NAT Gateway
- Bastion Host (Jump Server)
- Application Load Balancer (ALB)
- Target Group
- EC2 Instances (Bastion + Application Servers)
- Python Web Server (Flask / HTTP Server)
- Route Tables (Public & Private)

---

## 📊 Traffic Flow

### 🌍 Internet Access Flow

1. Users access application via ALB DNS
2. ALB forwards traffic to Target Group
3. Target Group routes request to EC2 instances running Python server

---

### 🔐 Secure Admin Access Flow

1. Admin connects to Bastion Host (Public Subnet)
2. Bastion Host is used to SSH into Private EC2 instances
3. Private instances are NOT directly exposed to the internet

---

### 🌐 Outbound Access Flow

- Private EC2 instances access internet via NAT Gateway
- No direct inbound access is allowed to private subnet

---

## 🔐 Security Architecture

- Private EC2 instances are not publicly accessible
- Bastion Host acts as secure entry point for SSH access
- Security Groups restrict access to required ports only
- ALB handles external traffic instead of exposing EC2 directly
- NAT Gateway enables secure outbound internet access

---

## ⚙️ Implementation Steps

### 1. VPC Setup
- Created custom VPC with CIDR block

### 2. Subnet Design
- Public Subnets → Bastion Host, NAT Gateway, ALB
- Private Subnets → Application EC2 instances

### 3. Internet Gateway
- Attached IGW to enable internet access for public subnet

### 4. NAT Gateway
- Configured NAT Gateway in public subnet
- Enabled outbound internet access for private EC2 instances

### 5. Bastion Host Setup
- Launched EC2 instance in public subnet
- Used as jump server to access private instances via SSH

### 6. Application Deployment
- Installed Python on EC2 instances
- Hosted simple web server (Flask / HTTP server)
- Application runs inside private subnet

### 7. Target Group Configuration
- Created Target Group for EC2 instances
- Registered private EC2 instances as targets

### 8. Application Load Balancer (ALB)
- Configured ALB in public subnet
- Attached Target Group to ALB listener
- ALB routes HTTP traffic to backend instances

### 9. Route Table Configuration
- Public Route Table → Internet Gateway
- Private Route Table → NAT Gateway

### 10. Validation
- Accessed application via ALB DNS name
- Verified private instances are not directly reachable
- SSH access confirmed via Bastion Host
- Python application successfully served via ALB

---

## 📸 Screenshots

![Resource Map](screenshots/02-aws-resource-map.png)
![EC2 Instances](screenshots/03-ec2-instances.png)
![Load Balancer](screenshots/04-load-balancer.png)
![Target Group](screenshots/05-target-group-healthy.png)
![PEM Copy](screenshots/06-scp-pem-copy.png)
![PEM Error](screenshots/07-pem-permission-error.png)
![Python Server](screenshots/09-python-http-server.png)
![Final Output](screenshots/11-final-webpage.png)

---

## 🧠 Key Learnings

- VPC design and subnet segmentation
- Bastion Host architecture pattern
- NAT Gateway for secure outbound internet access
- Load Balancing using ALB + Target Groups
- Deploying Python applications on EC2
- Real-world AWS multi-tier architecture design
- Security-first cloud infrastructure design

---

## 🚀 Outcome

Successfully built a secure, scalable AWS architecture that demonstrates:

- Public/private subnet isolation
- Secure SSH access using Bastion Host
- Load-balanced Python application using ALB
- Proper traffic routing using Target Groups

This project represents a production-style AWS architecture suitable for DevOps and Cloud Engineering roles.
