# 📚 INTT 332 — DevOps, Virtualization & Configuration Management

![DevOps](https://img.shields.io/badge/DevOps-Automation-orange)
![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)
![Jenkins](https://img.shields.io/badge/Jenkins-CI/CD-red?logo=jenkins)
![Linux](https://img.shields.io/badge/Linux-Administration-green?logo=linux)
![Cloud](https://img.shields.io/badge/Cloud-Computing-blue)

---

# 📌 Course Overview

INTT 332 focuses on modern DevOps practices, virtualization technologies, cloud computing, containerization, automation, and deployment pipelines.

The course helps students understand:

- Software Development Life Cycle
- DevOps Methodology
- Linux Administration
- Docker Containerization
- Jenkins CI/CD
- Cloud Deployment
- Configuration Management
- Monitoring & Automation

This repository contains:

- Detailed Unit Notes
- Linux Commands
- Docker Commands
- Jenkins Pipelines
- Practical Labs
- Mini Projects
- Real-Time DevOps Projects
- Deployment Examples

---

# 🎯 Course Learning Outcomes

After completing this course students will be able to:

✅ Understand DevOps lifecycle  
✅ Work with Linux operating systems  
✅ Create Docker containers  
✅ Build CI/CD pipelines  
✅ Configure Jenkins automation  
✅ Deploy applications on cloud  
✅ Automate infrastructure  
✅ Monitor applications and services  
✅ Build real-world DevOps projects  

---

# 📂 Repository Structure

```bash
INTT-332/
│
├── README.md
│
├── UNIT-1-DevOps-Virtualization/
│
├── UNIT-2-Linux-Configuration-Management/
│
├── UNIT-3-Docker-Containerization/
│
├── UNIT-4-Jenkins-CI-CD/
│
├── UNIT-5-Cloud-Monitoring-Deployment/
│
├── Practical-Labs/
│
├── Projects/
│
├── Notes/
│
└── Screenshots/
```

---

# 📖 UNIT 1 — Introduction to DevOps & Virtualization

---

# 🔹 Introduction to DevOps

DevOps is a combination of:

```text
Development + Operations
```

It is used to automate software development, testing, deployment, and monitoring.

---

# 🔹 Goals of DevOps

- Faster software delivery
- Automation
- Continuous deployment
- Better collaboration
- Reduced errors
- Faster recovery

---

# 🔹 DevOps Lifecycle

```text
Plan → Develop → Build → Test → Release → Deploy → Operate → Monitor
```

---

# 🔹 Software Development Life Cycle (SDLC)

SDLC defines the process of software development.

## SDLC Phases

1. Requirement Gathering
2. System Design
3. Development
4. Testing
5. Deployment
6. Maintenance

---

# 🔹 Agile Methodology

Agile is an iterative software development methodology.

## Features of Agile

- Continuous improvement
- Faster delivery
- Sprint-based development
- Team collaboration

---

# 🔹 Continuous Integration (CI)

CI automatically integrates code changes into a shared repository.

### Advantages

- Detects bugs early
- Improves software quality
- Reduces integration problems

---

# 🔹 Continuous Deployment (CD)

CD automatically deploys tested applications to production.

---

# 🔹 Virtualization

Virtualization allows multiple operating systems to run on a single physical machine.

---

# 🔹 Types of Virtualization

| Type | Description |
|---|---|
| Hardware Virtualization | Creates virtual machines |
| Server Virtualization | Divides physical servers |
| Storage Virtualization | Combines storage devices |
| Network Virtualization | Creates virtual networks |

---

# 🔹 Hypervisors

A hypervisor manages virtual machines.

## Types

| Type | Description |
|---|---|
| Type 1 | Runs directly on hardware |
| Type 2 | Runs on host OS |

Examples:

- VMware
- VirtualBox
- Hyper-V

---

# 🧪 Practicals — UNIT 1

## Practical 1 — Install VirtualBox

### Steps

1. Download VirtualBox
2. Install software
3. Create virtual machine
4. Install Ubuntu Linux

---

## Practical 2 — Create Ubuntu Virtual Machine

### Requirements

- Ubuntu ISO
- 4GB RAM
- 20GB Storage

---

# 🚀 Mini Project — UNIT 1

## Project: Create Linux Virtual Machine

### Objective

Create and configure Ubuntu VM using VirtualBox.

### Features

- Linux installation
- User creation
- Network configuration
- Shared folders

---

# 📖 UNIT 2 — Linux & Configuration Management

---

# 🔹 Introduction to Linux

Linux is an open-source operating system widely used in DevOps and cloud computing.

---

# 🔹 Linux File System

```text
/
├── home
├── etc
├── var
├── bin
├── usr
└── tmp
```

---

# 🔹 Basic Linux Commands

## Check Current Directory

```bash
pwd
```

---

## List Files

```bash
ls
```

---

## Change Directory

```bash
cd folder_name
```

---

## Create File

```bash
touch file.txt
```

---

## Remove File

```bash
rm file.txt
```

---

# 🔹 User Management

## Create User

```bash
sudo adduser username
```

---

## Change Password

```bash
passwd username
```

---

# 🔹 Permission Management

## Change Permissions

```bash
chmod 777 file.txt
```

---

# 🔹 Process Management

## Display Processes

```bash
ps aux
```

---

## Kill Process

```bash
kill PID
```

---

# 🔹 Shell Scripting

Shell scripting automates Linux tasks.

---

# 🔹 Sample Shell Script

```bash
#!/bin/bash

echo "Welcome to DevOps"
date
```

Run:

```bash
chmod +x script.sh
./script.sh
```

---

# 🔹 Configuration Management

Configuration management automates server setup and maintenance.

---

# 🔹 Infrastructure as Code (IaC)

Infrastructure is managed using code.

Examples:

- Ansible
- Terraform
- Puppet
- Chef

---

# 🔹 Ansible Basics

## Install Ansible

```bash
sudo apt install ansible
```

---

## Check Version

```bash
ansible --version
```

---

# 🧪 Practicals — UNIT 2

## Practical 1 — Linux Commands Practice

Commands:

```bash
ls
pwd
mkdir
touch
cp
mv
rm
```

---

## Practical 2 — Shell Scripting

Create automation script.

---

## Practical 3 — User Management

Create multiple users and groups.

---

# 🚀 Mini Project — UNIT 2

## Project: Linux Server Administration

### Tasks

- User management
- File permissions
- Shell scripts
- Process monitoring

---

# 📖 UNIT 3 — Docker & Containerization

---

# 🔹 Introduction to Docker

Docker is a containerization platform.

Containers package:

- Application
- Libraries
- Dependencies

---

# 🔹 Docker Architecture

```text
Docker Client → Docker Daemon → Docker Images → Containers
```

---

# 🔹 Docker Images

Docker images are templates used to create containers.

---

# 🔹 Docker Containers

Containers are running instances of Docker images.

---

# 🔹 Docker Installation

## Windows

Install Docker Desktop.

Verify:

```bash
docker --version
```

---

# 🔹 Docker Commands

## Pull Image

```bash
docker pull nginx
```

---

## Run Container

```bash
docker run -d -p 8080:80 nginx
```

---

## List Containers

```bash
docker ps
```

---

## Stop Container

```bash
docker stop container_id
```

---

## Remove Container

```bash
docker rm container_id
```

---

# 🔹 Dockerfile

Dockerfile automates image creation.

---

# 🔹 Dockerfile Example

```dockerfile
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80
```

---

# 🔹 Docker Volumes

Volumes store persistent data.

---

# 🔹 Docker Networking

Allows communication between containers.

---

# 🔹 Docker Compose

Manages multi-container applications.

---

# 🧪 Practicals — UNIT 3

## Practical 1 — Install Docker

---

## Practical 2 — Run Nginx Container

```bash
docker run -d -p 8080:80 nginx
```

---

## Practical 3 — Create Dockerfile

---

## Practical 4 — Build Docker Image

```bash
docker build -t myapp .
```

---

# 🚀 Mini Projects — UNIT 3

---

# 🔹 Project 1 — Docker Nginx Website

### Features

- Static website deployment
- Nginx container
- Port mapping

---

# 🔹 Project 2 — Node.js Docker App

### Features

- Node.js application
- Dockerized backend
- Container deployment

---

# 📖 UNIT 4 — Jenkins & CI/CD Pipeline

---

# 🔹 Introduction to Jenkins

Jenkins is an automation server used for CI/CD.

---

# 🔹 Jenkins Features

- Automated builds
- Automated testing
- Deployment automation
- Plugin support

---

# 🔹 Jenkins Architecture

```text
Developer → GitHub → Jenkins → Build → Test → Deploy
```

---

# 🔹 Jenkins Installation

## Windows

Download Jenkins WAR file or installer.

---

# 🔹 Jenkins Pipeline

Pipelines automate build and deployment processes.

---

# 🔹 Jenkinsfile Example

```groovy
pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Application'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Application'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application'
            }
        }
    }
}
```

---

# 🔹 GitHub Integration

Jenkins integrates with GitHub repositories.

---

# 🔹 Jenkins + Docker Integration

Jenkins can automatically build Docker images.

---

# 🧪 Practicals — UNIT 4

## Practical 1 — Install Jenkins

---

## Practical 2 — Create Jenkins Job

---

## Practical 3 — Connect GitHub Repository

---

## Practical 4 — Create CI/CD Pipeline

---

# 🚀 Mini Projects — UNIT 4

## Project: CI/CD Pipeline using Jenkins & Docker

### Features

- GitHub integration
- Automatic builds
- Docker image creation
- Deployment automation

---

# 📖 UNIT 5 — Cloud, Monitoring & Deployment

---

# 🔹 Cloud Computing

Cloud computing provides services over the internet.

---

# 🔹 Cloud Models

| Model | Description |
|---|---|
| IaaS | Infrastructure as a Service |
| PaaS | Platform as a Service |
| SaaS | Software as a Service |

---

# 🔹 AWS Basics

Amazon Web Services provides cloud services like:

- EC2
- S3
- IAM
- RDS

---

# 🔹 Monitoring Tools

## Prometheus

Used for monitoring systems.

---

## Grafana

Used for data visualization.

---

## Splunk

Used for log monitoring.

---

# 🔹 Deployment Strategies

- Blue-Green Deployment
- Rolling Deployment
- Canary Deployment

---

# 🔹 DevOps Security

Security practices in DevOps.

Examples:

- Secure credentials
- Access control
- Vulnerability scanning

---

# 🧪 Practicals — UNIT 5

## Practical 1 — AWS EC2 Setup

---

## Practical 2 — Install Prometheus

---

## Practical 3 — Install Grafana

---

## Practical 4 — Monitor Docker Containers

---

# 🚀 Final Projects

---

# 🔹 Project 1 — Complete DevOps CI/CD Pipeline

## Technologies

- GitHub
- Jenkins
- Docker
- Nginx

## Workflow

```text
Developer → GitHub → Jenkins → Docker Build → Deployment
```

---

# 🔹 Project 2 — Dockerized Node.js Application

## Features

- Node.js backend
- Docker container
- Port mapping
- Nginx reverse proxy

---

# 🔹 Project 3 — Linux Server Monitoring System

## Features

- CPU monitoring
- Memory monitoring
- Process tracking
- Log analysis

---

# 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Docker | Containerization |
| Jenkins | CI/CD |
| GitHub | Version Control |
| Linux | Server Administration |
| AWS | Cloud Deployment |
| Prometheus | Monitoring |
| Grafana | Visualization |
| Ansible | Automation |

---

# 📈 Practical Skills Gained

- Linux Administration
- Shell Scripting
- Docker Management
- Jenkins Automation
- CI/CD Pipeline Creation
- Cloud Deployment
- Infrastructure Automation
- Monitoring & Logging

---

# 📜 License

This repository is for educational purposes only.

---

# 👨‍💻 Author

## Himanshu Singh

DevOps | Docker | Cloud | CI/CD

---

# ⭐ Support

If this repository helped you:

- Star the repository
- Fork the project
- Share with friends

---

# 📬 Contact

GitHub: Your GitHub Username  
LinkedIn: Your LinkedIn Profile  
Email: your-email@example.com
