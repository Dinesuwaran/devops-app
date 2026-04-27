# DevOps Class Project — Spring Boot CI/CD Pipeline

**Course:** CSEB5143 DevOps: Tools and Technologies  
**Semester:** 2 2025/2026

## Overview

A simple Spring Boot REST API deployed through a full DevOps pipeline:

**Git → Jenkins → Maven → Docker → Kubernetes**

## Application Endpoints

| Endpoint  | Description              |
|-----------|--------------------------|
| `/`       | Returns "Hello DevOps"   |
| `/health` | Service health check     |
| `/info`   | App and pipeline info    |

## Tech Stack

| Tool        | Purpose                    |
|-------------|----------------------------|
| Git/GitHub  | Version control            |
| Maven       | Build automation           |
| Jenkins     | CI/CD pipeline             |
| Docker      | Containerization           |
| Kubernetes  | Deployment & orchestration |

## Running Locally

### Prerequisites
- Java 17+
- Maven 3.8+
- Docker
- kubectl + Minikube (for Kubernetes)

### 1. Build and Run with Maven
```bash
mvn clean package
java -jar target/devops-app-1.0.0.jar
```
Visit: http://localhost:8080

### 2. Build and Run with Docker
```bash
docker build -t devops-app:1.0.0 .
docker run -d -p 8080:8080 devops-app:1.0.0
```

### 3. Deploy to Kubernetes
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl get pods
kubectl get services
```

## Project Structure

```
devops-app/
├── src/
│   └── main/
│       ├── java/com/devops/app/
│       │   ├── DevOpsApplication.java
│       │   └── controller/
│       │       └── AppController.java
│       └── resources/
│           └── application.properties
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── Dockerfile
├── Jenkinsfile
├── pom.xml
└── README.md
```
