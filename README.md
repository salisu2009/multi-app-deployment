# 🚀 Multi-Application Deployment Portfolio

A hands-on DevOps project where I forked, cloned, tested locally, and deployed **4 different applications** to an AWS EC2 server. The applications span across **4 different programming languages/frameworks**.

---

## 📋 Project Overview

| App | Language/Framework | Local Port | AWS Port |
|-----|--------------------|------------|----------|
| JavaScript Todo App | Node.js + Express | 3000 | 3000 |
| Python Soccer App | Python + Flask | 5000 | 5000 |
| Java Spring Boot App | Java + Spring Boot | 8080 | 8080 |
| Golang Movie App | Go + Gin | 5050 | 8080 |

---

## 🛠️ Tools & Technologies

- **Git & GitHub** — Version control and forking repos
- **AWS EC2** — Cloud server (Ubuntu 24.04)
- **SSH** — Remote server access via `.pem` key
- **Node.js & npm** — JavaScript runtime and package manager
- **Python 3 & pip** — Python runtime and package manager
- **Flask** — Python web framework
- **Java 17 (Temurin)** — Java runtime
- **Maven** — Java build and dependency tool
- **Spring Boot** — Java web framework
- **Go (Golang)** — Go runtime
- **Gin** — Go web framework

---

## 📁 Repositories

1. [javascript-application](https://github.com/salisu2009/javascript-application) — Todo List App
2. [python-web-app](https://github.com/salisu2009/python-web-app) — Soccer Player Comparison App
3. [java-application](https://github.com/salisu2009/java-application) — Spring Boot REST App
4. [golang-application](https://github.com/salisu2009/golang-application) — Random Movie App

---

## 🖥️ Local Deployment Steps

### 1️⃣ JavaScript Application (Node.js + Express)

```bash
# Navigate into the project
cd javascript-application

# Install dependencies
npm install

# Run the app
npm start
```
✅ App runs on: `http://localhost:3000`

---

### 2️⃣ Python Web Application (Flask)

```bash
# Navigate into the project
cd python-web-app

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```
✅ App runs on: `http://localhost:5000`

---

### 3️⃣ Java Application (Spring Boot)

```bash
# Navigate into the project
cd java-application

# Build the project
mvn clean install

# Run the app
mvn spring-boot:run
```
✅ App runs on: `http://localhost:8080`

> ⚠️ Requires Java 17 or higher and Maven installed.

---

### 4️⃣ Golang Application (Gin Framework)

```bash
# Navigate into the project
cd golang-application

# Install dependencies
go mod tidy

# Run the app
go run main.go
```
✅ App runs on: `http://localhost:5050`

---

## ☁️ AWS EC2 Deployment Steps

### Server Setup

```bash
# Connect to EC2 instance
ssh -i "your-key.pem" ubuntu@your-ec2-public-ip

# Update the server
sudo apt update
```

---

### 1️⃣ JavaScript Application

```bash
# Install Node.js and npm
sudo apt install nodejs npm -y

# Clone the repo
git clone https://github.com/salisu2009/javascript-application.git
cd javascript-application

# Install dependencies and run
npm install
npm start
```
✅ Live at: `http://your-ec2-ip:3000`

---

### 2️⃣ Python Web Application

```bash
# Install Python and pip
sudo apt install python3 python3-pip -y

# Clone the repo
git clone https://github.com/salisu2009/python-web-app.git
cd python-web-app

# Install dependencies
pip3 install -r requirements.txt --break-system-packages

# Update app.py to allow external access
sed -i "s/app.run(debug=True)/app.run(debug=True, host='0.0.0.0')/" app.py

# Run in background
nohup python3 app.py &
```
✅ Live at: `http://your-ec2-ip:5000`

---

### 3️⃣ Java Application

```bash
# Install Java 17 and Maven
sudo apt install -y openjdk-17-jdk maven

# Clone the repo
git clone https://github.com/salisu2009/java-application.git
cd java-application

# Build and run
mvn clean install
mvn spring-boot:run
```
✅ Live at: `http://your-ec2-ip:8080`

---

### 4️⃣ Golang Application

```bash
# Install Go
sudo apt install -y golang

# Clone the repo
git clone https://github.com/salisu2009/golang-application.git
cd golang-application

# Install dependencies and run
go mod tidy
go run main.go
```
✅ Live at: `http://your-ec2-ip:8080`

---

## 🔐 AWS Security Group — Inbound Rules

| Port | Protocol | Source | Purpose |
|------|----------|--------|---------|
| 22 | TCP | 0.0.0.0/0 | SSH Access |
| 80 | TCP | 0.0.0.0/0 | HTTP |
| 443 | TCP | 0.0.0.0/0 | HTTPS |
| 3000 | TCP | 0.0.0.0/0 | JavaScript App |
| 5000 | TCP | 0.0.0.0/0 | Python App |
| 8080 | TCP | 0.0.0.0/0 | Java & Go App |

---

## 💡 Key Lessons Learned

- Always test locally before deploying to a server
- Different languages require different runtimes and build tools
- Flask apps need `host='0.0.0.0'` to be accessible externally
- AWS Security Groups act as a firewall — always open the right ports
- Use `nohup` to keep apps running after closing the terminal
- AWS EC2 public IPs can change when an instance restarts

---

## 👤 Author

**Salisu** — DevOps Enthusiast  
GitHub: [@salisu2009](https://github.com/salisu2009)
