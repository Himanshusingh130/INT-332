# 🚀 Docker Commands & DevOps Projects Repository

![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)
![DevOps](https://img.shields.io/badge/DevOps-Practice-orange)
![Linux](https://img.shields.io/badge/Linux-Compatible-green?logo=linux)
![NodeJS](https://img.shields.io/badge/Node.js-App-brightgreen?logo=node.js)
![Nginx](https://img.shields.io/badge/Nginx-WebServer-success?logo=nginx)

---

# 📌 Overview

This repository contains:

- Docker basic commands
- Docker container management
- Environment variables
- Docker networking
- Docker volumes
- Real Docker projects
- Nginx deployment
- Node.js containerization
- DevOps hands-on practice

This project is designed for:

- DevOps beginners
- Docker practice
- College practicals
- Internship preparation
- CI/CD learning
- Cloud & deployment basics

---

# 📂 Repository Structure

```bash
docker-projects/
│
├── README.md
│
├── basic-commands/
│   └── docker_commands.md
│
├── nginx-docker-app/
│   ├── index.html
│   ├── default.conf
│   └── Dockerfile
│
├── node-docker-app/
│   ├── app.js
│   ├── package.json
│   └── Dockerfile
│
└── screenshots/
    ├── 1_pull_images.png
    ├── 2_docker_images.png
    ├── 3_run_hello_world.png
    ├── 4_run_ubuntu.png
    ├── 5_run_nginx.png
    └── 6_browser_output.png
```

---

# 🐳 What is Docker?

Docker is a containerization platform used to package applications with all dependencies into lightweight containers.

## Advantages of Docker

- Fast deployment
- Lightweight containers
- Platform independent
- Easy scalability
- Simplifies DevOps workflow
- Better resource utilization

---

# ⚙️ Prerequisites

Before starting install:

- Docker Desktop
- Git
- VS Code

Supported Platforms:

- Windows
- Linux
- macOS

---

# 🔧 Install Docker

## Windows

Download Docker Desktop:

https://www.docker.com/products/docker-desktop/

Verify installation:

```bash
docker --version
```

Example output:

```bash
Docker version 26.0.0
```

---

# 📚 Docker Basic Commands

## 1️⃣ Docker Version

```bash
docker --version
```

---

## 2️⃣ Docker Information

```bash
docker info
```

Displays:

- Docker server info
- Number of containers
- Number of images
- Storage driver
- CPU & memory details

---

## 3️⃣ Pull Docker Images

```bash
docker pull nginx
docker pull ubuntu
docker pull alpine
docker pull node
docker pull mysql
docker pull postgres
docker pull redis
docker pull mongo
```

---

## 4️⃣ List Docker Images

```bash
docker images
```

---

## 5️⃣ Remove Docker Images

```bash
docker rmi nginx
```

Force remove:

```bash
docker rmi -f nginx
```

---

# 🧱 Docker Containers

## Run Container

```bash
docker run nginx
```

Detached mode:

```bash
docker run -d nginx
```

Interactive mode:

```bash
docker run -it ubuntu bash
```

Container with custom name:

```bash
docker run --name my-nginx nginx
```

---

# 📌 Docker Run Options

| Option | Description |
|---|---|
| `-d` | Detached mode |
| `-it` | Interactive terminal |
| `--name` | Custom container name |
| `-p` | Port mapping |
| `-e` | Environment variables |
| `-v` | Mount volume |
| `--rm` | Remove container automatically |

---

# 🌐 Port Mapping

Syntax:

```bash
docker run -p HOST_PORT:CONTAINER_PORT IMAGE
```

Example:

```bash
docker run -d -p 8080:80 nginx
```

Open in browser:

```bash
http://localhost:8080
```

---

# 🔐 Environment Variables

Single variable:

```bash
docker run -e APP_ENV=production nginx
```

Multiple variables:

```bash
docker run \
-e APP_ENV=production \
-e APP_VERSION=1.0 \
nginx
```

---

# 📄 Using .env File

Create `.env`

```env
DB_HOST=localhost
DB_USER=root
DB_PASS=secret
```

Run:

```bash
docker run --env-file .env myapp
```

---

# 📦 Docker Volumes

Create volume:

```bash
docker volume create mydata
```

List volumes:

```bash
docker volume ls
```

Inspect volume:

```bash
docker volume inspect mydata
```

Use volume:

```bash
docker run -dit -v mydata:/app/data ubuntu
```

Remove volume:

```bash
docker volume rm mydata
```

---

# 🔄 Container Lifecycle Commands

Start container:

```bash
docker start <container>
```

Stop container:

```bash
docker stop <container>
```

Restart container:

```bash
docker restart <container>
```

Pause container:

```bash
docker pause <container>
```

Unpause:

```bash
docker unpause <container>
```

Kill container:

```bash
docker kill <container>
```

Remove container:

```bash
docker rm <container>
```

---

# 📋 List Containers

Running containers:

```bash
docker ps
```

All containers:

```bash
docker ps -a
```

---

# 🔎 Container Interaction

Execute command:

```bash
docker exec -it <container> bash
```

View logs:

```bash
docker logs <container>
```

Follow logs:

```bash
docker logs -f <container>
```

---

# 📁 Copy Files

Container → Host

```bash
docker cp container:/file.txt /host/path
```

Host → Container

```bash
docker cp /host/file.txt container:/path
```

---

# 🧹 Cleanup Commands

Remove stopped containers:

```bash
docker container prune
```

Remove unused images:

```bash
docker image prune
```

Remove unused volumes:

```bash
docker volume prune
```

Remove everything unused:

```bash
docker system prune -a
```

---

# 🌐 Project 1 — Custom Nginx Docker Application

## 📂 Project Structure

```bash
nginx-docker-app/
│
├── index.html
├── default.conf
└── Dockerfile
```

---

## 📄 index.html

```html
<h1>Welcome to My Docker Nginx App</h1>
<p>Docker Project Running Successfully</p>
```

---

## 📄 Dockerfile

```dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
```

---

## 🔨 Build Docker Image

```bash
docker build -t custom-nginx:v1 .
```

---

## ▶️ Run Container

```bash
docker run -d -p 8080:80 --name nginx-container custom-nginx:v1
```

---

## 🌍 Browser Output

Open:

```bash
http://localhost:8080
```

Expected output:

```text
Welcome to My Docker Nginx App
Docker Project Running Successfully
```

---

# ⚡ Project 2 — Node.js Docker Application

## 📂 Project Structure

```bash
node-docker-app/
│
├── app.js
├── package.json
└── Dockerfile
```

---

## 📄 app.js

```javascript
const express = require("express");

const app = express();

app.get("/", (req, res) => {
  res.send("Docker Node App Running!");
});

app.listen(3000, "0.0.0.0", () => {
  console.log("Server running on port 3000");
});
```

---

## 📄 package.json

```json
{
  "name": "docker-node-app",
  "version": "1.0.0",
  "main": "app.js",
  "dependencies": {
    "express": "^4.18.2"
  }
}
```

---

## 📄 Dockerfile

```dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY app.js .

EXPOSE 3000

CMD ["node", "app.js"]
```

---

## 🔨 Build Image

```bash
docker build -t node-demo:v1 .
```

---

## ▶️ Run Container

```bash
docker run -d -p 3000:3000 --name node-container node-demo:v1
```

---

## 🌍 Browser Output

Open:

```bash
http://localhost:3000
```

Expected output:

```text
Docker Node App Running!
```

---

# 🛠️ Common Docker Errors & Fixes

| Error | Solution |
|---|---|
| Docker daemon not running | Start Docker Desktop |
| Port already allocated | Change host port |
| Permission denied | Run terminal as administrator |
| Image not found | Pull image first |
| Container exited | Check logs |

---

# 📈 Learning Outcomes

After completing this repository, you will learn:

- Docker fundamentals
- Container lifecycle
- Image management
- Docker networking
- Docker volumes
- Container deployment
- Nginx setup
- Node.js containerization
- DevOps basics

---

# 🚀 Future Improvements

- Docker Compose
- Kubernetes integration
- Jenkins CI/CD
- GitHub Actions
- Multi-container apps
- Monitoring with Prometheus & Grafana

---

# 🤝 Contributing

Contributions are welcome.

## Steps

1. Fork repository
2. Create branch
3. Commit changes
4. Push code
5. Create pull request

---


# 👨‍💻 Author

## Himanshu Singh

DevOps | Docker | Cloud | Full Stack Learning
