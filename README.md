# 🐳 Docker Projects & Commands


---


# 📥 Basic Docker Commands

## Pull Docker Images

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

## List Local Images

```bash
docker images
```

---

## Run Containers

### Run Hello World

```bash
docker run hello-world
```

### Run Ubuntu Interactive Container

```bash
docker run -it ubuntu
```

### Run Nginx Web Server

```bash
docker run -d -p 8080:80 nginx
```

Open browser

```
http://localhost:8080
```

---

## Remove Unused Images

```bash
docker image prune
```

---

# 🌐 Project 1 — Custom Nginx Docker Application

This project creates a **custom Nginx container serving a static HTML page**.

---

## Step 1: Create Project Folder

```bash
mkdir nginx-app
cd nginx-app
```

---

## Step 2: Create HTML Page

Create **index.html**

```html
<!DOCTYPE html>
<html>
<head>
<title>Medium Level Docker App</title>
</head>
<body>

<h1>Welcome to My Custom Docker Nginx App</h1>
<p>This is a medium-level Docker project.</p>

</body>
</html>
```

---

## Step 3: Create Nginx Configuration

Create **default.conf**

```nginx
server {
    listen 80;
    server_name localhost;

    location / {
        root /usr/share/nginx/html;
        index index.html;
    }
}
```

---

## Step 4: Create Dockerfile

```dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
```

---

## Step 5: Build Docker Image

```bash
docker build -t custom-nginx:v1 .
```

---

## Step 6: Run Container

```bash
docker run -d -p 8080:80 --name nginx-container custom-nginx:v1
```

---

## Step 7: Open Browser

```
http://localhost:8080
```

You should see the **custom Nginx page**.

---

# ⚡ Project 2 — Node.js Docker Application

This project runs a **simple Node.js Express server inside Docker**.

---

## Step 1: Create Project Folder

```bash
mkdir node-app
cd node-app
```

---

## Step 2: Create app.js

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

## Step 3: Create package.json

```json
{
  "name": "node-docker-app",
  "version": "1.0.0",
  "main": "app.js",
  "dependencies": {
    "express": "^4.18.2"
  }
}
```

---

## Step 4: Create Dockerfile

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

## Step 5: Build Image

```bash
docker build -t node-demo:v1 .
```

---

## Step 6: Run Container

```bash
docker run -d -p 3000:3000 --name node-container node-demo:v1
```

---

## Step 7: Verify Running Containers

```bash
docker ps
```

---

## Step 8: Open Browser

```
http://localhost:3000
```

Output:

```
Docker Node App Running!
```

---


