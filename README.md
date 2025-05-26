# Crewmeister Challenge

## DevOps Coding Challenge – Spring Boot + MySQL Deployment

This project is a completed solution for the Crewmeister DevOps Coding Challenge. It includes a Spring Boot REST API that calculates workdays for a given month and is deployed locally using Docker Compose and Kubernetes.

---

## 📦 Technologies Used

- **Java 17** + **Spring Boot**
- **MySQL 8**
- **Flyway** for database migrations
- **Docker** and **Docker Compose**
- **Kubernetes (Kind)** for container orchestration
- **kubectl** for local cluster management

---

## 🚀 Features Implemented

✅ **Exposed REST API**:


✅ Connected Spring Boot to MySQL with full persistence  
✅ Flyway integration to handle schema migration  
✅ Multi-stage Docker build for Java application  
✅ Docker Compose file to bring up app + MySQL in a single command  
✅ Kubernetes deployment and service manifests (`k8s/`) for local cluster deployment using Kind  
✅ Configured Spring Boot to run on port 8081 to avoid port conflict with Jenkins  
✅ Successful port-forwarding to test Kubernetes deployment locally  

---

```bash
docker-compose up --build
curl http://localhost:9090/api/work-days?month=1

kind create cluster --name kind-kind
2. Build and Load Image

docker build -t devops-coding-challenge-app:latest .
kind load docker-image devops-coding-challenge-app:latest --name kind-kind
3. Deploy to Kubernetes

kubectl apply -f k8s/
4. Access the App

kubectl port-forward service/devops-app-service 8081:8081
Then visit:

http://localhost:8081/api/work-days?month=1
📁 Folder Structure
.
├── Dockerfile
├── docker-compose.yml
├── k8s/
│   ├── app-deployment.yaml
│   ├── app-service.yaml
│   ├── mysql-deployment.yaml
│   ├── mysql-service.yaml
│   └── config-map.yaml
└── src/
    └── main/
        └── ...
