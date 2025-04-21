# GCP Auto-Scaling & Secure VM Deployment

## 🚀 Project Overview

This project illustrates the deployment of a secure and auto-scaling virtual machine infrastructure on **Google Cloud Platform (GCP)**. The solution leverages **Managed Instance Groups (MIGs)** that automatically scale based on CPU usage and enforces access control via **IAM roles** and **Firewall Rules**.

---

## 📌 Scope

This documentation walks through:

- Creating and configuring VM instances on GCP.
- Deploying a **Managed Instance Group** (MIG) with auto-scaling based on CPU utilization.
- Implementing security using **IAM** and **Firewall Rules**.
- Testing system behavior under load.
- Recording the system setup and performance through video and script demonstrations.

---

## 🔄 Definitions

- **VM (Virtual Machine)** – A software-emulated system running on cloud infrastructure.
- **MIG (Managed Instance Group)** – A scalable group of VM instances managed as a unit.
- **IAM (Identity and Access Management)** – Access control system for managing GCP permissions.
- **Firewall Rules** – Rules for controlling traffic to and from instances.
- **Stress** – Tool used to simulate CPU load.
- **YAML** – Configuration format used in GCP deployments.

---

## 🧰 Tools & Technologies

| Component           | Technology Used            |
|--------------------|----------------------------|
| Cloud Platform      | Google Cloud Platform      |
| Operating System    | Ubuntu 20.04 LTS           |
| Scripting           | Bash                       |
| Monitoring          | GCP Metrics                |
| Auto-scaling Setup  | GCP Console / CLI / YAML   |
| Testing Tool        | `stress` (CPU load)        |
| Security            | IAM Roles, Firewall Rules  |
| Docs & Demo         | Markdown, OBS Studio       |

---

## ⚙️ Implementation Steps

### 1. VM Instance Creation
- Launched an Ubuntu 20.04 VM in Compute Engine.
- Enabled HTTP & HTTPS traffic using firewall rules.

### 2. Managed Instance Group Setup
- Created an **instance template** with `e2-medium` machine type.
- Configured a **Managed Instance Group (MIG)** with autoscaling.
- Set scaling trigger to activate when CPU exceeds 60%.

### 3. Security Configuration
- IAM Viewer role assigned for limited access.
- Opened ports 22 (SSH), 80 (HTTP), and 443 (HTTPS) via firewall rules.

### 4. Load Testing
- Installed `stress` using:
  ```bash
  sudo apt update
  sudo apt install stress
  stress --cpu 2 --timeout 90
