# ShopNow – DevOps Assignment

## 1. Introduction
ShopNow is a full-stack e-commerce application developed to demonstrate an end-to-end DevOps workflow.  
This assignment focuses on containerization, Kubernetes deployment, CI/CD automation, and GitOps practices.

---

## 2. Technology Stack
- Frontend: React with Nginx
- Backend: Node.js (Express)
- Database: MongoDB
- Containerization: Docker
- Orchestration: Kubernetes
- Package Management: Helm
- CI/CD: Jenkins
- GitOps Deployment: ArgoCD
- Traffic Management: NGINX Ingress Controller

---

## 3. Application Architecture
The application follows a microservice-based architecture:
- Frontend and backend are containerized using Docker
- MongoDB runs inside the Kubernetes cluster
- Jenkins handles CI pipelines
- ArgoCD manages continuous deployment using GitOps
- NGINX Ingress exposes the application to users

---

## 4. Dockerization
Both frontend and backend applications are packaged as Docker images.

### Backend
```bash
docker build -t shopnow-backend backend/

### Frontend
```bash
docker build -t shopnow-frontend frontend/

Docker images are pushed to Docker Hub and referenced in Kubernetes deployments.
---
## 5. Kubernetes Deployment (Helm)
Helm charts are used to deploy all components into the Kubernetes cluster.

```bash
kubectl create namespace shopnow
helm install shopnow kubernetes/helm/charts/shopnow -n shopnow

### Deployed resources:

- Frontend Deployment and Service

- Backend Deployment and Service

- MongoDB Deployment and Service

- Ingress Resource
---
## 6. MongoDB in Kubernetes
MongoDB is deployed as a Kubernetes Deployment with an internal ClusterIP Service.
The backend connects to MongoDB using Kubernetes service discovery.
---
## 7. CI/CD using Jenkins
### Jenkins automates the CI process:

- Source code checkout from GitHub

- Docker image build

- Docker image push to Docker Hub

- Deployment configuration update
---
## 8. GitOps Deployment using ArgoCD
- ArgoCD continuously monitors the GitHub repository and synchronizes Kubernetes manifests automatically.
- Any change pushed to GitHub is deployed to the cluster without manual intervention.
- Manual deployment steps are eliminated
---
## 9. Application Access using Ingress
The application is exposed to users using the NGINX Ingress Controller.


http://shopnow.local
---
## 10. Screenshots
- Architecture Diagram
- Jenkins Pipeline
- Screenshot showing Jenkins CI/CD stages.
---
### ArgoCD Application
Screenshot showing application synced and healthy.
---
### Application UI
Screenshot of ShopNow application accessed via browser.
---
## 11. Conclusion
This assignment demonstrates a real-world DevOps implementation using Docker, Kubernetes, Jenkins, Helm, and ArgoCD following GitOps principles.

### Author: Rajesh Pawar
