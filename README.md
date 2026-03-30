# DevSecOps Pytho Microservices Platform

This project demonstrates a complete DevSecOps pipeline for deploying a microservices-based application on Kubernetes.

The platform integrates containerization, CI/CD automation, security scanning, and monitoring to simulate a real-world DevOps production environment.

The application is built using Python and deployed using a modern cloud-native architecture.

# Project Architecture

Developer pushes code to GitHub → CI/CD pipeline triggers → Docker image is built → Security scan is performed → Image is pushed to DockerHub → Application is deployed to Kubernetes → Monitoring stack collects metrics.

Pipeline Flow:

GitHub → Jenkins → Docker Build → Trivy Scan → DockerHub → Kubernetes → Prometheus → Grafana

# Technologies Used
Docker – containerization platform
Kubernetes – container orchestration
Jenkins – CI/CD automation
Trivy – container vulnerability scanning
Prometheus – monitoring and metrics
Grafana – visualization dashboards
NGINX Ingress – traffic routing
Python Flask – web application

# Project Features

• Containerized microservices application
• Automated CI/CD pipeline using Jenkins
• security scanning with Trivy
• Kubernetes deployment with best practices
• Horizontal Pod Autoscaling (HPA)
• NGINX Ingress controller for external access
• Monitoring using Prometheus and Grafana

# CI/CD Pipeline

The CI/CD pipeline is implemented using Jenkins.

Pipeline stages:

Clone source code from GitHub
Build Docker image
Perform security scan using Trivy
Push Docker image to DockerHub
Deploy the application to Kubernetes cluster

# Monitoring Stack

Monitoring is implemented using:

Prometheus for Metrics Collection
Grafana for visualization Dashboards
Alertmanager for Alerts & Notifications

The monitoring stack observes:

• CPU and Memory usage
• Pod health and availability
• Kubernetes cluster metrics

# How to Run the Project

Build Docker image:

docker build -t python-devsecops .

Run locally:

docker-compose up -d

Deploy to Kubernetes:

kubectl apply -f k8s/

Access the application through Ingress

# DevOps Concepts Demonstrated

• Containerization
• Infrastructure as Code (IaC)
• CI/CD automation
• Security scanning
• Kubernetes orchestration
• Observability and monitoring

# Future Improvements

• Add Helm charts
• Implement GitOps using ArgoCD
• Add automated security policies
• Integrate Kubernetes secrets management
