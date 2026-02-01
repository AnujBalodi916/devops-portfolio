# 🚀 DevOps CI/CD Portfolio Project

## 📌 Project Overview
This project demonstrates a real-world **end-to-end CI/CD pipeline** implemented using **Jenkins, Docker, Trivy, and AWS EC2**.  
The goal of this project is to eliminate manual deployment, reduce errors, and automate build, security scanning, and deployment processes.

---

## 🏗️ Architecture & Flow
GitHub → Jenkins → Docker Build → Trivy Security Scan → Deployment on AWS EC2

---

## 🛠️ Tools & Technologies Used
- **GitHub** – Source code management
- **Jenkins** – CI/CD automation
- **Docker** – Application containerization
- **Trivy** – Container image vulnerability scanning
- **AWS EC2** – Application hosting
- **Nginx** – Web server inside Docker container

---

## 🔄 CI/CD Workflow (Step-by-Step)
1. Developer pushes code to GitHub repository
2. GitHub webhook automatically triggers Jenkins pipeline
3. Jenkins pulls the latest source code
4. Docker builds a container image of the application
5. Trivy scans the Docker image for security vulnerabilities
6. If no critical issues are found, the container is deployed on AWS EC2
7. Application becomes live and accessible via public IP

---

## 🔐 Security Implementation
- Trivy is used for container image scanning
- The image is checked for HIGH and CRITICAL vulnerabilities
- Current scan result: **0 critical vulnerabilities**

---

## ✅ Project Outcome
- Fully automated CI/CD pipeline
- Secure containerized deployment
- Real-world DevOps implementation using industry-standard tools
- No manual intervention required after code push

---

## 🌐 Live Application
The application is live and accessible at:

**http://3.110.186.105**

---

## 📌 Key Learning
- CI/CD automation using Jenkins
- Docker-based application deployment
- Security scanning with Trivy
- Cloud deployment on AWS EC2
