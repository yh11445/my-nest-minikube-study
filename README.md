# NestJS Mariadb Minikube Example

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
   docker build -t nestjs-mariadb-minikube-example:latest .
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
   kubectl apply -f k8s/
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
