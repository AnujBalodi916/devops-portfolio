# 🚀 DevOps CI/CD Portfolio Project

## 📌 Project Overview
This project demonstrates a real-world **end-to-end CI/CD pipeline** implemented using **Jenkins, Docker, Trivy, GitHub Webhooks, and AWS EC2**.  
The objective is to eliminate manual deployments, reduce human errors, and automate build, security scanning, and deployment processes.

---

## 🏗️ Architecture & Flow
**GitHub (Webhook) → Jenkins → Docker Build → Trivy Security Scan → Deployment on AWS EC2**

---

## 🛠️ Tools & Technologies Used
- **GitHub** – Source code management & webhook integration  
- **GitHub Webhooks** – Automatic CI trigger on every code push  
- **Jenkins** – CI/CD automation server  
- **Docker** – Application containerization  
- **Trivy** – Container image vulnerability scanning  
- **AWS EC2** – Application hosting  
- **Nginx** – Web server inside Docker container  

---

## 🔄 CI/CD Workflow (Step-by-Step)
1. Developer pushes code to the GitHub repository  
2. **GitHub Webhook automatically triggers Jenkins pipeline**  
3. Jenkins pulls the latest source code  
4. Docker builds a container image  
5. Trivy scans the Docker image for security vulnerabilities  
6. If no **CRITICAL** vulnerabilities are found, the pipeline proceeds  
7. Docker container is deployed on AWS EC2  
8. Application becomes live and accessible via public IP  

---

## 🔐 Security Implementation
- Trivy is used to scan Docker images for vulnerabilities  
- HIGH and CRITICAL vulnerabilities are evaluated  
- Current scan result: **0 Critical Vulnerabilities** ✅  

---

## ✅ Project Outcome
- Fully automated CI/CD pipeline triggered via **GitHub Webhooks**  
- Secure containerized deployment  
- Industry-standard DevOps tools and practices  
- No manual intervention required after code push  

---

## 🌐 Live Application
**http://3.110.186.105**

---

## 📌 Key Learnings
- CI/CD automation using Jenkins  
- Webhook-based pipeline triggering  
- Docker container lifecycle management  
- Container security scanning with Trivy  
- AWS EC2 deployment and networking  
- Real-world DevOps troubleshooting  

---

## 👥 Project Members
- **Anuj Balodi**  
- **Mayank Bhatt**  
- **Rahul Joshi**  
- **Bikram Singh**

---

## 💡 Resume / Interview Highlight
> Implemented a webhook-driven, end-to-end CI/CD pipeline using Jenkins, Docker, and Trivy with automated deployment on AWS EC2.
