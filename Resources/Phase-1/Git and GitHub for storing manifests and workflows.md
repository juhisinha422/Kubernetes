# Git and GitHub for Storing Manifests and Workflows in Kubernetes (K8s)

In Kubernetes (K8s), Git and GitHub are commonly used for versioning and storing Kubernetes manifests and workflows. Git provides a mechanism to track changes over time, collaborate with teams, and ensure that the infrastructure-as-code (IaC) philosophy is adhered to. GitHub adds more functionality with features such as collaboration, code review, and CI/CD integrations.

## Table of Contents

1. [Introduction to Git & GitHub for Kubernetes](#introduction-to-git--github-for-kubernetes)
2. [Kubernetes Manifests](#kubernetes-manifests)
3. [Storing Manifests in GitHub](#storing-manifests-in-github)
4. [GitOps and GitHub Workflow](#gitops-and-github-workflow)
5. [GitHub Actions for CI/CD](#github-actions-for-cicd)
6. [Kubernetes Workflow Automation](#kubernetes-workflow-automation)
7. [Best Practices for Storing Manifests in Git](#best-practices-for-storing-manifests-in-git)
8. [GitHub and Kubernetes Cluster Integration](#github-and-kubernetes-cluster-integration)
9. [CI/CD Pipeline Example with Kubernetes](#cicd-pipeline-example-with-kubernetes)
10. [Scaling and Rollbacks](#scaling-and-rollbacks)
11. [Monitoring and Observability](#monitoring-and-observability)
12. [Conclusion](#conclusion)
13. [Additional Resources](#additional-resources)

## 1. Introduction to Git & GitHub for Kubernetes

- **Git** is a version control system that tracks changes in source code during software development. It is essential for tracking changes to Kubernetes manifests, which define the desired state of Kubernetes resources like Pods, Deployments, Services, and ConfigMaps.
- **GitHub** is a cloud-based platform that hosts Git repositories. It provides additional collaboration features, such as pull requests, issues, discussions, and integration with continuous integration/continuous delivery (CI/CD) pipelines.

## 2. Kubernetes Manifests

Kubernetes manifests are YAML files that describe the desired state of a Kubernetes cluster. They include definitions of resources like Pods, Services, ConfigMaps, Secrets, Deployments, and Persistent Volumes.

Example of a simple **Deployment** manifest:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```
## 3. Storing Manifests in GitHub

Version Control: Storing Kubernetes manifests in Git enables version control. This ensures that any changes to the infrastructure can be tracked, and any modifications can be rolled back if needed.

Repository Structure: Organize manifests in a logical directory structure. Example structure:

k8s-manifests/
├── deployments/
│   └── nginx-deployment.yaml
├── services/
│   └── nginx-service.yaml
├── configmaps/
│   └── nginx-config.yaml
└── secrets/
    └── nginx-secret.yaml


## 4. GitOps and GitHub Workflow

GitOps is an operational framework for Kubernetes that uses Git repositories as the source of truth for the desired state of applications and infrastructure. In a GitOps workflow, changes made to Git repositories automatically trigger the update of resources in the Kubernetes cluster.

GitOps tools such as Argo CD and Flux can be used to sync the Git repository with the Kubernetes cluster. These tools continuously monitor the Git repository for changes and apply them to the cluster.

Example of GitOps Flow:

Commit changes (such as updates to Kubernetes manifests) to GitHub.

CI/CD pipelines (using GitHub Actions or other CI tools) trigger the changes to a Kubernetes cluster.

Argo CD/Flux automatically detects and applies the new state from the GitHub repository to the cluster.

## 5. GitHub Actions for CI/CD

GitHub Actions can automate workflows, such as testing, building, and deploying Kubernetes applications.

Example of a simple GitHub Actions workflow for Kubernetes deployment:

name: Deploy to Kubernetes

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Set up kubectl
      uses: azure/setup-kubectl@v1
      with:
        kubectl-version: 'v1.21.2'

    - name: Deploy to Kubernetes
      run: |
        kubectl apply -f k8s-manifests/deployments/nginx-deployment.yaml
        kubectl apply -f k8s-manifests/services/nginx-service.yaml

## 6. Kubernetes Workflow Automation

K8s Workflows refer to the automation of tasks and the deployment of services in a Kubernetes environment. This is often managed using GitOps, CI/CD pipelines, and tools like Helm.

Helm is a Kubernetes package manager that simplifies the deployment and management of Kubernetes applications. You can store Helm charts in GitHub repositories and use GitHub Actions or Argo CD to deploy them automatically.

## 7. Best Practices for Storing Manifests in Git

Immutable Infrastructure: Treat Kubernetes manifests as immutable. Any change to the infrastructure should be made via a new commit in Git, not manually applied to the cluster.

Branching Strategy: Use feature branches, release branches, or environment-specific branches (e.g., dev, staging, prod) to manage different versions of Kubernetes manifests.

Use Helm Charts: For reusable applications and configurations, use Helm charts to package Kubernetes manifests. This allows you to version control entire applications and configurations.

Sensitive Data Management: Be cautious with sensitive data like passwords and secrets in GitHub repositories. Use tools like Kubernetes Secrets or a secret management tool (e.g., HashiCorp Vault, AWS Secrets Manager) and store sensitive data securely.

Automate Validation: Use tools like kubeval, kubetest, or kube-score to validate your YAML files before applying them to Kubernetes. You can automate this validation in GitHub Actions.

## 8. GitHub and Kubernetes Cluster Integration

GitHub Secrets: Store sensitive information (like Kubernetes cluster credentials) securely in GitHub Secrets, which are encrypted and used in GitHub Actions workflows.

Service Accounts: Set up Kubernetes Service Accounts with the necessary permissions to allow CI/CD tools (like GitHub Actions) to deploy to Kubernetes clusters securely.

## 9. CI/CD Pipeline Example with Kubernetes

A full GitHub Actions-based CI/CD pipeline typically involves:

Source Code: Developers push changes to a GitHub repository.

CI/CD Build: The pipeline automatically runs tests, builds containers, and pushes images to a container registry.

Deployment: The pipeline applies Kubernetes manifests to the cluster.

Monitoring: The CI/CD pipeline includes steps for monitoring and rolling back in case of failures.

Example workflow steps for deployment:

Build Docker images.

Push images to Docker Hub or a container registry.

Deploy the new image using kubectl or Helm to the Kubernetes cluster.

## 10. Scaling and Rollbacks

Scaling: GitHub Actions or other CI/CD tools can handle scaling operations by modifying the Kubernetes manifest or Helm chart values (e.g., changing the replica count of a Deployment).

Rollbacks: Use the Git repository to version control Kubernetes manifests. If there’s a failure after a deployment, you can roll back to a previous version of the manifest using Git, e.g., by reverting to a prior commit and applying it to the cluster.

## 11. Monitoring and Observability

After deploying Kubernetes manifests via GitHub workflows, ensure your Kubernetes cluster is properly monitored. Tools like Prometheus, Grafana, and ELK Stack can help monitor logs and metrics.

You can integrate observability tools into your GitHub workflows by adding deployment steps that monitor the success or failure of the deployment.

## 12. Conclusion

Storing Kubernetes manifests and workflows in Git and GitHub enhances collaboration, version control, and automation. GitOps practices, CI/CD pipelines, and integrations with tools like GitHub Actions, Argo CD, and Helm help streamline the process of deploying and managing applications in Kubernetes.

By following best practices and integrating proper tooling, you can ensure smooth, scalable, and reliable Kubernetes deployments.


## 13. Additional Resources

- [Kubernetes Official Docs](https://kubernetes.io/docs/)
- [What is GitOps?](https://www.weave.works/technologies/gitops/)
- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [Helm Docs](https://helm.sh/docs/)

