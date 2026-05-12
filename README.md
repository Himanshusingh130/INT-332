🚀 Docker Commands & DevOps Projects Repository










📌 Overview

This repository contains:

Docker basic commands
Docker container management
Environment variables
Docker networking
Docker volumes
Real Docker projects
Nginx deployment
Node.js containerization
DevOps hands-on practice

This project is designed for:

DevOps beginners
Docker practice
College practicals
Internship preparation
CI/CD learning
Cloud & deployment basics
📂 Repository Structure
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
🐳 What is Docker?

Docker is a containerization platform used to package applications with all dependencies into lightweight containers.

Advantages of Docker:

Fast deployment
Lightweight containers
Platform independent
Easy scalability
Simplifies DevOps workflow
Better resource utilization
⚙️ Prerequisites

Before starting:

Install:

Docker Desktop
Git
VS Code

Supported Platforms:

Windows
Linux
macOS
🔧 Install Docker
Windows

Download Docker Desktop:

👉 https://www.docker.com/products/docker-desktop/

Verify installation:

docker --version

Example output:

Docker version 26.0.0
📚 Docker Basic Commands
1️⃣ Docker Version
docker --version
2️⃣ Docker Information
docker info

Displays:

Docker server info
Number of containers
Number of images
Storage driver
CPU & memory details
3️⃣ Pull Docker Images
docker pull nginx
docker pull ubuntu
docker pull alpine
docker pull node
docker pull mysql
docker pull postgres
docker pull redis
docker pull mongo
4️⃣ List Docker Images
docker images
5️⃣ Remove Docker Images
docker rmi nginx

Force remove:

docker rmi -f nginx
🧱 Docker Containers
Run Container
docker run nginx

Detached mode:

docker run -d nginx

Interactive mode:

docker run -it ubuntu bash

Container with custom name:

docker run --name my-nginx nginx
📌 Docker Run Options
Option	Description
-d	Detached mode
-it	Interactive terminal
--name	Custom container name
-p	Port mapping
-e	Environment variables
-v	Mount volume
--rm	Remove container automatically
🌐 Port Mapping

Syntax:

docker run -p HOST_PORT:CONTAINER_PORT IMAGE

Example:

docker run -d -p 8080:80 nginx

Open in browser:

http://localhost:8080
🔐 Environment Variables

Single variable:

docker run -e APP_ENV=production nginx

Multiple variables:

docker run \
-e APP_ENV=production \
-e APP_VERSION=1.0 \
nginx
📄 Using .env File

Create .env

DB_HOST=localhost
DB_USER=root
DB_PASS=secret

Run:

docker run --env-file .env myapp
📦 Docker Volumes

Create volume:

docker volume create mydata

List volumes:

docker volume ls

Inspect volume:

docker volume inspect mydata

Use volume:

docker run -dit -v mydata:/app/data ubuntu

Remove volume:

docker volume rm mydata
🔄 Container Lifecycle Commands

Start container:

docker start <container>

Stop container:

docker stop <container>

Restart container:

docker restart <container>

Pause container:

docker pause <container>

Unpause:

docker unpause <container>

Kill container:

docker kill <container>

Remove container:

docker rm <container>
📋 List Containers

Running containers:

docker ps

All containers:

docker ps -a
🔎 Container Interaction

Execute command:

docker exec -it <container> bash

View logs:

docker logs <container>

Follow logs:

docker logs -f <container>
📁 Copy Files

Container → Host

docker cp container:/file.txt /host/path

Host → Container

docker cp /host/file.txt container:/path
🧹 Cleanup Commands

Remove stopped containers:

docker container prune

Remove unused images:

docker image prune

Remove unused volumes:

docker volume prune

Remove everything unused:

docker system prune -a
🌐 Project 1 — Custom Nginx Docker Application
📂 Project Structure
nginx-docker-app/
│
├── index.html
├── default.conf
└── Dockerfile
📄 index.html
<h1>Welcome to My Docker Nginx App</h1>
<p>Docker Project Running Successfully</p>
📄 Dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
🔨 Build Docker Image
docker build -t custom-nginx:v1 .
▶️ Run Container
docker run -d -p 8080:80 --name nginx-container custom-nginx:v1
🌍 Browser Output

Open:

http://localhost:8080

Expected output:

Welcome to My Docker Nginx App
Docker Project Running Successfully
⚡ Project 2 — Node.js Docker Application
📂 Project Structure
node-docker-app/
│
├── app.js
├── package.json
└── Dockerfile
📄 app.js
const express = require("express");

const app = express();

app.get("/", (req, res) => {
  res.send("Docker Node App Running!");
});

app.listen(3000, "0.0.0.0", () => {
  console.log("Server running on port 3000");
});
📄 package.json
{
  "name": "docker-node-app",
  "version": "1.0.0",
  "main": "app.js",
  "dependencies": {
    "express": "^4.18.2"
  }
}
📄 Dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY app.js .

EXPOSE 3000

CMD ["node", "app.js"]
🔨 Build Image
docker build -t node-demo:v1 .
▶️ Run Container
docker run -d -p 3000:3000 --name node-container node-demo:v1
🌍 Browser Output

Open:

http://localhost:3000

Expected output:

Docker Node App Running!
🛠️ Common Docker Errors & Fixes
Error	Solution
Docker daemon not running	Start Docker Desktop
Port already allocated	Change host port
Permission denied	Run terminal as administrator
Image not found	Pull image first
Container exited	Check logs
📈 Learning Outcomes

After completing this repository, you will learn:

Docker fundamentals
Container lifecycle
Image management
Docker networking
Docker volumes
Container deployment
Nginx setup
Node.js containerization
DevOps basics
🚀 Future Improvements
Docker Compose
Kubernetes integration
Jenkins CI/CD
GitHub Actions
Multi-container apps
Monitoring with Prometheus & Grafana
🤝 Contributing

Contributions are welcome.

Steps:

Fork repository
Create branch
Commit changes
Push code
Create pull request
📜 License

This project is licensed under the MIT License.

👨‍💻 Author
Himanshu Singh

DevOps | Docker | Cloud | Full Stack Learning
