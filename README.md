# Multiple multi-tier arhitecture (Manual Provisioning via Vagrant) 🛠️

This project sets up a multi-layer Java web application architecture using **Vagrant** and **VirtualBox**, with **manual provisioning** of backend services already configured within the Vagrant setup.

Once cloned, the user can bring up the entire environment using a **single command: `vagrant up`**. All required provisioning steps (MySQL, Memcached, RabbitMQ, Tomcat, Nginx) are built into the Vagrantfile and its supporting configuration, so no manual installation is required after `vagrant up`.

---

## 📦 What This Project Does

This is a local DevOps lab that simulates deploying a real web application across five services running on five virtual machines. It mirrors a production-like environment using Vagrant-based virtualization and manually installed Linux services.

### Architecture Overview

| Layer            | Technology     | Purpose                      |
|------------------|----------------|-------------------------------|
| Web Layer        | Nginx          | Reverse proxy to app server  |
| Application Layer| Tomcat + Java  | Hosts the Java web application (WAR file) |
| Database         | MariaDB (MySQL)| Stores user data              |
| Caching          | Memcached      | Improves performance via caching |
| Message Broker   | RabbitMQ       | Handles background tasks and messaging |

---

## 🖥️ Virtual Machines Used

This setup provisions the following VMs using Vagrant:

| VM Name | Role            |
|---------|-----------------|
| `db01`  | Database Server (MySQL) |
| `mc01`  | Cache Server (Memcached) |
| `rmq01` | Message Queue (RabbitMQ) |
| `app01` | Application Server (Tomcat) |
| `web01` | Web Server (Nginx) |

Each VM is fully provisioned through shell scripts or inline Vagrant provisioning so that the services are automatically installed and configured during `vagrant up`.

---

## ⚙️ Tools Used

| Tool          | Purpose                               |
|---------------|----------------------------------------|
| **Vagrant**   | Automates VM creation and provisioning |
| **VirtualBox**| Runs the actual virtual machines       |
| **Linux (CentOS/Ubuntu)** | Host OS for services       |
| **Git**       | Version control and project setup      |
| **Bash**      | Provisioning and configuration scripts |
| **Systemd**   | Service management inside VMs          |

---

## 🚀 How to Run the Project

### ✅ Prerequisites

- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant](https://www.vagrantup.com/)
- Recommended: Git Bash or a UNIX-like terminal
- Run this plugin command before starting: vagrant plugin install vagrant-hostmanager
 git clone https://github.com/aogungbe/multitier-java-app.git
 cd multitier-java-app
 vagrant up

### Application Code Credit
The Java web application deployed in this environment originates from the public repository:

🔗 https://github.com/hkhcoder/vprofile-project

This repository only provides the infrastructure provisioning and environment setup required to run the application across multiple services and VMs. It is for local provisioning only.

⚠️ All rights and ownership of the original application code belong to the original author.

