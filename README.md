Networking Assignment – Domain, EC2 & DNS

Successfully completed a hands-on networking assignment by purchasing my own domain zachahmed.co.uk, deploying an NGINX web server on AWS EC2, and configuring DNS** to make the website accessible via my custom domain.

This project demonstrates practical application of core networking concepts including DNS resolution, IP addressing, routing, firewall configuration, and HTTP protocols.

---

Project Outcome
Live website: http://zachahmed.co.uk
Web server: NGINX on AWS EC2  
DNS provider: GoDaddy

---

Architecture (End-to-End Flow)
User Browser  
→ DNS Resolution (GoDaddy)  
→ EC2 Public IP  
→ NGINX (Port 80)  
→ Web Page Response

---

Domain Registration (GoDaddy)
- Purchased zachahmed.co.uk via GoDaddy Registrar
- Managed DNS records using GoDaddy DNS dashboard

---

AWS EC2 Instance Setup
- Launched an Ubuntu EC2 instance
- Instance type: t2.micro
- Created and downloaded a new key pair for SSH access
- Instance assigned both:
  - Public IP (internet access)
  - Private IP (internal AWS networking)

---

Security Group Configuration
Configured an EC2 security group with the following inbound rules:

- Port 80 (HTTP) → Open to `0.0.0.0/0` (public web access)
- Port 22 (SSH) → For secure remote access

---

NGINX Installation on Ubuntu
Connected to the EC2 instance via SSH and installed NGINX:


ssh -i "my-key.pem" ubuntu@<ec2-public-ip>
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

---

DNS Configuration (GoDaddy)

Created the following A records in GoDaddy:

@ (root domain) → EC2 Public IP

www → EC2 Public IP

---

EC2 Instance

Security Groups

DNS Records

NGINX Status

Live Website

---

What I Learned
DNS in Practice

I gained hands-on experience with DNS resolution, understanding how a domain name like zachahmed.co.uk is translated into an IP address and routed to the correct server hosting the website.

Servers and IP Addressing

I learned that an EC2 instance has both public and private IP addresses. The public IP enables access from the internet, while the private IP is used for internal communication within AWS.

Security and Traffic Management

AWS Security Groups function as instance-level firewalls. Configuring inbound HTTP traffic on port 80 ensured the web server was accessible publicly while maintaining controlled access.

End-to-End Request Flow

Observing the complete request lifecycle — browser → DNS → EC2 → NGINX → response — helped me understand how network components interact in a real-world environment.

Challenge Encountered

Issue: The website initially did not load after configuring DNS.
Cause: DNS propagation delay.
Solution: Verified that NGINX was running correctly via the EC2 public IP, then waited for DNS propagation. After a few minutes, the domain successfully loaded the website.



After DNS propagation, the domain successfully resolved to the EC2 instance.x
sudo systemctl status nginx
