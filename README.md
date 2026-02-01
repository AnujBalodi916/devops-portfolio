# 🚀 DevOps CI/CD Portfolio Project

## 📌 Overview
This project demonstrates an end-to-end CI/CD pipeline using Jenkins, Docker, and AWS EC2 to deploy a containerized web application with security scanning.

## 🏗️ Architecture
GitHub → Jenkins → Docker Build → Trivy Scan → Deploy on AWS EC2

## 🛠️ Tools & Technologies
- Jenkins (CI/CD automation)
- Docker (Containerization)
- AWS EC2 (Deployment)
- GitHub (Source Control)
- Trivy (Container Security Scanning)
- Nginx (Web Server)

## 🔄 CI/CD Workflow
1. Source code is pushed to GitHub
2. Jenkins pulls the repository
3. Docker image is built
4. Trivy scans the image for vulnerabilities
5. Application is deployed automatically on EC2

## 🔐 Security
- Container image scanned using Trivy
- Zero HIGH or CRITICAL vulnerabilities detected

## ✅ Outcome
- Fully automated CI/CD pipeline
- Secure containerized deployment
- Real-world DevOps workflow implementation

## 🌐 Live Demo
Access the deployed application via EC2 public IP.
