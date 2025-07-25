# 🚀 End-to-End CI/CD Pipeline for Node.js on Amazon EKS | GitHub Actions

![AWS EKS](https://img.shields.io/badge/AWS_EKS-FF9900?style=for-the-badge&logo=amazonecs&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)

**Automated CI/CD pipeline** for deploying Node.js applications to **Amazon EKS** using GitHub Actions, Terraform, and Kustomize. Features multi-environment support, GitOps practices, and security scanning.

---

## 📌 Table of Contents
- [🏗️ Repository Structure](#-repository-structure)
- [🔧 Prerequisites](#-prerequisites)
- [⚡ CI/CD Workflow](#-cicd-workflow)
- [🌐 Infrastructure](#-infrastructure)
- [🛡️ Security](#%EF%B8%8F-security)
- [📊 Monitoring](#-monitoring)
- [🤝 Contributing](#-contributing)

---

## 🏗️ Repository Structure

``bash
.
├── app/                  # Node.js application
│   ├── src/              # Source code
│   ├── tests/            # Unit/integration tests
│   ├── Dockerfile        # Container definition
│   └── package.json
│
├── kustomize/            # Kubernetes manifests
│   ├── base/             # Common configurations
│   └── overlays/         # Env-specific (dev/staging/prod)
│
├── terraform/            # Infrastructure as Code
│   ├── modules/          # Reusable components
│   ├── main.tf           # EKS cluster definition
│   └── variables.tf
│
└── .github/workflows/    # GitHub Actions pipelines
    ├── ci.yml            # CI workflow
    └── cd.yml            # CD workflow

🔧 Prerequisites
Tool	Purpose
Node.js v16+	Application runtime
Docker	Containerization
Terraform	Infrastructure provisioning
kubectl	Kubernetes cluster interaction
AWS CLI v2	AWS resource management
GitHub Secrets	Secure credential storage
💡 Ensure AWS IAM permissions include EKS, ECR, and VPC management.

⚡ CI/CD Workflow
🔄 Pipeline Stages
Continuous Integration (CI)

Code linting (ESLint)

Unit tests (npm test)

Docker image build & push to ECR

Trivy vulnerability scanning

Continuous Deployment (CD)

Terraform plan/apply (infrastructure)

Kustomize environment-specific deployments

Smoke tests post-deployment

🎯 Deployment Strategies
Environment	Strategy	Rollback Mechanism
Dev	Rolling Updates	Manual (kubectl rollout undo)
Production	Blue-Green	Traffic switching (ALB)
🌐 Infrastructure
🏗️ EKS Cluster Architecture
graph TD
    A[GitHub Actions] --> B[Terraform]
    B --> C[EKS Cluster]
    C --> D[Node Groups]
    D --> E[ECR + ALB]





📦 Resource Allocation
Component	Dev	Production
Node Type	t3.small	t3.large
Replicas	1	3
Scaling	Manual	HPA (CPU 70%)
🛡️ Security
Secrets Management: AWS Secrets Manager + GitHub Encrypted Secrets

Container Security:

Trivy scans in CI pipeline

Non-root user in Dockerfiles

Network Policies:

Calico for pod-to-pod communication limits

Ingress restricted to Cloudflare IPs

📊 Monitoring
Layer	Tools
Infrastructure	Amazon CloudWatch
Kubernetes	Prometheus + Grafana
Application	OpenTelemetry + AWS X-Ray
🤝 Contributing
Fork the repository

Create a feature branch (git checkout -b feat/awesome-feature)

Commit changes (git commit -m "Add awesome feature")

Push to branch (git push origin feat/awesome-feature)

Open a Pull Request

