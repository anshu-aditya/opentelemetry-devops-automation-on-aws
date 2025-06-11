# 🚀 OpenTelemetry DevOps Automation on AWS

![GitHub repo size](https://img.shields.io/github/repo-size/your-username/opentelemetry-devops-automation-on-aws)
![GitHub last commit](https://img.shields.io/github/last-commit/your-username/opentelemetry-devops-automation-on-aws)
![GitHub stars](https://img.shields.io/github/stars/your-username/opentelemetry-devops-automation-on-aws?style=social)

---

## 🧑‍💻 About the Project

This project implements a complete DevOps automation pipeline for deploying the **OpenTelemetry Astronomy Shop microservices demo application** on AWS using modern DevOps practices.

It leverages:

- ✅ **Terraform** for infrastructure provisioning
- ✅ **Kubernetes** (EKS) for container orchestration
- ✅ **Ansible** for configuration management (optional)
- ✅ **GitHub Actions** for CI/CD
- ✅ **OpenTelemetry** for observability (logs, traces, metrics)

Ideal for DevOps engineers aiming to demonstrate real-world infrastructure automation, secure application delivery, and AWS best practices.

---

## 📚 Table of Contents

- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Folder Structure](#-folder-structure)
- [Setup Instructions](#-setup-instructions)
- [Features](#-features)
- [Screenshots / Demo](#-screenshots--demo)
- [License](#-license)
- [Author](#-author)
- [Connect](#-connect)

---

## 🚀 Tech Stack

- **Cloud**: AWS (EKS, IAM, S3, CloudWatch)
- **IaC**: Terraform
- **Orchestration**: Kubernetes (EKS)
- **Observability**: OpenTelemetry, Jaeger, Prometheus, Grafana (optional)
- **CI/CD**: GitHub Actions (or Jenkins)
- **App Stack**: OpenTelemetry Demo (Astronomy Shop – multi-service e-commerce app)
- **Backup**: S3 + Shell Script
- **Monitoring & Logging**: CloudWatch Logs, Prometheus, OpenTelemetry Collector

---

## 🧱 Folder Structure

```bash
opentelemetry-devops-automation-on-aws/
├── terraform/                # Infrastructure provisioning (EKS, VPC, IAM, S3, CloudWatch)
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── backend.tf
│
├── kubernetes/              # Kubernetes manifests or Helm charts for OpenTelemetry Demo
│   ├── manifests/
│   │   ├── frontend-deployment.yaml
│   │   ├── checkoutservice-deployment.yaml
│   │   └── ingress.yaml
│   └── helm/
│       ├── Chart.yaml
│       ├── values.yaml
│       └── templates/
│           ├── deployment.yaml
│           └── service.yaml
│
├── otel-config/             # OpenTelemetry Collector configuration files
│   ├── otel-collector-config.yaml
│   └── exporters-config.yaml
│
├── cicd/                    # CI/CD pipeline config (GitHub Actions)
│   └── github-actions/
│       └── deploy.yml
│
├── scripts/                 # Utility scripts (backup, cleanup, validation)
│   ├── backup-to-s3.sh
│   └── cluster-cleanup.sh
│
├── diagrams/                # Architecture diagrams and visual docs
│   ├── architecture-diagram.png
│   └── architecture-explanation.md
│
├── .github/                 # GitHub-specific files
│   └── workflows/
│       └── ci-cd-pipeline.yml
│
├── .gitignore               # Git ignored files
├── LICENSE                  # Project license (MIT or Apache 2.0)
└── README.md                # Project documentation

```

---

## 🏗 Architecture

![Architecture Diagram](diagrams/architecture-diagram.png)

See `diagrams/architecture-explanation.md` for a detailed breakdown of this diagram.

---

## ⚙️ Setup Instructions

Follow these steps to deploy the OpenTelemetry Demo microservices application on AWS using Terraform, EKS, GitHub Actions, and OpenTelemetry.

---

### 1️⃣ Provision AWS Infrastructure with Terraform

```bash
# Navigate to the Terraform directory
cd terraform

# Initialize Terraform to download providers and modules
terraform init

# Apply the infrastructure plan (creates EKS, VPC, IAM, S3, etc.)
terraform apply

🧠 This step provisions the core AWS infrastructure:

VPC with public/private subnets

EKS cluster with worker node group

IAM roles and policies

CloudWatch Log Groups

S3 bucket for storing backups and configs
```

### 2️⃣ Configure EC2 with Ansible

```bash
cd ansible
ansible-playbook -i inventory install-lamp.yml
ansible-playbook -i inventory deploy-suitecrm.yml
```

### 3️⃣ Setup CI/CD Pipeline

- Use `jenkins/Jenkinsfile` for Jenkins.
- GitHub Actions option coming soon.

### 4️⃣ Automate Backups to S3

```bash
crontab -e
# Add the following line:
0 2 * * * /home/ubuntu/scripts/suitecrm-backup.sh
```

---

## ✨ Features

- 🔁 End-to-end DevOps automation (Infrastructure + Microservices + CI/CD)
- ☁️ AWS-native architecture using EKS, IAM, S3, and CloudWatch
- 📦 Deployment of OpenTelemetry Demo (Astronomy Shop) microservices on Kubernetes
- ⚙️ Infrastructure provisioning with Terraform using modular best practices
- 🚀 CI/CD pipeline with GitHub Actions for continuous integration and deployment
- 📊 Observability setup with OpenTelemetry Collector, Jaeger, and Prometheus
- 🔐 IAM-based secure access and EKS node role management
- 📈 Centralized monitoring, logs, and traces with CloudWatch and OpenTelemetry
- 💾 Backup automation to S3 with customizable shell scripts

---

## 🖼 Screenshots / Demo

> 📌 Add screenshots or CLI logs from Jenkins, Terraform apply, Ansible, and SuiteCRM UI here

---

## 🪪 License

This project is licensed under the [MIT License](LICENSE).

---

## 👤 Author

**Anshu Aditya**  
DevOps Engineer | AWS | Python Automation

---

## 💬 Connect

- LinkedIn: https://www.linkedin.com/in/anshu-aditya/
- GitHub: https://github.com/anshu-aditya/

---

🗓 Updated: June 09, 2025
