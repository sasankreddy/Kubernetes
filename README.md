# Kubernetes
Demonstration of my Kubernetes expertise through deploying my MERN application Wandora. This repository showcases configuration files, manifests, and deployment strategies for containerizing and orchestrating a full-stack MERN application using Kubernetes.

# Overview
This deployment consists of the following microservices:
- **User Service:**
- Manages user-related operations such as authentication and profile handling.
- Deployed using the sasankreddy18/wandora:user_service_V1.0 Docker image.
- **Trip Service:**
- Handles trip-related functionalities like scheduling and management.
- Deployed using the sasankreddy18/wandora:trip_service_V1.0 Docker image.
- **Registration Service:**
- Manages user registrations and onboarding.
- Deployed using the sasankreddy18/wandora:registration_service_V1.0 Docker image.

Each service is deployed as a Kubernetes Deployment with **two replicas** to ensure high availability.

# Features
- Scalability: Configured with replicas for high availability.
- Environment Management: Secrets are used to securely store sensitive data like JWT_SECRET and MONGO_URI.
- Containerized Microservices: Each microservice is deployed as a Docker container from Docker Hub.

# Prerequisites
- Kubernetes cluster setup (e.g., Minikube, AWS EKS, GKE, etc.)
- kubectl installed and configured.
- Docker images for the services are pushed to Docker Hub (sasankreddy18/wandora)

# Steps to Deploy
- **Clone the repository:**
- git clone https://github.com/sasankreddy18/wandora-k8s-deployment.git
- cd wandora-k8s-deployment
- **Apply the secret files for all services:**
kubectl apply -f secrets/
- **Deploy the services:**
- kubectl apply -f deployments/
- kubectl apply -f services/
- **Verify the deployments:**
- kubectl get deployments
- kubectl get pods

# Future Enhancements
- Add horizontal pod autoscaling (HPA) for dynamic scaling based on traffic.
- Use Helm charts for easier deployment and management.
- Configure Ingress for better routing and load balancing.
- Add CI/CD pipelines to automate deployment.
