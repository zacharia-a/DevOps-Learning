📌 Amazon Web Services (AWS) - VPC, Subnet & EC2 Deployment
🌐 Overview

This project was built using Amazon Web Services (AWS) to design and deploy a secure virtual network infrastructure.

The architecture demonstrates fundamental cloud networking principles by separating resources into public and private environments using Virtual Private Cloud (VPC) segmentation.

The project includes:

Custom VPC creation

Public and private subnet configuration

Internet Gateway and NAT Gateway setup

EC2 instance deployment

Security group enforcement

Web server installation using NGINX

---

🏗 Architecture Design

The infrastructure was structured as follows:

VPC CIDR Block → 10.0.0.0/16

Public Subnet → Internet-facing resources

Private Subnet → Internal restricted resources

Internet access was controlled through:

Internet Gateway for public subnet traffic

NAT Gateway for secure outbound private subnet traffic

---

⚙️ Technologies Used

Cloud Platform: AWS

Networking: VPC, Subnets, Route Tables

Compute: EC2 Instances

Security: Security Groups

Operating System: Ubuntu

---

🚀 Implementation Steps
1. VPC Setup

Created a custom VPC using CIDR block 10.0.0.0/16

Enabled DNS hostname and DNS resolution

2. Subnet Configuration

Created:

One public subnet

One private subnet

3. Internet Connectivity

Created and attached an Internet Gateway

Allocated an Elastic IP

Created a NAT Gateway inside the public subnet

4. Route Table Configuration

Public Route Table:

Route: 0.0.0.0/0 → Internet Gateway

Associated with public subnet

Private Route Table:

Route: 0.0.0.0/0 → NAT Gateway

Associated with private subnet

5. EC2 Instance Deployment

Public EC2 Instance:

Deployed in public subnet

Assigned public IP address

Private EC2 Instance:

Deployed in private subnet

No public IP assigned

6. Security Group Configuration

Public EC2 Security Group:

Allowed SSH access from my IP address

Allowed HTTP traffic

Private EC2 Security Group:

Allowed internal network communication only

--- 

⚠️ Challenges Faced

SSH connection failures due to incorrect key pair file permissions

Target group health status initially showing no registered healthy instances

Understanding how to securely access private EC2 instances

I resolved these issues by verifying key permissions, network rules, and instance configurations.

---

🔒 Security Considerations

Restricted SSH access to my personal IP address

Prevented direct internet exposure of private instances

Used subnet isolation to improve security posture

---

📈 Future Improvements

Deploy a dedicated Bastion Host instead of using the public EC2 instance for private instance access

Implement Application Load Balancer for high availability

Add monitoring using CloudWatch metrics and alarms

Introduce auto-scaling groups for production scalability

Enable HTTPS using SSL/TLS certificates

Configure stricter Network Access Control Lists
