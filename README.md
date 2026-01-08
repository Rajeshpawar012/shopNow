# ShopNow – Full DevOps GitOps Project

This project demonstrates a complete DevOps workflow using Docker, Kubernetes, Helm, ArgoCD, Jenkins, and Nginx Ingress.

---

## 1. Project Architecture

- Frontend: React + Nginx
- Backend: Node.js + Express
- Database: MongoDB
- Containerization: Docker
- Orchestration: Kubernetes
- Deployment: Helm Charts
- GitOps: ArgoCD
- CI/CD: Jenkins
- Ingress Controller: Nginx Ingress

---

## 2. Dockerization

### Backend
```bash
cd backend
docker build -t shopnow-backend .
docker run -d -p 5000:5000 shopnow-backend

### Frontend
```bash 
cd frontend
docker build -t shopnow-frontend .
docker run -d -p 80:80 shopnow-frontend

3. Kubernetes Deployment (Helm)
```bash
kubectl create namespace shopnow
helm install shopnow kubernetes/helm/charts/shopnow -n shopnow

Resources deployed:

Frontend Deployment & Service

Backend Deployment & Service

MongoDB

Ingress

4. MongoDB on Kubernetes

MongoDB is deployed using Kubernetes Deployment and Service inside the shopnow namespace.

5. Nginx Ingress
Ingress resource
```bash
kubectl apply -f kubernetes/helm/charts/shopnow/templates/ingress.yaml

Application accessible via:
http://shopnow.local

6. ArgoCD GitOps Deployment
Access ArgoCD
```bash
kubectl port-forward svc/argocd-server -n argocd 8082:443

Open:
https://localhost:8082

Create Application

Repo: https://github.com/Rajeshpawar012/shopNow.git

Path: kubernetes/helm/charts/shopnow

Sync Policy: Auto-sync enabled

Any Git commit automatically deploys to Kubernetes.

7. Jenkins CI/CD Pipeline

Pipeline stages:

Git Checkout

Docker Build

Docker Push

Helm Update

ArgoCD Sync

Jenkinsfile is available under jenkins/.

8. Git Workflow
```bash
git status
git add .
git commit -m "Update deployment configuration"
git push origin main

9. Conclusion

This project demonstrates a real-world DevOps implementation using modern CI/CD and GitOps practices.

Author: Rajesh Pawar
