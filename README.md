# Infrastructure-as-Code Labs

[![Terraform](https://img.shields.io/badge/Terraform-1.5.6-blue?logo=terraform&logoColor=white)](https://www.terraform.io/) 
[![Ansible](https://img.shields.io/badge/Ansible-2.14-red?logo=ansible&logoColor=white)](https://www.ansible.com/) 
[![Kubernetes](https://img.shields.io/badge/Kubernetes-1.27-blue?logo=kubernetes&logoColor=white)](https://kubernetes.io/) 
[![Prometheus](https://img.shields.io/badge/Prometheus-2.44-orange?logo=prometheus&logoColor=white)](https://prometheus.io/) 
[![Grafana](https://img.shields.io/badge/Grafana-10.3-orange?logo=grafana&logoColor=white)](https://grafana.com/)

This repository contains hands-on labs to practice DevOps, SRE, and infrastructure-as-code skills on a local Fedora VM. Each lab is self-contained and focuses on a specific tool or area.

---

## Labs Overview

### 1. DevOps Terraform Lab (`devops-terraform`)
[![Terraform](https://img.shields.io/badge/Terraform-1.5.6-blue?logo=terraform&logoColor=white)](https://www.terraform.io/)

**Purpose:** Practice infrastructure provisioning using Terraform.  
**Features:**
- Deploy Docker containers
- Parameterize resources using variables
- Output resource information for SRE observability

**Getting Started:**
```bash
cd devops-terraform
terraform init
terraform plan
terraform apply
Cleanup:

terraform destroy
2. DevOps Ansible Lab (devops-ansible)

Purpose: Automate system configuration and deployment using Ansible.
Features:

Install and configure Docker on Fedora

Practice playbooks and inventory management

Getting Started:

cd devops-ansible
ansible-playbook -i inventory.ini playbooks/setup-docker.yml
3. DevOps Kubernetes Lab (devops-kubernetes)

Purpose: Deploy and manage containerized applications with Kubernetes.
Features:

Nginx deployment with replicas

Resource limits and liveness probes

Hands-on with kubectl manifests

Getting Started:

cd devops-kubernetes
kubectl apply -f manifests/nginx-deployment.yaml
kubectl get pods
4. SRE Observability Lab (sre-observability)


Purpose: Explore observability with Prometheus and Grafana.
Features:

Prometheus monitoring for Kubernetes pods

Grafana dashboards for visual metrics

Connect monitoring to the Kubernetes Nginx lab

Getting Started:

cd sre-observability
# Deploy Prometheus and Grafana using Helm
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install monitoring prometheus-community/kube-prometheus-stack

# Forward ports to access dashboards
kubectl port-forward svc/monitoring-grafana 3000:80 -n monitoring
kubectl port-forward svc/monitoring-kube-prometheus-prometheus 9090:9090 -n monitoring
Open Grafana at http://localhost:3000 and import dashboards from grafana/dashboards.json.

Repository Structure
.
├── devops-ansible
├── devops-kubernetes
├── devops-terraform
├── sre-observability
└── README.md
Each folder contains its own README and lab resources.

Labs can be run independently or in combination for end-to-end practice.

Recommended Workflow
Start with Terraform lab to provision resources (optional: Docker or cloud VMs).

Use Ansible lab to configure systems or containers.

Deploy apps via Kubernetes manifests.

Observe metrics and dashboards in the SRE observability lab.

Cleanup resources after each lab to maintain a clean environment.

Notes
All labs are designed for learning and experimentation.

Use Git for version control: commit changes, push updates to your GitHub repo.

Recommended for practicing:

Terraform, Ansible, Kubernetes, Prometheus, Grafana

DevOps workflows, automation, observability, and SRE practices

Author
Anup Ranjan – DevOps/SRE enthusiast
GitHub: https://github.com/anupanupranjan-gif/infrastructure-as-code