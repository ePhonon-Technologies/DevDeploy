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

```bash
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
