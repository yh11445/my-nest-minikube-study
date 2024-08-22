# My NestJS Minikube Study

This repository provides an example of deploying a NestJS application in a Kubernetes environment using Minikube.

## Features

- **Kubernetes Deployment**: Example deployment configuration for a NestJS application.
- **Minikube**: Local Kubernetes setup for testing and development.
- **Docker Integration**: Dockerfile included for building the NestJS application image.

## Getting Started

### Prerequisites

- **Minikube**
- **kubectl**
- **Docker**

### Deployment

1. Build Docker image:
   ```bash
   docker build -t my-nestjs-image:latest .
   ```

2. Setting Environment
   ```bash
   eval $(minikube -p minikube docker-env)
   ```

3. Start Minikube:
   ```bash
   minikube start
   ```

4. Deploy
   ```bash
   kubectl apply -f app-env-configmap.yaml
   kubectl apply -f mariadb-secret.yaml
   kubectl apply -f mariadb-pvc.yaml
   kubectl apply -f mariadb-deployment.yaml
   kubectl apply -f mariadb-service.yaml
   kubectl apply -f app-service.yaml
   kubectl apply -f app-deployment.yaml
   ```
5. Application status check
   ```bash
   kubectl get pods
   kubectl get services
   ```

6. Minikube tunneling
   ```bash
   minikube tunnel
   ```

7. Access to service
   ```bash
   curl http://127.0.0.1:80
   ```
