# 📘 Application Playbooks

![Ansible Logo](https://congdonglinux.com/wp-content/uploads/2020/11/Ansible.png)

## Overview
This repository contains **application playbooks** that automate the **installation, configuration, and basic hardening of software applications** on Ubuntu systems using **Ansible**.

The playbooks are designed so that anyone can **clone the repository and run a playbook within minutes**, without struggling with complex setup steps.

---

## 🧩 What Are Application Playbooks?
Application playbooks are **automation scripts** that:
- Install required system dependencies
- Configure services and runtimes
- Apply sensible default settings
- Verify that the application is running correctly

They ensure deployments are **repeatable, consistent, and reliable**.

---

## 📦 Playbooks Included / Planned
- Kimai – Time-tracking application
- Ghost – Publishing platform
- Jellyfin – Media server
- Firefox – Desktop application setup
- More application playbooks will be added over time

---

## ⚡ How to Run a Playbook (Step-by-Step)
##🟢 STEP 1: Install Ansible
sudo apt update
sudo apt install -y ansible git

##Confirm Ansible is installed:
ansible --version

##🟢 STEP 2: Clone the Repository
git clone https://github.com/your-username/application-playbooks.git
cd application-playbooks

##🟢 STEP 3: Create an Inventory File

Create a file called inventory:
nano hosts.ini


Paste this:
[servers]
YOUR_SERVER_IP ansible_user=ubuntu


🔁 Replace:
YOUR_SERVER_IP → your server IP address
ubuntu → your SSH username (if different)

Save and exit.

##🟢 STEP 4: Test Connection (No Risk)
ansible all -i inventory -m ping

If you see pong, you’re ready ✅

##🟢 STEP 5: Run a Playbook

Example: Install Kimai
ansible-playbook -i inventory kimai/install-kimai-ubuntu-24.04.yml
![Illustration](https://tse3.mm.bing.net/th/id/OIP.zffzMQIsXU6oMqRByFE96wAAAA?rs=1&pid=ImgDetMain&o=7&rm=3)

The playbook will automatically:
- Install dependencies
- Configure services
- Set up the application
- Verify the installation
- ⏱️ Time required: ~5–20 minutes

##🟢 STEP 6: Access the Application

Open your browser:
http://YOUR_SERVER_IP


If login details are required, they will be displayed at the end of the playbook run.

##🔒 Important Security Notes
- Change default passwords after first login
- Enable HTTPS/SSL for production use
- Review firewall rules before public exposure
- These playbooks prioritise ease of use and learning
