# AWS DevOps Assignment

## Overview

This project demonstrates the deployment of a Node.js and Express application on AWS using DevOps best practices. The application is deployed on an Amazon EC2 instance with Nginx as a reverse proxy, PM2 for process management, GitHub Actions for CI/CD, Amazon S3 for storage, IAM for least-privilege access, CloudWatch for monitoring, and k6 for load testing.

---

## Live Application

**Application URL:**

http://54.254.227.155

---

## Architecture

```
Developer
     │
     ▼
GitHub Repository
     │
     ▼
GitHub Actions (CI/CD)
     │
 SSH Deployment
     │
     ▼
AWS EC2 (Ubuntu)
     │
 ├── Node.js + Express
 ├── PM2
 └── Nginx Reverse Proxy
     │
     ▼
Public HTTP Access (Port 80)

AWS Services Used
-----------------
• Amazon S3
• IAM User (Least Privilege)
• Amazon CloudWatch Dashboard
• CloudWatch CPU Alarm
• SNS Notification
```

---

## Technologies Used

- AWS EC2
- Amazon S3
- IAM
- Amazon CloudWatch
- Amazon SNS
- Node.js
- Express.js
- PM2
- Nginx
- Git
- GitHub
- GitHub Actions
- k6

---

## Project Features

- Node.js application deployed on AWS EC2
- Nginx reverse proxy
- PM2 process management
- Automated deployment using GitHub Actions
- Amazon S3 bucket
- IAM least-privilege user
- CloudWatch monitoring dashboard
- CPU utilization alarm
- SNS email notification
- Performance testing using k6

---

## Deployment Steps

1. Launch an Ubuntu EC2 instance.
2. Configure the Security Group to allow SSH (22) and HTTP (80).
3. Install Node.js, Git, PM2, and Nginx.
4. Clone the GitHub repository.
5. Install dependencies using:

```
npm install
```

6. Start the application using PM2:

```
pm2 start server.js --name devops-app
```

7. Save PM2 configuration:

```
pm2 save
```

8. Configure Nginx as a reverse proxy.

9. Access the application using the EC2 public IP.

---

## CI/CD Pipeline

GitHub Actions automatically performs:

- Connect to EC2
- Pull latest source code
- Install dependencies
- Restart PM2 application

GitHub Secrets

- EC2_HOST
- EC2_USER
- EC2_SSH_KEY

---

## Monitoring

CloudWatch Dashboard includes:

- CPUUtilization
- NetworkIn
- NetworkOut

CloudWatch Alarm

- Alarm Name: high-cpu-alarm
- Threshold: CPUUtilization > 80%

---

## Load Testing

Tool: k6

| Metric | Result |
|--------|--------|
| Requests | 45,363 |
| Throughput | ~1511 req/s |
| Average Latency | 13.1 ms |
| P95 Latency | 19.45 ms |
| Error Rate | 0.00% |

---

## Screenshots

The screenshots folder includes:

- GitHub Repository
- GitHub Actions
- EC2 Instance
- Running Application
- S3 Bucket
- IAM User
- CloudWatch Dashboard
- CloudWatch Alarm
- k6 Load Test

---

## Author

**Manku Sireesha**

B.Tech Computer Science Engineering

Aspiring Cloud & DevOps Engineer

---

## License

This project was created for educational purposes as part of an AWS DevOps Assignment.
