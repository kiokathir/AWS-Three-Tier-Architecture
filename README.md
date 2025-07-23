# AWS-Three-Tier-Architecture

This architecture demonstrates a three-tier web application deployed in the ap-south-1 (Mumbai) AWS region. It is designed for high availability, scalability, and security using AWS best practices.

🔸 1. Presentation Tier (Web Layer)
User → awskathirdevops.shop (Domain)

The user accesses the web app via a custom domain.

AWS WAF protects against attacks like SQL injection and XSS.

Amazon CloudFront serves cached content quickly worldwide.

Static files (HTML, CSS, JS) are stored in an Amazon S3 bucket.

Requests are routed through an Internet-Facing Load Balancer (ALB) to web servers.

🔸 2. Application Tier (Logic Layer)
Web requests are passed from the Web Tier to the Application Tier.

Webserver-ASG (Auto Scaling Group) contains EC2 instances for hosting the website.

Internal Load Balancer routes traffic to the Appserver-ASG (business logic servers).

This layer handles application logic and API processing.

🔸 3. Database Tier (Data Layer)
Backend EC2 servers connect to Amazon RDS (Relational Database Service).

The Primary RDS handles live traffic.

A Standby RDS in another Availability Zone provides automatic failover (Multi-AZ setup).

✅ Key Features
Highly Available: Spread across multiple availability zones with auto-scaling.

Scalable: Auto Scaling Groups allow resources to scale based on traffic.

Secure:

WAF and Security Groups protect the application.

Public and private subnets provide network isolation.

IAM roles manage access to AWS services.

🧩 Technologies Used
Amazon EC2 (Web & App Servers)

Amazon S3 (Static Assets)

Amazon RDS (Database)

CloudFront, WAF, Route 53

Application Load Balancer (Public & Internal)

Auto Scaling Groups (ASG)


for output and diagrams refer the attached files
