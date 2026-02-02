# 🚀 DevOps CI/CD Portfolio Project

## 📌 Project Overview
This project demonstrates a real-world **end-to-end CI/CD pipeline** implemented using **Jenkins, Docker, Trivy, and AWS EC2**.  
The objective of this project is to eliminate manual deployments, reduce human errors, and automate build, security scanning, and deployment processes.

---

## 🏗️ Architecture & Flow
GitHub → Jenkins → Docker Build → Trivy Security Scan → Deployment on AWS EC2

---

## 🛠️ Tools & Technologies Used
- **GitHub** – Source code management & webhook trigger  
- **Jenkins** – CI/CD automation  
- **Docker** – Application containerization  
- **Trivy** – Container image vulnerability scanning  
- **AWS EC2** – Application hosting  
- **Nginx** – Web server inside Docker container  

---

## 🔄 CI/CD Workflow (Step-by-Step)
1. Developer pushes code to the GitHub repository  
2. GitHub webhook automatically triggers the Jenkins pipeline  
3. Jenkins pulls the latest source code  
4. Docker builds a container image  
5. Trivy scans the Docker image for security vulnerabilities  
6. If no **CRITICAL** vulnerabilities are found, the pipeline proceeds  
7. Docker container is deployed on AWS EC2  
8. Application becomes live and accessible via public IP  

---

## 🔐 Security Implementation
- Trivy is used to scan Docker images  
- HIGH and CRITICAL vulnerabilities are evaluated  
- Current scan result: **0 Critical Vulnerabilities** ✅  

---

## ✅ Project Outcome
- Fully automated CI/CD pipeline  
- Secure containerized deployment  
- Industry-standard DevOps tools and practices  
- No manual intervention required after code push  

---

## 🌐 Live Application
**http://3.110.186.105**

---

## 📌 Key Learnings
- CI/CD automation using Jenkins  
- Docker-based application deployment  
- Container security scanning with Trivy  
- Cloud deployment and networking on AWS EC2  
- Real-world DevOps troubleshooting and implementation  

---

## 👥 Project Members
- **Anuj Balodi**  
- **Mayank Bhatt**  
- **Rahul Joshi**  
- **Bikram Singh**

---

## 💡 Resume / Interview Highlight
> Implemented a secure, end-to-end CI/CD pipeline using Jenkins, Docker, and Trivy with automated deployment on AWS EC2.
