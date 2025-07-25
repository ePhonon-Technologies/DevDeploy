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

``bash
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




🔧 Prerequisites
Ensure the following are installed and configured:

✅ Node.js (v14+)

✅ Docker (latest)

✅ Terraform (v1.0+)

✅ kubectl

✅ Kustomize

✅ AWS CLI & eksctl

✅ GitHub Actions enabled

✅ AWS IAM permissions for EKS

⚙️ CI/CD Workflow
🔨 Build Job
Environment Setup

Install Node.js dependencies via npm install

Lint the codebase

Run Tests

Run unit tests via npm test

Generate coverage reports

Versioning

Follows Semantic Versioning

Auto-increments via commit messages

Build & Push Docker Image

Build Docker image

Push to Amazon ECR

🚀 Deployment Job
Terraform Setup

terraform init, plan, and apply

Infrastructure state management

Provision EKS Cluster

VPC, subnets, nodes

Configure Kubernetes

Set kubectl context

Apply Kustomize overlays

Install Ingress Controller

Deploy NGINX via Helm

Deploy Application

Use the latest Docker image

Expose via LoadBalancer & Ingress

🏗️ Infrastructure Details
Environment	Instance Type	Replicas
Dev	t3.small	1
Staging	t3.medium	3
Prod	t3.large	3

DNS with Cloudflare

dev.example.com

staging.example.com

prod.example.com

📦 Application Deployment Strategy
Supports multiple rollout strategies:

🔄 Rolling Updates (default)

🟢 Blue-Green Deployments (prod)

🟡 Canary Deployments (safe rollout)

🔄 GitOps Principles
📝 Git = Single Source of Truth

📄 Declarative Infrastructure (Terraform + K8s)

🤖 Automated Deployments via GitHub Actions

🔒 Security Best Practices
🔐 Secrets via AWS Secrets Manager and GitHub Encrypted Secrets

🛡 Vulnerability scanning with Trivy

🔍 Container checks via Docker Bench Security

🔑 IAM roles follow Principle of Least Privilege

📢 Notifications & Alerts
🚨 CI/CD Alerts via Slack or Email

🌐 Cloudflare DNS update notifications

📊 Monitoring & Logging
Area	Tooling
App Logs	Fluent Bit
Infra Logs	AWS CloudWatch
Metrics & Dashboards	Prometheus + Grafana

📜 Contributing
We welcome contributions! 🙌

Fork the repo & create a feature branch

Make your changes with clean commits

Open a Pull Request (PR)

⭐ Support & Author
If you found this project helpful, please give it a star ⭐!

🛠️ Author & Community
Crafted with 💖 by Harshhaa

Feel free to:

Open issues

Submit PRs

Join discussions

📧 Let's Connect!






📢 Stay Updated!
Follow for the latest DevOps insights, tutorials, and project updates!



yaml
Copy
Edit

---

Let me know if you want this saved as a downloadable `.md` file or want to publish it on GitHub Pages to
