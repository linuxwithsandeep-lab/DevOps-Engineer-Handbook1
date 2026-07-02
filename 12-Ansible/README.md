# Chapter 12 – Ansible

Automation is one of the most important skills for a DevOps Engineer.

Managing a few servers manually is possible.

Managing hundreds or thousands of servers manually is almost impossible.

Organizations use **Configuration Management** tools to automate repetitive tasks.

One of the most popular tools for this purpose is **Ansible**.

---

# Topics Covered

## 12.1 Introduction to Ansible

- What is Configuration Management?
- What is Infrastructure Automation?
- Why Ansible?
- Benefits of Ansible
- Push vs Pull Architecture
- Agentless Architecture
- How Ansible Works
- Real-World Example

---

## 12.2 Installing Ansible

- Installation on Ubuntu
- Installation on RHEL/Rocky
- Installation using pip
- Verifying Installation
- Ansible Version
- Directory Structure

---

## 12.3 Inventory

- What is Inventory?
- Static Inventory
- Dynamic Inventory
- Inventory Groups
- Child Groups
- Host Variables
- Group Variables
- Inventory Best Practices

---

## 12.4 SSH & Passwordless Authentication

- SSH Keys
- ssh-copy-id
- Private/Public Keys
- Known Hosts
- Passwordless Login
- Production Best Practices

---

## 12.5 Ad-Hoc Commands

- ping
- shell
- command
- copy
- fetch
- file
- service
- package
- user
- group

---

## 12.6 YAML Basics

- YAML Syntax
- Variables
- Lists
- Dictionaries
- Indentation
- Comments
- Best Practices

---

## 12.7 Playbooks

- What is a Playbook?
- Play Structure
- Tasks
- Modules
- Variables
- Facts
- Tags
- Handlers

---

## 12.8 Variables

- Variable Types
- Inventory Variables
- Play Variables
- Registered Variables
- Magic Variables
- Facts
- Variable Precedence

---

## 12.9 Loops & Conditionals

- loop
- with_items
- when
- failed_when
- changed_when
- until
- retries

---

## 12.10 Handlers

- notify
- handlers
- Service Restart
- Best Practices

---

## 12.11 Templates (Jinja2)

- Variables
- Conditions
- Loops
- Template Rendering
- Dynamic Configuration Files

---

## 12.12 Roles

- Role Structure
- tasks/
- handlers/
- defaults/
- vars/
- templates/
- files/
- meta/
- Best Practices

---

## 12.13 Ansible Galaxy

- Installing Roles
- Collections
- Requirements File
- Community Roles

---

## 12.14 Vault

- What is Ansible Vault?
- Encrypt Files
- Encrypt Variables
- Vault Password
- Production Usage

---

## 12.15 Error Handling

- ignore_errors
- failed_when
- block
- rescue
- always

---

## 12.16 Ansible Modules

- copy
- file
- template
- yum
- apt
- service
- systemd
- user
- cron
- lineinfile
- replace

---

## 12.17 Ansible with Docker

- Docker Module
- Container Deployment
- Image Management
- Docker Compose

---

## 12.18 Ansible with Kubernetes

- Kubernetes Module
- Deployments
- Services
- ConfigMaps
- Secrets

---

## 12.19 Enterprise Ansible

- Project Structure
- Environment Separation
- Secrets Management
- CI/CD Integration
- AWX
- Red Hat Ansible Automation Platform

---

## 12.20 Production Best Practices

- Directory Structure
- Naming Standards
- Idempotency
- Error Handling
- Security
- Performance
- Logging
- Interview Questions
- Hands-on Labs
- Real-World Examples

---

# Goal

By the end of this chapter, you will be able to automate Linux servers, manage configurations, deploy applications, and integrate Ansible with Docker, Kubernetes and CI/CD pipelines like an experienced DevOps Engineer.
---

# 12.1 Introduction to Ansible

Imagine your company has:

- 10 Linux Servers
- 20 Docker Servers
- 15 Kubernetes Nodes
- 5 Database Servers

One day your manager says:

> "Install Nginx on every Linux server."

Doing this manually would require:

```
Login

↓

Install Package

↓

Start Service

↓

Enable Service

↓

Repeat Again

↓

Repeat Again

↓

Repeat Again...
```

If you have 500 servers,

this process becomes almost impossible.

To solve this problem,

organizations use **Configuration Management** and **Infrastructure Automation** tools.

One of the most popular tools is **Ansible**.

---

# What is Configuration Management?

Configuration Management is the process of keeping servers in a desired state automatically.

Instead of configuring every server manually,

we define the desired configuration once,

and automation ensures every server matches it.

Example:

```
Desired State

↓

Nginx Installed

↓

Service Running

↓

Port 80 Open
```

No matter how many servers exist,

they all receive the same configuration.

---

# What is Infrastructure Automation?

Infrastructure Automation means using software to perform infrastructure tasks automatically.

Instead of manually:

- Installing Packages
- Creating Users
- Configuring Services
- Deploying Applications
- Updating Servers

automation performs these tasks consistently.

---

# Manual Administration

```
Admin

↓

SSH

↓

Server 1

↓

Install Package

↓

SSH

↓

Server 2

↓

Install Package

↓

SSH

↓

Server 3

↓

Install Package
```

This is slow,

error-prone,

and difficult to scale.

---

# Automated Administration

```
Administrator

↓

Ansible

↓

Server 1

Server 2

Server 3

Server 4

Server 5

↓

Task Completed
```

One command configures every server.

---

# What is Ansible?

Ansible is an open-source automation platform used for:

- Configuration Management
- Application Deployment
- Server Provisioning
- Infrastructure Automation
- Cloud Automation
- Network Automation
- Security Automation

Ansible is developed by **Red Hat**.

---

# Simple Definition

```
Write Once

↓

Run Everywhere
```

One automation script can manage hundreds or thousands of servers.

---

# Why Ansible?

Before Ansible,

administrators often wrote long shell scripts.

Problems included:

- Difficult Maintenance
- Error-Prone Scripts
- No Standardization
- Poor Reusability

Ansible solves these problems using simple YAML files called **Playbooks**.

---

# Real-World Example

Suppose your company has:

```
100 Ubuntu Servers

50 Rocky Linux Servers

20 Amazon Linux Servers
```

The security team says:

```
Install Docker
```

Without Ansible:

```
170 Manual Logins
```

With Ansible:

```
1 Playbook

↓

170 Servers Updated
```

---

# Why Companies Use Ansible

Organizations choose Ansible because it provides:

✔ Easy to Learn

✔ Agentless Architecture

✔ YAML-Based Configuration

✔ Idempotent Operations

✔ Cross-Platform Support

✔ Cloud Integration

✔ Kubernetes Integration

✔ CI/CD Integration

✔ Large Community

---

# Ansible Architecture

```
                Control Node

                     │

     ┌───────────────┼───────────────┐

     │               │               │

 Managed Node    Managed Node    Managed Node

     │               │               │

 Ubuntu         Rocky Linux       CentOS
```

The **Control Node** runs Ansible.

The **Managed Nodes** are the systems being managed.

---

# Control Node

The Control Node is the machine where Ansible is installed.

Responsibilities:

- Stores Playbooks
- Stores Inventory
- Executes Tasks
- Connects to Remote Servers
- Displays Results

---

# Managed Node

Managed Nodes are the target systems.

Examples:

- Linux Servers
- Cloud VMs
- Docker Hosts
- Kubernetes Nodes
- Network Devices

No Ansible software needs to be installed on these systems.

---

# Agentless Architecture

One of Ansible's biggest advantages is:

```
No Agent Required
```

Unlike many configuration management tools,

Ansible communicates directly using SSH (Linux) or WinRM (Windows).

```
Control Node

↓

SSH

↓

Managed Server
```

---

# Push Architecture

Ansible follows a **Push Model**.

```
Control Node

↓

Push Tasks

↓

Managed Nodes
```

The Control Node initiates every operation.

---

# Push vs Pull

| Push | Pull |
|------|------|
| Control Node initiates | Managed Node initiates |
| Ansible | Puppet (traditional agent model) |
| No Agent | Usually Agent Required |
| Simple | More Complex |

---

# Idempotency

One of the most important Ansible concepts is:

```
Idempotency
```

Running the same playbook multiple times produces the same desired result.

Example:

```
Install Nginx

↓

Already Installed

↓

Nothing Changes
```

No duplicate work is performed.

---

# Without Idempotency

```
Run Script

↓

Install Again

↓

Duplicate Configuration

↓

Errors
```

---

# With Idempotency

```
Run Playbook

↓

Already Correct

↓

Skip Changes
```

Safe to execute repeatedly.

---

# YAML

Ansible uses YAML because it is:

- Human Readable
- Simple
- Lightweight
- Easy to Maintain

Example

```yaml
- name: Install nginx
  hosts: webservers
  become: yes

  tasks:
    - name: Install package
      apt:
        name: nginx
        state: present
```

---

# Common Ansible Use Cases

Ansible is commonly used for:

- Linux Administration
- Package Installation
- User Management
- Service Management
- Server Hardening
- Docker Deployment
- Kubernetes Deployment
- Cloud Provisioning
- Database Configuration
- CI/CD Automation

---

# Enterprise Example

A production company may use Ansible to:

```
Git Repository

↓

Jenkins

↓

Ansible

↓

500 Linux Servers

↓

Application Updated
```

Deployment becomes fast, consistent and repeatable.

---

# Advantages

✔ Easy Syntax

✔ Agentless

✔ Idempotent

✔ Fast Deployment

✔ Open Source

✔ Large Community

✔ Cloud Support

✔ Enterprise Ready

---

# Limitations

Ansible is excellent for configuration management,

but it is **not** intended to replace:

- Terraform (Infrastructure Provisioning)
- Kubernetes (Container Orchestration)
- Jenkins (CI/CD Orchestration)

Instead,

these tools work together.

---

# Tool Comparison

| Tool | Primary Purpose |
|------|-----------------|
| Ansible | Configuration Management |
| Terraform | Infrastructure Provisioning |
| Docker | Containerization |
| Kubernetes | Container Orchestration |
| Jenkins | CI/CD Automation |

---

# Common Beginner Mistakes

### Mistake 1

Thinking Ansible replaces Terraform.

Terraform creates infrastructure.

Ansible configures infrastructure.

---

### Mistake 2

Running commands manually after using Ansible.

Infrastructure should remain automated.

---

### Mistake 3

Writing huge shell scripts instead of playbooks.

Prefer reusable Ansible playbooks.

---

### Mistake 4

Ignoring idempotency.

Playbooks should always be safe to run multiple times.

---

### Mistake 5

Using Ansible only for package installation.

It can automate nearly every administrative task.

---

# Interview Questions

### Q1. What is Ansible?

Ansible is an open-source automation platform for configuration management, application deployment and infrastructure automation.

---

### Q2. What is a Control Node?

The Control Node is the machine where Ansible is installed and from which automation tasks are executed.

---

### Q3. What is a Managed Node?

A Managed Node is a target machine that Ansible configures remotely.

---

### Q4. Why is Ansible called Agentless?

Because it communicates using SSH (Linux) or WinRM (Windows) without requiring an agent on managed nodes.

---

### Q5. What is Idempotency?

Idempotency means running the same playbook multiple times results in the same desired state without unnecessary changes.

---

### Q6. What language does Ansible use?

Ansible Playbooks are written in **YAML**.

---

# Production Best Practices

✔ Store playbooks in Git.

✔ Use SSH key authentication.

✔ Organize inventories properly.

✔ Keep playbooks idempotent.

✔ Separate development, staging and production inventories.

✔ Reuse code with roles.

✔ Avoid hardcoded values.

✔ Test playbooks before production.

---

# Key Takeaways

- Ansible is a powerful automation and configuration management tool.
- It uses an agentless architecture based on SSH or WinRM.
- Playbooks are written in simple YAML syntax.
- Idempotency ensures safe and repeatable automation.
- Ansible is widely used with Docker, Kubernetes, cloud platforms and CI/CD pipelines.

---

# Next Section

## 12.2 Installing Ansible

In the next section, we will learn:

- Installing Ansible on Ubuntu
- Installing on Rocky Linux/RHEL
- Installing with pip
- Verifying Installation
- Understanding the Ansible Directory Structure
- First Ansible Command
- Hands-on Lab
---

# 12.2 Installing Ansible

Before Ansible can automate servers,

it must be installed on a machine called the **Control Node**.

The Control Node is responsible for:

- Executing Playbooks
- Connecting to Remote Servers
- Managing Inventory
- Running Automation Tasks

Only the Control Node requires Ansible to be installed.

Managed Nodes do **not** require Ansible.

---

# Installation Architecture

```
                    Control Node
                (Ansible Installed)

                        │
              SSH / WinRM Connection
                        │

        ┌───────────────┼───────────────┐

        │               │               │

   Ubuntu Server    Rocky Linux     Amazon Linux

(No Ansible)     (No Ansible)     (No Ansible)
```

---

# Prerequisites

Before installing Ansible, ensure:

✔ Python Installed

✔ SSH Installed

✔ Internet Connectivity

✔ Sudo Privileges

✔ SSH Access to Target Servers

---

# Check Python Version

Ubuntu

```bash
python3 --version
```

Example Output

```text
Python 3.12.3
```

---

# Check pip

```bash
pip3 --version
```

---

# Update Ubuntu

Always update package information before installation.

```bash
sudo apt update
```

Upgrade packages

```bash
sudo apt upgrade -y
```

---

# Installing Ansible on Ubuntu

Ubuntu provides Ansible packages through its repositories.

Install:

```bash
sudo apt install ansible -y
```

After installation,

verify:

```bash
ansible --version
```

---

# Example Output

```text
ansible [core 2.18.x]

python version = 3.x

jinja version = 3.x
```

---

# Installing Ansible using pip

Sometimes newer versions are required.

Install pip first:

```bash
sudo apt install python3-pip -y
```

Install Ansible:

```bash
pip install ansible
```

Or

```bash
pip3 install ansible
```

---

# Upgrade Ansible

```bash
pip install --upgrade ansible
```

---

# Installing on Rocky Linux / RHEL

Enable EPEL (if required):

```bash
sudo dnf install epel-release -y
```

Install Ansible:

```bash
sudo dnf install ansible -y
```

Verify:

```bash
ansible --version
```

---

# Installing on CentOS

```bash
sudo yum install epel-release -y

sudo yum install ansible -y
```

---

# Installing on Fedora

```bash
sudo dnf install ansible -y
```

---

# Installing on Arch Linux

```bash
sudo pacman -S ansible
```

---

# Installing on macOS

Using Homebrew

```bash
brew install ansible
```

Verify

```bash
ansible --version
```

---

# Installing on Windows

Windows usually runs Ansible through:

- WSL (Recommended)
- Ubuntu on WSL
- Virtual Machine
- Linux Server

Native Windows installation is generally not recommended for production use.

---

# Verify Installation

Run

```bash
ansible --version
```

Example

```text
ansible [core 2.18.x]
```

---

# Locate Ansible Binary

```bash
which ansible
```

Example

```text
/usr/bin/ansible
```

---

# Check Python Used by Ansible

```bash
ansible --version
```

Look for:

```
python version
```

---

# Important Ansible Commands

Check Version

```bash
ansible --version
```

Check Configuration

```bash
ansible-config dump
```

List Modules

```bash
ansible-doc -l
```

Show Documentation

```bash
ansible-doc copy
```

Show Help

```bash
ansible --help
```

---

# Ansible Directory Structure

A production project usually looks like:

```
ansible-project/

├── inventory/

│   ├── production

│   ├── staging

│   └── development

├── playbooks/

├── roles/

├── group_vars/

├── host_vars/

├── templates/

├── files/

├── handlers/

├── library/

├── ansible.cfg

└── README.md
```

---

# Inventory

Inventory contains the list of servers.

Example

```
inventory/

↓

production

↓

Web Servers

↓

Database Servers
```

We will study Inventory in detail in the next sections.

---

# ansible.cfg

The configuration file.

Example

```ini
[defaults]

inventory=inventory/production

host_key_checking=False

remote_user=ubuntu
```

---

# First Ansible Command

Check localhost

```bash
ansible localhost -m ping
```

Example Output

```json
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

---

# Understanding the Command

```
ansible

↓

localhost

↓

Module

↓

ping
```

The **ping** module checks communication with the target.

It does **not** use ICMP ping.

Instead,

it verifies Ansible connectivity.

---

# Running Against Inventory

Suppose inventory contains:

```ini
[web]

192.168.1.10

192.168.1.11
```

Run

```bash
ansible web -m ping
```

Both servers will be tested simultaneously.

---

# Installing Collections

Modern Ansible uses Collections.

Install one:

```bash
ansible-galaxy collection install community.general
```

List installed collections

```bash
ansible-galaxy collection list
```

---

# Installing Roles

Install a community role

```bash
ansible-galaxy install geerlingguy.nginx
```

Roles make playbooks reusable.

---

# Enterprise Installation Workflow

```
Install Linux

↓

Install Python

↓

Install Ansible

↓

Configure SSH

↓

Create Inventory

↓

Run Playbook

↓

Manage Infrastructure
```

---

# Common Installation Problems

### Problem 1

```
ansible: command not found
```

Reason

Ansible not installed or PATH incorrect.

---

### Problem 2

```
python not found
```

Install Python.

---

### Problem 3

```
Permission denied
```

Use sudo or correct permissions.

---

### Problem 4

```
SSH Connection Failed
```

Check:

- SSH Service
- Firewall
- SSH Keys
- User Credentials

---

### Problem 5

```
Module Not Found
```

Install required collections or Python dependencies.

---

# Real-World Example

A DevOps Engineer prepares a new automation server.

```
Ubuntu VM

↓

Install Python

↓

Install Ansible

↓

Configure SSH Keys

↓

Create Inventory

↓

Run Playbooks

↓

Manage 500 Servers
```

One Control Node can automate an entire infrastructure.

---

# Interview Questions

### Q1. Does every managed server require Ansible?

No.

Only the Control Node requires Ansible.

---

### Q2. Which protocol does Ansible use for Linux?

SSH.

---

### Q3. Which command verifies installation?

```bash
ansible --version
```

---

### Q4. What is the purpose of ansible.cfg?

It stores default Ansible configuration.

---

### Q5. What does the ping module do?

It verifies Ansible connectivity, not ICMP network reachability.

---

### Q6. Where are reusable community roles downloaded from?

Ansible Galaxy.

---

# Production Best Practices

✔ Keep Ansible updated.

✔ Store playbooks in Git.

✔ Use SSH key authentication.

✔ Separate inventories by environment.

✔ Use ansible.cfg for project configuration.

✔ Install required collections.

✔ Test automation in staging first.

✔ Document your project structure.

---

# Key Takeaways

- Only the Control Node requires Ansible installation.
- Managed Nodes communicate over SSH or WinRM.
- Installation is straightforward on Linux distributions.
- `ansible --version` verifies a successful installation.
- Organizing projects with inventories, roles and configuration files makes automation scalable.

---

# Next Section

## 12.3 Inventory

In the next section, we will learn:

- What is Inventory?
- Static Inventory
- Dynamic Inventory
- Host Groups
- Child Groups
- Host Variables
- Group Variables
- Inventory Best Practices
- Hands-on Labs
---

# 12.3 Inventory

Imagine you have multiple servers.

Example:

```
Web Server 1

192.168.1.10

----------------

Web Server 2

192.168.1.11

----------------

Database Server

192.168.1.20

----------------

Jenkins Server

192.168.1.30
```

How will Ansible know which servers to manage?

The answer is:

**Inventory**

---

# What is Inventory?

Inventory is a file that tells Ansible:

- Which servers exist
- Their IP addresses
- Hostnames
- Groups
- Variables
- Connection information

Without an Inventory,

Ansible does not know where to execute tasks.

---

# Simple Definition

```
Inventory

↓

List of Servers

↓

Ansible

↓

Automation
```

---

# Why Inventory?

Without Inventory

```
Administrator

↓

Remember Every IP

↓

Run Commands Manually
```

---

With Inventory

```
Inventory File

↓

Server List

↓

Run Once

↓

All Servers Updated
```

---

# Inventory Types

Ansible supports two major inventory types.

```
Inventory

│

├── Static Inventory

└── Dynamic Inventory
```

---

# Static Inventory

A Static Inventory is a manually created file.

Example:

```ini
192.168.1.10

192.168.1.11

192.168.1.20
```

The administrator updates this file manually whenever servers change.

---

# Example Static Inventory

```ini
[web]

192.168.1.10

192.168.1.11

[db]

192.168.1.20
```

Here,

servers are organized into groups.

---

# Inventory Groups

Groups allow multiple servers to be managed together.

Example

```
Inventory

│

├── Web

├── Database

├── Monitoring

└── Kubernetes
```

Instead of targeting individual servers,

Ansible targets groups.

---

# Example

```
[web]

web01

web02

web03

----------------

[db]

db01

db02
```

Now,

running:

```bash
ansible web -m ping
```

targets every web server.

---

# Hostnames vs IP Addresses

Inventory can contain:

Hostnames

```ini
web01.example.com
```

or

IP Addresses

```ini
192.168.1.10
```

Both are valid.

---

# Inventory File Location

Default inventory:

```text
/etc/ansible/hosts
```

Project-specific inventory:

```
inventory/

↓

production
```

Using project inventories is considered a best practice.

---

# Custom Inventory

Run Ansible using a custom inventory.

```bash
ansible all \
-i inventory/production \
-m ping
```

The **-i** option specifies the inventory file.

---

# Grouping Servers

Example

```ini
[web]

web01

web02

web03

[database]

db01

db02

[monitoring]

prometheus

grafana
```

Each group represents a different role.

---

# Group of Groups

Ansible supports nested groups.

Example

```ini
[web]

web01

web02

[database]

db01

[kubernetes:children]

web

database
```

The **kubernetes** group now contains both child groups.

---

# Child Groups

```
Infrastructure

│

├── Web

├── Database

└── Monitoring
```

Managing large infrastructures becomes much easier.

---

# Host Variables

Variables can be assigned to individual hosts.

Example

```ini
web01 ansible_host=192.168.1.10 ansible_user=ubuntu

web02 ansible_host=192.168.1.11 ansible_user=ubuntu
```

Each host has its own configuration.

---

# Group Variables

Variables can also be shared.

Example

```ini
[web:vars]

http_port=80

package=nginx
```

Every web server inherits these values.

---

# Inventory Variables

Common variables include:

- ansible_host
- ansible_user
- ansible_port
- ansible_password
- ansible_ssh_private_key_file
- ansible_python_interpreter

---

# Example

```ini
web01

ansible_host=192.168.1.10

ansible_user=ubuntu

ansible_port=22
```

Ansible now knows:

- IP Address
- SSH User
- SSH Port

---

# Inventory Directory Structure

Large projects often use:

```
inventory/

├── production

├── staging

├── development

├── group_vars/

└── host_vars/
```

Each environment has its own inventory.

---

# Production Example

```
inventory/

│

├── production

├── staging

└── development
```

Different environments prevent accidental production changes.

---

# Dynamic Inventory

Cloud environments change frequently.

Example:

```
AWS

↓

Auto Scaling

↓

New EC2 Instance

↓

Inventory Updated Automatically
```

Manually editing inventory becomes impractical.

---

# Dynamic Inventory Sources

Examples:

- AWS EC2
- Azure
- Google Cloud
- VMware
- OpenStack
- Kubernetes

Inventory is generated automatically.

---

# Dynamic Inventory Workflow

```
Cloud

↓

API

↓

Dynamic Inventory Plugin

↓

Ansible

↓

Automation
```

No manual inventory updates are required.

---

# Example

Instead of:

```ini
192.168.1.10
```

Ansible queries AWS directly:

```
AWS API

↓

Running Instances

↓

Inventory
```

---

# Verify Inventory

List all hosts.

```bash
ansible all \
-i inventory/production \
--list-hosts
```

Example Output

```text
hosts (5):

web01

web02

db01

prometheus

grafana
```

---

# Inventory Graph

Display group hierarchy.

```bash
ansible-inventory \
-i inventory/production \
--graph
```

Example

```text
@all

|--@web

|  |--web01

|  |--web02

|--@database

|  |--db01
```

---

# Export Inventory

Display inventory as JSON.

```bash
ansible-inventory \
-i inventory/production \
--list
```

Useful for troubleshooting.

---

# Enterprise Example

A company manages:

```
AWS

↓

250 Servers

↓

Dynamic Inventory

↓

Ansible

↓

Docker Deployment
```

No manual inventory maintenance is required.

---

# Common Inventory Mistakes

### Mistake 1

Keeping every server in one group.

Use logical grouping.

---

### Mistake 2

Using IP addresses everywhere.

Prefer meaningful hostnames when possible.

---

### Mistake 3

Keeping production and development together.

Separate environments.

---

### Mistake 4

Hardcoding credentials.

Use Ansible Vault instead.

---

### Mistake 5

Editing cloud inventories manually.

Use Dynamic Inventory plugins.

---

# Interview Questions

### Q1. What is Inventory?

Inventory is the list of managed hosts that Ansible uses for automation.

---

### Q2. What are the two major inventory types?

- Static Inventory
- Dynamic Inventory

---

### Q3. What is the default inventory location?

```text
/etc/ansible/hosts
```

---

### Q4. Which option specifies a custom inventory?

```bash
-i
```

---

### Q5. What is Dynamic Inventory?

Dynamic Inventory automatically retrieves hosts from cloud providers or external systems.

---

### Q6. Why are Groups used?

Groups allow multiple servers to be managed together using a single command.

---

# Production Best Practices

✔ Separate Production, Staging and Development inventories.

✔ Use meaningful group names.

✔ Store inventories in Git.

✔ Use Dynamic Inventory for cloud environments.

✔ Keep credentials in Ansible Vault.

✔ Use group_vars and host_vars appropriately.

✔ Validate inventory before running playbooks.

✔ Document inventory structure.

---

# Key Takeaways

- Inventory tells Ansible which systems to manage.
- Static Inventory is manually maintained.
- Dynamic Inventory automatically discovers cloud resources.
- Groups simplify automation across many servers.
- Host variables and group variables provide flexible configuration management.
- A well-organized inventory is the foundation of scalable Ansible automation.

---

# Next Section

## 12.4 SSH & Passwordless Authentication

In the next section, we will learn:

- SSH Basics
- Public & Private Keys
- Passwordless Authentication
- ssh-keygen
- ssh-copy-id
- Known Hosts
- SSH Best Practices
- Production Security
- Hands-on Labs
---

# 12.4 SSH & Passwordless Authentication

One of the biggest reasons Ansible became so popular is that it does **not require an agent** on managed servers.

Instead,

Ansible connects securely using **SSH**.

Every task you execute is sent over an encrypted SSH connection.

Without SSH,

Ansible cannot communicate with Linux servers.

---

# What is SSH?

SSH stands for:

```
Secure Shell
```

SSH is a secure protocol used to remotely access Linux and Unix systems.

It provides:

- Encrypted Communication
- Secure Authentication
- File Transfer
- Remote Command Execution
- Port Forwarding

---

# Why SSH?

Without SSH

```
Administrator

↓

Plain Text Login

↓

Password Can Be Stolen
```

---

With SSH

```
Administrator

↓

Encrypted Connection

↓

Secure Login
```

Everything transmitted is encrypted.

---

# SSH Architecture

```
Administrator

↓

SSH Client

↓

Encrypted Connection

↓

SSH Server

↓

Linux Machine
```

---

# SSH Default Port

SSH uses:

```
22
```

Example

```bash
ssh ubuntu@192.168.1.10
```

---

# SSH Authentication Methods

SSH supports two authentication methods.

```
SSH

│

├── Password Authentication

└── Public Key Authentication
```

---

# Password Authentication

```
Administrator

↓

Username

↓

Password

↓

Server
```

Easy to use,

but not recommended for production.

---

# Public Key Authentication

```
Private Key

↓

Client

↓

Public Key

↓

Server
```

Only the owner of the private key can authenticate.

This is the preferred method.

---

# Why Passwordless Authentication?

Imagine managing:

```
500 Servers
```

Typing passwords repeatedly is:

- Slow
- Error-Prone
- Difficult to Automate

Instead,

SSH Keys provide automatic authentication.

---

# SSH Key Pair

A key pair consists of:

```
Private Key

↓

Keep Secret

----------------

Public Key

↓

Copy to Server
```

---

# Generate SSH Key

Create a key pair.

```bash
ssh-keygen
```

Example

```text
Generating public/private rsa key pair.
```

Modern systems may default to Ed25519 instead of RSA.

---

# Key Location

Default location:

```
~/.ssh/

│

├── id_rsa

├── id_rsa.pub
```

or

```
~/.ssh/

├── id_ed25519

├── id_ed25519.pub
```

Private key:

```
id_rsa
```

or

```
id_ed25519
```

Public key:

```
id_rsa.pub
```

or

```
id_ed25519.pub
```

---

# Never Share Private Key

```
Private Key

❌ Never Share
```

Only the public key should be copied to servers.

---

# Copy Public Key

Copy the public key.

```bash
ssh-copy-id ubuntu@192.168.1.10
```

The server stores it in:

```
~/.ssh/authorized_keys
```

---

# Authentication Flow

```
Client

↓

Private Key

↓

SSH Server

↓

Public Key

↓

Access Granted
```

Passwords are no longer required for future logins.

---

# Test Passwordless Login

```bash
ssh ubuntu@192.168.1.10
```

Expected:

```
No Password Prompt
```

---

# SSH with Custom Key

```bash
ssh \
-i ~/.ssh/id_rsa \
ubuntu@192.168.1.10
```

---

# Known Hosts

The first connection produces:

```text
Are you sure you want to continue connecting?
```

SSH stores the server fingerprint in:

```
~/.ssh/known_hosts
```

Future connections verify the server identity.

---

# Why known_hosts?

```
Client

↓

Fingerprint

↓

known_hosts

↓

Verify Server
```

This helps defend against man-in-the-middle attacks.

---

# SSH Configuration File

Client configuration:

```
~/.ssh/config
```

Example

```text
Host web01
    HostName 192.168.1.10
    User ubuntu
    IdentityFile ~/.ssh/id_rsa
```

Now connect using:

```bash
ssh web01
```

---

# SSH Config Benefits

✔ Easy Hostnames

✔ Custom Ports

✔ Multiple Keys

✔ Simplified Commands

---

# SSH Agent

Instead of typing passphrases repeatedly,

use:

```bash
ssh-agent
```

Add key

```bash
ssh-add ~/.ssh/id_rsa
```

---

# SSH Permissions

Private key permissions:

```bash
chmod 600 ~/.ssh/id_rsa
```

Public key:

```bash
chmod 644 ~/.ssh/id_rsa.pub
```

SSH directory:

```bash
chmod 700 ~/.ssh
```

Incorrect permissions can cause authentication failures.

---

# SSH Service

Check SSH service:

Ubuntu

```bash
sudo systemctl status ssh
```

Rocky Linux

```bash
sudo systemctl status sshd
```

Start service

```bash
sudo systemctl start ssh
```

Enable service

```bash
sudo systemctl enable ssh
```

or

```bash
sudo systemctl enable sshd
```

---

# SSH and Ansible

Ansible uses SSH automatically.

Example Inventory

```ini
web01

ansible_host=192.168.1.10

ansible_user=ubuntu
```

Run

```bash
ansible web \
-m ping
```

SSH establishes the connection automatically.

---

# Multiple Server Example

```
Control Node

↓

SSH

↓

Web01

↓

SSH

↓

Web02

↓

SSH

↓

Database01
```

One command manages every server.

---

# SSH Best Practices

✔ Use SSH Keys

✔ Disable Password Authentication (when appropriate)

✔ Disable Root Login

✔ Rotate Keys Periodically

✔ Protect Private Keys

✔ Use MFA where supported

✔ Restrict SSH Access with Firewalls

✔ Monitor Login Attempts

---

# Enterprise Example

```
Administrator

↓

Git

↓

Jenkins

↓

Ansible

↓

SSH Keys

↓

500 Linux Servers
```

No passwords are stored inside playbooks.

---

# Common SSH Problems

### Problem 1

```
Permission denied (publickey)
```

Possible Causes

- Wrong Key
- Public Key Missing
- Wrong User
- Incorrect File Permissions

---

### Problem 2

```
Connection refused
```

Check:

- SSH Service
- Firewall
- Security Groups
- Port Number

---

### Problem 3

```
Host key verification failed
```

The server fingerprint changed.

Review the change before updating `known_hosts`.

---

### Problem 4

```
Timeout
```

Possible Causes

- Network Issue
- Firewall
- Wrong IP Address
- Server Down

---

### Problem 5

Password still requested.

Possible Causes

- Public key not copied
- Wrong private key
- Incorrect permissions

---

# Interview Questions

### Q1. What protocol does Ansible use to communicate with Linux servers?

SSH.

---

### Q2. Which port does SSH use by default?

Port 22.

---

### Q3. What command generates SSH keys?

```bash
ssh-keygen
```

---

### Q4. Which file stores authorized public keys on the server?

```text
~/.ssh/authorized_keys
```

---

### Q5. Should the private key ever be shared?

No.

Only the public key should be shared.

---

### Q6. Why is passwordless authentication recommended?

It improves security and enables automation without interactive password prompts.

---

# Production Best Practices

✔ Use SSH key authentication.

✔ Disable direct root login where possible.

✔ Use strong key algorithms such as Ed25519 or RSA with appropriate key sizes.

✔ Protect private keys with correct permissions.

✔ Rotate SSH keys periodically.

✔ Restrict SSH access using firewalls or security groups.

✔ Monitor SSH authentication logs.

✔ Never store passwords inside Ansible playbooks.

---

# Key Takeaways

- SSH provides secure remote administration.
- Ansible relies on SSH for Linux automation.
- Passwordless authentication uses public/private key pairs.
- Only the public key is copied to managed servers.
- SSH key authentication is the recommended approach for production automation.

---

# Next Section

## 12.5 Ad-Hoc Commands

In the next section, we will learn:

- What are Ad-Hoc Commands?
- Ansible Modules
- ping
- command
- shell
- copy
- file
- package
- service
- user
- group
- Real-World Examples
- Production Best Practices
- Hands-on Labs
---

# 12.5 Ad-Hoc Commands

Imagine your manager calls and says:

> "Restart the Nginx service on all web servers immediately."

Do you need to write a Playbook?

**No.**

For quick, one-time tasks, Ansible provides **Ad-Hoc Commands**.

They are simple command-line instructions that execute tasks immediately without creating a Playbook.

---

# What are Ad-Hoc Commands?

Ad-Hoc Commands are one-line Ansible commands used for quick automation tasks.

They are commonly used for:

- Checking Connectivity
- Installing Packages
- Restarting Services
- Copying Files
- Creating Users
- Rebooting Servers
- Collecting Information

---

# Simple Definition

```
One Command

↓

One Task

↓

Immediate Execution
```

---

# Why Ad-Hoc Commands?

Without Ad-Hoc Commands

```
Create Playbook

↓

Write YAML

↓

Run Playbook

↓

Delete Playbook
```

For a small task,

this is unnecessary.

---

With Ad-Hoc Commands

```
One Command

↓

Immediate Execution

↓

Done
```

---

# Command Structure

Basic syntax:

```bash
ansible <host-pattern> -m <module> -a "<arguments>"
```

Example:

```bash
ansible web -m ping
```

---

# Understanding the Syntax

```
ansible

↓

Host Pattern

↓

Module

↓

Arguments
```

Each part has a specific purpose.

---

# Host Pattern

Examples:

```bash
all
```

All servers.

---

```bash
web
```

Only web servers.

---

```bash
database
```

Only database servers.

---

```bash
web01
```

A single server.

---

# Modules

Modules are small programs that perform specific tasks.

Examples:

- ping
- command
- shell
- copy
- file
- package
- service
- user
- group

---

# The ping Module

The simplest module.

```bash
ansible all -m ping
```

Example Output

```text
web01 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

This confirms Ansible connectivity.

---

# The command Module

Executes commands without using a shell.

Example

```bash
ansible all \
-m command \
-a "uptime"
```

Output

```text
14:52:00 up 8 days
```

---

# command vs shell

| command | shell |
|----------|-------|
| No shell | Uses shell |
| Safer | More Flexible |
| No pipes | Supports pipes |
| No redirects | Supports redirects |

---

# The shell Module

Uses the system shell.

Example

```bash
ansible all \
-m shell \
-a "df -h"
```

---

Using Pipes

```bash
ansible all \
-m shell \
-a "ps -ef | grep nginx"
```

The **command** module cannot execute this.

---

# The copy Module

Copies files to remote servers.

Example

```bash
ansible web \
-m copy \
-a "src=index.html dest=/var/www/html/index.html"
```

---

# The file Module

Manages files and directories.

Create directory

```bash
ansible all \
-m file \
-a "path=/demo state=directory"
```

Remove directory

```bash
ansible all \
-m file \
-a "path=/demo state=absent"
```

---

# The package Module

Installs software packages.

Ubuntu

```bash
ansible web \
-m apt \
-a "name=nginx state=present"
```

Rocky Linux

```bash
ansible web \
-m dnf \
-a "name=nginx state=present"
```

Generic package module

```bash
ansible web \
-m package \
-a "name=nginx state=present"
```

---

# Installing Multiple Packages

```bash
ansible all \
-m package \
-a "name=git,curl,wget state=present"
```

---

# Remove Package

```bash
ansible all \
-m package \
-a "name=nginx state=absent"
```

---

# Update Packages

Ubuntu

```bash
ansible all \
-m apt \
-a "upgrade=yes"
```

---

# The service Module

Start service

```bash
ansible web \
-m service \
-a "name=nginx state=started"
```

Stop service

```bash
ansible web \
-m service \
-a "name=nginx state=stopped"
```

Restart

```bash
ansible web \
-m service \
-a "name=nginx state=restarted"
```

Enable

```bash
ansible web \
-m service \
-a "name=nginx enabled=yes"
```

---

# The user Module

Create user

```bash
ansible all \
-m user \
-a "name=developer state=present"
```

Delete user

```bash
ansible all \
-m user \
-a "name=developer state=absent remove=yes"
```

---

# The group Module

Create group

```bash
ansible all \
-m group \
-a "name=devops state=present"
```

---

# The setup Module

Collect system facts.

```bash
ansible all -m setup
```

Collect only network facts.

```bash
ansible all \
-m setup \
-a "filter=ansible_default_ipv4"
```

---

# Become (sudo)

Administrative tasks require elevated privileges.

Example

```bash
ansible all \
-b \
-m package \
-a "name=nginx state=present"
```

`-b` means **become** (sudo).

---

# Check Disk Space

```bash
ansible all \
-m shell \
-a "df -h"
```

---

# Check Memory

```bash
ansible all \
-m shell \
-a "free -m"
```

---

# Check Running Processes

```bash
ansible all \
-m shell \
-a "ps -ef"
```

---

# Reboot Servers

```bash
ansible all \
-b \
-m reboot
```

---

# Copy SSH Key

```bash
ansible all \
-m authorized_key \
-a "user=ubuntu key='{{ lookup('file','~/.ssh/id_rsa.pub') }}'"
```

---

# Enterprise Example

Suppose an organization has:

```
200 Web Servers
```

Security Team requests:

```
Restart Apache
```

Administrator executes:

```bash
ansible web \
-b \
-m service \
-a "name=httpd state=restarted"
```

Within seconds,

every server is updated.

---

# Ad-Hoc Command Workflow

```
Administrator

↓

Ad-Hoc Command

↓

Inventory

↓

SSH

↓

Module

↓

Managed Servers

↓

Result
```

---

# When to Use Ad-Hoc Commands

Use Ad-Hoc Commands for:

✔ Quick Fixes

✔ One-Time Tasks

✔ Troubleshooting

✔ Connectivity Tests

✔ Emergency Changes

---

# When NOT to Use Ad-Hoc Commands

Avoid them for:

- Repetitive Tasks
- Large Deployments
- Infrastructure Automation
- Configuration Management

Use **Playbooks** instead.

---

# Common Beginner Mistakes

### Mistake 1

Using `shell` when `command` is sufficient.

Prefer `command` unless shell features are required.

---

### Mistake 2

Forgetting `-b` for privileged operations.

Package installation usually requires sudo.

---

### Mistake 3

Running commands on `all` accidentally.

Always verify the target hosts.

---

### Mistake 4

Using Ad-Hoc Commands for repetitive work.

Convert repeated tasks into Playbooks.

---

### Mistake 5

Ignoring command output.

Always review the execution results.

---

# Interview Questions

### Q1. What are Ad-Hoc Commands?

Ad-Hoc Commands are one-line Ansible commands used for quick, one-time automation tasks.

---

### Q2. What is the difference between `command` and `shell`?

The `command` module does not use a shell and is safer.

The `shell` module executes commands through a shell and supports pipes, redirects and shell features.

---

### Q3. Which module checks Ansible connectivity?

The `ping` module.

---

### Q4. Which option enables sudo?

```bash
-b
```

---

### Q5. Which module manages services?

The `service` module.

---

### Q6. Should large deployments use Ad-Hoc Commands?

No.

Large or repeatable automation should use Playbooks.

---

# Production Best Practices

✔ Prefer `command` over `shell` when possible.

✔ Test commands on staging first.

✔ Use inventories and host groups carefully.

✔ Use `-b` only when required.

✔ Store reusable automation in Playbooks.

✔ Review command output after execution.

✔ Avoid running risky commands against `all`.

✔ Use version control for automation scripts.

---

# Key Takeaways

- Ad-Hoc Commands are ideal for quick, one-time administrative tasks.
- They execute modules directly without requiring a Playbook.
- Common modules include `ping`, `command`, `shell`, `copy`, `file`, `package`, `service`, `user` and `group`.
- Repetitive automation should be implemented using Playbooks.
- Understanding Ad-Hoc Commands builds a strong foundation before learning Playbooks.

---

# Next Section

## 12.6 YAML Basics

In the next section, we will learn:

- What is YAML?
- YAML Syntax
- Indentation Rules
- Scalars
- Lists
- Dictionaries
- Variables
- Comments
- Multi-line Strings
- Best Practices
- Hands-on Labs
---

# 12.6 YAML Basics

Before learning Ansible Playbooks,

you must understand **YAML**.

Every Ansible Playbook,

Inventory Variables,

Role Configuration,

and many Kubernetes configuration files are written in YAML.

If you understand YAML well,

learning Ansible becomes much easier.

---

# What is YAML?

YAML stands for:

```
YAML Ain't Markup Language
```

Originally it meant:

```
Yet Another Markup Language
```

Today,

it is officially known as:

```
YAML Ain't Markup Language
```

It is a **human-readable data serialization language**.

---

# Why YAML?

Imagine writing configuration like this:

```json
{
"name":"nginx",
"state":"present"
}
```

Now compare it with YAML.

```yaml
name: nginx
state: present
```

YAML is:

✔ Easier to Read

✔ Easier to Write

✔ Easier to Maintain

---

# Where is YAML Used?

YAML is widely used in:

- Ansible
- Kubernetes
- Docker Compose
- GitHub Actions
- GitLab CI
- Helm Charts
- AWS CloudFormation (some templates)
- Azure DevOps Pipelines

Learning YAML benefits many DevOps tools.

---

# YAML Structure

A YAML document is made up of:

- Keys
- Values
- Lists
- Dictionaries
- Comments

Everything is based on indentation.

---

# Key-Value Pair

The simplest YAML format:

```yaml
name: nginx
state: present
port: 80
```

Here,

```
name
```

is the key,

and

```
nginx
```

is the value.

---

# Multiple Values

```yaml
application: nginx

version: 1.26

enabled: true
```

Simple and readable.

---

# Indentation

The most important YAML rule:

```
Indentation defines structure.
```

YAML does **not** use:

- {}
- []
- ;

Instead,

it uses spaces.

---

# Correct Indentation

```yaml
server:

  name: web01

  ip: 192.168.1.10
```

---

# Incorrect Indentation

```yaml
server:

name: web01

ip: 192.168.1.10
```

This produces a parsing error.

---

# Spaces vs Tabs

Always use:

```
Spaces
```

Never use:

```
Tabs
```

Most YAML parsers reject tab characters.

---

# Scalar Values

Scalar means a single value.

Examples

```yaml
name: nginx

port: 80

enabled: true

version: 1.25
```

---

# Strings

```yaml
name: nginx

environment: production
```

Quotes are optional in many cases.

---

# Numbers

```yaml
cpu: 4

memory: 8

disk: 100
```

---

# Boolean Values

```yaml
enabled: true

debug: false
```

---

# Lists

Lists use a dash (`-`).

Example

```yaml
packages:

  - nginx

  - git

  - curl

  - wget
```

---

# Another List Example

```yaml
users:

  - alice

  - bob

  - charlie
```

---

# Dictionaries

A dictionary contains multiple key-value pairs.

```yaml
server:

  hostname: web01

  ip: 192.168.1.10

  os: Ubuntu
```

---

# Nested Dictionaries

```yaml
database:

  mysql:

    port: 3306

    version: 8

  redis:

    port: 6379
```

---

# List of Dictionaries

Very common in Ansible.

```yaml
users:

  - name: alice

    uid: 1001

  - name: bob

    uid: 1002
```

---

# Comments

Comments begin with:

```
#
```

Example

```yaml
# Install nginx

package: nginx
```

Comments improve readability.

---

# Multi-line Strings

Sometimes configuration spans multiple lines.

Use:

```
|
```

Example

```yaml
message: |

  Welcome

  to

  DevOps
```

---

# Folded Strings

Use:

```
>
```

Example

```yaml
description: >

  This is

  a long

  message.
```

The lines are folded into a single string.

---

# Null Values

```yaml
username:

password: null
```

Both indicate no value.

---

# Special Characters

Strings containing special characters should be quoted.

```yaml
password: "P@ssw0rd!"

url: "https://example.com"
```

---

# Variables in YAML

Variables are common in Ansible.

```yaml
package: nginx

service: nginx

port: 80
```

Variables can later be referenced inside playbooks.

---

# Example Configuration

```yaml
webserver:

  package: nginx

  service: nginx

  port: 80

  enabled: true
```

---

# YAML Validation

Before using YAML,

validate it.

Useful tools include:

- yamllint
- ansible-lint
- IDE extensions

Example

```bash
yamllint playbook.yml
```

---

# YAML File Extensions

Common extensions:

```
.yml

.yaml
```

Both are valid.

---

# Real-World Example

An Ansible Playbook begins like this:

```yaml
- name: Install Nginx

  hosts: web

  become: true

  tasks:

    - name: Install package

      package:

        name: nginx

        state: present
```

Everything depends on proper indentation.

---

# Enterprise Example

A company stores:

```
Git Repository

↓

YAML Playbooks

↓

Jenkins

↓

Ansible

↓

500 Servers
```

Every automation starts with correctly written YAML.

---

# YAML Best Practices

✔ Use two spaces for indentation.

✔ Never use tabs.

✔ Keep key names meaningful.

✔ Add comments where necessary.

✔ Validate YAML before deployment.

✔ Keep files clean and readable.

✔ Group related values together.

✔ Avoid unnecessary nesting.

---

# Common Beginner Mistakes

### Mistake 1

Using tabs instead of spaces.

Always use spaces.

---

### Mistake 2

Incorrect indentation.

YAML is indentation-sensitive.

---

### Mistake 3

Writing complex nested structures unnecessarily.

Keep YAML simple.

---

### Mistake 4

Ignoring validation.

Always lint YAML files.

---

### Mistake 5

Using inconsistent indentation widths.

Choose a consistent style (commonly two spaces).

---

# Interview Questions

### Q1. What does YAML stand for?

YAML Ain't Markup Language.

---

### Q2. Why is YAML popular in DevOps?

Because it is simple, human-readable and easy to maintain.

---

### Q3. Which DevOps tools use YAML?

Examples include:

- Ansible
- Kubernetes
- Docker Compose
- GitHub Actions
- Helm

---

### Q4. Does YAML use tabs?

No.

YAML uses spaces for indentation.

---

### Q5. Which characters represent a list?

A dash (`-`).

---

### Q6. What is the most common reason for YAML errors?

Incorrect indentation.

---

# Production Best Practices

✔ Validate every YAML file before deployment.

✔ Use consistent indentation.

✔ Keep files modular and readable.

✔ Store YAML files in Git.

✔ Add meaningful comments.

✔ Use descriptive variable names.

✔ Avoid duplicate configuration.

✔ Follow team formatting standards.

---

# Key Takeaways

- YAML is the foundation of Ansible Playbooks and many DevOps tools.
- Indentation determines structure.
- YAML supports key-value pairs, lists and dictionaries.
- Spaces—not tabs—must be used.
- Clean, validated YAML reduces configuration errors and improves maintainability.

---

# Next Section

## 12.7 Playbooks

In the next section, we will learn:

- What is a Playbook?
- Playbook Structure
- Tasks
- Modules
- Variables
- Facts
- Handlers
- Tags
- Execution Flow
- Real-World Examples
- Hands-on Labs
---

# 12.7 Playbooks

Imagine you need to:

- Install Nginx
- Create a User
- Copy Configuration Files
- Start the Service
- Enable Auto Start

You can execute each task individually using Ad-Hoc Commands.

However,

what if you need to perform the same tasks every week?

Or every time a new server is created?

Instead of typing multiple commands repeatedly,

Ansible provides **Playbooks**.

A Playbook automates an entire workflow.

---

# What is a Playbook?

A Playbook is a YAML file that describes one or more automation tasks to be executed on managed servers.

Think of it as a recipe.

Just as a cooking recipe contains multiple steps,

a Playbook contains multiple automation tasks.

---

# Simple Definition

```
Playbook

↓

Multiple Tasks

↓

Automation

↓

Desired State
```

---

# Why Playbooks?

Without Playbooks

```
Login

↓

Install Package

↓

Copy File

↓

Restart Service

↓

Repeat Again
```

---

With Playbooks

```
Run Playbook

↓

Everything Automated
```

---

# Playbook Workflow

```
Administrator

↓

Playbook

↓

Inventory

↓

SSH

↓

Managed Nodes

↓

Configuration Applied
```

---

# Playbook File Extension

Common file extensions:

```
site.yml

install_nginx.yml

users.yaml
```

Both `.yml` and `.yaml` are supported.

---

# Basic Playbook Structure

Every Playbook begins with:

```yaml
- name: Install Nginx

  hosts: web

  become: true

  tasks:

    - name: Install nginx

      package:

        name: nginx

        state: present
```

---

# Understanding the Structure

```
Play

↓

Hosts

↓

Tasks

↓

Modules

↓

Result
```

Each section has a specific purpose.

---

# name

Example

```yaml
name: Install Nginx
```

The **name** provides a human-readable description.

It appears during execution.

---

# hosts

Example

```yaml
hosts: web
```

This tells Ansible which inventory group should execute the Playbook.

Examples:

```yaml
hosts: all
```

```yaml
hosts: database
```

```yaml
hosts: localhost
```

---

# become

Many Linux tasks require root privileges.

```yaml
become: true
```

This is equivalent to using:

```bash
sudo
```

---

# tasks

Tasks contain the actual work.

Example

```yaml
tasks:

  - name: Install nginx

    package:

      name: nginx

      state: present
```

Each task performs one operation.

---

# Modules

Tasks call Ansible Modules.

Example

```yaml
package:

  name: nginx

  state: present
```

The module is:

```
package
```

---

# Complete Example

```yaml
- name: Configure Web Server

  hosts: web

  become: true

  tasks:

    - name: Install nginx

      package:

        name: nginx

        state: present

    - name: Start nginx

      service:

        name: nginx

        state: started

    - name: Enable nginx

      service:

        name: nginx

        enabled: true
```

---

# Execution Flow

```
Playbook

↓

Inventory

↓

SSH

↓

Task 1

↓

Task 2

↓

Task 3

↓

Complete
```

Tasks execute from top to bottom.

---

# Running a Playbook

Execute:

```bash
ansible-playbook install_nginx.yml
```

Using a custom inventory:

```bash
ansible-playbook \
-i inventory/production \
install_nginx.yml
```

---

# Dry Run (Check Mode)

Preview changes without modifying servers.

```bash
ansible-playbook \
install_nginx.yml \
--check
```

Useful before production deployments.

---

# Diff Mode

View configuration differences.

```bash
ansible-playbook \
install_nginx.yml \
--diff
```

---

# Syntax Check

Validate the Playbook.

```bash
ansible-playbook \
install_nginx.yml \
--syntax-check
```

Always perform a syntax check before execution.

---

# Limiting Hosts

Run only on one server.

```bash
ansible-playbook \
install_nginx.yml \
--limit web01
```

Or

```bash
--limit database
```

---

# Tags

Execute only selected tasks.

Example

```yaml
tasks:

- name: Install nginx

  tags:

    - install
```

Run

```bash
ansible-playbook \
install.yml \
--tags install
```

---

# Skip Tags

```bash
ansible-playbook \
install.yml \
--skip-tags install
```

---

# Verbose Output

```bash
ansible-playbook install.yml -v
```

More details

```bash
-vv
```

Even more

```bash
-vvv
```

Maximum debugging

```bash
-vvvv
```

---

# Idempotency

Playbooks are designed to be idempotent.

Example

```
Nginx Installed

↓

Run Again

↓

No Changes
```

Safe to execute repeatedly.

---

# Enterprise Example

A company deploys a web application.

```
Git

↓

Jenkins

↓

Ansible Playbook

↓

100 Servers

↓

Deployment Completed
```

One Playbook performs the entire deployment.

---

# Playbook vs Ad-Hoc Commands

| Playbook | Ad-Hoc |
|----------|---------|
| Multiple Tasks | One Task |
| YAML | CLI |
| Reusable | Temporary |
| Version Controlled | Usually Not |
| Best for Automation | Best for Quick Actions |

---

# Benefits of Playbooks

✔ Reusable

✔ Readable

✔ Version Controlled

✔ Idempotent

✔ Easy to Maintain

✔ Team Collaboration

✔ CI/CD Friendly

✔ Production Ready

---

# Common Beginner Mistakes

### Mistake 1

Putting too many unrelated tasks into one Playbook.

Keep Playbooks focused.

---

### Mistake 2

Skipping syntax validation.

Always use:

```bash
ansible-playbook --syntax-check
```

---

### Mistake 3

Not using `become` for privileged tasks.

Package installation often requires elevated privileges.

---

### Mistake 4

Ignoring idempotency.

Avoid shell commands when Ansible modules already exist.

---

### Mistake 5

Hardcoding values.

Use variables instead.

---

# Interview Questions

### Q1. What is an Ansible Playbook?

A Playbook is a YAML file that defines automation tasks to be executed on managed hosts.

---

### Q2. Which command executes a Playbook?

```bash
ansible-playbook playbook.yml
```

---

### Q3. What does `hosts` specify?

The inventory hosts or group where the Playbook runs.

---

### Q4. What is `become: true`?

It enables privilege escalation (similar to `sudo`).

---

### Q5. Why are Playbooks preferred over Ad-Hoc Commands?

Because they are reusable, version-controlled and suitable for repeatable automation.

---

### Q6. What does `--check` do?

It performs a dry run without making actual changes.

---

# Production Best Practices

✔ Keep Playbooks modular.

✔ Store them in Git.

✔ Validate syntax before execution.

✔ Use variables instead of hardcoded values.

✔ Use tags for selective execution.

✔ Test in staging before production.

✔ Prefer built-in modules over shell commands.

✔ Write idempotent automation.

---

# Key Takeaways

- Playbooks are the core automation mechanism in Ansible.
- They are written in YAML and execute tasks sequentially.
- Playbooks are reusable, maintainable and version-controlled.
- Features like `--check`, `--diff` and `--syntax-check` improve deployment safety.
- Well-designed Playbooks are essential for production-grade infrastructure automation.

---

# Next Section

## 12.8 Variables

In the next section, we will learn:

- What are Variables?
- Variable Types
- Inventory Variables
- Play Variables
- Registered Variables
- Facts
- Magic Variables
- Variable Precedence
- Best Practices
- Hands-on Labs
---

# 12.8 Variables

Imagine you have 100 web servers.

Every Playbook contains:

```yaml
name: nginx

port: 80

user: ubuntu
```

Now imagine your company decides to replace **Nginx** with **Apache**.

Will you manually edit hundreds of Playbooks?

**No.**

Instead, we use **Variables**.

Variables make Playbooks reusable, flexible and easy to maintain.

---

# What are Variables?

Variables are named values that store data.

Instead of hardcoding information,

we store it in variables and reference it whenever needed.

---

# Simple Definition

```
Variable

↓

Stores Value

↓

Playbook Uses Value
```

---

# Why Variables?

Without Variables

```yaml
name: nginx
```

Repeated everywhere.

---

With Variables

```yaml
package_name: nginx
```

Later

```yaml
name: "{{ package_name }}"
```

Change once,

update everywhere.

---

# Basic Variable

```yaml
package_name: nginx

service_name: nginx

http_port: 80
```

---

# Using Variables

```yaml
tasks:

  - name: Install package

    package:

      name: "{{ package_name }}"

      state: present
```

Variables are referenced using:

```text
{{ variable_name }}
```

---

# Variable Workflow

```
Variable

↓

Playbook

↓

Module

↓

Execution
```

---

# Types of Variables

Ansible supports many variable types.

```
Variables

│

├── Play Variables

├── Inventory Variables

├── Host Variables

├── Group Variables

├── Registered Variables

├── Facts

└── Extra Variables
```

---

# Play Variables

Defined inside the Playbook.

Example

```yaml
- hosts: web

  vars:

    package_name: nginx

    http_port: 80
```

Only available within that Play.

---

# Inventory Variables

Stored inside Inventory.

Example

```ini
web01

ansible_host=192.168.1.10

http_port=80
```

Useful for server-specific settings.

---

# Host Variables

Host-specific values.

Example

```yaml
web01

↓

host_vars/

↓

web01.yml
```

Example file

```yaml
package_name: nginx

timezone: Asia/Kolkata
```

Only applies to **web01**.

---

# Group Variables

Shared across all hosts in a group.

```
group_vars/

↓

web.yml
```

Example

```yaml
package_name: nginx

service_name: nginx
```

Every host in the **web** group receives these values.

---

# Registered Variables

Sometimes a task produces output.

We can save it.

Example

```yaml
- name: Check uptime

  command: uptime

  register: uptime_output
```

Display

```yaml
- debug:

    var: uptime_output.stdout
```

---

# Facts

Facts are automatically collected system information.

Collect facts

```yaml
gather_facts: true
```

Example variables

```yaml
{{ ansible_hostname }}

{{ ansible_distribution }}

{{ ansible_processor_vcpus }}

{{ ansible_memtotal_mb }}
```

---

# Display Facts

```yaml
- debug:

    var: ansible_hostname
```

Example Output

```
web01
```

---

# Magic Variables

Magic Variables are built into Ansible.

Examples

```yaml
inventory_hostname

playbook_dir

group_names

hostvars
```

These provide runtime information.

---

# Extra Variables

Extra Variables are passed at runtime.

Playbook

```yaml
package_name: nginx
```

Run

```bash
ansible-playbook install.yml \
-e "package_name=httpd"
```

The Playbook now installs Apache instead of Nginx.

---

# Variable File

Instead of defining variables inside Playbooks,

store them separately.

```
vars/

↓

packages.yml
```

Example

```yaml
package_name: nginx

service_name: nginx
```

Load file

```yaml
vars_files:

  - vars/packages.yml
```

---

# Multiple Variables

```yaml
vars:

  app_name: ecommerce

  app_port: 8080

  app_user: developer

  app_group: devops
```

---

# Dictionary Variable

```yaml
webserver:

  package: nginx

  port: 80

  service: nginx
```

Access

```yaml
{{ webserver.package }}
```

---

# List Variable

```yaml
packages:

  - git

  - curl

  - nginx
```

Loop later

```yaml
{{ packages }}
```

---

# Variable Example

```yaml
vars:

  package_name: nginx

tasks:

  - package:

      name: "{{ package_name }}"

      state: present
```

Result

```
Install nginx
```

Change one variable,

the Playbook behaves differently.

---

# Variable Precedence

Sometimes the same variable exists in multiple places.

Ansible decides which one wins.

Simplified order:

```
Extra Variables

↓

Task Variables

↓

Play Variables

↓

Host Variables

↓

Group Variables

↓

Inventory Variables

↓

Role Defaults
```

Higher precedence overrides lower precedence.

---

# Variable Workflow

```
Variables

↓

Merge

↓

Highest Priority Selected

↓

Playbook Executes
```

---

# Enterprise Example

A company has:

```
Production

↓

group_vars/

↓

package_name=nginx
```

Development

```
group_vars/

↓

package_name=apache2
```

Same Playbook,

different environments.

No code changes required.

---

# Debug Variables

View variables.

```yaml
- debug:

    var: package_name
```

Display message

```yaml
- debug:

    msg: "Installing {{ package_name }}"
```

---

# Variable Naming Best Practices

✔ Use lowercase.

✔ Use underscores.

Example

```yaml
database_port

web_server_name

application_user
```

Avoid:

```yaml
DatabasePort

MyVariable

x
```

---

# Common Beginner Mistakes

### Mistake 1

Hardcoding values.

Use variables instead.

---

### Mistake 2

Using unclear names.

Prefer descriptive variable names.

---

### Mistake 3

Repeating values.

Store common values in `group_vars`.

---

### Mistake 4

Ignoring variable precedence.

Higher-priority variables override lower ones.

---

### Mistake 5

Keeping secrets in plain variables.

Use **Ansible Vault** for sensitive information.

---

# Interview Questions

### Q1. What are Variables in Ansible?

Variables store reusable values that can be referenced throughout Playbooks.

---

### Q2. How do you reference a variable?

```yaml
{{ variable_name }}
```

---

### Q3. What are Facts?

Facts are automatically collected information about managed hosts.

---

### Q4. What is the purpose of `register`?

It stores the output of a task for later use.

---

### Q5. Which variable type has the highest precedence?

Extra Variables (`-e`) have one of the highest priorities and override most other variable sources.

---

### Q6. Where should common variables for a host group be stored?

Inside the `group_vars/` directory.

---

# Production Best Practices

✔ Store environment-specific values in `group_vars`.

✔ Store host-specific values in `host_vars`.

✔ Use descriptive variable names.

✔ Avoid hardcoding configuration.

✔ Keep reusable variables in separate files.

✔ Use `debug` during development.

✔ Protect sensitive variables using Ansible Vault.

✔ Document important variables.

---

# Key Takeaways

- Variables make Playbooks reusable and flexible.
- Ansible supports Play, Inventory, Host, Group, Registered and Extra Variables.
- Facts provide system information automatically.
- Variable precedence determines which value is used.
- Proper variable management is essential for production-ready automation.

---

# Next Section

## 12.9 Loops & Conditionals

In the next section, we will learn:

- Loops
- loop
- with_items
- when
- failed_when
- changed_when
- until
- retries
- Conditional Execution
- Real-World Examples
- Production Best Practices
- Hands-on Labs
---

# 12.9 Loops & Conditionals

Imagine you need to install the following packages on every server:

- nginx
- git
- curl
- wget
- unzip

One option is to write five separate tasks.

Another option is to write **one task** and let Ansible repeat it automatically.

This is where **Loops** become useful.

Similarly,

sometimes a task should execute **only if a condition is true**.

This is achieved using **Conditionals**.

Loops and Conditionals make Playbooks smaller,

cleaner,

and more intelligent.

---

# What are Loops?

Loops allow one task to execute multiple times using different values.

Instead of writing:

```
Install nginx

↓

Install git

↓

Install curl

↓

Install wget
```

We write one task that repeats automatically.

---

# Simple Definition

```
One Task

↓

Multiple Items

↓

Repeated Execution
```

---

# Why Loops?

Without Loops

```yaml
- package:
    name: nginx

- package:
    name: git

- package:
    name: curl
```

---

With Loops

```yaml
loop:

  - nginx

  - git

  - curl
```

Much shorter and easier to maintain.

---

# Basic Loop

```yaml
tasks:

  - name: Install packages

    package:

      name: "{{ item }}"

      state: present

    loop:

      - nginx

      - git

      - curl
```

---

# Understanding item

During every iteration,

```
item
```

contains one value.

Iteration 1

```
item

↓

nginx
```

Iteration 2

```
item

↓

git
```

Iteration 3

```
item

↓

curl
```

---

# Loop Workflow

```
Loop

↓

Item 1

↓

Execute

↓

Item 2

↓

Execute

↓

Item 3

↓

Execute
```

---

# Loop with Variables

```yaml
vars:

  packages:

    - nginx

    - git

    - curl
```

Task

```yaml
- package:

    name: "{{ item }}"

    state: present

  loop: "{{ packages }}"
```

---

# Loop with Dictionaries

```yaml
users:

  - name: alice

    uid: 1001

  - name: bob

    uid: 1002
```

Task

```yaml
- user:

    name: "{{ item.name }}"

    uid: "{{ item.uid }}"

  loop: "{{ users }}"
```

---

# Loop over Files

```yaml
files:

  - index.html

  - app.conf

  - nginx.conf
```

Copy

```yaml
- copy:

    src: "{{ item }}"

    dest: /tmp/

  loop: "{{ files }}"
```

---

# with_items (Legacy)

Older Playbooks use:

```yaml
with_items:

  - nginx

  - git
```

Modern Ansible recommends:

```yaml
loop:
```

Prefer `loop` for new Playbooks.

---

# What are Conditionals?

Conditionals allow tasks to execute only when a condition is true.

Keyword:

```yaml
when:
```

---

# Why Conditionals?

Without Conditionals

```
Run Every Task

↓

Even if Unnecessary
```

---

With Conditionals

```
Check Condition

↓

True?

↓

Execute

↓

False?

↓

Skip
```

---

# Basic when

```yaml
- name: Install Apache

  package:

    name: httpd

    state: present

  when:

    ansible_distribution == "Rocky"
```

Only Rocky Linux executes the task.

---

# Ubuntu Example

```yaml
- package:

    name: nginx

    state: present

  when:

    ansible_distribution == "Ubuntu"
```

---

# Multiple Conditions

```yaml
when:

  - ansible_distribution == "Ubuntu"

  - ansible_memtotal_mb > 2048
```

Both conditions must be true.

---

# OR Condition

```yaml
when:

  ansible_distribution == "Ubuntu"
  or
  ansible_distribution == "Debian"
```

---

# AND Condition

```yaml
when:

  ansible_distribution == "Ubuntu"
  and
  ansible_processor_vcpus >= 4
```

---

# Boolean Variable

```yaml
vars:

  install_nginx: true
```

Task

```yaml
- package:

    name: nginx

    state: present

  when:

    install_nginx
```

---

# Checking Variable Exists

```yaml
when:

  package_name is defined
```

---

# Checking Variable Missing

```yaml
when:

  package_name is not defined
```

---

# failed_when

Sometimes a command returns success,

but you still want Ansible to treat it as failed.

Example

```yaml
- command: ./healthcheck.sh

  register: result

  failed_when:

    "'FAILED' in result.stdout"
```

---

# changed_when

Prevent Ansible from reporting a task as changed.

```yaml
changed_when: false
```

Useful for read-only operations.

---

# until

Retry until a condition becomes true.

Example

```yaml
- uri:

    url: http://localhost

  register: result

  until:

    result.status == 200

  retries: 5

  delay: 10
```

---

# retries

```
Retry

↓

Failure

↓

Retry Again

↓

Success
```

Example

```yaml
retries: 5
```

---

# delay

Wait between retries.

```yaml
delay: 15
```

Waits 15 seconds before retrying.

---

# Loop + Condition

```yaml
- package:

    name: "{{ item }}"

    state: present

  loop:

    - nginx

    - git

    - curl

  when:

    ansible_distribution == "Ubuntu"
```

---

# Real-World Example

Suppose a company has:

```
Ubuntu

↓

Install nginx

----------------

Rocky

↓

Install httpd
```

Playbook

```yaml
- package:

    name: nginx

  when:

    ansible_distribution == "Ubuntu"

- package:

    name: httpd

  when:

    ansible_distribution == "Rocky"
```

One Playbook supports multiple operating systems.

---

# Enterprise Example

```
Inventory

↓

100 Servers

↓

Loop

↓

Install Packages

↓

Condition

↓

OS-specific Tasks

↓

Deployment Complete
```

---

# Advantages

✔ Less Code

✔ Better Readability

✔ Reusable Playbooks

✔ OS-specific Automation

✔ Dynamic Execution

✔ Easier Maintenance

---

# Common Beginner Mistakes

### Mistake 1

Writing separate tasks instead of loops.

Use `loop` whenever possible.

---

### Mistake 2

Using `with_items` in new Playbooks.

Prefer `loop`.

---

### Mistake 3

Writing incorrect `when` conditions.

Test conditions carefully.

---

### Mistake 4

Ignoring `failed_when`.

Some scripts return misleading exit codes.

---

### Mistake 5

Using infinite retries.

Always define reasonable `retries` and `delay`.

---

# Interview Questions

### Q1. What is a Loop?

A Loop executes the same task multiple times using different values.

---

### Q2. Which keyword is recommended for loops?

```yaml
loop
```

---

### Q3. Which keyword performs conditional execution?

```yaml
when
```

---

### Q4. What is `failed_when` used for?

It allows you to define custom failure conditions for a task.

---

### Q5. What does `changed_when` do?

It controls whether Ansible reports a task as changed.

---

### Q6. What is the purpose of `until`?

It retries a task until a specified condition becomes true or the retry limit is reached.

---

# Production Best Practices

✔ Use `loop` instead of duplicate tasks.

✔ Keep conditions simple and readable.

✔ Store loop values in variables.

✔ Use `failed_when` for custom validation.

✔ Use `changed_when` for read-only tasks.

✔ Configure reasonable retry values.

✔ Test conditional logic in staging.

✔ Document complex conditions.

---

# Key Takeaways

- Loops eliminate repetitive tasks.
- `loop` is the preferred looping mechanism in modern Ansible.
- `when` enables conditional task execution.
- `failed_when` and `changed_when` provide fine-grained task control.
- Combining loops and conditionals creates flexible, production-ready Playbooks.

---

# Next Section

## 12.10 Handlers

In the next section, we will learn:

- What are Handlers?
- notify
- Handler Execution
- Service Restart
- Multiple Notifications
- Handler Best Practices
- Real-World Examples
- Production Best Practices
- Hands-on Labs
---

# 12.10 Handlers

Imagine you update the Nginx configuration file.

Should Ansible restart the Nginx service every time the Playbook runs?

Consider this scenario:

```
Playbook Run

↓

Configuration Not Changed

↓

Restart Nginx

↓

Unnecessary Restart
```

This creates unnecessary downtime.

Instead,

Ansible should restart the service **only when something has actually changed**.

This is exactly what **Handlers** are designed for.

---

# What are Handlers?

Handlers are special Ansible tasks that execute **only when notified by another task**.

They are commonly used for:

- Restarting Services
- Reloading Services
- Rebooting Servers
- Restarting Applications
- Refreshing Configurations

---

# Simple Definition

```
Task Changed

↓

Notify Handler

↓

Handler Executes
```

If nothing changes,

the Handler does **not** run.

---

# Why Handlers?

Without Handlers

```
Copy File

↓

Restart Service

↓

Every Time
```

---

With Handlers

```
Copy File

↓

File Changed?

↓

YES

↓

Restart Service

----------------

NO

↓

Skip Restart
```

---

# Handler Workflow

```
Task

↓

Changed?

↓

Notify

↓

Handler

↓

Restart Service
```

---

# Basic Handler Example

```yaml
- hosts: web

  become: true

  tasks:

    - name: Copy nginx config

      copy:

        src: nginx.conf

        dest: /etc/nginx/nginx.conf

      notify:

        - Restart Nginx

  handlers:

    - name: Restart Nginx

      service:

        name: nginx

        state: restarted
```

---

# Understanding the Flow

```
Copy File

↓

Changed?

↓

Notify Handler

↓

Restart Nginx
```

---

# If File Doesn't Change

```
Copy File

↓

No Changes

↓

No Notification

↓

No Restart
```

This makes Playbooks more efficient.

---

# notify

The keyword

```yaml
notify:
```

tells Ansible which Handler should execute.

Example

```yaml
notify:

  - Restart Apache
```

---

# handlers

Handlers are defined at the end of the Play.

Example

```yaml
handlers:

  - name: Restart Apache

    service:

      name: httpd

      state: restarted
```

---

# Multiple Notifications

A task can notify multiple Handlers.

```yaml
notify:

  - Restart Nginx

  - Reload Firewall
```

Both Handlers execute if the task changes.

---

# Multiple Tasks → One Handler

Example

```yaml
Task 1

↓

Notify

↓

Restart Nginx

----------------

Task 2

↓

Notify

↓

Restart Nginx
```

Even if both tasks notify the same Handler,

it runs **only once** at the end of the Play.

---

# Handler Execution Timing

Handlers execute **after all normal tasks complete**.

```
Task 1

↓

Task 2

↓

Task 3

↓

Handler
```

---

# Example

```yaml
tasks:

  - copy:

      src: app.conf

      dest: /etc/app.conf

    notify:

      - Restart App

handlers:

  - name: Restart App

    service:

      name: app

      state: restarted
```

---

# Reload Instead of Restart

Some services support reload.

Example

```yaml
handlers:

  - name: Reload Nginx

    service:

      name: nginx

      state: reloaded
```

Reloading usually avoids downtime.

---

# Handler with Template

```yaml
- name: Deploy configuration

  template:

    src: nginx.j2

    dest: /etc/nginx/nginx.conf

  notify:

    - Restart Nginx
```

If the rendered template changes,

the Handler executes.

---

# Handler with Lineinfile

```yaml
- lineinfile:

    path: /etc/ssh/sshd_config

    line: "PermitRootLogin no"

  notify:

    - Restart SSH
```

---

# Handler with Multiple Services

```yaml
handlers:

  - name: Restart Nginx

    service:

      name: nginx

      state: restarted

  - name: Restart PHP

    service:

      name: php-fpm

      state: restarted
```

---

# Force Handler Execution

Normally,

Handlers execute at the end.

To force execution immediately:

```yaml
- meta: flush_handlers
```

Workflow

```
Task

↓

Notify

↓

flush_handlers

↓

Handler Executes Immediately
```

---

# Handler Execution Example

```
Task 1

↓

Notify

↓

Task 2

↓

Task 3

↓

Handler Runs Once
```

---

# Real-World Example

A company updates:

```
Nginx Config

↓

Changed?

↓

Restart Nginx

↓

Website Updated
```

If there are no changes,

the web server continues running without interruption.

---

# Enterprise Example

```
Git

↓

Jenkins

↓

Ansible

↓

Deploy Config

↓

Notify

↓

Restart Service

↓

Production Updated
```

Efficient deployments reduce downtime.

---

# Handler Best Practices

✔ Restart services only when required.

✔ Prefer reload over restart if supported.

✔ Use meaningful Handler names.

✔ Keep Handlers at the end of the Playbook.

✔ Reuse Handlers across multiple tasks.

---

# Common Beginner Mistakes

### Mistake 1

Restarting services after every task.

Use Handlers instead.

---

### Mistake 2

Using different Handler names for the same service.

Reuse one Handler.

---

### Mistake 3

Restarting instead of reloading.

Reload is often sufficient.

---

### Mistake 4

Forgetting `notify`.

Without `notify`,

Handlers never execute.

---

### Mistake 5

Using shell commands instead of the `service` module.

Prefer native Ansible modules.

---

# Interview Questions

### Q1. What is a Handler?

A Handler is a special task that executes only when notified by another task.

---

### Q2. Which keyword triggers a Handler?

```yaml
notify
```

---

### Q3. When are Handlers executed?

By default,

after all normal tasks in the Play have completed.

---

### Q4. What is the purpose of `meta: flush_handlers`?

It forces pending Handlers to execute immediately.

---

### Q5. Can multiple tasks notify the same Handler?

Yes.

The Handler still runs only once at the end of the Play.

---

### Q6. Why are Handlers important?

They prevent unnecessary service restarts and improve deployment efficiency.

---

# Production Best Practices

✔ Use Handlers for service restarts.

✔ Prefer service reloads when available.

✔ Avoid duplicate Handlers.

✔ Use `flush_handlers` only when necessary.

✔ Keep Handler logic simple.

✔ Test service restarts in staging.

✔ Use built-in modules instead of shell commands.

✔ Document Handler behavior.

---

# Key Takeaways

- Handlers execute only when notified.
- They help avoid unnecessary service restarts.
- Multiple tasks can notify the same Handler.
- Handlers normally execute after all tasks complete.
- Proper use of Handlers improves reliability and reduces downtime.

---

# Next Section

## 12.11 Templates (Jinja2)

In the next section, we will learn:

- What are Templates?
- Jinja2 Basics
- Variables in Templates
- Loops
- Conditions
- Filters
- Dynamic Configuration Files
- Real-World Examples
- Production Best Practices
- Hands-on Labs
---

# 12.11 Templates (Jinja2)

Imagine your company has:

- 100 Web Servers
- 20 Database Servers
- 10 Cache Servers

Each server requires a different configuration.

For example,

```
Server 1

↓

server_name = web01.company.com

----------------

Server 2

↓

server_name = web02.company.com

----------------

Server 3

↓

server_name = web03.company.com
```

Will you create **100 different configuration files?**

**No.**

Instead,

Ansible uses **Jinja2 Templates** to generate configuration files dynamically.

---

# What are Templates?

Templates are configuration files containing variables and logic.

During Playbook execution,

Ansible replaces variables with actual values and generates the final configuration file.

---

# Simple Definition

```
Template

↓

Variables

↓

Rendered File

↓

Server
```

---

# Why Templates?

Without Templates

```
100 Servers

↓

100 Config Files
```

---

With Templates

```
1 Template

↓

100 Variables

↓

100 Generated Files
```

One template can serve hundreds of servers.

---

# What is Jinja2?

Jinja2 is a Python-based templating engine used by Ansible.

It allows:

- Variables
- Loops
- Conditions
- Filters
- Expressions

inside configuration files.

---

# Template Workflow

```
Template (.j2)

↓

Variables

↓

Jinja2 Engine

↓

Rendered File

↓

Target Server
```

---

# Template File Extension

Templates usually end with:

```
.j2
```

Examples

```
nginx.conf.j2

index.html.j2

hosts.j2
```

---

# Example Template

```text
server {

    listen {{ http_port }};

    server_name {{ server_name }};

}
```

---

# Variables

Playbook

```yaml
vars:

  http_port: 80

  server_name: example.com
```

Template

```text
listen {{ http_port }};

server_name {{ server_name }};
```

Rendered Output

```text
listen 80;

server_name example.com;
```

---

# Template Module

Templates are deployed using:

```yaml
template:
```

Example

```yaml
- name: Deploy nginx config

  template:

    src: nginx.conf.j2

    dest: /etc/nginx/nginx.conf
```

---

# Template Directory

Project Structure

```
roles/

└── web/

    ├── templates/

    │     nginx.conf.j2

    ├── tasks/

    └── handlers/
```

Templates are usually stored inside the **templates/** directory.

---

# If Statement

Example

```text
{% if ssl_enabled %}

listen 443 ssl;

{% endif %}
```

If

```
ssl_enabled = true
```

Output

```text
listen 443 ssl;
```

Otherwise,

nothing is generated.

---

# If Else

```text
{% if environment == "production" %}

Production

{% else %}

Development

{% endif %}
```

---

# For Loop

Example

```text
{% for server in servers %}

server {{ server }}

{% endfor %}
```

Variables

```yaml
servers:

  - web01

  - web02

  - web03
```

Output

```text
server web01

server web02

server web03
```

---

# Loop Workflow

```
List

↓

Loop

↓

Render

↓

Configuration
```

---

# Comments

Template comments

```text
{# This is a comment #}
```

Comments are not included in the rendered file.

---

# Filters

Jinja2 provides filters.

Example

```text
{{ hostname | upper }}
```

Output

```
WEB01
```

Lowercase

```text
{{ hostname | lower }}
```

Title Case

```text
{{ hostname | title }}
```

---

# Default Values

```text
{{ port | default(80) }}
```

If

```
port
```

doesn't exist,

80 is used.

---

# Length Filter

```text
{{ servers | length }}
```

Returns

```
3
```

---

# Join Filter

Variables

```yaml
packages:

  - git

  - curl

  - wget
```

Template

```text
{{ packages | join(", ") }}
```

Output

```
git, curl, wget
```

---

# Date Example

```text
Generated on:

{{ ansible_date_time.date }}
```

Useful for generated configuration headers.

---

# Using Facts

Template

```text
Hostname:

{{ ansible_hostname }}
```

Output

```
Hostname:

web01
```

---

# Using Inventory Variables

Inventory

```ini
web01

http_port=8080
```

Template

```text
listen {{ http_port }};
```

Output

```text
listen 8080;
```

---

# Dynamic Nginx Example

Template

```text
server {

listen {{ port }};

server_name {{ server_name }};

root {{ document_root }};

}
```

Variables

```yaml
port: 80

server_name: devops.com

document_root: /var/www/html
```

Final Output

```text
server {

listen 80;

server_name devops.com;

root /var/www/html;

}
```

---

# Template + Handler

```yaml
- template:

    src: nginx.conf.j2

    dest: /etc/nginx/nginx.conf

  notify:

    - Restart Nginx
```

If the rendered file changes,

the Handler restarts Nginx.

---

# Enterprise Example

A company manages:

```
500 Servers

↓

One Template

↓

Inventory Variables

↓

Generated Configurations

↓

Deployment
```

No duplicate configuration files are required.

---

# Advantages

✔ Dynamic Configuration

✔ Reusable

✔ Easy Maintenance

✔ Supports Variables

✔ Supports Loops

✔ Supports Conditions

✔ Production Ready

✔ Works with Handlers

---

# Common Beginner Mistakes

### Mistake 1

Using the `copy` module instead of `template`.

If variables are required,

use `template`.

---

### Mistake 2

Forgetting `.j2` extension.

Use meaningful template filenames.

---

### Mistake 3

Hardcoding values.

Always use variables.

---

### Mistake 4

Incorrect Jinja2 syntax.

Remember:

```
{{ }}

{% %}

{# #}
```

---

### Mistake 5

Not testing rendered output.

Always verify generated configuration files.

---

# Interview Questions

### Q1. What is a Template?

A Template is a configuration file containing variables and Jinja2 expressions that Ansible renders before deployment.

---

### Q2. Which module deploys Templates?

```yaml
template
```

---

### Q3. What is the default extension for Template files?

```
.j2
```

---

### Q4. Which syntax prints variables?

```text
{{ variable }}
```

---

### Q5. Which syntax is used for conditions and loops?

```text
{% %}
```

---

### Q6. Why are Templates preferred over static configuration files?

Because one Template can dynamically generate different configurations for many servers using variables.

---

# Production Best Practices

✔ Store Templates inside the `templates/` directory.

✔ Keep Templates generic.

✔ Use variables instead of hardcoded values.

✔ Validate generated configuration files.

✔ Use Handlers to restart services only when Templates change.

✔ Reuse Templates across environments.

✔ Store Templates in Git.

✔ Test rendering before production deployment.

---

# Key Takeaways

- Templates generate dynamic configuration files.
- Ansible uses the Jinja2 templating engine.
- Templates support variables, loops, conditions and filters.
- The `template` module renders and deploys Templates.
- Jinja2 Templates eliminate duplicate configuration files and simplify large-scale infrastructure management.

---

# Next Section

## 12.12 Roles

In the next section, we will learn:

- What are Roles?
- Why Roles?
- Standard Role Directory Structure
- tasks/
- handlers/
- templates/
- files/
- vars/
- defaults/
- meta/
- Reusing Roles
- Ansible Galaxy
- Production Best Practices
- Hands-on Labs
---

# 12.12 Roles

As your Ansible projects grow,

Playbooks also become larger.

Imagine a Playbook that:

- Installs Nginx
- Configures Nginx
- Creates Users
- Installs Docker
- Configures Firewall
- Deploys Applications
- Configures Monitoring

Eventually,

the Playbook becomes hundreds or even thousands of lines long.

Managing such Playbooks becomes difficult.

To solve this problem,

Ansible provides **Roles**.

Roles organize automation into reusable components.

---

# What are Roles?

A Role is a predefined directory structure used to organize Ansible code.

Instead of storing everything inside one Playbook,

Roles separate:

- Tasks
- Variables
- Handlers
- Templates
- Files
- Defaults
- Metadata

Each Role performs one specific responsibility.

---

# Simple Definition

```
Playbook

↓

Role

↓

Reusable Automation
```

---

# Why Roles?

Without Roles

```
Huge Playbook

↓

Thousands of Lines

↓

Difficult Maintenance
```

---

With Roles

```
Playbook

↓

Web Role

↓

Database Role

↓

Monitoring Role

↓

Docker Role
```

Each Role handles one responsibility.

---

# Real-World Example

Suppose a company deploys a web application.

Instead of writing everything inside one Playbook,

they create:

```
roles/

├── nginx/

├── mysql/

├── docker/

├── monitoring/

└── users/
```

Every project can reuse these Roles.

---

# Role Architecture

```
Playbook

↓

Role

↓

Tasks

↓

Handlers

↓

Templates

↓

Files

↓

Variables
```

---

# Standard Role Structure

A typical Role looks like:

```text
roles/

└── nginx/

    ├── defaults/

    │     main.yml

    │

    ├── files/

    │

    ├── handlers/

    │     main.yml

    │

    ├── meta/

    │     main.yml

    │

    ├── tasks/

    │     main.yml

    │

    ├── templates/

    │

    ├── tests/

    │

    ├── vars/

    │     main.yml

    │

    └── README.md
```

Every directory has a specific purpose.

---

# tasks/

The **tasks/** directory contains automation tasks.

Example

```text
tasks/

└── main.yml
```

Example

```yaml
- name: Install nginx

  package:

    name: nginx

    state: present
```

---

# handlers/

Stores Handlers.

Example

```yaml
- name: Restart nginx

  service:

    name: nginx

    state: restarted
```

---

# files/

Contains static files.

Examples

```
index.html

logo.png

backup.sh

application.jar
```

These files are copied exactly as they are.

---

# templates/

Stores Jinja2 Templates.

Examples

```
nginx.conf.j2

httpd.conf.j2

index.html.j2
```

Templates generate dynamic configuration files.

---

# vars/

Contains variables with relatively high precedence.

Example

```yaml
package_name: nginx

service_name: nginx
```

---

# defaults/

Contains default values.

Example

```yaml
package_name: nginx

http_port: 80
```

These values can easily be overridden.

---

# meta/

Stores metadata.

Example

```yaml
dependencies:

  - role: common

  - role: firewall
```

A Role can automatically depend on another Role.

---

# tests/

Used to test Roles.

Typical contents:

```
inventory

test.yml
```

Useful during development.

---

# Creating a Role

Automatically create a Role.

```bash
ansible-galaxy init nginx
```

Generated Structure

```
roles/

└── nginx/
```

All standard directories are created automatically.

---

# Using a Role

Example

```yaml
- hosts: web

  become: true

  roles:

    - nginx
```

That's all.

The Playbook automatically executes:

```
roles/nginx/tasks/main.yml
```

---

# Multiple Roles

```yaml
roles:

  - common

  - docker

  - nginx

  - monitoring
```

Execution order:

```
Common

↓

Docker

↓

Nginx

↓

Monitoring
```

---

# Role Variables

Variables can be passed.

Example

```yaml
roles:

  - role: nginx

    vars:

      http_port: 8080
```

Now the Role uses port **8080**.

---

# Role Dependencies

Role

```
Application
```

depends on

```
Docker
```

Meta

```yaml
dependencies:

  - docker
```

Docker executes first.

---

# Role Reusability

Suppose your company has:

```
Project A

↓

Uses nginx Role

----------------

Project B

↓

Uses nginx Role

----------------

Project C

↓

Uses nginx Role
```

One Role serves multiple projects.

---

# Enterprise Project Structure

```
ansible/

├── inventory/

├── playbooks/

├── roles/

│   ├── common/

│   ├── docker/

│   ├── nginx/

│   ├── mysql/

│   ├── monitoring/

│   └── security/

├── group_vars/

├── host_vars/

└── ansible.cfg
```

This is a common production layout.

---

# Role Execution Flow

```
Playbook

↓

Role

↓

tasks/main.yml

↓

Modules

↓

Managed Hosts
```

---

# Advantages

✔ Modular

✔ Reusable

✔ Easy Maintenance

✔ Team Collaboration

✔ Scalable

✔ Production Ready

✔ Version Controlled

✔ Standard Directory Structure

---

# Role vs Playbook

| Playbook | Role |
|----------|------|
| Executes Automation | Organizes Automation |
| Can Use Roles | Cannot Run Alone |
| Small or Large | Reusable Component |
| Calls Tasks | Contains Tasks |

---

# Enterprise Example

Company Infrastructure

```
GitHub

↓

Jenkins

↓

Playbook

↓

Roles

↓

500 Servers

↓

Deployment Complete
```

Developers maintain Roles independently.

---

# Common Beginner Mistakes

### Mistake 1

Putting everything inside one Playbook.

Break automation into Roles.

---

### Mistake 2

Keeping templates outside the templates directory.

Follow the standard directory structure.

---

### Mistake 3

Hardcoding variables.

Store values inside defaults or vars.

---

### Mistake 4

Duplicating code.

Reuse Roles whenever possible.

---

### Mistake 5

Ignoring dependencies.

Use the **meta/** directory for dependent Roles.

---

# Interview Questions

### Q1. What is an Ansible Role?

A Role is a standardized directory structure that organizes reusable Ansible automation.

---

### Q2. Which command creates a new Role?

```bash
ansible-galaxy init <role_name>
```

---

### Q3. Which directory stores Templates?

```
templates/
```

---

### Q4. Which directory stores Handlers?

```
handlers/
```

---

### Q5. What is the purpose of defaults/?

It stores default variable values that can be overridden.

---

### Q6. Why are Roles important?

Roles improve modularity, reusability and maintainability in large Ansible projects.

---

# Production Best Practices

✔ Keep one responsibility per Role.

✔ Use meaningful Role names.

✔ Store reusable variables in defaults/.

✔ Keep templates inside templates/.

✔ Use Handlers inside handlers/.

✔ Version-control Roles with Git.

✔ Test Roles independently.

✔ Document every Role.

---

# Key Takeaways

- Roles organize Ansible automation into reusable components.
- Each Role follows a standard directory structure.
- Roles improve scalability and maintainability.
- One Playbook can execute multiple Roles.
- Large production environments rely heavily on Roles for clean automation.

---

# Next Section

## 12.13 Ansible Galaxy

In the next section, we will learn:

- What is Ansible Galaxy?
- Installing Roles
- Installing Collections
- Publishing Roles
- Requirements Files
- Version Management
- Private Galaxy Servers
- Production Best Practices
- Hands-on Labs
