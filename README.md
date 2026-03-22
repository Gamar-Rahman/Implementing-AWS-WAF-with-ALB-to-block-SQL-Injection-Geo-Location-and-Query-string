# Implementing-AWS-WAF-with-ALB-to-block-SQL-Injection-Geo-Location-and-Query-string

### Overview

This project demonstrates how to secure a web application using AWS WAF integrated with an Application Load Balancer (ALB) to block malicious traffic including:
SQL Injection attacks
Geo-restricted access
Suspicious query strings

 ### Key Concepts
🔹 What is Amazon EC2?

Amazon EC2 provides scalable virtual servers in the cloud to host applications.

🔹 What is Elastic Load Balancing (ELB)?

ELB distributes incoming traffic across multiple EC2 instances, ensuring:

High availability
Fault tolerance
Automatic scaling
🔹 What is AWS WAF?

AWS WAF is a Web Application Firewall that filters and monitors HTTP requests, protecting applications from common exploits like:

SQL Injection

bots

### Problem Statement

Web applications are highly vulnerable to attacks such as:

SQL Injection
Malicious query manipulation
Unauthorized geographic access

### The challenge:
How can we block malicious traffic before it reaches backend servers?

### Solution

We implemented:

Application Load Balancer (ALB) as the entry point
AWS WAF Web ACL attached to ALB
Custom rules to filter and block malicious requests
Cross-Site Scripting (XSS)
Malicious bots

### Implementation Steps
Launch two EC2 instances
Configure web servers
Create Target Group
Deploy Application Load Balancer
Verify traffic routing
Create AWS WAF Web ACL
Add rules:
SQL Injection match
Geo-location restriction
Query string filtering
Associate WAF with ALB
Test attack scenarios

### Security Controls Implemented
✅ SQL Injection protection
✅ Geo-blocking (restrict countries)
✅ Query string filtering
✅ Traffic inspection before backend

### Testing
| Test Case             | Result     |
| --------------------- | ---------  |
| SQL Injection payload | Blocked ❌ |
| Unauthorized country  | Blocked ❌ |
| Valid request         | Allowed ✅ |


### Key Security Insight

Placing AWS WAF in front of ALB ensures:

Attacks are blocked before reaching EC2
Reduced attack surface
Improved application resilience

### Future Improvements
Integrate AWS Shield for DDoS protection
Automate deployment using Terraform
Enable logging & monitoring with CloudWatch

