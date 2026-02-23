# Networking Assignment – Domain, EC2 & DNS Deployment

## 📌 Project Overview

This project demonstrates practical networking and cloud deployment skills by building a live website hosted on AWS infrastructure.

The assignment involved purchasing a custom domain, deploying a web server on an EC2 instance, and configuring DNS records to make the website publicly accessible.

The project showcases real-world implementation of networking fundamentals such as DNS resolution, IP routing, firewall configuration, and HTTP web server hosting.

### 🌍 Live Website
- http://zachahmed.co.uk

---

## 🏗 System Architecture (End-to-End Request Flow)

The website follows this request lifecycle:
User Browser
↓
DNS Resolution (GoDaddy DNS Servers)
↓
Domain mapped to EC2 Public IP Address
↓
AWS EC2 Instance receives request
↓
NGINX Web Server listens on Port 80
↓
Website content is returned to the browser


This architecture demonstrates how web traffic travels across network layers before reaching the hosted application.

---

## 🌐 Domain Registration & DNS Management

### Domain Purchase

- Purchased custom domain: `zachahmed.co.uk`
- Domain registration was completed through a domain registrar platform.

### DNS Configuration

Configured DNS A records to map the domain to the EC2 instance public IP.

The following DNS records were created:

- Root domain (`@`) → EC2 Public IP address
- `www` subdomain → EC2 Public IP address

This ensured both domain versions correctly resolved to the hosted server.

---

## ☁️ AWS EC2 Instance Setup

### Instance Configuration

- Ubuntu-based EC2 virtual machine
- Instance type: `t2.micro`
- Generated SSH key pair for secure server access

The instance was assigned:

- Public IP address for internet accessibility
- Private IP address for internal AWS networking communication

---

## 🔐 Security Group Configuration

Security groups were configured as virtual firewall rules to control network traffic.

### Inbound Rules

| Protocol | Port | Purpose |
|---|---|---|
| TCP | 80 | HTTP web traffic |
| TCP | 22 | SSH remote server access |

These rules allowed public web access while maintaining secure administrative access.

---

## 🖥 Web Server Deployment (NGINX)

NGINX was installed and configured as the web server.

### Server Setup Commands

sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

---

Verify NGINX Status
sudo systemctl status nginx

This ensured the web server was running properly.

---


📡 Networking Concepts Demonstrated
This project demonstrates understanding of several core networking principles:

Domain Name System (DNS) resolution

IP addressing and routing

Firewall security configuration

HTTP protocol communication

Client-server request lifecycle

⏳ DNS Propagation Observation
After configuring DNS records, the website did not immediately become accessible.

This was caused by DNS propagation delay across global DNS servers.

Troubleshooting Steps

Verified NGINX service was running using EC2 public IP.

Confirmed security group port 80 was open.

Waited for DNS propagation to complete.

After propagation, the domain successfully resolved to the EC2 instance.

🧠 Key Learning Outcomes

Practical experience with cloud infrastructure deployment

Understanding how DNS translates domain names into IP addresses

Server configuration and web hosting fundamentals

Network security using firewall rules

End-to-end request-response flow

⚠️ Challenges Encountered – DNS Propagation Delay

Issue: Website was not immediately accessible after DNS configuration.

Cause: Global DNS record update latency.

Solution:

Verified NGINX service status

Checked EC2 public IP accessibility

Waited for propagation completion

📸 Evidence Screenshots Included

Web application running on custom domain

NGINX server status verification

EC2 instance dashboard

DNS configuration records

🚀 Future Improvements

Implement HTTPS using SSL/TLS certificates

Add automated deployment pipeline

Configure load balancing

Introduce monitoring and logging

Containerise the application using Docker

Website content is returned to the browser







