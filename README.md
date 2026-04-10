🚀 DevOps CI/CD Pipeline Project (Jenkins + Docker + AWS + Monitoring)

📌 Project Overview

This project demonstrates a complete CI/CD pipeline that automatically builds, tests, scans, pushes, and deploys a containerized web application using DevOps tools and practices.

The pipeline is triggered automatically whenever code is pushed to GitHub.

🏗️ Architecture

Developer → GitHub → Jenkins → Docker Build → Trivy Security Scan → Docker Hub → EC2 Deployment → Monitoring (Prometheus + Grafana)

⚙️ Tech Stack

Git & GitHub

Jenkins (CI/CD Automation)

Docker

Docker Hub (Container Registry)

AWS EC2 (Deployment Server)

Prometheus (Monitoring)

Grafana (Dashboard & Visualization)

Trivy (Security Scanning)


📂 Project Structure

ai-vision-website/

│

├── website/

│   ├── index.html

│   ├── style.css

│

├── Dockerfile

├── Jenkinsfile

├── .env.example

└── README.md


🐳 Docker Setup


Build Image

docker build -t pravinukunde/ai-static-site .

Run Container

docker run -d -p 3000:80 pravinukunde/ai-static-site


👉 Application Access:
http://<EC2PUBLICIP>:3000

🔄 CI/CD Pipeline (Jenkins)

Pipeline Stages:

Checkout

  Pull source code from GitHub
  
Build

  Build Docker image
  
Test

  Run basic validation tests
  
Security Scan

  Scan Docker image using Trivy
  
Push Image

  Push Docker image to Docker Hub
  
Deploy

  Run container on AWS EC2 instance
  

Jenkins Pipeline Flow

Git Push → Jenkins Trigger → Build → Test → Security Scan → Docker Hub → Deploy


🔐 Security Integration

Tool used:

Trivy

trivy image pravinukunde/ai-static-site

✔ Detects vulnerabilities in Docker images

✔ Ensures secure container deployment


☁️ Deployment (AWS EC2)

Deployment Command

docker run -d -p 3000:80 pravinukunde/ai-static-site

Access Application

http://<EC2-PUBLIC-IP>:3000


📊 Monitoring Setup

Tools Used

 Prometheus
 
 Grafana
 
Metrics Monitored

 ✔ CPU Usage
 
 ✔ Memory Usage
 
 ✔ Container Health
 

Access URLs

Tool	URL

Prometheus	http://<EC2IP>:9090

Grafana	http://<EC2IP>:3001


📦 Docker Hub Image

pravinukunde/ai-static-site


🔁 CI/CD Flow Diagram

Developer

   ↓
   
GitHub Push

   ↓
   
Jenkins Pipeline

   ↓
   
Docker Build

   ↓
   
Trivy Security Scan

   ↓
   
Docker Hub Push

   ↓
   
EC2 Deployment

   ↓
   
Monitoring (Grafana + Prometheus)


📌 Key Features

✔ Fully automated CI/CD pipeline

✔ Dockerized application

✔ Security scanning integrated

✔ Cloud deployment on AWS EC2

✔ Monitoring with Prometheus & Grafana

✔ Auto-trigger via GitHub webhook


🎯 Learning Outcome

This project demonstrates:

CI/CD automation using Jenkins

Containerization using Docker

Secure DevOps practices

Cloud deployment on AWS

Real-time monitoring setup


👨‍💻 Author

Pravin Ukunde

Cloud & DevSecOps Engineer (2+ Years Experience)


🚀 Status

✅ Project Completed Successfully


