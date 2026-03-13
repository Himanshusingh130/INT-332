# 🐳 Docker Commands & Projects Repository

![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)
![DevOps](https://img.shields.io/badge/DevOps-Practice-orange)
![Linux](https://img.shields.io/badge/Linux-Compatible-green?logo=linux)
![NodeJS](https://img.shields.io/badge/Node.js-App-brightgreen?logo=node.js)
![Nginx](https://img.shields.io/badge/Nginx-WebServer-success?logo=nginx)

This repository contains **Docker basic commands, container management commands, environment variables, volumes, and real Docker projects**.

It is designed for **DevOps learning, Docker labs, and hands-on practice**.

---

# 📂 Repository Structure

```
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

# 📚 Table of Contents

1. Check Docker Installation
2. Basic Docker Commands
3. Docker Run Options
4. Environment Variables
5. Port Mapping
6. Container Lifecycle Commands
7. Container Interaction Commands
8. Docker Volumes
9. Docker Practice Tasks
10. Project 1 – Custom Nginx Docker App
11. Project 2 – Node.js Docker App

---

# 1️⃣ Check Docker Installation

```bash
docker --version
```

Example output

```
Docker version 18.09.6
```

---

# 2️⃣ Docker System Information

```bash
docker info
```

Displays:

* Number of containers
* Number of images
* Storage driver
* Docker server version

---

# 3️⃣ Pull Docker Images

```bash
docker pull hello-world
docker pull ubuntu
docker pull ubuntu:22.04
docker pull alpine
docker pull busybox
docker pull nginx
docker pull nginx:alpine
docker pull httpd
docker pull mysql
docker pull postgres
docker pull mongo
docker pull redis
docker pull python
docker pull python:3.9
docker pull node
docker pull node:18
docker pull openjdk
docker pull tomcat
docker pull php
docker pull golang
```

---

# 4️⃣ List Docker Images

```bash
docker images
```

---

# 5️⃣ Run Docker Containers

Basic syntax

```
docker run [OPTIONS] IMAGE [COMMAND] [ARG]
```

Example

```bash
docker run httpd echo "Hello World"
```

---

# Docker Run Options

| Option   | Description                    |
| -------- | ------------------------------ |
| `-it`    | Interactive mode               |
| `-d`     | Detached (background) mode     |
| `--name` | Container name                 |
| `--rm`   | Remove container automatically |
| `-p`     | Port mapping                   |
| `-e`     | Environment variable           |
| `-v`     | Mount volume                   |

Example

```bash
docker run --name my-container httpd echo "Hello World"
```

---

# 6️⃣ Environment Variables in Docker

Example:

```bash
docker run -e MY_VAR=value httpd env
```

Interactive example

```bash
docker run -it -e MY_NAME=Harpreet ubuntu bash
```

Check variable

```bash
echo $MY_NAME
```

---

# Multiple Environment Variables

```bash
docker run -e APP_ENV=production -e APP_VERSION=1.0 nginx
```

---

# MySQL Container with Environment Variables

```bash
docker run -d \
-e MYSQL_ROOT_PASSWORD=root123 \
-e MYSQL_DATABASE=college \
-e MYSQL_USER=admin \
-e MYSQL_PASSWORD=admin123 \
mysql:8
```

---

# Using `.env` File

Create `.env`

```
DB_HOST=localhost
DB_USER=root
DB_PASS=secret
```

Run container

```bash
docker run --env-file .env myapp
```

---

# 7️⃣ Port Mapping

Syntax

```
docker run -p HOST_PORT:CONTAINER_PORT IMAGE
```

Example

```bash
docker run -p 8080:80 nginx
```

Open browser

```
http://localhost:8080
```

---

# 8️⃣ Container Lifecycle Commands

Run container

```bash
docker run -d -p 80:80 --name my_container nginx
```

Start container

```bash
docker start <container>
```

Stop container

```bash
docker stop <container>
```

Restart container

```bash
docker restart <container>
```

Pause container

```bash
docker pause <container>
```

Unpause container

```bash
docker unpause <container>
```

Kill container

```bash
docker kill <container>
```

Remove container

```bash
docker rm <container>
```

Remove stopped containers

```bash
docker container prune
```

---

# 9️⃣ Listing Containers

Running containers

```bash
docker ps
```

All containers

```bash
docker ps -a
```

---

# 🔎 Container Interaction

Execute command inside container

```bash
docker exec -it <container_id> bash
```

View logs

```bash
docker logs <container>
```

Follow logs

```bash
docker logs -f <container>
```

Copy files

Container → Host

```bash
docker cp container:/file.txt /host
```

Host → Container

```bash
docker cp /host/file.txt container:/path
```

---

# 📦 Docker Volumes

Create volume

```bash
docker volume create mydata
```

List volumes

```bash
docker volume ls
```

Inspect volume

```bash
docker volume inspect mydata
```

Run container with volume

```bash
docker run -dit --name mycontainer -v mydata:/app/data ubuntu
```

Remove volume

```bash
docker volume rm mydata
```

---

# 🌐 Project 1 — Custom Nginx Docker Application

Create project

```bash
mkdir nginx-app
cd nginx-app
```

Create HTML

```html
<h1>Welcome to My Custom Docker Nginx App</h1>
<p>This is a medium-level Docker project.</p>
```

Create Dockerfile

```dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
```

Build image

```bash
docker build -t custom-nginx:v1 .
```

Run container

```bash
docker run -d -p 8080:80 --name nginx-container custom-nginx:v1
```

Open browser

```
http://localhost:8080
```

---

# ⚡ Project 2 — Node.js Docker Application

Create project

```bash
mkdir node-app
cd node-app
```

app.js

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

Dockerfile

```dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package.json .
RUN npm install

COPY app.js .

EXPOSE 3000

CMD ["node", "app.js"]
```

Build image

```bash
docker build -t node-demo:v1 .
```

Run container

```bash
docker run -d -p 3000:3000 --name node-container node-demo:v1
```

Open browser

```
http://localhost:3000
```

Output

```
Docker Node App Running!
```

---

# 👨‍💻 Author

Himanshu Singh

---

