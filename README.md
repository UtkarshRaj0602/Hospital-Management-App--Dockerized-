# Hospital-Management-App-Dockerized
A full-stack Hospital Management System built using **Node.js, Express, MySQL**, now fully containerized using **Docker, Multi-stage builds, and Docker Compose** for seamless local deployment.

This project is forked from the following github repo - https://github.com/s-a-zhd/Hospital-Management-Using-NodeJs-Mysql-Express.git

---

## 🚀 Features

- User Authentication (Login/Signup)
- Doctor & Patient Management
- Appointment Booking System
- Session Handling
- MySQL Database Integration
- Fully Dockerized Setup

---

## 🐳 Dockerization Highlights

This project is containerized with:

- ✅ Multi-stage Docker build (optimized image size)
- ✅ Docker Compose for multi-container orchestration
- ✅ MySQL container with persistent volume
- ✅ Automatic DB initialization using SQL script
- ✅ Environment-based configuration
- ✅ Internal Docker networking (service-to-service communication)

---

## 📁 Project Structure

.
├── backend/
│ ├── app.js
│ ├── package.json
│ ├── models/
│ ├── controllers/
│ ├── views/
│ ├── public/
│ ├── nodelogin.sql
│ ├── Dockerfile
│ └── .dockerignore
│
├── docker-compose.yml
└── .env

---

## ⚙️ Prerequisites

Make sure you have installed:

- Docker
- Docker Compose

---

## 🔧 Environment Variables

Create a `.env` file in root:

```env
DB_HOST=mysql
DB_USER=appuser
DB_PASSWORD=apppassword
DB_NAME=hospital_db
DB_PORT=3306
PORT=3000
```

---

## 🐳 Docker Setup

🔨 Build and Run Containers
docker-compose up --build

🧹 Clean Setup (Recommended First Run)
docker-compose down -v
docker-compose up --build

## 🌐 Access Application
Open in browser:

http://localhost:3000

---

## 🗄️ Database Setup

MySQL container automatically initializes database
SQL file used:
backend/nodelogin.sql
Loaded via:
/docker-entrypoint-initdb.d/

---

## 🧠 Docker Architecture

Browser
   ↓
Node.js App (Container)
   ↓
MySQL (Container)

## 🔥 Multi-Stage Docker Build

Stage 1 (Builder)
Installs dependencies
Prepares application
Stage 2 (Runner)
Lightweight image (node:alpine)
Copies only required files
Reduces image size

---

🧩 Docker Compose Services

Backend Service
Node.js app container
Exposes port 3000
Uses .env for config
MySQL Service
MySQL 8.0 container
Persistent storage using volumes
Auto DB initialization


The Docker Images are hosted on Docker Hub. You can access it using the following link - https://hub.docker.com/r/dockerutkarsh99/hospital-management-app

