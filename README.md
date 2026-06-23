# Kubernetes CI/CD Application

This project demonstrates a complete CI/CD pipeline using Jenkins, Docker, and Kubernetes.

## 📂 Project Structure


.
├── deployment.yml      # Kubernetes Deployment configuration
├── service.yml         # Kubernetes Service configuration
├── hpa.yml             # Horizontal Pod Autoscaler configuration
├── Dockerfile          # Docker image build instructions
├── Jenkinsfile         # Jenkins CI/CD pipeline
└── README.md

## 🚀 Technologies Used
- Docker
- Jenkins
- Kubernetes
- Horizontal Pod Autoscaler (HPA)

## 🐳 Docker Build

Build the Docker image:

```bash
docker build -t your-image-name .
```

Run the container:

```bash
docker run -p 8080:8080 your-image-name
```

## ☸️ Kubernetes Deployment

Deploy the application:

```bash
kubectl apply -f deployment.yml
kubectl apply -f service.yml
kubectl apply -f hpa.yml
```

Verify resources:

```bash
kubectl get deployments
kubectl get services
kubectl get pods
kubectl get hpa
```

## 🔄 Jenkins CI/CD Pipeline

The Jenkins pipeline performs the following tasks:

1. Pull source code from GitHub.
2. Build the application.
3. Create Docker image.
4. Push Docker image to Docker Registry.
5. Deploy application to Kubernetes cluster.
6. Verify deployment status.

Run the pipeline through Jenkins using the provided `Jenkinsfile`.

## 📈 Auto Scaling

The project includes a Horizontal Pod Autoscaler (HPA) that automatically scales application pods based on resource utilization.

Check HPA status:

```bash
kubectl get hpa
```

## 🛠 Prerequisites

- Docker installed
- Kubernetes cluster (Minikube, EKS, AKS, GKE, etc.)
- kubectl configured
- Jenkins server
- Docker Hub account (or another container registry)

## 📋 Useful Commands

Check pods:

```bash
kubectl get pods
```

Check services:

```bash
kubectl get svc
```

Describe deployment:

```bash
kubectl describe deployment <deployment-name>
```

View logs:

```bash
kubectl logs <pod-name>
```

## 👨‍💻 Author

**Bigyan KC**

GitHub: Bigyan1021
