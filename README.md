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
- Frontend and backend are containerised using Docker
- MongoDB runs inside the Kubernetes cluster
- Jenkins handles CI pipelines
- ArgoCD manages continuous deployment using GitOps
- NGINX Ingress exposes the application to users
<img width="350" height="308" alt="image" src="https://github.com/user-attachments/assets/3ca50ad8-d1da-4141-a8ce-adc3fc7afd02" />

---

## 4. Dockerization
Both frontend and backend applications are packaged as Docker images.

### Backend
```bash
docker build -t shopnow-backend backend/
docker run -d -p 5000:5000 shopnow-backend
```
### Frontend
```bash
docker build -t shopnow-frontend frontend/
docker run -d -p 80:80 shopnow-frontend
```
Docker images are pushed to Docker Hub and referenced in Kubernetes manifests.

---

## 6. Kubernetes Deployment (Helm)
Helm charts are used to deploy all components into the Kubernetes cluster.

```bash
kubectl create namespace shopnow
helm install shopnow kubernetes/helm/charts/shopnow -n shopnow
```
### Deployed Components

-Frontend Deployment & Service

-Backend Deployment & Service

-MongoDB StatefulSet & Service

-NGINX Ingress Resource

---

## 7. MongoDB on Kubernetes

MongoDB is deployed using Kubernetes StatefulSet to ensure data persistence and stable network identity.

Key features:

-Persistent Volume Claims (PVC)

-Cluster-internal service

-Secure communication with backend

---

## 8. CI/CD Pipeline – Jenkins

### Jenkins automates the CI process:

- Pulls source code from GitHub

- Builds Docker images

- Pushes images to Docker Hub

- Updates Kubernetes manifests / Helm values

- Pipeline execution is triggered automatically on Git commits.

---

## 9. GitOps Deployment – ArgoCD

ArgoCD continuously monitors the Git repository and ensures the Kubernetes cluster state matches the Git configuration.

### Features used:

- Automatic sync

- Declarative deployments

- Rollback via Git history
  
---

## 10. Application Exposure – NGINX Ingress

The application is exposed externally using NGINX Ingress Controller.

### Benefits:

- Centralised traffic management

- Clean URL routing

- Scalable ingress configuration
  
---

## 11. Screenshots
- Jenkins Pipeline

<img width="950" height="455" alt="Screenshot 2026-01-07 181650" src="https://github.com/user-attachments/assets/9c7093d5-649a-4a12-b0d7-20849d3ed666" />


<img width="955" height="465" alt="Screenshot 2026-01-07 181938" src="https://github.com/user-attachments/assets/167a6d54-ba33-469e-8bbf-860510806d76" />


- ArgoCD Dashboard
  
<img width="956" height="518" alt="Screenshot 2026-01-08 174952" src="https://github.com/user-attachments/assets/78d55e58-abd7-4a49-b488-baf48ee660c6" />


<img width="959" height="460" alt="Screenshot 2026-01-08 175328" src="https://github.com/user-attachments/assets/d58e882f-9d18-4720-9888-c4c6456d47a3" />

- Application UI

<img width="827" height="472" alt="Screenshot 2026-01-06 230536" src="https://github.com/user-attachments/assets/86ecd36b-241e-4d92-ba65-13c1224e61ad" />


---

## 12. Conclusion

- This project demonstrates a complete production-grade DevOps workflow using Docker, Kubernetes, Helm, Jenkins, ArgoCD, and NGINX Ingress.
It follows industry best practices for automation, scalability, and maintainability.

---

### Author
```
Rajesh Pawar
DevOps Engineer
```



