# DevOps CI/CD Pipeline using GitHub Actions, Docker, and Kubernetes

## Project Overview

This project demonstrates a complete CI/CD pipeline for a Spring Boot application using:

- GitHub Actions
- Docker
- Kubernetes (Minikube)
- Maven
- Docker Hub

The pipeline automatically:
1. Builds the application
2. Creates Docker image
3. Pushes image to Docker Hub
4. Deploys application to Kubernetes

---

## Architecture

```text
Developer Pushes Code
        ↓
GitHub Actions Triggered
        ↓
Maven Build + Test
        ↓
Docker Image Build
        ↓
Push to Docker Hub
        ↓
Deploy to Kubernetes
```

---

## Tech Stack

| Tool | Purpose |
|------|----------|
| Java 17 | Application Development |
| Spring Boot | Backend Framework |
| Maven | Build Tool |
| Docker | Containerization |
| GitHub Actions | CI/CD Pipeline |
| Docker Hub | Container Registry |
| Kubernetes | Container Orchestration |
| Minikube | Local Kubernetes Cluster |

---

## Project Structure

```text
DEVOPS-GITHUB-ACTIONS/
│
├── .github/
│   └── workflows/
│       └── main.yaml
│
├── .mvn/
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/demo/
│   │   │       ├── DemoApplication.java
│   │   │       └── HelloController.java
│   │   │
│   │   └── resources/
│   │
│   └── test/
│
├── target/
│
├── Dockerfile
├── pom.xml
├── mvnw
├── mvnw.cmd
├── .gitignore
├── .gitattributes
├── HELP.md
└── README.md
```

---

## CI/CD Pipeline Workflow

### 1. Developer Pushes Code
Code is pushed to GitHub repository.

### 2. GitHub Actions Triggered
GitHub Actions automatically starts the CI/CD pipeline.

### 3. Maven Build
The application is compiled and packaged using Maven.

```bash
mvn clean package
```

### 4. Docker Image Build

```bash
docker build -t sndeep310/devops-github-actions:v2 .
```

### 5. Docker Image Push

```bash
docker push sndeep310/devops-github-actions:v2
```

### 6. Kubernetes Deployment

```bash
kubectl apply -f k8s/
```

---

## GitHub Actions Workflow

Workflow file location:

```text
.github/workflows/main.yaml
```

Pipeline stages:
- Checkout Code
- Setup Java
- Maven Build
- Docker Login
- Docker Build
- Docker Push

---

## Docker Commands

### Build Docker Image

```bash
docker build -t sndeep310/devops-github-actions:v3 .
```

### Run Docker Container

```bash
docker run -p 8080:8080 sndeep310/devops-github-actions:v3
```

---

## Kubernetes Deployment

### Deploy Application

```bash
kubectl apply -f k8s/
```

### Check Pods

```bash
kubectl get pods
```

### Check Services

```bash
kubectl get svc
```

### Access Application

```bash
minikube service github-actions-service
```

---

## Screenshots

### GitHub Actions Pipeline


### Docker Image in Docker Hub
<img width="1915" height="1079" alt="image" src="https://github.com/user-attachments/assets/4e235329-6401-4e5c-ad7f-b727bc868f26" />


### Kubernetes Pods Running
<img width="1916" height="1078" alt="image" src="https://github.com/user-attachments/assets/5637f89c-ca19-4df9-8b67-938bcf1da178" />


### Application Running in Browser
<img width="1814" height="1079" alt="image" src="https://github.com/user-attachments/assets/2b58ebc3-e13f-4001-839f-814c37ad3b95" />


---

## Challenges Faced

- Fixed Kubernetes YAML formatting issues
- Resolved Docker image caching problem
- Debugged Spring Boot controller mapping issue
- Implemented CI/CD automation using GitHub Actions
- Learned Kubernetes deployment troubleshooting

---

## Future Improvements

- Add Helm Charts
- Implement Prometheus Monitoring
- Add Grafana Dashboards
- Integrate SonarQube
- Add Trivy Security Scanning
- Deploy on AWS EKS
- Implement ArgoCD GitOps

---

## Author

Sandeep  
Aspiring DevOps Engineer
