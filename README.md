# 🚀 End-to-End CI/CD Pipeline for Node.js App Deployment on EKS using GitHub Actions

![EKS Banner](https://imgur.com/h87KAuY.png)

---

![CI/CD Pipeline](https://imgur.com/Ctznv2m.png)

---

## 📌 Table of Contents

- [📂 Repository Structure](#-repository-structure)
- [🔧 Prerequisites](#-prerequisites)
- [⚙️ CI/CD Workflow](#️-cicd-workflow)
  - [🔨 Build Job](#-build-job)
  - [🚀 Deployment Job](#-deployment-job)
- [🏗️ Infrastructure Details](#️-infrastructure-details)
- [📦 Application Deployment Strategy](#-application-deployment-strategy)
- [🔄 GitOps Principles](#-gitops-principles)
- [🔒 Security Best Practices](#-security-best-practices)
- [📢 Notifications & Alerts](#-notifications--alerts)
- [📊 Monitoring & Logging](#-monitoring--logging)
- [📜 Contributing](#-contributing)
- [⭐ Support & Author](#-support--author)
- [📧 Let's Connect!](#-lets-connect)
- [📢 Stay Updated!](#-stay-updated)

---

## 📂 Repository Structure

```bash
📦 root
├── 📁 app
│   ├── app.py
│   ├── calculator.js
│   ├── calculator.test.js
│   ├── Dockerfile
│   ├── Dockerfile-python
│   ├── index.js
│   └── package.json
│
├── 📁 kustomize
│   ├── 📁 base
│   │   ├── deploy.yaml
│   │   ├── ingress.yaml
│   │   ├── kustomization.yaml
│   │   └── svc.yaml
│   │
│   └── 📁 overlays
│       ├── 📁 dev
│       ├── 📁 staging
│       └── 📁 prod
│
├── 📁 terraform
│   ├── ingress-nginx.tf
│   ├── main.tf
│   ├── outputs.tf
│   ├── terraform.tf
│   └── variables.tf
│
├── README.md
└── VERSION
