# ansible_deploy_k8s_1.32
# Kubernetes Cluster Deployment with Ansible

This project provides an Ansible playbook to deploy a **Kubernetes v1.32** cluster on **Ubuntu 22.04** with **one master node** and **multiple worker nodes**.

---

## 📋 Features

- Kubernetes 1.32 installation using `kubeadm`
- Single master, multiple worker setup
- Automatically loads required kernel modules and configures sysctl
- Ubuntu 22.04 compatible

---

## ✅ Prerequisites

Before running the playbook, ensure:

- You have installed **Ansible** on your control machine.
- All target nodes are accessible via **passwordless SSH**.
- The Ansible user on all target machines has **passwordless sudo** privileges.

---

## ⚙️ Setup Instructions

### 1. Clone or download the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Configure your inventory
Edit the file inventory/hosts.ini to list the IPs and usernames of your Kubernetes nodes.

```bash
[masters]
master01 ansible_host=192.168.27.140 hostname=master

[nodes]
node01 ansible_host=192.168.27.141 hostname=node01
```

### 3. Run the playbook

```bash
ansible-playbook -i inventory/hosts.ini playbook.yaml
```
