# 🚀 Kubernetes CI/CD & Deployment Workflow Project

<div align="center">

### 📦 End-to-End Kubernetes Deployment & CI/CD Learning Project

</div>

---

## 📌 Overview

This project demonstrates a complete Kubernetes deployment workflow integrated with Docker, GitHub Actions, AWS services, and Minikube.

The goal of this repository is to provide a practical understanding of:

* Kubernetes Fundamentals
* Docker Containerization
* CI/CD Pipelines with GitHub Actions
* AWS ECR Integration
* Minikube Local Kubernetes Cluster
* Kubernetes Deployments & Services
* Managed Kubernetes Services (EKS / AKS / GKE)
* Scaling & Fault Tolerance Concepts

---

# ⚠️ Disclaimer

> This project is developed solely for learning and educational purposes.
> It is intended to explore Kubernetes concepts, CI/CD workflows, Docker containerization, and cloud-native deployment practices.
> This project is **not intended for production use**.

---

# 🏗️ Project Architecture

```text
Developer Pushes Code
          │
          ▼
   GitHub Repository
          │
          ▼
    GitHub Actions
          │
          ▼
   Build Docker Image
          │
          ▼
 Push Image to AWS ECR
          │
          ▼
 Kubernetes Deployment
          │
          ▼
  Minikube / AWS EKS
          │
          ▼
   Running Application
```

---

# ✨ Features

✅ Dockerized Application

✅ Kubernetes Deployment & Services

✅ GitHub Actions CI/CD Workflow

✅ AWS ECR Integration

✅ Minikube Local Cluster Setup

✅ Pod Monitoring & Debugging

✅ Load Testing with Postman

✅ Multi-Node Kubernetes Cluster

✅ Kubernetes Scaling Concepts

✅ Managed Kubernetes Service Comparison

---

# 🛠️ Tech Stack

| Technology     | Purpose                   |
| -------------- | ------------------------- |
| Kubernetes     | Container Orchestration   |
| Docker         | Containerization          |
| GitHub Actions | CI/CD Automation          |
| AWS ECR        | Docker Image Registry     |
| Minikube       | Local Kubernetes Cluster  |
| kubectl        | Kubernetes CLI            |
| YAML           | Kubernetes Configurations |
| Postman        | API & Load Testing        |

---

# 📂 Project Structure

```bash
Kubernetes_Project/
│
├── deployment.yaml
├── service.yaml
├── Dockerfile
├── .github/
│   └── workflows/
│       └── ci-cd.yaml
├── app/
├── README.md
└── LICENSE
```

---

# ⚙️ Prerequisites

Before starting, ensure the following tools are installed:

* Docker Desktop
* Git
* kubectl
* Minikube
* VS Code
* AWS CLI

---

# 🚀 Getting Started

## 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd Kubernetes_Project
```

---

## 2️⃣ Build Docker Image

```bash
docker build -t kubernetes-test-app:latest .
```

Verify Docker images:

```bash
docker images
```

---

## 3️⃣ Run Application Locally

```bash
docker run -p 5000:5000 kubernetes-test-app:latest
```

---

# ☸️ Kubernetes Setup

## Start Minikube

```bash
minikube start
```

Or:

```bash
minikube start --embed-certs
```

---

## Verify Cluster Status

```bash
minikube status
```

Check resources:

```bash
kubectl get all -A
kubectl get pods -A
kubectl get nodes -A
```

---

# 📦 Load Docker Image into Minikube

```bash
minikube image load kubernetes-test-app:latest
```

---

# 🚀 Deploy Application to Kubernetes

## Apply Deployment

```bash
kubectl apply -f deployment.yaml
```

## Apply Service

```bash
kubectl apply -f service.yaml
```

---

# 🔍 Monitoring & Debugging

## View Pods

```bash
kubectl get pods
```

## View Logs

```bash
kubectl logs -f <pod-name>
```

## View Services

```bash
kubectl get service
```

## Open Dashboard

```bash
minikube dashboard
```

---

# 🌐 Access Application

```bash
minikube service kubernetes-test-app
```

---

# 🔄 Scaling Kubernetes Cluster

## Add More Nodes

```bash
minikube start --nodes=2
```

---

# 🔥 CI/CD Workflow with GitHub Actions

This project integrates GitHub Actions for automated deployment workflows.

## Workflow Steps

1. Push code to GitHub
2. GitHub Actions triggers pipeline
3. Build Docker image
4. Push image to AWS ECR
5. Deploy latest image to Kubernetes

---

# 📄 Example GitHub Actions Workflow

```yaml
name: CI/CD Pipeline with Kubernetes

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Build Docker Image
        run: docker build -t app:latest .

      - name: Deploy to Kubernetes
        run: kubectl apply -f deployment.yaml
```

---

# ☁️ Managed Kubernetes Services

## AWS EKS

* Tight AWS ecosystem integration
* IAM support
* CloudWatch monitoring
* High scalability

## Azure AKS

* Beginner-friendly
* Azure AD integration
* Simplified upgrades

## Google GKE

* Best for AI/ML workloads
* GPU/TPU support
* Advanced autoscaling

---

# 📊 EKS vs AKS vs GKE

| Feature     | AWS EKS         | Azure AKS         | Google GKE        |
| ----------- | --------------- | ----------------- | ----------------- |
| Ease of Use | Medium          | Beginner Friendly | Beginner Friendly |
| Best For    | Enterprise Apps | Azure Ecosystem   | AI/ML Workloads   |
| Autoscaling | Good            | Good              | Advanced          |
| Networking  | Flexible        | Simple            | Seamless          |
| Monitoring  | CloudWatch      | Azure Monitor     | Cloud Monitoring  |

---

# 🧪 Load Testing

Use Postman Performance Testing:

```text
Collection → Runs → Performance → Run Performance Test
```

Example:

* 10 Users
* Duration: 1 Minute

---

# ❗ Common Errors & Fixes

## ImagePullBackOff

### Fix:

Push Docker image to Docker Hub:

```bash
docker tag kubernetes-test-app:latest <dockerhub-username>/kubernetes-test-app:latest

docker push <dockerhub-username>/kubernetes-test-app:latest
```

---

## Minikube Registry Error

### Fix:

```bash
unset HTTP_PROXY
unset HTTPS_PROXY
unset NO_PROXY
```

Then restart:

```bash
minikube stop
minikube delete --all
minikube start
```

---

# 📚 Learning Outcomes

By completing this project, you will learn:

* Kubernetes Fundamentals
* Container Orchestration
* CI/CD Automation
* Docker Image Management
* Kubernetes Scaling
* Cloud-Native Deployments
* Kubernetes Debugging & Monitoring
* Managed Kubernetes Services

---

# 🤝 Contributing

Contributions are welcome.

If you'd like to improve this project:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to your branch
5. Open a Pull Request

---

# 📜 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

### Suraj Kumar

Passionate about:

* DevOps
* Kubernetes
* Cloud Computing
* AI & MLOps
* Generative AI

---

<div align="center">

### ⭐ If you found this project useful, consider giving it a star ⭐

</div>
