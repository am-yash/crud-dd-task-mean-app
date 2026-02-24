# 🚀 MEAN Stack Application – DevOps CI/CD Assignment

This project demonstrates a complete **DevOps workflow** for a **MEAN stack (MongoDB, Express, Angular, Node.js)** application.  
The application is fully **containerized**, **deployed on an Ubuntu EC2 instance**, and **automated using a Jenkins CI/CD pipeline** with Docker and Docker Compose.

---

## 📌 Project Overview

The application is a **CRUD (Create, Read, Update, Delete)** system for managing tutorials.  
Each tutorial contains:
- ID
- Title
- Description
- Published status

### Features
- Create, update, delete tutorials
- View all tutorials
- Search tutorials by title
- Full frontend–backend integration
- MongoDB database for persistence

---

## 🛠 Tech Stack Used

### Application
- Frontend: Angular 15
- Backend: Node.js + Express
- Database: MongoDB

### DevOps / Infrastructure
- Docker & Docker Compose
- Nginx (Reverse Proxy)
- Jenkins (CI/CD Pipeline)
- AWS EC2 (Ubuntu)
- Docker Hub (Image Registry)

---

## 📂 Project Structure

```
crud-dd-task-mean-app/
├── backend/
│   ├── Dockerfile
│   ├── server.js
│   ├── package.json
│   └── app/
│
├── frontend/
│   ├── Dockerfile
│   ├── nginx.conf
│   ├── angular.json
│   ├── src/
│   └── package.json
│
├── docker-compose.yml
├── Jenkinsfile
└── README.md
```

---

## 🐳 Dockerization

### Backend
- Built using `node:18-alpine`
- Exposes port `3000`
- Connects to MongoDB via environment variables

### Frontend
- Angular app built using multi-stage Docker build
- Served using **Nginx**
- Exposes port `80`

---

## 🧩 Docker Compose Setup

Docker Compose is used to run all services together:

- Frontend (Angular + Nginx)
- Backend (Node.js + Express)
- MongoDB (Official image)
- Persistent MongoDB volume

### Services & Ports
- Frontend → Port 80
- Backend → Port 3000
- MongoDB → Port 27017

---

## 🌐 Nginx Reverse Proxy

- Nginx serves the Angular frontend on port **80**
- Backend APIs are accessed internally via Docker network
- HTTPS and domain mapping are not required (as per assignment)

---

## 🔁 CI/CD Pipeline (Jenkins)

The project uses a **Jenkins Declarative Pipeline** for automation.

### Pipeline Stages
1. Checkout code from GitHub
2. Build backend Docker image
3. Build frontend Docker image
4. Login to Docker Hub using Jenkins credentials
5. Push Docker images to Docker Hub
6. Deploy application using Docker Compose

---

## 🔐 Credentials Management

- Docker Hub credentials are stored securely in **Jenkins Credentials**
- No secrets are hard-coded in the repository

---

## ☁️ Deployment Environment

- Cloud Provider: AWS
- OS: Ubuntu
- Jenkins installed on EC2
- Docker & Docker Compose installed

---

## ▶️ Run the Project Manually

### 1️⃣ Clone Repository
```
git clone https://github.com/am-yash/crud-dd-task-mean-app.git
cd crud-dd-task-mean-app
```

### 2️⃣ Build Docker Images
```
docker build -t yashdockerio/mean-backend backend/
docker build -t yashdockerio/mean-frontend frontend/
```

### 3️⃣ Start Application
```
docker-compose up -d
```

### 4️⃣ Access Application
```
http://18.189.30.196/tutorials
```

---

## 📸 Screenshots

The repository includes screenshots of:
- Jenkins pipeline execution
![Jenkins pipeline execution screenshot](./Screenshot%202026-02-24%20164248.png)
- Running containers
![Alt text](./Screenshot%202026-02-24%20164420.png)
- Application UI
![Application UI](./Screenshot%202026-02-24%20164302.png)

---

## 🧠 Key Learnings

- End-to-end CI/CD pipeline implementation
- Docker multi-stage builds
- Jenkins pipeline debugging
- Real-world containerized deployment
- Nginx reverse proxy configuration

---

## ✅ Assignment Requirements Status

| Requirement | Status |
|------------|--------|
GitHub repository | ✅ |
Dockerized frontend & backend | ✅ |
Docker Hub images | ✅ |
MongoDB using Docker | ✅ |
Docker Compose deployment | ✅ |
CI/CD with Jenkins | ✅ |
Nginx reverse proxy on port 80 | ✅ |

---

## 👤 Author

**Yash Vishwakarma**  
B.Tech CSE (2026)  
DevOps & Cloud Enthusiast  

- GitHub: https://github.com/am-yash  
- Docker Hub: https://hub.docker.com/u/yashdockerio  
- LinkedIn: https://www.linkedin.com/in/yash-vishwakarma-devops/

---

## 📌 Final Note

This project was completed as part of a **DevOps Engineer Internship assignment**, focusing on practical implementation of containerization, CI/CD automation, and cloud deployment best practices.
