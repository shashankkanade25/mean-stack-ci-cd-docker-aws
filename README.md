# 📦MEAN Stack CI/CD Deployment 
Docker | GitHub Actions | AWS EC2


1️⃣ Project Overview:
- It’s a Dockerized MEAN app
- CI/CD via GitHub Actions
- Images pushed to Docker Hub
- Auto deployed to EC2
- Nginx reverse proxy configured
  
---

## 🏗 Architecture

```
User → Nginx (Frontend) → Backend (Node.js) → MongoDB
```
CI/CD Flow:
```
GitHub → GitHub Actions → Docker Hub → EC2 → Docker Compose
```
---

## 🐳 Docker Configuration

- Backend containerized using Node base image
- Frontend uses multi-stage Angular build
- Nginx serves frontend and proxies /api to backend
- Services orchestrated via Docker Compose

### 📸 Docker Compose Configuration

<img width="2879" height="721" alt="Screenshot 2026-02-24 030202" src="https://github.com/user-attachments/assets/81660aef-08fa-4621-9b17-0087164eb08a" />

## 📸 Nginx Reverse Proxy

<img width="1720" height="613" alt="Screenshot 2026-02-24 034645" src="https://github.com/user-attachments/assets/4c3a410a-4a53-40dc-b030-68fb55360ce3" />

---

## 🔁 CI/CD Pipeline (GitHub Actions)

Pipeline automatically runs on push to main.

Stages:

1. Checkout repository
2. Build backend image
3. Build frontend image
4. Push images to Docker Hub
5. SSH into EC2
6. Pull and redeploy containers

📸 Workflow File

<img width="2839" height="1698" alt="Screenshot 2026-02-25 011024" src="https://github.com/user-attachments/assets/d9d7fec9-f43f-4776-96ea-e41adc842b05" />

---

## 📦Docker Image Build & Push Proof

Images are pushed to Docker Hub registry.

📸 Docker Hub Repository
<img width="2531" height="792" alt="image" src="https://github.com/user-attachments/assets/71bbe13b-f719-480c-aa07-06e7e87c997d" />

---

## ☁ AWS EC2 Deployment
EC2 Setup Commands
```sudo apt update
sudo apt update -y
sudo apt install docker.io -y
sudo apt install docker-compose-plugin -y
```
Deploy Application
```
docker compose pull
docker compose up -d
```

---

## 🌐 Application Deployment

Application accessible at:

<http://44.220.147.117>

📸 Working UI

<img width="2879" height="1406" alt="Screenshot 2026-02-25 010929" src="https://github.com/user-attachments/assets/ce1bc6cb-1066-42e2-9c60-9de019e74f12" />

<img width="2879" height="1031" alt="Screenshot 2026-02-24 034416" src="https://github.com/user-attachments/assets/0b2ff966-2755-4442-8405-583dd6279eb8" />


---

## 🔐 Infrastructure Details

- Ubuntu EC2 instance
- Ports open: 80 (HTTP), 22 (SSH)
- Reverse proxy configured via Nginx

📸 EC2 Instance & Security Group

<img width="2879" height="483" alt="image" src="https://github.com/user-attachments/assets/de0a6231-dfe3-4059-bc05-d840d75f0c57" />

<img width="2782" height="936" alt="image" src="https://github.com/user-attachments/assets/af622c62-38a6-4a7e-8682-5ef3f3ee0783" />


