
# 🚀 ECOMMERCE APP

## CI / CD Pipeline with Jenkins | Docker | Docker Hub

---

## 📌 Project Overview

This project demonstrates a complete CI/CD pipeline automation using:

* GitHub (Source Code Management)
* Jenkins (Automation Server)
* Docker (Containerization)
* Docker Hub (Image Registry)
* Ubuntu Server (Deployment Environment)

The application is containerized using Docker and automatically built, tagged, and pushed to Docker Hub via Jenkins Pipeline.

---

## 🏗 Architecture Flow

Developer pushes code to GitHub
⬇
Jenkins detects change and triggers pipeline
⬇
Code is pulled from GitHub
⬇
Docker image is built
⬇
Docker login to Docker Hub
⬇
Image is tagged
⬇
Image is pushed to Docker Hub
⬇
Container is deployed

---

## 🛠 Technologies Used

* Ubuntu Server
* Jenkins
* Docker Engine
* Docker Hub
* Git
* Nginx (Base Image)

---

## 📦 Docker Commands

### ✅ Build Image

```
docker build -t ecom-images .
```

---

### ✅ Tag Image

```
docker tag ecom-images <dockerhub-username>/ecom-app:1.0
```

---

### ✅ Login to Docker Hub

```
docker login
```

OR Using Token:

```
echo <TOKEN> | docker login -u <username> --password-stdin
```

---

### ✅ Push Image

```
docker push <dockerhub-username>/ecom-app:1.0
```

---

## 🚀 Jenkins Pipeline Stages

### 1. Pull Code

Clones latest code from GitHub repository.

### 2. Build

Builds Docker image from Dockerfile.

### 3. Docker Login

Authenticates with Docker Hub using stored credentials.

### 4. Tag & Push

Tags image and pushes it to Docker Hub.

### 5. Deploy

Runs container from pushed image:

```
docker run -d -p 8080:80 <dockerhub-username>/ecom-app:1.0
```

---

## 🔐 Jenkins Credentials Setup

Go to:

Jenkins → Manage Jenkins → Credentials → Global

Add:

* Kind: Username with password
* Username: Docker Hub username
* Password: Access Token
* ID: `dockerhub`

---

## ⚡ How To Run

1. Push code to GitHub
2. Jenkins automatically triggers pipeline
3. Image is built
4. Image is pushed to Docker Hub
5. Application gets deployed

---

## 🔮 Future Improvements

* Auto Versioning using `${BUILD_NUMBER}`
* Docker Compose Integration
* Automated Testing Stage
* Kubernetes Deployment
* Auto Cleanup of Old Images

---


## 👩‍💻 Author : Kaneri Taklikar

Created for DevOps Practice – End to End CI/CD Automation

