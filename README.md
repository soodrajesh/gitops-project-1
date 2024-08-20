# GitOps with AWS EKS, ECR, Docker, Kubernetes, Helm, Terraform, and ArgoCD

This project demonstrates a complete GitOps setup using AWS EKS, ECR, Docker, Kubernetes, Helm, Terraform, and ArgoCD. The deployment pipeline automatically handles the build, push, and deployment of containerized applications to Kubernetes.

## Project Structure

```bash
.
├── .github/
│   └── workflows/
│       └── ci-cd.yml            # GitHub Actions workflow for CI/CD pipeline
├── argocd/
│   └── app.yaml                  # ArgoCD Application manifest
├── deploy/
│   ├── ingress.yaml              # Ingress configuration for exposing the application
│   ├── deployment.yaml           # Kubernetes deployment manifest
│   ├── service.yaml              # Kubernetes service manifest
│   └── values.yaml               # Helm values for customization
├── terraform/
│   ├── eks-cluster.tf            # Terraform configuration for EKS cluster setup
│   ├── ecr-repository.tf         # Terraform configuration for ECR repository
│   └── vpc-network.tf            # Terraform configuration for VPC and networking
├── docker/
│   └── Dockerfile                # Dockerfile for building the application image
├── scripts/
│   └── deploy.sh                 # Script for deploying application using Helm
└── README.md                     # Project documentation

Docker

    Build and push the Docker image:

    bash

    docker build -t <your-ecr-repository>:latest .

Helm

    Deploy the application using Helm:

    bash

    ./scripts/deploy.sh

ArgoCD

    Apply the ArgoCD application manifest:

    bash

    kubectl apply -f argocd/app.yaml

Accessing the Application

    Ingress URL: The application is exposed through an Ingress resource. Access it using the hostname defined in deploy/ingress.yaml.

CI/CD Pipeline

    The pipeline is configured in .github/workflows/ci-cd.yml to automatically build, push Docker images, and deploy the application on code changes.