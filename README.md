# Ansible Infrastructure Automation Project

## Overview

This project automates the deployment of a multi-node Linux infrastructure using **Ansible**.

The infrastructure includes:

* Web servers (Apache)
* Database server (MariaDB)
* Firewall configuration
* SELinux security configuration
* Logical Volume Management (LVM)
* Automated database backups
* System user management

The goal of this project is to demonstrate **Infrastructure as Code (IaC)** using Ansible roles.

---

# Architecture

Control Node (Ansible)

│
├── Web Server 1
├── Web Server 2
└── Database Server

The control node uses SSH to manage all servers and deploy configurations automatically.

---

# Technologies Used

* Linux
* Ansible
* Apache HTTP Server
* MariaDB
* Firewalld
* SELinux
* LVM
* Bash
* Git

---

# Project Structure

```
project/
│
├── ansible.cfg
├── inventory
├── site.yml
│
└── roles/
    ├── common/
    ├── users/
    ├── lvm/
    ├── web/
    ├── firewall/
    ├── selinux/
    ├── database/
    └── backup/
```

---

# Roles Description

## common

Basic configuration applied to all servers.

Tasks include:

* Installing required packages
* System configuration
* Time synchronization

---

## users

Manages system users.

Features:

* Create admin group
* Create system users
* Configure sudo privileges

---

## lvm

Automates storage setup.

Tasks:

* Create volume groups
* Create logical volumes
* Format filesystem
* Mount storage

Example mount points:

```
/webdata
/dbdata
```

---

## web

Deploys Apache web servers.

Tasks:

* Install Apache
* Deploy web page
* Enable and start HTTP service

---

## firewall

Configures Firewalld rules.

Tasks:

* Enable firewall
* Allow SSH access
* Allow HTTP access for web servers

---

## selinux

Configures SELinux policies for web servers.

Tasks:

* Enable SELinux
* Configure Apache SELinux settings
* Apply correct security contexts

---

## database

Deploys MariaDB server.

Tasks:

* Install MariaDB packages
* Enable and start database service

---

## backup

Automates database backups.

Tasks:

* Create backup directory
* Create backup script
* Configure cron job for scheduled backups

Example backup location:

```
/backup
```

---

# How to Run

Execute the main playbook from the control node:

```
ansible-playbook -i inventory site.yml
```

This will configure all servers automatically.

---

# Example Outcome

After running the playbook:

* Web servers serve Apache pages
* Database server runs MariaDB
* Storage is automatically mounted
* Firewall and SELinux are configured
* Automated database backups are scheduled

---

# Skills Demonstrated

* Infrastructure automation
* Configuration management
* Linux system administration
* Security hardening
* Storage automation
* Database deployment
* Backup automation

---

# Author

Alind Wilson

GitHub
https://github.com/Alind-wilson10
