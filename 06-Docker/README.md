# Chapter 6 – Docker

---

# Chapter Overview

Welcome to **Chapter 6**.

After learning Linux, Networking, Git, AWS, and Nginx,

it's time to learn one of the most important technologies in modern DevOps—

# Docker

Today almost every company uses Docker.

Companies including:

- Google
- Microsoft
- Amazon
- Netflix
- Adobe
- Spotify
- Uber
- PayPal

use containers in production.

Docker completely changed how software is built, tested and deployed.

---

# Learning Objectives

After completing this chapter you will be able to:

- Understand Containers
- Understand Docker
- Install Docker
- Run Containers
- Build Images
- Create Dockerfiles
- Manage Images
- Manage Containers
- Configure Networking
- Use Volumes
- Use Docker Compose
- Push Images to Docker Hub
- Deploy Multi-Container Applications
- Understand Docker in Production
- Answer Docker Interview Questions

---

# Chapter Roadmap

This chapter contains the following sections.

```
6.1 Introduction to Docker

6.2 Why Docker?

6.3 Virtual Machines vs Containers

6.4 Docker Architecture

6.5 Installing Docker

6.6 Docker Images

6.7 Docker Containers

6.8 Basic Docker Commands

6.9 Dockerfile

6.10 Building Images

6.11 Docker Volumes

6.12 Docker Networking

6.13 Docker Compose

6.14 Docker Hub

6.15 Multi-Container Applications

6.16 Docker Logs & Monitoring

6.17 Docker Security

6.18 Docker Best Practices

6.19 Docker in Production

6.20 Chapter Summary
```

---

# Prerequisites

Before learning Docker,

you should know:

- Linux Commands
- File Permissions
- Networking Basics
- Basic Nginx
- SSH
- Package Installation

If you completed previous chapters,

you are ready.

---

# Lab Environment

We will perform all practicals on:

- Ubuntu 24.04 LTS
- Rocky Linux 9
- Amazon Linux 2023

Cloud Platform

- AWS EC2

Docker Version

- Latest Stable Release

---

# Learning Approach

This chapter focuses on:

```
Theory

↓

Visualization

↓

Practical

↓

Production Example

↓

Interview Questions

↓

Hands-On Lab
```

Every topic will first explain the concept,

then demonstrate it with commands,

followed by production use cases.

---

# Real DevOps Scenario

Suppose a developer says:

> "My application works on my laptop but not on the production server."

Docker solves this common problem by packaging the application together with its dependencies into a container.

The same container can run consistently across development, testing and production environments.

---

# What You Will Build

During this chapter,

you will build:

- Docker Images
- Docker Containers
- Docker Networks
- Docker Volumes
- Multi-Container Applications
- Docker Compose Projects

By the end,

you will be able to deploy a complete application using Docker.

---

# Production Focus

Every section includes:

✔ Real-world Examples

✔ Production Architecture

✔ Troubleshooting

✔ Best Practices

✔ Interview Questions

✔ Common Mistakes

---

# Next Section

## 6.1 Introduction to Docker

In the next section, we will learn:

- What is Docker?
- History of Docker
- Why Docker was Created
- Container Technology
- Docker Ecosystem
- Real Production Examples
- Interview Questions
---

# 6.1 Introduction to Docker

Before learning Docker commands,

you must first understand **what Docker actually is** and **why it became one of the biggest revolutions in software development.**

Today,

Docker is one of the most widely used tools in DevOps, Cloud Computing and Microservices.

Nearly every modern company uses Docker in some form.

---

# What is Docker?

Docker is an **open-source containerization platform** that allows developers to package an application along with everything it needs to run.

This includes:

- Application Code
- Runtime
- Libraries
- Dependencies
- Configuration Files
- Environment Variables

These are packaged into a single unit called a **Container**.

---

# Simple Definition

Docker allows developers to

> **Build Once, Run Anywhere**

Whether your application runs on

- Windows
- Linux
- AWS
- Azure
- Google Cloud
- Kubernetes

Docker ensures consistent behavior.

---

# Official Definition

Docker is a platform used to:

- Build Applications
- Package Applications
- Ship Applications
- Run Applications

inside lightweight containers.

---

# Why is Docker Needed?

Before Docker,

developers commonly faced problems like:

```
Works on My Laptop

↓

Fails on Testing Server

↓

Fails on Production Server
```

Reasons included:

- Different Operating Systems
- Different Software Versions
- Missing Libraries
- Missing Dependencies
- Incorrect Configurations

Docker packages everything together,

making deployments predictable.

---

# Real Life Analogy

Imagine moving to another city.

Without Docker

```
TV

↓

Bed

↓

Chair

↓

Table

↓

Kitchen Items

↓

Move Separately
```

Many items may be forgotten.

With Docker

```
Everything

↓

Packed Inside One Container

↓

Move

↓

Everything Works
```

Docker containers package everything needed together.

---

# Docker Solves Dependency Problems

Suppose an application needs:

```
Java 21

↓

Maven

↓

Spring Boot

↓

Redis Client

↓

Configuration Files
```

Instead of installing each dependency manually,

Docker packages everything inside one image.

---

# What is Containerization?

Containerization is the process of packaging an application together with all of its dependencies into an isolated environment called a **Container**.

Unlike Virtual Machines,

containers share the host operating system kernel,

making them lightweight.

---

# Container Concept

```
Application

↓

Dependencies

↓

Libraries

↓

Configuration

↓

Docker Image

↓

Docker Container
```

Everything required to run the application is included.

---

# Docker Workflow

```
Developer

↓

Dockerfile

↓

Docker Image

↓

Docker Container

↓

Application Running
```

This is the basic Docker lifecycle.

---

# Key Components

Docker consists of several important components.

```
Docker

│

├── Docker Engine

├── Docker Image

├── Docker Container

├── Docker Registry

├── Docker Volume

└── Docker Network
```

Each component will be covered in detail later.

---

# Docker Ecosystem

```
Developer

↓

Dockerfile

↓

Docker Image

↓

Docker Hub

↓

Docker Host

↓

Running Container
```

This ecosystem enables easy sharing and deployment of applications.

---

# Docker in DevOps

Docker plays a central role in modern DevOps workflows.

```
Developer

↓

Git

↓

CI/CD

↓

Docker Build

↓

Docker Registry

↓

Deployment

↓

Production
```

It provides consistency across all environments.

---

# Docker in Cloud

Cloud providers fully support Docker.

Examples include:

- AWS
- Microsoft Azure
- Google Cloud Platform

Docker images can be deployed consistently across these platforms.

---

# Companies Using Docker

Many well-known organizations use Docker.

Examples:

- Netflix
- Spotify
- Uber
- PayPal
- Adobe
- Shopify
- Pinterest
- eBay

Docker is widely adopted for modern application deployment.

---

# Benefits of Docker

✔ Lightweight

✔ Fast Startup

✔ Portable

✔ Easy Deployment

✔ Easy Scaling

✔ Isolation

✔ Resource Efficient

✔ Developer Friendly

✔ CI/CD Integration

✔ Cloud Ready

---

# Docker vs Traditional Deployment

Traditional Deployment

```
Install OS

↓

Install Java

↓

Install Libraries

↓

Install Dependencies

↓

Configure

↓

Run Application
```

Docker Deployment

```
Pull Image

↓

Run Container

↓

Application Ready
```

Docker greatly simplifies deployment.

---

# Real Production Example

Suppose an e-commerce company has:

- Website
- API
- Database
- Redis
- Payment Service

Instead of installing everything manually,

each component runs in its own Docker container.

```
Users

↓

Nginx

↓

Docker Containers

├── Website

├── API

├── Redis

├── Worker

└── Monitoring
```

This architecture is common in production.

---

# Docker Advantages

Docker provides:

- Consistent Environments
- Easy Rollback
- Faster Deployment
- Better Resource Utilization
- Easy Automation
- Simple Scaling
- Improved Developer Productivity

---

# Docker Limitations

Docker is powerful,

but it is not a complete replacement for Virtual Machines.

Some limitations include:

- Containers share the host kernel.
- Strong isolation requirements may still require Virtual Machines.
- Misconfigured containers can introduce security risks.

Understanding these trade-offs is important for production use.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Docker is a Virtual Machine.

Docker uses containers,

not full virtual machines.

---

### Mistake 2

Believing Docker replaces Linux.

Docker runs on top of the operating system.

---

### Mistake 3

Thinking Docker only works for developers.

Operations teams,

DevOps Engineers,

Cloud Engineers,

and SREs also use Docker extensively.

---

### Mistake 4

Installing applications directly inside production servers instead of using containers.

Containers provide better consistency and easier deployments.

---

# Interview Questions

### Q1. What is Docker?

Docker is an open-source containerization platform used to build, package and run applications inside lightweight containers.

---

### Q2. What problem does Docker solve?

Docker eliminates environment inconsistencies by packaging applications together with all required dependencies.

---

### Q3. What is Containerization?

Containerization is the process of packaging an application and all its dependencies into an isolated container.

---

### Q4. Name four major Docker components.

- Docker Engine
- Docker Image
- Docker Container
- Docker Registry

---

### Q5. Why is Docker popular in DevOps?

Because it provides consistent deployments, portability, fast startup, automation support and seamless CI/CD integration.

---

# Production Best Practices

✔ Build immutable Docker images.

✔ Keep containers lightweight.

✔ Use official base images whenever possible.

✔ Version Docker images.

✔ Store images in a trusted registry.

✔ Scan images for vulnerabilities.

✔ Keep Docker updated.

✔ Follow the principle of one process per container where practical.

---

# Key Takeaways

- Docker is a containerization platform.
- It packages applications with all required dependencies.
- Containers provide consistency across environments.
- Docker simplifies application deployment and scaling.
- Docker is a foundational technology for modern DevOps.

---

# Next Section

## 6.2 Why Docker?

In the next section, we will learn:

- Problems Before Docker
- Traditional Deployment Challenges
- Dependency Hell
- Environment Consistency
- Docker Advantages
- Real Production Scenarios
- Why Companies Adopt Docker
- Interview Questions
---

# 6.2 Why Docker?

Docker became popular because it solved one of the biggest problems in software development:

> **"It works on my machine, but it doesn't work on yours."**

Before Docker,

developers, testers and system administrators often struggled because every environment was different.

Docker introduced a standardized way to package and run applications,

making deployments far more predictable.

---

# Problems Before Docker

Before Docker,

every server had to be configured manually.

Typical installation process

```
Install Linux

↓

Install Java

↓

Install Python

↓

Install Node.js

↓

Install Database

↓

Install Libraries

↓

Configure Everything

↓

Deploy Application
```

Every server required repeating the same steps.

---

# Environment Differences

Imagine three environments.

```
Developer Laptop

↓

Java 17

↓

Ubuntu 24

------------------------

Testing Server

↓

Java 21

↓

Ubuntu 22

------------------------

Production

↓

Java 21

↓

Rocky Linux
```

Even small differences could cause applications to behave unexpectedly.

---

# Dependency Hell

Suppose Application A requires

```
Python 3.10
```

while Application B requires

```
Python 3.12
```

Installing both applications on the same server may create dependency conflicts.

This situation is commonly called

```
Dependency Hell
```

---

# Configuration Drift

Over time,

servers are updated manually.

Example

```
Server-1

↓

Package Updated

------------------------

Server-2

↓

Package Not Updated
```

Eventually,

servers become inconsistent.

This is known as **Configuration Drift**.

Docker helps reduce this problem by packaging the application and its dependencies together.

---

# Slow Deployment

Traditional deployments often required:

- Installing packages
- Configuring services
- Updating libraries
- Restarting services
- Manual verification

This could take considerable time.

Docker simplifies deployment by running a pre-built image.

---

# Difficult Rollback

Suppose Version 2 fails.

Traditional deployment

```
Version 1

↓

Upgrade

↓

Version 2

↓

Failure
```

Rolling back often required restoring backups or reinstalling software.

With Docker,

rollback is usually much simpler.

```
Stop Container

↓

Run Previous Image

↓

Application Restored
```

---

# Resource Consumption

Traditional deployment often used Virtual Machines.

```
Application

↓

Operating System

↓

Hypervisor

↓

Hardware
```

Each VM requires its own operating system,

increasing resource usage.

Docker containers share the host kernel,

making them much lighter.

---

# Scaling Challenges

Suppose traffic increases suddenly.

Traditional deployment

```
Order Server

↓

Install Software

↓

Configure

↓

Deploy
```

Docker

```
Run New Container

↓

Ready
```

Scaling becomes much faster.

---

# Why Companies Adopt Docker

Organizations choose Docker because it provides:

✔ Faster Deployment

✔ Consistent Environments

✔ Easier Scaling

✔ Better Resource Utilization

✔ Simpler Rollbacks

✔ Improved CI/CD Integration

✔ Cloud Compatibility

---

# Build Once, Run Anywhere

Docker's biggest advantage is portability.

```
Developer

↓

Docker Image

↓

Testing

↓

Staging

↓

Production

↓

Cloud
```

The same image is used everywhere.

---

# Faster Developer Onboarding

A new developer joins the team.

Without Docker

```
Install Software

↓

Configure

↓

Fix Errors

↓

Wait
```

With Docker

```
Clone Repository

↓

docker compose up

↓

Start Working
```

Setup time is dramatically reduced.

---

# Consistency Across Teams

Everyone runs the same container image.

```
Developer A

↓

Docker Image

--------------------

Developer B

↓

Docker Image

--------------------

Production

↓

Docker Image
```

The application behaves consistently across environments.

---

# Docker in CI/CD

Docker integrates naturally with Continuous Integration and Continuous Deployment.

```
Git Push

↓

CI Pipeline

↓

Build Docker Image

↓

Run Tests

↓

Push Image

↓

Deploy
```

Automation becomes simpler and more reliable.

---

# Cloud-Native Applications

Modern cloud platforms are designed to run containers.

```
Docker Image

↓

Kubernetes

↓

AWS

↓

Azure

↓

Google Cloud
```

Containers can be scheduled and scaled automatically.

---

# Microservices

Suppose an application consists of:

- Authentication Service
- User Service
- Payment Service
- Notification Service

Each service can run in its own Docker container.

```
Users

↓

API Gateway

↓

Authentication

↓

Users

↓

Payments

↓

Notifications
```

Independent deployment becomes possible.

---

# Better Isolation

Each container has:

- Its own filesystem
- Its own processes
- Its own network namespace
- Its own environment variables

Applications are isolated from one another,

reducing conflicts.

---

# Simplified Upgrades

Instead of modifying a running server,

Docker encourages replacing containers with new image versions.

```
Old Container

↓

Stop

↓

New Container

↓

Running
```

This approach reduces configuration drift.

---

# Production Example

An online shopping platform runs:

```
Nginx

↓

Docker

├── Frontend

├── API

├── Redis

├── Worker

└── Notification Service
```

Each service can be updated independently.

---

# Traditional Deployment vs Docker

| Traditional Deployment | Docker Deployment |
|-------------------------|-------------------|
| Manual Installation | Image-Based Deployment |
| Environment Differences | Consistent Environment |
| Slow Rollback | Fast Rollback |
| Dependency Conflicts | Isolated Dependencies |
| Higher Resource Usage | Lightweight Containers |
| Slower Scaling | Faster Scaling |

---

# Common Beginner Mistakes

### Mistake 1

Assuming Docker automatically fixes application bugs.

Docker packages applications consistently,

but it does not correct application logic errors.

---

### Mistake 2

Thinking Docker removes the need for testing.

Applications should still be thoroughly tested before deployment.

---

### Mistake 3

Believing Docker replaces all infrastructure management.

Servers, networking, storage and security still require proper administration.

---

### Mistake 4

Running multiple unrelated applications inside one container.

Containers are generally easier to manage when focused on a single primary process.

---

# Interview Questions

### Q1. Why was Docker created?

Docker was created to solve environment inconsistency and dependency management problems while simplifying application deployment.

---

### Q2. What is Dependency Hell?

Dependency Hell occurs when applications require conflicting versions of libraries or software.

---

### Q3. What is Configuration Drift?

Configuration Drift is the gradual difference between systems caused by manual updates or inconsistent changes.

---

### Q4. Why is Docker useful in CI/CD?

Docker provides consistent build artifacts that can be tested and deployed across multiple environments.

---

### Q5. Name five benefits of Docker.

- Consistency
- Portability
- Faster Deployment
- Lightweight Containers
- Easy Scaling

---

# Production Best Practices

✔ Build immutable Docker images.

✔ Version images properly.

✔ Keep containers small.

✔ Automate builds using CI/CD.

✔ Avoid manual changes inside running containers.

✔ Store images in trusted registries.

✔ Scan images for vulnerabilities.

✔ Document image versions and deployment procedures.

---

# Key Takeaways

- Docker solves environment consistency problems.
- It eliminates many dependency conflicts.
- Containers simplify deployment, scaling and rollback.
- Docker integrates naturally with CI/CD and cloud platforms.
- Docker has become a standard technology for modern software delivery.

---

# Next Section

## 6.3 Virtual Machines vs Containers

In the next section, we will learn:

- What is a Virtual Machine?
- What is a Container?
- Architecture Comparison
- Performance Comparison
- Resource Usage
- Startup Time
- Security Differences
- Production Use Cases
- Interview Questions
---

# 6.3 Virtual Machines vs Containers

One of the most common Docker interview questions is:

> **What is the difference between a Virtual Machine and a Container?**

Many beginners think Docker containers are simply "lightweight Virtual Machines."

This is **not correct**.

Although both Virtual Machines and Containers isolate applications,

they work in very different ways.

Understanding this difference is essential for every DevOps Engineer.

---

# What is a Virtual Machine?

A Virtual Machine (VM) is a complete computer running inside another computer.

Each VM contains:

- Guest Operating System
- Kernel
- Libraries
- Application
- Dependencies

A Hypervisor manages multiple Virtual Machines.

---

# Virtual Machine Architecture

```
Application

↓

Libraries

↓

Guest OS

↓

Hypervisor

↓

Host OS

↓

Physical Hardware
```

Each VM has its own operating system.

---

# What is a Container?

A Container packages:

- Application
- Libraries
- Dependencies
- Runtime

Unlike a VM,

a container **shares the Host Operating System Kernel**.

---

# Container Architecture

```
Application

↓

Libraries

↓

Docker Engine

↓

Host OS Kernel

↓

Hardware
```

Containers do not include a complete operating system.

---

# Visual Comparison

### Virtual Machines

```
Hardware

↓

Host OS

↓

Hypervisor

│

├── VM-1

│     Guest OS

│     App

│

├── VM-2

│     Guest OS

│     App

│

└── VM-3

      Guest OS

      App
```

---

### Containers

```
Hardware

↓

Host OS

↓

Docker Engine

│

├── Container-1

│     App

│

├── Container-2

│     App

│

└── Container-3

      App
```

Notice that containers share the Host OS kernel.

---

# Major Difference

Virtual Machines

```
Each VM

↓

Own Operating System
```

Containers

```
All Containers

↓

Share Host Kernel
```

This makes containers much lighter.

---

# Resource Usage

Virtual Machine

```
Guest OS

↓

Consumes RAM

↓

Consumes CPU

↓

Consumes Disk
```

Container

```
No Guest OS

↓

Lower RAM

↓

Lower CPU

↓

Lower Disk Usage
```

---

# Startup Time

Virtual Machine

```
Power On

↓

Boot OS

↓

Start Application

↓

Ready

≈ Minutes
```

---

Container

```
Start Container

↓

Application Starts

↓

Ready

≈ Seconds
```

Containers generally start much faster.

---

# Size Comparison

Typical Virtual Machine

```
2 GB

↓

20 GB
```

Typical Docker Image

```
20 MB

↓

500 MB
```

Actual sizes vary,

but containers are generally much smaller.

---

# Performance

Virtual Machine

```
Hardware

↓

Hypervisor

↓

Guest OS

↓

Application
```

More layers introduce additional overhead.

---

Container

```
Hardware

↓

Host Kernel

↓

Docker

↓

Application
```

Fewer layers generally improve efficiency.

---

# Isolation

Virtual Machines provide stronger isolation because each VM has its own operating system.

Containers provide process-level isolation,

which is sufficient for many workloads but requires proper security practices.

---

# Security

Virtual Machines

✔ Stronger isolation

✔ Separate Kernel

✔ Better suited for some multi-tenant workloads

---

Containers

✔ Lightweight

✔ Fast

✔ Efficient

✔ Security depends on correct configuration and host protection

---

# Resource Comparison

| Feature | Virtual Machine | Container |
|----------|----------------|-----------|
| Guest OS | Yes | No |
| Boot Time | Minutes | Seconds |
| Size | Large | Small |
| Memory Usage | Higher | Lower |
| Startup Speed | Slower | Faster |
| Density | Lower | Higher |
| Kernel | Separate | Shared |

---

# Example

Suppose a server has

```
32 GB RAM
```

Virtual Machines

```
VM-1

↓

4 GB

-------------------

VM-2

↓

4 GB

-------------------

VM-3

↓

4 GB
```

A significant amount of memory is consumed by guest operating systems.

---

Containers

```
Container-1

↓

App

--------------------

Container-2

↓

App

--------------------

Container-30

↓

App
```

Many more containers can often run on the same hardware.

---

# Production Example

Modern Production

```
Users

↓

Load Balancer

↓

Docker Containers

↓

Microservices

↓

Database
```

Legacy Production

```
Users

↓

Load Balancer

↓

Virtual Machines

↓

Applications

↓

Database
```

Many organizations still use both technologies together.

---

# Can Docker Run Inside a Virtual Machine?

Yes.

A very common production architecture is:

```
Cloud

↓

Virtual Machine

↓

Linux

↓

Docker

↓

Containers
```

For example,

an AWS EC2 instance (virtual machine) can run Docker containers.

---

# When Should You Use Virtual Machines?

Virtual Machines are often preferred when:

- Different operating systems are required.
- Strong isolation is needed.
- Legacy applications depend on full operating systems.
- Compliance requirements demand OS-level separation.

---

# When Should You Use Containers?

Containers are ideal for:

- Microservices
- CI/CD Pipelines
- Cloud Deployments
- Kubernetes
- APIs
- Web Applications
- Background Workers

---

# Can They Work Together?

Yes.

One of the most common enterprise architectures is:

```
AWS EC2

↓

Ubuntu

↓

Docker

↓

Containers

↓

Applications
```

The VM provides infrastructure,

while Docker manages applications.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Docker replaces Virtual Machines.

Both technologies solve different problems and are often used together.

---

### Mistake 2

Believing Containers have their own Operating System.

Containers share the host kernel.

---

### Mistake 3

Thinking Containers are less useful because they don't contain a full OS.

Sharing the host kernel is one of the reasons containers are lightweight and fast.

---

### Mistake 4

Assuming Virtual Machines are obsolete.

Virtual Machines remain widely used in cloud computing and enterprise environments.

---

# Interview Questions

### Q1. What is the biggest difference between a Virtual Machine and a Container?

A Virtual Machine includes its own guest operating system, while a container shares the host operating system kernel.

---

### Q2. Which starts faster?

Containers generally start much faster than Virtual Machines.

---

### Q3. Which consumes less memory?

Containers usually consume less memory because they do not require a separate guest operating system.

---

### Q4. Can Docker run inside a Virtual Machine?

Yes. Running Docker inside cloud virtual machines such as AWS EC2 instances is very common.

---

### Q5. Which provides stronger isolation?

Virtual Machines generally provide stronger isolation because each VM has its own operating system kernel.

---

# Production Best Practices

✔ Use Containers for modern applications and microservices.

✔ Use Virtual Machines when OS-level isolation or different operating systems are required.

✔ Combine Virtual Machines and Docker for flexible production architectures.

✔ Keep containers lightweight.

✔ Secure both the host operating system and the containers.

✔ Monitor resource usage continuously.

---

# Key Takeaways

- Virtual Machines and Containers both provide isolation but work differently.
- Containers share the host kernel, making them lightweight and fast.
- Virtual Machines include a complete guest operating system.
- Docker containers are ideal for modern cloud-native applications.
- Most enterprise environments use both Virtual Machines and Containers together.

---

# Next Section

## 6.4 Docker Architecture

In the next section, we will learn:

- Docker Engine
- Docker Client
- Docker Daemon
- Docker REST API
- Docker Images
- Docker Containers
- Docker Registry
- Docker Hub
- Complete Request Flow
- Interview Questions
---

# 6.4 Docker Architecture

Now that you understand what Docker is and why it was created,

it's time to understand **how Docker works internally.**

One of the most frequently asked Docker interview questions is:

> **Explain Docker Architecture.**

Every Docker command you execute,

such as

```bash
docker run

docker build

docker pull

docker push
```

travels through Docker Architecture.

Understanding this architecture will help you troubleshoot Docker problems much more effectively.

---

# High-Level Docker Architecture

Docker consists of several major components.

```
Docker Client

↓

Docker Engine

↓

Docker Daemon

↓

Docker Objects

↓

Images

↓

Containers

↓

Volumes

↓

Networks

↓

Docker Registry
```

Every component has a different responsibility.

---

# Major Components

Docker Architecture mainly consists of:

- Docker Client
- Docker Engine
- Docker Daemon
- Docker REST API
- Docker Images
- Docker Containers
- Docker Registry
- Docker Volumes
- Docker Networks

---

# Docker Client

The Docker Client is the command-line interface (CLI) that users interact with.

Examples

```bash
docker run

docker build

docker pull

docker push

docker ps
```

Whenever you execute a Docker command,

you are communicating with the Docker Client.

---

# Docker Client Workflow

```
User

↓

docker run nginx

↓

Docker Client
```

The client itself does not create containers.

Instead,

it sends the request to the Docker Daemon.

---

# Docker Daemon (dockerd)

The Docker Daemon is the core service of Docker.

Service Name

```
dockerd
```

Responsibilities:

- Build Images
- Run Containers
- Stop Containers
- Delete Containers
- Create Networks
- Create Volumes
- Pull Images
- Push Images

Almost every Docker operation is handled by the Docker Daemon.

---

# Docker Daemon Workflow

```
Docker Client

↓

Docker Daemon

↓

Create Container

↓

Application Running
```

---

# Docker Engine

Docker Engine is the complete Docker runtime.

It consists of:

```
Docker Engine

│

├── Docker Client

├── Docker Daemon

└── REST API
```

Docker Engine is what gets installed when you install Docker.

---

# Docker REST API

The Docker Client communicates with the Docker Daemon using the Docker REST API.

Workflow

```
Docker Client

↓

REST API

↓

Docker Daemon
```

This API allows tools and automation platforms to control Docker programmatically.

---

# Docker Objects

Docker creates different types of objects.

```
Docker

│

├── Images

├── Containers

├── Volumes

└── Networks
```

These objects represent different parts of the Docker ecosystem.

---

# Docker Images

A Docker Image is a read-only template used to create containers.

Example

```
Ubuntu Image

↓

Docker Container
```

One image can create many containers.

---

# Docker Containers

A Docker Container is a running instance of a Docker Image.

```
Image

↓

Container

↓

Running Application
```

Containers are isolated from one another.

---

# Docker Registry

Docker stores images inside a Registry.

Examples

- Docker Hub
- Amazon ECR
- Google Artifact Registry
- Azure Container Registry
- GitHub Container Registry

---

# Docker Hub

Docker Hub is Docker's public image repository.

Example

```bash
docker pull nginx
```

Workflow

```
Docker Hub

↓

Download Image

↓

Local Machine
```

---

# Complete Docker Request Flow

Suppose you execute:

```bash
docker run nginx
```

Workflow

```
User

↓

Docker Client

↓

Docker Daemon

↓

Image Exists?

↓

No

↓

Docker Hub

↓

Download Image

↓

Create Container

↓

Run Container
```

---

# What Happens Internally?

Step 1

User executes

```bash
docker run nginx
```

↓

Step 2

Docker Client receives command.

↓

Step 3

Docker Daemon checks whether the image exists locally.

↓

Step 4

If missing,

Docker downloads the image from Docker Hub.

↓

Step 5

Docker creates a writable container layer.

↓

Step 6

Container starts.

↓

Application begins running.

---

# Architecture Diagram

```
User

↓

Docker CLI

↓

Docker REST API

↓

Docker Daemon

│

├── Images

├── Containers

├── Networks

├── Volumes

└── Registry
```

---

# Docker Daemon Responsibilities

The daemon performs:

✔ Build Images

✔ Run Containers

✔ Stop Containers

✔ Remove Containers

✔ Pull Images

✔ Push Images

✔ Manage Networks

✔ Manage Volumes

✔ Allocate Resources

---

# Docker Engine Workflow

```
docker build

↓

Docker Client

↓

Docker Daemon

↓

Build Image

↓

Store Image
```

---

# Container Creation Workflow

```
Image

↓

Writable Layer

↓

Container

↓

Application Running
```

Containers always originate from images.

---

# Image Download Workflow

```
docker pull nginx

↓

Docker Client

↓

Docker Daemon

↓

Docker Hub

↓

Download

↓

Store Locally
```

---

# Container Start Workflow

```
docker start

↓

Docker Daemon

↓

Container Running
```

---

# Production Architecture

```
Developer

↓

Git

↓

CI/CD

↓

Docker Build

↓

Docker Registry

↓

Production Server

↓

Docker Daemon

↓

Containers

↓

Users
```

This is the architecture used by many modern DevOps teams.

---

# Docker on Linux

```
Linux

↓

Docker Engine

↓

Containers

↓

Applications
```

Docker uses Linux kernel features such as:

- Namespaces
- Control Groups (cgroups)
- Union Filesystems

These technologies enable isolation and resource management.

---

# Real Production Example

Suppose a company deploys:

```
Docker Engine

│

├── Nginx Container

├── Spring Boot Container

├── Redis Container

├── RabbitMQ Container

└── Monitoring Container
```

Each application runs independently while sharing the same Docker Engine.

---

# Common Beginner Mistakes

### Mistake 1

Thinking the Docker Client creates containers.

The Docker Client only sends commands.

The Docker Daemon performs the work.

---

### Mistake 2

Thinking Docker Hub stores running containers.

Docker Hub stores images,

not containers.

---

### Mistake 3

Believing Images are running applications.

Images are templates.

Containers are running instances.

---

### Mistake 4

Thinking Docker Engine and Docker Daemon are the same.

Docker Engine includes the Docker Daemon,

the Docker Client,

and the REST API.

---

# Interview Questions

### Q1. What are the main components of Docker Architecture?

- Docker Client
- Docker Daemon
- Docker Engine
- Docker Images
- Docker Containers
- Docker Registry

---

### Q2. What is the Docker Daemon?

The Docker Daemon (`dockerd`) is the background service responsible for building images, creating containers and managing Docker resources.

---

### Q3. What is Docker Engine?

Docker Engine is the complete Docker runtime consisting of the Docker Client, Docker Daemon and Docker REST API.

---

### Q4. What happens when you execute `docker run nginx`?

Docker checks whether the image exists locally. If not, it downloads the image from a registry, creates a container and starts it.

---

### Q5. What is Docker Hub?

Docker Hub is Docker's default public registry used to store and distribute Docker images.

---

# Production Best Practices

✔ Keep the Docker Daemon updated.

✔ Use trusted image registries.

✔ Restrict access to the Docker socket.

✔ Monitor Docker Engine health.

✔ Store private images in secure registries.

✔ Avoid running unnecessary containers.

✔ Regularly clean unused images and containers.

✔ Automate image builds using CI/CD.

---

# Key Takeaways

- Docker Architecture consists of the Docker Client, Docker Daemon, Docker Engine and Docker objects.
- The Docker Client sends commands to the Docker Daemon.
- The Docker Daemon performs all container operations.
- Docker Images are templates, while Containers are running instances.
- Docker Hub is the default public registry for Docker images.

---

# Next Section

## 6.5 Installing Docker

In the next section, we will learn:

- Installing Docker on Ubuntu
- Installing Docker on Rocky Linux
- Installing Docker on Amazon Linux
- Starting Docker
- Enabling Docker at Boot
- Verifying Installation
- Running the First Container
- Production Installation Best Practices
- Interview Questions
---

# 6.5 Installing Docker

Now that you understand Docker Architecture,

it's time to install Docker.

In this section,

we will install Docker on:

- Ubuntu
- Rocky Linux
- Amazon Linux

We will also learn:

- Start Docker
- Stop Docker
- Restart Docker
- Enable Docker at Boot
- Verify Installation
- Run Your First Container

---

# Lab Environment

This chapter uses:

```
Ubuntu 24.04 LTS

or

Rocky Linux 9

or

Amazon Linux 2023
```

You can perform these steps on:

- Physical Machine
- Virtual Machine
- AWS EC2
- Azure VM
- Google Cloud VM

---

# Before Installing

Always update package information.

Ubuntu

```bash
sudo apt update
```

Rocky Linux

```bash
sudo dnf check-update
```

Amazon Linux

```bash
sudo dnf check-update
```

---

# Install Docker on Ubuntu

Remove old Docker packages (if installed).

```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

Install required packages.

```bash
sudo apt install ca-certificates curl gnupg lsb-release -y
```

Create Docker key directory.

```bash
sudo install -m 0755 -d /etc/apt/keyrings
```

Download Docker GPG key.

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

Set permissions.

```bash
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

Add Docker Repository.

```bash
echo \
"deb [arch=$(dpkg --print-architecture) \
signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Update repository.

```bash
sudo apt update
```

Install Docker.

```bash
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

---

# Install Docker on Rocky Linux

Install Docker repository.

```bash
sudo dnf config-manager --add-repo \
https://download.docker.com/linux/centos/docker-ce.repo
```

Install Docker.

```bash
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

---

# Install Docker on Amazon Linux

Update packages.

```bash
sudo dnf update -y
```

Install Docker.

```bash
sudo dnf install docker -y
```

---

# Verify Docker Installation

Check Docker version.

```bash
docker --version
```

Example

```text
Docker version 28.x.x
```

---

# Check Docker Service

```bash
sudo systemctl status docker
```

Expected Output

```text
Active: active (running)
```

---

# Start Docker

```bash
sudo systemctl start docker
```

---

# Stop Docker

```bash
sudo systemctl stop docker
```

---

# Restart Docker

```bash
sudo systemctl restart docker
```

---

# Reload Docker

```bash
sudo systemctl reload docker
```

If supported by your configuration.

---

# Enable Docker at Boot

```bash
sudo systemctl enable docker
```

Verify

```bash
systemctl is-enabled docker
```

Expected

```text
enabled
```

---

# Disable Auto Start

```bash
sudo systemctl disable docker
```

---

# Check Docker Information

```bash
docker info
```

Displays

- Docker Root Directory
- Storage Driver
- Number of Images
- Number of Containers
- CPU
- Memory
- Docker Version

---

# Run Your First Container

```bash
docker run hello-world
```

Workflow

```
Docker Client

↓

Docker Daemon

↓

Docker Hub

↓

Download Image

↓

Run Container

↓

Success Message
```

Expected Output

```
Hello from Docker!
```

This confirms Docker is working correctly.

---

# Download an Image

```bash
docker pull nginx
```

Verify

```bash
docker images
```

Example

```
REPOSITORY

TAG

IMAGE ID
```

---

# Run Nginx Container

```bash
docker run -d -p 80:80 nginx
```

Explanation

```
-d

↓

Detached Mode

---------------------

-p

↓

Port Mapping

80:80
```

Open Browser

```
http://SERVER-IP
```

You should see the Nginx Welcome Page.

---

# List Running Containers

```bash
docker ps
```

Example

```
CONTAINER ID

IMAGE

STATUS

PORTS

NAMES
```

---

# List All Containers

```bash
docker ps -a
```

Displays both running and stopped containers.

---

# Stop Container

```bash
docker stop CONTAINER_ID
```

Example

```bash
docker stop 7f34a1
```

---

# Start Existing Container

```bash
docker start CONTAINER_ID
```

---

# Remove Container

```bash
docker rm CONTAINER_ID
```

---

# Remove Image

```bash
docker rmi IMAGE_ID
```

---

# Allow Non-Root User

By default,

Docker requires `sudo`.

Add your user to the Docker group.

```bash
sudo usermod -aG docker $USER
```

Apply changes by logging out and back in,

or by starting a new login session.

Verify

```bash
docker ps
```

without using `sudo`.

---

# Verify Docker Daemon

```bash
ps -ef | grep dockerd
```

Expected

```
dockerd
```

should be running.

---

# Docker Installation Workflow

```
Install Docker

↓

Start Service

↓

Enable at Boot

↓

Verify Version

↓

Run hello-world

↓

Run nginx

↓

Docker Ready
```

---

# Troubleshooting

### Docker Service Not Running

Check

```bash
sudo systemctl status docker
```

---

### Docker Daemon Logs

```bash
journalctl -u docker
```

---

### Permission Denied

Add user to Docker group.

```bash
sudo usermod -aG docker $USER
```

Then re-login.

---

### Verify Port Usage

```bash
ss -tulpn | grep 80
```

Useful if Nginx container fails to start due to a port conflict.

---

# Real Production Example

```
Ubuntu Server

↓

Docker Engine

↓

Nginx Container

↓

Spring Boot Container

↓

Redis Container

↓

MySQL Container
```

Multiple applications run independently on the same Docker Engine.

---

# Common Beginner Mistakes

### Mistake 1

Forgetting to start the Docker service after installation.

---

### Mistake 2

Running Docker commands without sufficient permissions.

---

### Mistake 3

Ignoring Docker daemon errors.

Always check:

```bash
journalctl -u docker
```

---

### Mistake 4

Not enabling Docker at boot.

Production servers should automatically start Docker after reboot.

---

### Mistake 5

Assuming `docker run` only starts a container.

It may also download the image if it is not available locally.

---

# Interview Questions

### Q1. Which command installs Docker on Ubuntu?

```bash
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

---

### Q2. Which command verifies Docker installation?

```bash
docker --version
```

---

### Q3. Which command runs the Docker test container?

```bash
docker run hello-world
```

---

### Q4. Which command lists running containers?

```bash
docker ps
```

---

### Q5. Which command enables Docker after reboot?

```bash
sudo systemctl enable docker
```

---

### Q6. Which command displays Docker daemon information?

```bash
docker info
```

---

# Production Best Practices

✔ Install Docker from the official repository.

✔ Enable Docker at boot.

✔ Verify installation with `hello-world`.

✔ Use non-root Docker access where appropriate.

✔ Monitor the Docker daemon.

✔ Keep Docker updated.

✔ Remove unused images and containers.

✔ Regularly review Docker logs.

---

# Key Takeaways

- Docker installation is straightforward on major Linux distributions.
- Always verify the Docker daemon after installation.
- `docker run hello-world` is the quickest installation test.
- Enable Docker to start automatically after reboot.
- Production systems should use the official Docker packages and follow least-privilege principles.

---

# Next Section

## 6.6 Docker Images

In the next section, we will learn:

- What is a Docker Image?
- Image Layers
- Image Architecture
- Base Images
- Pulling Images
- Listing Images
- Removing Images
- Image Tags
- Best Practices
- Interview Questions
---

# 6.6 Docker Images

Before running a Docker container,

you need a **Docker Image**.

A container **cannot exist without an image.**

Think of an image as a blueprint.

Just as a building is constructed from a blueprint,

a Docker container is created from a Docker image.

---

# What is a Docker Image?

A Docker Image is a **read-only template** used to create one or more Docker containers.

It contains everything required to run an application:

- Application Code
- Runtime
- Libraries
- Dependencies
- Configuration Files
- Environment Variables

An image never changes while it is being used.

---

# Simple Definition

```
Image

↓

Blueprint

↓

Container

↓

Running Application
```

---

# Real-Life Analogy

Imagine making many photocopies.

```
Original Document

↓

Photocopy Machine

↓

Copy 1

Copy 2

Copy 3
```

The original document never changes.

Similarly,

```
Docker Image

↓

Container 1

Container 2

Container 3
```

One image can create many containers.

---

# Docker Image Workflow

```
Dockerfile

↓

Build

↓

Docker Image

↓

Run

↓

Docker Container
```

Every container starts from an image.

---

# Image vs Container

| Docker Image | Docker Container |
|---------------|------------------|
| Read Only | Read/Write |
| Template | Running Instance |
| Cannot Execute | Executes Application |
| Stored on Disk | Runs in Memory |
| Can Create Multiple Containers | Created From One Image |

---

# Where Are Images Stored?

Docker stores downloaded images locally.

Linux

```
/var/lib/docker/
```

You normally do not access this directory manually.

Docker manages it automatically.

---

# Docker Hub

Docker Hub is Docker's default public registry.

```
Docker Hub

↓

Download Image

↓

Local Machine

↓

Run Container
```

Thousands of official images are available.

Examples

- Ubuntu
- Nginx
- Redis
- MySQL
- PostgreSQL
- MongoDB
- Jenkins
- Python

---

# Pull an Image

Download an image.

```bash
docker pull nginx
```

Workflow

```
Docker Hub

↓

Download

↓

Local Images
```

---

# Pull Ubuntu

```bash
docker pull ubuntu
```

---

# Pull Redis

```bash
docker pull redis
```

---

# Pull MySQL

```bash
docker pull mysql
```

---

# List Images

```bash
docker images
```

or

```bash
docker image ls
```

Example

```text
REPOSITORY    TAG      IMAGE ID

nginx         latest   4ab....

ubuntu        latest   d78....

redis         latest   91c....
```

---

# Image Components

Every image has:

- Repository
- Tag
- Image ID
- Created Time
- Size

---

# Repository

Repository is the image name.

Example

```
nginx

ubuntu

redis

mysql
```

---

# Tag

Tags identify image versions.

Example

```
ubuntu:24.04

ubuntu:22.04

nginx:latest

mysql:8.4
```

---

# Why Use Tags?

Instead of downloading

```
latest
```

you can download a specific version.

Example

```bash
docker pull nginx:1.27
```

This provides predictable deployments.

---

# Image ID

Every image has a unique identifier.

Example

```
sha256:

a45d9d89...

```

Docker uses this internally.

---

# Image Size

Example

```
Ubuntu

↓

78 MB

--------------------

Nginx

↓

55 MB

--------------------

Redis

↓

120 MB
```

Sizes vary by version and base image.

---

# Inspect an Image

```bash
docker image inspect nginx
```

Shows

- Layers
- Environment Variables
- Entrypoint
- Working Directory
- Metadata

---

# Search Images

```bash
docker search nginx
```

Displays available images from Docker Hub.

---

# Remove an Image

```bash
docker rmi nginx
```

or

```bash
docker image rm nginx
```

---

# Remove Multiple Images

```bash
docker rmi nginx redis ubuntu
```

---

# Remove All Unused Images

```bash
docker image prune
```

Remove all unused images.

```bash
docker image prune -a
```

Use with care,

as this removes all images not currently used by containers.

---

# Image Layers

Docker Images are built using layers.

Example

```
Ubuntu Base

↓

Install Java

↓

Install Maven

↓

Copy Application

↓

Configuration
```

Each instruction creates a new layer.

---

# Layer Architecture

```
Layer 5

Application

↓

Layer 4

Libraries

↓

Layer 3

Java

↓

Layer 2

Packages

↓

Layer 1

Ubuntu
```

Docker reuses unchanged layers,

making builds faster.

---

# Layer Caching

Suppose only the application code changes.

```
Ubuntu Layer

↓

Reuse

----------------------

Java Layer

↓

Reuse

----------------------

Application Layer

↓

Rebuild
```

Docker rebuilds only the changed layers.

This significantly speeds up builds.

---

# Read-Only Nature

Docker Images are immutable.

```
Image

↓

Read Only
```

Containers add a writable layer on top of the image.

---

# Multiple Containers

One image

↓

Many containers

```
nginx Image

↓

Container-1

↓

Container-2

↓

Container-3
```

Each container has its own writable layer.

---

# Export an Image

Save an image.

```bash
docker save nginx -o nginx.tar
```

---

# Import an Image

Load an image.

```bash
docker load -i nginx.tar
```

Useful when transferring images without Internet access.

---

# Real Production Example

A company creates

```
company-api:v1.0
```

Deploys

```
50 Containers

↓

Same Image
```

Every container behaves consistently because they all originate from the same image.

---

# Common Beginner Mistakes

### Mistake 1

Thinking an image is a running application.

Images are templates.

Containers run applications.

---

### Mistake 2

Always using the `latest` tag.

Specific version tags provide more predictable deployments.

---

### Mistake 3

Deleting images that are still required by running containers.

Docker prevents removal in many cases, but verify dependencies before cleanup.

---

### Mistake 4

Downloading images from untrusted sources.

Use official or trusted registries whenever possible.

---

# Interview Questions

### Q1. What is a Docker Image?

A Docker Image is a read-only template used to create Docker containers.

---

### Q2. Which command downloads an image?

```bash
docker pull IMAGE_NAME
```

---

### Q3. Which command lists local images?

```bash
docker images
```

---

### Q4. What is an image tag?

A tag identifies a specific version of a Docker image.

---

### Q5. Why are Docker Images immutable?

Images remain unchanged to ensure consistency and reproducibility. Containers add a writable layer for runtime changes.

---

### Q6. What are Docker Image layers?

Layers are incremental filesystem changes created during the image build process. Docker reuses unchanged layers to improve build efficiency.

---

# Production Best Practices

✔ Use official base images.

✔ Pin images to specific version tags.

✔ Keep images as small as possible.

✔ Remove unused images regularly.

✔ Scan images for security vulnerabilities.

✔ Store production images in a trusted registry.

✔ Reuse layers to optimize build times.

✔ Version images consistently.

---

# Key Takeaways

- Docker Images are read-only templates.
- Containers are created from images.
- Images consist of reusable layers.
- Version tags provide predictable deployments.
- Proper image management improves security, consistency and performance.

---

# Next Section

## 6.7 Docker Containers

In the next section, we will learn:

- What is a Docker Container?
- Container Lifecycle
- Running Containers
- Starting & Stopping Containers
- Container States
- Interactive Containers
- Detached Mode
- Removing Containers
- Production Best Practices
- Interview Questions
---

# 6.7 Docker Containers

In the previous section,

we learned about **Docker Images**.

A Docker Image is only a **template**.

To actually run an application,

Docker creates a **Container** from that image.

Think of it this way:

```
Image

↓

Container

↓

Running Application
```

A container is the **live, running instance** of an image.

---

# What is a Docker Container?

A Docker Container is a lightweight, isolated runtime environment that runs an application.

It contains:

- Application
- Libraries
- Dependencies
- Runtime
- Configuration

Unlike Virtual Machines,

containers share the Host OS Kernel.

---

# Simple Definition

```
Docker Image

↓

docker run

↓

Docker Container

↓

Application Running
```

---

# Real-Life Analogy

Imagine a cake recipe.

```
Recipe

↓

Bake

↓

Cake
```

Recipe = Docker Image

Cake = Docker Container

You can bake many cakes from one recipe.

Similarly,

```
One Image

↓

Container-1

↓

Container-2

↓

Container-3
```

---

# Container Architecture

```
Docker Image

↓

Writable Layer

↓

Container

↓

Application
```

Containers add a writable layer on top of the image.

---

# Why Do We Need Containers?

Containers provide:

✔ Isolation

✔ Portability

✔ Fast Startup

✔ Easy Deployment

✔ Consistent Runtime

✔ Lightweight Execution

---

# Container Lifecycle

A Docker Container passes through several states.

```
Created

↓

Running

↓

Paused

↓

Stopped

↓

Removed
```

Understanding these states is important for troubleshooting.

---

# Create a Container

Create without starting.

```bash
docker create nginx
```

Docker creates the container,

but it is not yet running.

---

# Start a Container

```bash
docker start CONTAINER_ID
```

The container moves from

```
Created

↓

Running
```

---

# Run a Container

Most commonly,

you create and start a container together.

```bash
docker run nginx
```

Docker performs:

```
Create

↓

Start

↓

Run
```

in one command.

---

# Run in Detached Mode

```bash
docker run -d nginx
```

Explanation

```
-d

↓

Detached Mode
```

The container runs in the background,

allowing you to continue using the terminal.

---

# Run in Interactive Mode

```bash
docker run -it ubuntu
```

Explanation

```
-i

↓

Interactive

---------------------

-t

↓

Terminal
```

This opens a shell inside the container.

---

# Container States

Running Containers

```bash
docker ps
```

All Containers

```bash
docker ps -a
```

Example

```text
CONTAINER ID

IMAGE

STATUS

PORTS

NAMES
```

---

# Stop a Container

```bash
docker stop CONTAINER_ID
```

Gracefully stops the container.

---

# Force Stop

```bash
docker kill CONTAINER_ID
```

Immediately terminates the container.

Use carefully.

---

# Restart a Container

```bash
docker restart CONTAINER_ID
```

Equivalent to

```
Stop

↓

Start
```

---

# Pause a Container

```bash
docker pause CONTAINER_ID
```

The container remains in memory,

but its processes are suspended.

---

# Resume a Container

```bash
docker unpause CONTAINER_ID
```

Processes continue execution.

---

# Remove a Container

```bash
docker rm CONTAINER_ID
```

The container must usually be stopped first.

---

# Remove Running Container

```bash
docker rm -f CONTAINER_ID
```

The `-f` option forcefully stops and removes the container.

---

# Name a Container

Instead of random names,

assign a meaningful name.

```bash
docker run --name webserver nginx
```

Verify

```bash
docker ps
```

Example

```
webserver
```

---

# Port Mapping

Expose container ports.

```bash
docker run -d -p 8080:80 nginx
```

Meaning

```
Host

8080

↓

Container

80
```

Open

```
http://SERVER-IP:8080
```

---

# Container Logs

View logs.

```bash
docker logs CONTAINER_ID
```

Follow logs continuously.

```bash
docker logs -f CONTAINER_ID
```

---

# Execute Commands Inside Container

```bash
docker exec -it CONTAINER_ID bash
```

If Bash is unavailable,

use

```bash
docker exec -it CONTAINER_ID sh
```

---

# Inspect a Container

```bash
docker inspect CONTAINER_ID
```

Displays:

- IP Address
- Mounts
- Networks
- Environment Variables
- Ports
- Configuration

---

# View Running Processes

```bash
docker top CONTAINER_ID
```

Displays processes running inside the container.

---

# View Resource Usage

```bash
docker stats
```

Shows

- CPU Usage
- Memory Usage
- Network Usage
- Disk I/O

in real time.

---

# Rename a Container

```bash
docker rename oldname newname
```

---

# Container Exit Codes

Common exit codes:

| Exit Code | Meaning |
|-----------|----------|
| 0 | Successful Exit |
| 1 | General Error |
| 125 | Docker Error |
| 126 | Command Cannot Execute |
| 127 | Command Not Found |
| 137 | Killed (SIGKILL / OOM) |
| 143 | Graceful Stop (SIGTERM) |

Exit codes help diagnose failures.

---

# Container Workflow

```
Docker Image

↓

docker run

↓

Container Created

↓

Container Running

↓

Stop

↓

Remove
```

---

# Multiple Containers

One image can create multiple containers.

```
nginx Image

↓

Web-1

↓

Web-2

↓

Web-3
```

Each container is isolated.

---

# Production Example

A company hosts:

```
Docker Engine

│

├── Nginx

├── API

├── Redis

├── Worker

├── RabbitMQ

└── Prometheus
```

Each application runs inside its own container.

---

# Container Isolation

Each container has its own:

- Process Space
- Filesystem
- Network Namespace
- Environment Variables

This isolation prevents applications from interfering with each other.

---

# Common Beginner Mistakes

### Mistake 1

Stopping a container and expecting it to be deleted automatically.

Stopping and removing are different operations.

---

### Mistake 2

Using `docker kill` instead of `docker stop`.

Prefer graceful shutdowns whenever possible.

---

### Mistake 3

Running every container in interactive mode.

Production containers usually run in detached mode.

---

### Mistake 4

Using random container names.

Assign meaningful names to simplify management.

---

### Mistake 5

Ignoring container logs during troubleshooting.

Always check:

```bash
docker logs
```

before investigating further.

---

# Interview Questions

### Q1. What is a Docker Container?

A Docker Container is a running instance of a Docker Image.

---

### Q2. Which command lists running containers?

```bash
docker ps
```

---

### Q3. Which command starts a stopped container?

```bash
docker start CONTAINER_ID
```

---

### Q4. What is the difference between `docker stop` and `docker kill`?

`docker stop` performs a graceful shutdown by sending a termination signal.

`docker kill` immediately terminates the container.

---

### Q5. Which command opens a shell inside a running container?

```bash
docker exec -it CONTAINER_ID bash
```

(or `sh` if Bash is unavailable.)

---

### Q6. Which command displays real-time CPU and memory usage?

```bash
docker stats
```

---

# Production Best Practices

✔ Give containers meaningful names.

✔ Run production containers in detached mode.

✔ Monitor container resource usage.

✔ Review container logs regularly.

✔ Stop containers gracefully.

✔ Remove unused containers.

✔ Keep one primary process per container.

✔ Monitor exit codes to detect failures.

---

# Key Takeaways

- Containers are running instances of Docker Images.
- Containers are lightweight and isolated.
- `docker run` creates and starts a container.
- `docker exec`, `docker logs` and `docker stats` are essential troubleshooting commands.
- Containers form the foundation of modern cloud-native applications.

---

# Next Section

## 6.8 Basic Docker Commands

In the next section, we will learn:

- Essential Docker Commands
- Image Commands
- Container Commands
- Volume Commands
- Network Commands
- Cleanup Commands
- Frequently Used Options
- Real Production Examples
- Interview Questions
---

# 6.8 Basic Docker Commands

A DevOps Engineer uses Docker commands every day.

Whether you are:

- Building Applications
- Deploying Containers
- Troubleshooting
- Monitoring
- Cleaning Resources

you will constantly use Docker CLI commands.

This section covers the **most frequently used Docker commands** used in real production environments.

---

# Docker Command Categories

Docker commands can be grouped into:

```
Docker

│

├── Image Commands

├── Container Commands

├── Volume Commands

├── Network Commands

├── System Commands

└── Cleanup Commands
```

---

# Check Docker Version

```bash
docker --version
```

Example

```text
Docker version 28.x.x
```

---

# Display Docker Information

```bash
docker info
```

Shows

- Docker Version
- Storage Driver
- CPU
- Memory
- Images
- Containers
- Networks
- Volumes

---

# Display Docker Help

```bash
docker --help
```

Show help for a specific command.

Example

```bash
docker run --help
```

---

# Image Commands

## Download an Image

```bash
docker pull nginx
```

---

## List Images

```bash
docker images
```

or

```bash
docker image ls
```

---

## Search Images

```bash
docker search redis
```

---

## Remove an Image

```bash
docker rmi nginx
```

---

## Inspect an Image

```bash
docker image inspect nginx
```

---

## Save an Image

```bash
docker save nginx -o nginx.tar
```

---

## Load an Image

```bash
docker load -i nginx.tar
```

---

# Container Commands

## Run a Container

```bash
docker run nginx
```

---

## Run in Detached Mode

```bash
docker run -d nginx
```

---

## Run with Port Mapping

```bash
docker run -d -p 8080:80 nginx
```

---

## Run with Container Name

```bash
docker run --name web nginx
```

---

## Run Interactive Container

```bash
docker run -it ubuntu
```

---

## List Running Containers

```bash
docker ps
```

---

## List All Containers

```bash
docker ps -a
```

---

## Stop Container

```bash
docker stop CONTAINER_ID
```

---

## Start Container

```bash
docker start CONTAINER_ID
```

---

## Restart Container

```bash
docker restart CONTAINER_ID
```

---

## Kill Container

```bash
docker kill CONTAINER_ID
```

---

## Remove Container

```bash
docker rm CONTAINER_ID
```

---

## Force Remove

```bash
docker rm -f CONTAINER_ID
```

---

# Execute Commands

Open a shell.

```bash
docker exec -it CONTAINER_ID bash
```

If Bash is unavailable.

```bash
docker exec -it CONTAINER_ID sh
```

---

# View Logs

```bash
docker logs CONTAINER_ID
```

Follow logs.

```bash
docker logs -f CONTAINER_ID
```

---

# Inspect Container

```bash
docker inspect CONTAINER_ID
```

---

# Monitor Resource Usage

```bash
docker stats
```

Shows

- CPU
- Memory
- Network
- Block I/O

---

# Display Running Processes

```bash
docker top CONTAINER_ID
```

---

# Copy Files

Host → Container

```bash
docker cp test.txt CONTAINER_ID:/tmp/
```

Container → Host

```bash
docker cp CONTAINER_ID:/tmp/test.txt .
```

---

# Rename Container

```bash
docker rename oldname newname
```

---

# Pause Container

```bash
docker pause CONTAINER_ID
```

---

# Resume Container

```bash
docker unpause CONTAINER_ID
```

---

# Volume Commands

## List Volumes

```bash
docker volume ls
```

---

## Create Volume

```bash
docker volume create myvolume
```

---

## Inspect Volume

```bash
docker volume inspect myvolume
```

---

## Remove Volume

```bash
docker volume rm myvolume
```

---

# Network Commands

## List Networks

```bash
docker network ls
```

---

## Create Network

```bash
docker network create app-network
```

---

## Inspect Network

```bash
docker network inspect app-network
```

---

## Connect Container

```bash
docker network connect app-network CONTAINER_ID
```

---

## Disconnect Container

```bash
docker network disconnect app-network CONTAINER_ID
```

---

## Remove Network

```bash
docker network rm app-network
```

---

# System Commands

## Display Disk Usage

```bash
docker system df
```

Shows

- Images
- Containers
- Volumes
- Build Cache

---

## Display Docker Events

```bash
docker events
```

Shows live Docker activity.

---

## Display Docker System Information

```bash
docker system info
```

---

# Cleanup Commands

## Remove Stopped Containers

```bash
docker container prune
```

---

## Remove Unused Images

```bash
docker image prune
```

---

## Remove Unused Networks

```bash
docker network prune
```

---

## Remove Unused Volumes

```bash
docker volume prune
```

---

## Remove Everything Unused

```bash
docker system prune
```

Remove everything including unused images.

```bash
docker system prune -a
```

Use carefully in production.

---

# Real Production Workflow

```
Developer

↓

docker build

↓

docker push

↓

Production Server

↓

docker pull

↓

docker run

↓

Application Running
```

---

# Frequently Used Commands

| Task | Command |
|------|----------|
| Download Image | `docker pull` |
| Run Container | `docker run` |
| List Containers | `docker ps` |
| Stop Container | `docker stop` |
| Remove Container | `docker rm` |
| List Images | `docker images` |
| View Logs | `docker logs` |
| Execute Shell | `docker exec -it` |
| Resource Usage | `docker stats` |
| Cleanup | `docker system prune` |

---

# Common Beginner Mistakes

### Mistake 1

Using `docker rm` on a running container.

Stop it first or use:

```bash
docker rm -f
```

---

### Mistake 2

Using `docker system prune -a` without understanding its impact.

It can remove images that may still be needed.

---

### Mistake 3

Ignoring logs while troubleshooting.

Always check:

```bash
docker logs
```

---

### Mistake 4

Creating many unnamed containers.

Always assign meaningful names.

---

### Mistake 5

Forgetting to clean unused Docker resources.

Unused images, containers and volumes consume disk space.

---

# Interview Questions

### Q1. Which command downloads a Docker image?

```bash
docker pull IMAGE_NAME
```

---

### Q2. Which command lists running containers?

```bash
docker ps
```

---

### Q3. Which command opens a shell inside a container?

```bash
docker exec -it CONTAINER_ID bash
```

---

### Q4. Which command displays container logs?

```bash
docker logs CONTAINER_ID
```

---

### Q5. Which command displays real-time resource usage?

```bash
docker stats
```

---

### Q6. Which command removes unused Docker resources?

```bash
docker system prune
```

---

# Production Best Practices

✔ Learn the most frequently used Docker commands thoroughly.

✔ Name containers clearly.

✔ Monitor containers with `docker stats`.

✔ Use `docker logs` as the first troubleshooting step.

✔ Remove unused Docker resources regularly.

✔ Avoid using force options unless necessary.

✔ Use version-controlled scripts for repetitive Docker operations.

---

# Key Takeaways

- Docker CLI is the primary interface for managing Docker.
- Commands are grouped into Images, Containers, Networks, Volumes and System operations.
- A small set of commands covers most day-to-day Docker administration.
- Regular cleanup and monitoring help maintain healthy Docker environments.
- Mastering Docker CLI commands is essential for every DevOps Engineer.

---

# Next Section

## 6.9 Dockerfile

In the next section, we will learn:

- What is a Dockerfile?
- Dockerfile Instructions
- FROM
- RUN
- COPY
- ADD
- WORKDIR
- CMD
- ENTRYPOINT
- ENV
- EXPOSE
- Building Images
- Best Practices
- Interview Questions
---

# 6.9 Dockerfile

So far,

we have been downloading Docker Images from Docker Hub using commands like:

```bash
docker pull nginx

docker pull ubuntu
```

But what if your company develops its **own application**?

Docker Hub doesn't have your company's application.

You must create your own Docker Image.

To create a custom Docker Image,

Docker uses a special file called a **Dockerfile**.

A Dockerfile is one of the most important concepts in Docker.

---

# What is a Dockerfile?

A **Dockerfile** is a text file containing instructions that tell Docker how to build an image.

Think of it as a recipe.

```
Recipe

↓

Cook

↓

Food
```

Similarly,

```
Dockerfile

↓

docker build

↓

Docker Image
```

---

# Why Do We Need Dockerfiles?

Without Dockerfile

```
Install Ubuntu

↓

Install Java

↓

Install Maven

↓

Copy Application

↓

Run Application
```

Repeat these steps every time.

---

With Dockerfile

```
Dockerfile

↓

docker build

↓

Image Ready
```

Everything becomes automated.

---

# Dockerfile Workflow

```
Dockerfile

↓

docker build

↓

Docker Image

↓

docker run

↓

Container

↓

Application Running
```

---

# Dockerfile Example

```dockerfile
FROM ubuntu:24.04

RUN apt update

RUN apt install nginx -y

CMD ["nginx","-g","daemon off;"]
```

Docker executes each instruction one by one.

---

# Dockerfile Instructions

Common instructions include:

```
FROM

RUN

COPY

ADD

WORKDIR

CMD

ENTRYPOINT

ENV

EXPOSE

LABEL

USER

VOLUME
```

Each instruction serves a specific purpose.

---

# FROM

The **FROM** instruction specifies the base image.

Example

```dockerfile
FROM ubuntu:24.04
```

Everything in the image starts from this base.

Every Dockerfile should normally begin with `FROM`.

---

# FROM Example

```
Ubuntu

↓

Install Java

↓

Install Maven

↓

Application
```

---

# RUN

The **RUN** instruction executes commands while building the image.

Example

```dockerfile
RUN apt update
```

Another example

```dockerfile
RUN apt install nginx -y
```

Each `RUN` creates a new image layer.

---

# COPY

The **COPY** instruction copies files from the local machine into the image.

Example

```dockerfile
COPY app.jar /app/
```

Workflow

```
Local Machine

↓

COPY

↓

Docker Image
```

---

# ADD

The **ADD** instruction also copies files,

but it can additionally:

- Extract local archives automatically
- Download content from URLs (although COPY is generally preferred for local files)

Example

```dockerfile
ADD project.tar.gz /app/
```

For simple file copies,

prefer `COPY`.

---

# WORKDIR

The **WORKDIR** instruction sets the working directory.

Example

```dockerfile
WORKDIR /app
```

Subsequent commands execute from this directory.

---

# CMD

The **CMD** instruction specifies the default command executed when a container starts.

Example

```dockerfile
CMD ["nginx","-g","daemon off;"]
```

Only one CMD is normally effective.

If multiple CMD instructions exist,

the last one is used.

---

# ENTRYPOINT

ENTRYPOINT defines the main executable for the container.

Example

```dockerfile
ENTRYPOINT ["java","-jar","app.jar"]
```

Unlike CMD,

ENTRYPOINT is intended to define the container's primary command.

---

# CMD vs ENTRYPOINT

CMD

```
Default Command

↓

Can Be Overridden
```

ENTRYPOINT

```
Primary Executable

↓

Normally Always Runs
```

Often,

ENTRYPOINT and CMD are used together.

---

# ENV

Set environment variables.

Example

```dockerfile
ENV APP_ENV=production
```

Application

↓

Reads

↓

APP_ENV

---

# EXPOSE

Documents which port the application uses.

Example

```dockerfile
EXPOSE 8080
```

This does **not** publish the port to the host.

Port publishing happens with:

```bash
docker run -p
```

---

# LABEL

Labels add metadata.

Example

```dockerfile
LABEL maintainer="admin@example.com"
```

Useful for documentation and automation.

---

# USER

Specify which user runs the application.

Example

```dockerfile
USER appuser
```

Running applications as a non-root user improves security.

---

# VOLUME

Declare persistent storage.

Example

```dockerfile
VOLUME ["/data"]
```

Docker creates a mount point for persistent data.

---

# Complete Dockerfile Example

```dockerfile
FROM openjdk:21

WORKDIR /app

COPY target/app.jar .

EXPOSE 8080

ENTRYPOINT ["java","-jar","app.jar"]
```

This Dockerfile packages a Java application.

---

# Dockerfile Build Process

```
Dockerfile

↓

FROM

↓

RUN

↓

COPY

↓

WORKDIR

↓

CMD

↓

Docker Image
```

Docker executes instructions from top to bottom.

---

# Docker Layers

Each instruction usually creates a new layer.

```
FROM

↓

Layer 1

----------------

RUN

↓

Layer 2

----------------

COPY

↓

Layer 3

----------------

CMD

↓

Metadata
```

Layer caching improves build performance.

---

# Docker Build Command

```bash
docker build -t myapp:v1 .
```

Explanation

```
-t

↓

Tag

----------------

.

↓

Current Directory
```

---

# Verify Image

```bash
docker images
```

You should see:

```
myapp

v1
```

---

# Run Image

```bash
docker run myapp:v1
```

Container starts using the newly created image.

---

# Best Dockerfile Order

```
FROM

↓

Install Packages

↓

Copy Dependency Files

↓

Install Dependencies

↓

Copy Application

↓

CMD
```

This maximizes Docker layer caching.

---

# Real Production Example

Spring Boot Application

```
Source Code

↓

Dockerfile

↓

docker build

↓

Image

↓

Docker Registry

↓

Production

↓

Container
```

This is the workflow followed by many DevOps teams.

---

# Common Beginner Mistakes

### Mistake 1

Using multiple unnecessary `RUN` instructions.

Combine related commands where appropriate to reduce image layers.

---

### Mistake 2

Using `ADD` when `COPY` is sufficient.

Prefer `COPY` unless ADD's extra features are required.

---

### Mistake 3

Running applications as the root user.

Use a dedicated non-root user whenever practical.

---

### Mistake 4

Copying unnecessary files into the image.

Use a `.dockerignore` file to exclude temporary files, Git repositories and build artifacts.

---

### Mistake 5

Using `latest` as the base image.

Prefer specific versions such as:

```dockerfile
FROM ubuntu:24.04
```

---

# Interview Questions

### Q1. What is a Dockerfile?

A Dockerfile is a text file containing instructions used to build a Docker image.

---

### Q2. Which instruction specifies the base image?

```dockerfile
FROM
```

---

### Q3. Which instruction copies files into an image?

```dockerfile
COPY
```

---

### Q4. What is the purpose of `WORKDIR`?

It sets the working directory for subsequent Dockerfile instructions.

---

### Q5. What is the difference between CMD and ENTRYPOINT?

`CMD` provides a default command that can be overridden.

`ENTRYPOINT` defines the primary executable for the container.

---

### Q6. Which command builds an image?

```bash
docker build -t myapp:v1 .
```

---

# Production Best Practices

✔ Use official base images.

✔ Pin base image versions.

✔ Use `.dockerignore`.

✔ Minimize image layers.

✔ Run applications as non-root.

✔ Keep Dockerfiles simple and readable.

✔ Optimize instruction order for layer caching.

✔ Scan built images for vulnerabilities.

---

# Key Takeaways

- Dockerfiles automate image creation.
- Every Docker image begins with a base image (`FROM`).
- Instructions are executed sequentially.
- Layer caching makes builds faster.
- Well-designed Dockerfiles improve security, performance and maintainability.

---

# Next Section

## 6.10 Building Docker Images

In the next section, we will learn:

- Building Images
- Image Tags
- Build Context
- Build Cache
- Multi-Stage Builds
- Optimizing Image Size
- Build Arguments
- Production Build Strategies
- Best Practices
- Interview Questions
---

# 6.10 Building Docker Images

In the previous section,

we learned how to write a **Dockerfile**.

Now,

it's time to convert that Dockerfile into an actual **Docker Image**.

This process is called **Building an Image**.

Every DevOps Engineer builds Docker images almost daily.

Whether deploying Java,

Python,

Node.js,

Go,

or .NET,

the workflow remains nearly the same.

---

# What is Image Building?

Image Building is the process of converting a Dockerfile into a Docker Image.

```
Dockerfile

↓

docker build

↓

Docker Image

↓

docker run

↓

Container
```

---

# Docker Build Workflow

```
Application Code

↓

Dockerfile

↓

docker build

↓

Docker Image

↓

Docker Registry

↓

Production Server

↓

Docker Container
```

---

# Build Context

When you execute

```bash
docker build .
```

the

```
.
```

represents the **Build Context**.

Docker sends every file inside the current directory to the Docker Daemon.

Example

```
Project

│

├── Dockerfile

├── app.jar

├── pom.xml

├── src/

└── README.md
```

Everything inside this directory becomes available during the build.

---

# Why Build Context Matters?

Large build contexts increase build time.

Example

```
Project

↓

20 MB

↓

Fast Build

----------------------

Project

↓

5 GB

↓

Slow Build
```

Keep the build context as small as possible.

---

# Building an Image

Example

```bash
docker build -t myapp:v1 .
```

Explanation

```
docker build

↓

Build Image

----------------------

-t

↓

Tag

----------------------

myapp

↓

Repository

----------------------

v1

↓

Version

----------------------

.

↓

Current Directory
```

---

# Build Output

Example

```text
Step 1/6 : FROM ubuntu:24.04

Step 2/6 : RUN apt update

Step 3/6 : COPY app.jar /app/

...

Successfully built
```

Docker executes instructions one by one.

---

# Verify Image

```bash
docker images
```

Example

```text
REPOSITORY

TAG

IMAGE ID

SIZE
```

---

# Build Using Different Dockerfile

Sometimes projects have multiple Dockerfiles.

Example

```bash
docker build -f Dockerfile.dev -t myapp:dev .
```

Production

```bash
docker build -f Dockerfile.prod -t myapp:prod .
```

---

# Tagging Images

Tags identify versions.

Example

```bash
docker build -t company-api:v1 .
```

Later

```bash
docker build -t company-api:v2 .
```

Versions become easy to manage.

---

# Build Without Cache

Normally Docker uses cached layers.

Ignore cache

```bash
docker build --no-cache -t myapp:v1 .
```

Useful when rebuilding everything from scratch.

---

# Why Does Docker Use Cache?

Suppose only one file changes.

Docker reuses previous layers.

Example

```
FROM Ubuntu

↓

Reuse

-------------------

Install Java

↓

Reuse

-------------------

Copy Application

↓

Rebuild
```

This dramatically reduces build time.

---

# Layer Cache Example

Dockerfile

```dockerfile
FROM ubuntu

RUN apt update

RUN apt install nginx -y

COPY index.html /usr/share/nginx/html
```

If only

```
index.html
```

changes,

Docker rebuilds only the final layer.

---

# Build Arguments

Build Arguments allow values to be supplied during image creation.

Dockerfile

```dockerfile
ARG VERSION=1.0
```

Build

```bash
docker build --build-arg VERSION=2.0 -t myapp .
```

Useful for dynamic builds.

---

# Environment Variables vs Build Arguments

| Build Argument | Environment Variable |
|---------------|----------------------|
| Used During Build | Used During Runtime |
| ARG | ENV |
| Not Available After Build (unless copied into ENV) | Available Inside Running Container |

---

# Multi-Stage Builds

Large images consume:

- Disk
- Bandwidth
- Memory

Docker supports **Multi-Stage Builds** to reduce image size.

Example

```
Builder Image

↓

Compile Application

↓

Copy Output

↓

Small Runtime Image
```

Only the required application files are included in the final image.

---

# Example Multi-Stage Build

```dockerfile
FROM maven:3.9-eclipse-temurin-21 AS builder

WORKDIR /app

COPY . .

RUN mvn clean package

FROM eclipse-temurin:21-jre

WORKDIR /app

COPY --from=builder /app/target/app.jar .

ENTRYPOINT ["java","-jar","app.jar"]
```

The final image contains only the runtime and application,

not Maven.

---

# Why Multi-Stage Builds?

Benefits

✔ Smaller Images

✔ Faster Downloads

✔ Improved Security

✔ Faster Deployments

✔ Fewer Dependencies

---

# Build Progress

Docker shows build progress.

```
Load Dockerfile

↓

Load Context

↓

Pull Base Image

↓

Execute Instructions

↓

Create Layers

↓

Create Image

↓

Done
```

---

# Image History

Display image layers.

```bash
docker history myapp:v1
```

Useful for understanding image size and build layers.

---

# Inspect Built Image

```bash
docker inspect myapp:v1
```

Shows:

- Environment Variables
- Entrypoint
- Labels
- Layers
- Metadata

---

# Tag Existing Image

Create another tag.

```bash
docker tag myapp:v1 mycompany/myapp:v1
```

Same image,

different tag.

---

# Build Workflow in CI/CD

```
Developer

↓

Git Push

↓

Jenkins

↓

docker build

↓

Tests

↓

Push Image

↓

Deploy
```

This is one of the most common production workflows.

---

# Optimizing Image Size

Good Practices

✔ Use Alpine Images where appropriate

✔ Remove Temporary Files

✔ Use Multi-Stage Builds

✔ Combine Related RUN Commands

✔ Exclude Unnecessary Files

✔ Use `.dockerignore`

---

# Build Performance Tips

Instead of

```dockerfile
COPY . .
RUN npm install
```

Prefer

```dockerfile
COPY package*.json .

RUN npm install

COPY . .
```

If application source files change,

Docker can reuse the dependency installation layer.

---

# Real Production Example

```
Developer

↓

Dockerfile

↓

docker build

↓

company-api:v1.8

↓

Docker Registry

↓

Kubernetes

↓

Running Pods
```

This process is repeated for every application release.

---

# Common Beginner Mistakes

### Mistake 1

Using `latest` for every build.

Always use meaningful version tags.

---

### Mistake 2

Ignoring `.dockerignore`.

Sending unnecessary files increases build time.

---

### Mistake 3

Using huge base images.

Choose lightweight base images whenever appropriate.

---

### Mistake 4

Disabling cache unnecessarily.

Docker cache significantly speeds up builds.

---

### Mistake 5

Putting frequently changing instructions at the top of the Dockerfile.

Order instructions to maximize cache reuse.

---

# Interview Questions

### Q1. Which command builds a Docker image?

```bash
docker build -t myapp:v1 .
```

---

### Q2. What is Build Context?

The Build Context is the set of files sent to the Docker Daemon during the image build.

---

### Q3. Why does Docker use layer caching?

To reuse unchanged layers and reduce build time.

---

### Q4. What is a Multi-Stage Build?

A build process that uses multiple stages to create a smaller and cleaner final image.

---

### Q5. Which command displays image build history?

```bash
docker history IMAGE_NAME
```

---

### Q6. What is the purpose of `.dockerignore`?

It excludes unnecessary files from the build context, reducing build time and image size.

---

# Production Best Practices

✔ Version every image.

✔ Use Multi-Stage Builds.

✔ Keep images as small as possible.

✔ Use `.dockerignore`.

✔ Reuse Docker cache efficiently.

✔ Pin base image versions.

✔ Scan images for vulnerabilities.

✔ Automate builds through CI/CD pipelines.

---

# Key Takeaways

- `docker build` converts a Dockerfile into a Docker Image.
- The build context contains all files sent to the Docker Daemon.
- Docker uses layer caching to accelerate builds.
- Multi-Stage Builds create smaller and more secure images.
- Efficient image builds improve deployment speed, security and maintainability.

---

# Next Section

## 6.11 Docker Volumes

In the next section, we will learn:

- Why Containers Lose Data
- What are Docker Volumes?
- Named Volumes
- Bind Mounts
- Anonymous Volumes
- Volume Lifecycle
- Sharing Data Between Containers
- Backup & Restore
- Production Best Practices
- Interview Questions
---

# 6.11 Docker Volumes

One of the biggest misunderstandings among beginners is:

> **"If my container stops, my data will always remain safe."**

This is **not true**.

Containers are designed to be **temporary (ephemeral)**.

If a container is deleted,

all data stored inside the container's writable layer is also deleted.

To solve this problem,

Docker provides **Volumes**.

Volumes allow data to survive even after containers are removed.

---

# Why Do We Need Volumes?

Suppose you install MySQL inside a container.

```
Docker Container

↓

Database Files

↓

Customers Data
```

Now imagine you accidentally remove the container.

```
docker rm mysql-container
```

Without a volume,

your database files are lost.

---

# Container Without Volume

```
Container

↓

Application

↓

Database

↓

Delete Container

↓

Everything Lost
```

---

# Container With Volume

```
Container

↓

Volume

↓

Delete Container

↓

Volume Still Exists

↓

Data Safe
```

This is why production databases always use persistent storage.

---

# What is a Docker Volume?

A Docker Volume is a persistent storage mechanism managed by Docker.

Volumes exist **outside the container's writable layer**.

Even if a container is removed,

the volume remains.

---

# Simple Definition

```
Container

↓

Volume

↓

Persistent Storage
```

---

# Real-Life Analogy

Imagine renting a hotel room.

Without a locker,

all your belongings remain inside the room.

If you leave,

everything is gone.

With a locker,

```
Hotel Room

↓

Locker

↓

Belongings Safe
```

Containers are the hotel rooms.

Volumes are the lockers.

---

# Docker Volume Architecture

```
Application

↓

Container

↓

Docker Volume

↓

Host Storage
```

The application writes data to the volume,

not directly to the container.

---

# Types of Docker Storage

Docker supports three major storage options.

```
Volumes

↓

Bind Mounts

↓

tmpfs Mounts
```

Each has different use cases.

---

# Named Volume

Named Volumes are managed by Docker.

Create one.

```bash
docker volume create mysql-data
```

Verify.

```bash
docker volume ls
```

Example

```
DRIVER

local

----------------

VOLUME NAME

mysql-data
```

---

# Anonymous Volume

Docker can create unnamed volumes automatically.

Example

```bash
docker run -v /data nginx
```

Docker generates a random volume name.

Anonymous volumes are generally less convenient to manage.

---

# Bind Mount

Bind Mounts connect a host directory directly to a container.

Example

```bash
docker run -v /home/user/data:/app/data nginx
```

Workflow

```
Host Folder

↓

Container Folder
```

Any changes are immediately visible on both sides.

---

# Volume vs Bind Mount

| Volume | Bind Mount |
|---------|------------|
| Managed by Docker | Managed by Host OS |
| Portable | Host Path Dependent |
| Easier Backup | Uses Existing Directory |
| Preferred for Production | Useful During Development |

---

# Create Volume

```bash
docker volume create myvolume
```

---

# List Volumes

```bash
docker volume ls
```

---

# Inspect Volume

```bash
docker volume inspect myvolume
```

Shows

- Mount Point
- Driver
- Labels
- Metadata

---

# Remove Volume

```bash
docker volume rm myvolume
```

The volume must not be in use by a running container.

---

# Run Container with Volume

Example

```bash
docker run -d \

-v myvolume:/data \

nginx
```

Meaning

```
Docker Volume

↓

Mounted

↓

/data

Inside Container
```

---

# Multiple Containers Sharing a Volume

```
Volume

↓

Container A

↓

Container B

↓

Container C
```

All containers can access the same shared data if appropriate for the application.

---

# MySQL Example

```bash
docker run -d \

--name mysql \

-v mysql-data:/var/lib/mysql \

mysql:8.4
```

Database files remain safe even if the container is recreated.

---

# Nginx Example

```bash
docker run -d \

-v website:/usr/share/nginx/html \

nginx
```

Website files persist outside the container.

---

# Check Volume Usage

```bash
docker system df
```

Displays storage used by:

- Images
- Containers
- Volumes
- Build Cache

---

# Volume Location

Linux

```
/var/lib/docker/volumes/
```

Docker manages this directory automatically.

Avoid modifying files directly unless you understand the implications.

---

# Backup a Volume

One simple method is to mount the volume into a temporary container and archive its contents.

Example

```bash
docker run --rm \

-v myvolume:/data \

-v $(pwd):/backup \

ubuntu \

tar czf /backup/myvolume.tar.gz /data
```

This creates a compressed backup.

---

# Restore a Volume

Restore data into an existing volume.

```bash
docker run --rm \

-v myvolume:/data \

-v $(pwd):/backup \

ubuntu \

tar xzf /backup/myvolume.tar.gz -C /
```

Always verify backups before production restores.

---

# Volume Lifecycle

```
Create Volume

↓

Run Container

↓

Write Data

↓

Stop Container

↓

Remove Container

↓

Volume Remains

↓

Reuse Volume
```

---

# Real Production Example

```
Docker

│

├── MySQL

│      ↓

│   mysql-volume

│

├── Redis

│      ↓

│   redis-volume

│

└── Jenkins

       ↓

   jenkins-volume
```

Each service stores its persistent data in a dedicated volume.

---

# Common Beginner Mistakes

### Mistake 1

Storing important data only inside containers.

Always use volumes for persistent application data.

---

### Mistake 2

Deleting unused-looking volumes without verification.

A stopped application may still depend on them.

---

### Mistake 3

Using Bind Mounts for every production workload.

Named Volumes are generally easier to manage and migrate.

---

### Mistake 4

Backing up containers instead of backing up volumes.

Persistent data resides in the volume.

---

### Mistake 5

Sharing one volume between unrelated applications.

Use separate volumes for different services whenever practical.

---

# Interview Questions

### Q1. What is a Docker Volume?

A Docker Volume is a Docker-managed persistent storage mechanism that exists independently of containers.

---

### Q2. Why are Docker Volumes needed?

Because container writable layers are removed when containers are deleted, while volumes preserve important data.

---

### Q3. Which command creates a volume?

```bash
docker volume create myvolume
```

---

### Q4. Which command lists Docker Volumes?

```bash
docker volume ls
```

---

### Q5. What is the difference between a Volume and a Bind Mount?

Volumes are managed by Docker and are generally preferred for persistent application data.

Bind Mounts map an existing host directory into a container.

---

### Q6. Where are Docker Volumes stored on Linux?

```
/var/lib/docker/volumes/
```

---

# Production Best Practices

✔ Use Named Volumes for databases.

✔ Separate volumes for each application.

✔ Back up volumes regularly.

✔ Avoid storing critical data inside containers.

✔ Monitor disk usage.

✔ Remove unused volumes carefully.

✔ Encrypt sensitive storage where required.

✔ Test backup and restore procedures periodically.

---

# Key Takeaways

- Containers are ephemeral; volumes provide persistence.
- Docker Volumes are managed by Docker.
- Named Volumes are commonly used in production.
- Bind Mounts are useful during development and for specific host integrations.
- Persistent storage is essential for databases and stateful applications.

---

# Next Section

## 6.12 Docker Networking

In the next section, we will learn:

- What is Docker Networking?
- Network Drivers
- Bridge Network
- Host Network
- None Network
- Overlay Network
- Macvlan Network
- Container Communication
- DNS Resolution
- Production Best Practices
- Interview Questions
---

# 6.12 Docker Networking

Containers rarely work alone.

A real application usually consists of multiple services:

- Frontend
- Backend API
- Database
- Redis
- RabbitMQ
- Monitoring

These containers must communicate with each other.

Docker provides this communication using **Docker Networking**.

Without networking,

containers cannot exchange data.

---

# What is Docker Networking?

Docker Networking allows containers to communicate with:

- Other Containers
- The Host Machine
- External Networks
- The Internet

Docker automatically creates network interfaces for containers.

---

# Why Do We Need Docker Networking?

Suppose you have

```
Frontend

↓

Backend

↓

MySQL
```

The frontend must call the backend.

The backend must connect to MySQL.

Without networking,

these applications cannot communicate.

---

# Docker Networking Architecture

```
Docker Host

│

├── Frontend Container

│

├── Backend Container

│

└── MySQL Container
```

Docker connects these containers using networks.

---

# Network Drivers

Docker provides multiple network drivers.

```
Bridge

↓

Host

↓

None

↓

Overlay

↓

Macvlan
```

Each driver is designed for different use cases.

---

# Bridge Network

Bridge is the default Docker network.

When you run

```bash
docker run nginx
```

Docker automatically attaches the container to the default bridge network.

---

# Bridge Architecture

```
Container A

↓

Bridge Network

↓

Container B

↓

Container C
```

Containers connected to the same bridge network can communicate.

---

# List Networks

```bash
docker network ls
```

Example

```
NETWORK ID

NAME

bridge

host

none
```

---

# Inspect Network

```bash
docker network inspect bridge
```

Displays

- Connected Containers
- Subnet
- Gateway
- Driver

---

# Create Network

```bash
docker network create app-network
```

Verify

```bash
docker network ls
```

---

# Run Container on Network

```bash
docker run -d \

--network app-network \

--name web nginx
```

The container joins the specified network.

---

# Connect Existing Container

```bash
docker network connect app-network CONTAINER_ID
```

A container can be connected to multiple networks.

---

# Disconnect Container

```bash
docker network disconnect app-network CONTAINER_ID
```

---

# Remove Network

```bash
docker network rm app-network
```

The network must not be in use.

---

# Container Communication

Suppose

```
Container A

↓

Container B
```

Both containers are connected to

```
app-network
```

Container A can communicate with Container B using its container name.

Example

```
http://backend:8080
```

Docker automatically provides DNS-based name resolution.

---

# Docker DNS

Every Docker network has an internal DNS service.

Example

```
frontend

↓

backend

↓

mysql
```

Containers can use these names instead of IP addresses.

This makes applications easier to configure.

---

# Host Network

Host networking allows a container to share the host's network stack.

Example

```bash
docker run --network host nginx
```

Architecture

```
Host Network

↓

Container

↓

Same Network Stack
```

No network isolation exists between the host and the container.

---

# When to Use Host Network

Useful when

- Maximum Performance is required
- Low Network Latency is important
- Port Mapping should be avoided

Host networking is available on Linux but behaves differently on Docker Desktop.

---

# None Network

A container can also be started without networking.

Example

```bash
docker run --network none nginx
```

The container has:

- No Internet
- No Container Communication
- Only Loopback Interface

Useful for highly isolated workloads.

---

# Overlay Network

Overlay networks connect containers running on different Docker hosts.

Architecture

```
Host-1

↓

Overlay Network

↓

Host-2

↓

Overlay Network

↓

Host-3
```

Overlay networks are commonly used with:

- Docker Swarm
- Multi-host deployments

---

# Macvlan Network

Macvlan allows containers to appear as physical devices on the network.

Example

```
Switch

↓

Container-1

↓

Container-2

↓

Container-3
```

Each container receives its own MAC address.

Useful for applications requiring direct Layer-2 network access.

---

# Port Mapping

Containers are isolated.

To access an application from outside,

publish the container port.

Example

```bash
docker run -d -p 8080:80 nginx
```

Meaning

```
Host

8080

↓

Container

80
```

Open

```
http://SERVER-IP:8080
```

---

# Exposed Ports vs Published Ports

Dockerfile

```dockerfile
EXPOSE 80
```

Only documents the application's listening port.

Host access still requires:

```bash
docker run -p 8080:80
```

---

# Network Communication Example

```
Browser

↓

Nginx Container

↓

Spring Boot Container

↓

MySQL Container
```

Each service communicates over the Docker network.

---

# Inspect Container Network

```bash
docker inspect CONTAINER_ID
```

Shows

- IP Address
- Gateway
- MAC Address
- Connected Networks

---

# Display Network Usage

Docker itself does not provide bandwidth statistics.

Use Linux tools such as:

```bash
ip addr

ip route

ss -tulpn
```

or monitoring platforms like Prometheus.

---

# Network Cleanup

Remove unused networks.

```bash
docker network prune
```

Be careful,

unused networks will be deleted.

---

# Production Architecture

```
Internet

↓

Load Balancer

↓

Nginx Container

↓

Backend Network

│

├── API Container

├── Redis

├── RabbitMQ

└── MySQL
```

Applications are grouped into logical networks.

---

# Network Best Practices

Separate networks for:

- Frontend
- Backend
- Database

Example

```
Frontend Network

↓

Nginx

↓

Backend Network

↓

API

↓

Database Network

↓

MySQL
```

This improves isolation and security.

---

# Common Beginner Mistakes

### Mistake 1

Using the default bridge network for every application.

Create dedicated networks for each project.

---

### Mistake 2

Connecting databases directly to public-facing networks.

Keep databases on private Docker networks.

---

### Mistake 3

Using container IP addresses in application configuration.

Use container names instead.

---

### Mistake 4

Publishing every container port.

Only expose ports that must be accessible externally.

---

### Mistake 5

Deleting Docker networks without checking whether containers still depend on them.

---

# Interview Questions

### Q1. What is Docker Networking?

Docker Networking enables communication between containers, the host and external networks.

---

### Q2. What is the default Docker network?

The default network driver is:

```
Bridge
```

---

### Q3. Which command creates a Docker network?

```bash
docker network create app-network
```

---

### Q4. What is Host Networking?

Host Networking allows a container to share the host's network stack.

---

### Q5. Which network driver provides no networking?

```
none
```

---

### Q6. Why should container names be used instead of IP addresses?

Docker automatically provides DNS-based name resolution, while container IP addresses can change.

---

# Production Best Practices

✔ Create dedicated networks for each application.

✔ Isolate frontend, backend and database services.

✔ Publish only required ports.

✔ Use container names for communication.

✔ Keep databases on private networks.

✔ Monitor network traffic.

✔ Remove unused Docker networks periodically.

✔ Document network architecture.

---

# Key Takeaways

- Docker Networking enables communication between containers.
- Bridge is the default network driver.
- Docker provides built-in DNS for container name resolution.
- Overlay networks support multi-host communication.
- Proper network design improves security, scalability and maintainability.

---

# Next Section

## 6.13 Docker Compose

In the next section, we will learn:

- What is Docker Compose?
- Why Docker Compose?
- docker-compose.yml
- Services
- Networks
- Volumes
- Environment Variables
- Running Multi-Container Applications
- Production Best Practices
- Interview Questions
---

# 6.13 Docker Compose

So far,

we have been running containers one by one.

Example

```bash
docker run nginx

docker run mysql

docker run redis
```

Imagine an application with

- Frontend
- Backend
- MySQL
- Redis
- RabbitMQ
- Prometheus

Starting every container manually becomes difficult.

Docker solves this problem using **Docker Compose**.

Docker Compose allows you to define an entire application in a single YAML file.

---

# What is Docker Compose?

Docker Compose is a tool used to define and run **multi-container Docker applications**.

Instead of executing multiple `docker run` commands,

you define everything inside one file:

```
compose.yaml
```

or

```
docker-compose.yml
```

Then start everything using a single command.

---

# Why Docker Compose?

Without Compose

```
docker run mysql

↓

docker run redis

↓

docker run backend

↓

docker run frontend
```

Many commands must be executed manually.

---

With Compose

```
docker compose up
```

Everything starts automatically.

---

# Docker Compose Workflow

```
compose.yaml

↓

docker compose up

↓

Networks

↓

Volumes

↓

Containers

↓

Application Ready
```

---

# Real Production Example

An online shopping application contains

- Frontend
- Backend API
- MySQL
- Redis

Instead of creating each container manually,

Docker Compose creates the complete environment.

```
compose.yaml

↓

Frontend

↓

Backend

↓

Redis

↓

MySQL
```

---

# Docker Compose File

Compose uses YAML.

Example

```yaml
services:

  web:

    image: nginx
```

YAML is indentation-sensitive.

Use spaces,

not tabs.

---

# Basic Compose Example

```yaml
services:

  nginx:

    image: nginx

    ports:

      - "80:80"
```

Start

```bash
docker compose up
```

---

# Services

Every application is defined as a service.

Example

```yaml
services:

  frontend:

    image: nginx

  backend:

    image: company-api

  mysql:

    image: mysql:8.4
```

Each service becomes a container.

---

# Ports

Publish ports.

```yaml
ports:

  - "8080:80"
```

Meaning

```
Host

8080

↓

Container

80
```

---

# Environment Variables

Example

```yaml
environment:

  MYSQL_ROOT_PASSWORD: admin123
```

Application reads these values during runtime.

---

# Volumes

Persistent storage.

```yaml
volumes:

  - mysql-data:/var/lib/mysql
```

Database data remains safe even after container recreation.

---

# Networks

Create isolated communication.

```yaml
networks:

  - app-network
```

All services connected to this network can communicate.

---

# Restart Policy

Example

```yaml
restart: unless-stopped
```

Other options include:

```
no

always

on-failure

unless-stopped
```

Choose the policy that matches your operational requirements.

---

# Container Name

```yaml
container_name: frontend
```

Instead of random names,

Docker uses the specified name.

---

# Build from Dockerfile

Instead of downloading an image,

Compose can build one.

```yaml
build:

  context: .
```

Docker executes

```
docker build
```

automatically.

---

# Complete Example

```yaml
services:

  frontend:

    image: nginx

    ports:

      - "80:80"

  mysql:

    image: mysql:8.4

    environment:

      MYSQL_ROOT_PASSWORD: admin123

    volumes:

      - mysql-data:/var/lib/mysql

volumes:

  mysql-data:
```

---

# Start Application

Foreground

```bash
docker compose up
```

Background

```bash
docker compose up -d
```

---

# Stop Application

```bash
docker compose down
```

Containers,

networks and other resources created by Compose are removed.

Named volumes are retained unless explicitly removed.

---

# View Running Services

```bash
docker compose ps
```

---

# View Logs

```bash
docker compose logs
```

Follow logs

```bash
docker compose logs -f
```

---

# Restart Services

```bash
docker compose restart
```

Restart a specific service.

```bash
docker compose restart frontend
```

---

# Build Services

```bash
docker compose build
```

Rebuild images.

```bash
docker compose build --no-cache
```

---

# Pull Images

```bash
docker compose pull
```

Downloads the latest versions of referenced images.

---

# Execute Commands

```bash
docker compose exec frontend bash
```

If Bash is unavailable.

```bash
docker compose exec frontend sh
```

---

# Scaling Services

Example

```bash
docker compose up --scale backend=3
```

Creates

```
Backend-1

↓

Backend-2

↓

Backend-3
```

Load balancing typically requires additional configuration.

---

# Dependency Order

Compose supports startup dependencies.

Example

```yaml
depends_on:

  - mysql
```

This controls startup order,

but it does not guarantee that MySQL is fully ready to accept connections.

Applications should still implement health checks or retry logic.

---

# Compose Project

```
compose.yaml

↓

Docker Network

↓

Docker Volumes

↓

Docker Containers

↓

Application
```

Compose manages all related resources as one project.

---

# Production Workflow

```
Git

↓

CI/CD

↓

Docker Build

↓

Docker Registry

↓

Production

↓

docker compose up
```

Many small and medium deployments use this workflow.

---

# Directory Structure

```
project/

│

├── compose.yaml

├── Dockerfile

├── app/

├── config/

└── .env
```

A clean directory structure improves maintainability.

---

# .env File

Store configuration separately.

Example

```text
MYSQL_PASSWORD=admin123

APP_PORT=8080
```

Compose automatically loads variables from a `.env` file in the project directory.

---

# Variable Usage

Example

```yaml
environment:

  MYSQL_PASSWORD: ${MYSQL_PASSWORD}
```

Values come from

```
.env
```

---

# Common Beginner Mistakes

### Mistake 1

Using tabs instead of spaces in YAML.

YAML requires spaces for indentation.

---

### Mistake 2

Hardcoding passwords inside the Compose file.

Use environment variables or secrets where appropriate.

---

### Mistake 3

Running databases without persistent volumes.

Always configure storage for stateful services.

---

### Mistake 4

Assuming `depends_on` waits for application readiness.

It controls startup order only.

---

### Mistake 5

Running every service on the default network without planning network isolation.

---

# Interview Questions

### Q1. What is Docker Compose?

Docker Compose is a tool used to define and manage multi-container Docker applications using a YAML configuration file.

---

### Q2. Which command starts all services?

```bash
docker compose up
```

---

### Q3. Which command starts services in the background?

```bash
docker compose up -d
```

---

### Q4. Which command stops a Compose application?

```bash
docker compose down
```

---

### Q5. What is the purpose of `depends_on`?

It defines startup dependencies between services but does not guarantee application readiness.

---

### Q6. Which file defines a Docker Compose application?

```
compose.yaml
```

(or the legacy `docker-compose.yml`)

---

# Production Best Practices

✔ Keep Compose files simple and modular.

✔ Store configuration in `.env` files.

✔ Use named volumes for persistent data.

✔ Create dedicated networks.

✔ Avoid hardcoded credentials.

✔ Build immutable images.

✔ Use restart policies.

✔ Version-control Compose files.

---

# Key Takeaways

- Docker Compose simplifies multi-container application management.
- A single YAML file defines services, networks and volumes.
- `docker compose up` starts an entire application stack.
- Compose improves development, testing and small-to-medium production deployments.
- Proper Compose design leads to cleaner, more maintainable infrastructure.

---

# Next Section

## 6.14 Docker Hub

In the next section, we will learn:

- What is Docker Hub?
- Public vs Private Repositories
- Pulling Images
- Pushing Images
- Image Tags
- Repository Management
- Authentication
- Production Best Practices
- Interview Questions
---

# 6.14 Docker Hub

So far,

we have been downloading images like:

```bash
docker pull nginx

docker pull ubuntu

docker pull redis
```

But where do these images come from?

The answer is:

# Docker Hub

Docker Hub is the world's largest public repository for Docker Images.

It allows developers and organizations to:

- Store Images
- Share Images
- Download Images
- Version Images
- Collaborate on Projects

---

# What is Docker Hub?

Docker Hub is an online **Docker Image Registry**.

Think of it as **GitHub for Docker Images.**

```
GitHub

↓

Stores Source Code

-----------------------

Docker Hub

↓

Stores Docker Images
```

---

# Why Do We Need Docker Hub?

Suppose your company builds

```
Company API
```

Without Docker Hub

```
Developer

↓

Build Image

↓

Copy Image Manually

↓

Production
```

Very inconvenient.

---

With Docker Hub

```
Developer

↓

Build Image

↓

Push Image

↓

Docker Hub

↓

Production Server

↓

Pull Image
```

Deployment becomes much easier.

---

# Docker Hub Workflow

```
Developer

↓

docker build

↓

Docker Image

↓

docker push

↓

Docker Hub

↓

docker pull

↓

Production Server
```

---

# Docker Registry

Docker Hub is one example of a Docker Registry.

Other registries include:

- Docker Hub
- Amazon Elastic Container Registry (ECR)
- Azure Container Registry (ACR)
- Google Artifact Registry
- GitHub Container Registry (GHCR)
- Harbor

---

# Public Repository

Anyone can download images.

Example

```bash
docker pull nginx
```

Downloads

```
Docker Hub

↓

nginx

↓

Local Machine
```

---

# Private Repository

Private repositories require authentication.

Example

```
Company

↓

Private Images

↓

Only Authorized Users
```

Useful for proprietary applications.

---

# Create Docker Hub Account

Visit

```
hub.docker.com
```

Create

- Username
- Password
- Email

After verification,

you can create repositories.

---

# Login to Docker Hub

```bash
docker login
```

Example

```text
Username:

Password:

Login Succeeded
```

Docker stores authentication credentials securely on your system.

---

# Logout

```bash
docker logout
```

---

# Pull Image

Download an image.

```bash
docker pull nginx
```

Specific Version

```bash
docker pull nginx:1.27
```

---

# Search Images

```bash
docker search mysql
```

Displays

- Repository
- Description
- Stars
- Official Image

---

# Build Custom Image

Example

```bash
docker build -t myapp:v1 .
```

---

# Tag Image

Before pushing,

tag the image.

```bash
docker tag myapp:v1 username/myapp:v1
```

Example

```
Repository

↓

username/myapp

↓

Tag

↓

v1
```

---

# Push Image

Upload to Docker Hub.

```bash
docker push username/myapp:v1
```

Workflow

```
Local Image

↓

Docker Hub

↓

Cloud Repository
```

---

# Verify Uploaded Image

After pushing,

your repository appears on Docker Hub.

Example

```
username

↓

Repositories

↓

myapp
```

---

# Pull Your Own Image

Any authorized machine can now download it.

```bash
docker pull username/myapp:v1
```

---

# Image Versioning

Never overwrite production images unnecessarily.

Example

```
v1.0

↓

v1.1

↓

v1.2

↓

v2.0
```

Versioning simplifies rollbacks.

---

# Latest Tag

Docker automatically assumes

```
latest
```

if no tag is specified.

Example

```bash
docker pull nginx
```

is equivalent to

```bash
docker pull nginx:latest
```

Production environments should usually use explicit version tags instead of relying on `latest`.

---

# Repository Structure

```
Docker Hub

│

├── username

│

├── project-frontend

│

├── project-backend

│

└── mysql-backup
```

---

# Image Workflow

```
Dockerfile

↓

docker build

↓

docker tag

↓

docker push

↓

Docker Hub

↓

docker pull

↓

Production
```

---

# Updating an Image

Suppose version 2 is ready.

```
Build

↓

Tag

↓

Push

↓

Production Pulls New Version
```

Containers can then be recreated using the updated image.

---

# Delete Repository

Repositories can be deleted through the Docker Hub web interface.

Be careful,

because deleting a repository removes hosted image tags.

---

# Repository Visibility

Two options

```
Public

↓

Anyone Can Pull

--------------------

Private

↓

Authorized Users Only
```

---

# Docker Hub in CI/CD

```
Git Push

↓

CI/CD Pipeline

↓

Build Image

↓

Push Image

↓

Docker Hub

↓

Production Pull
```

This is a common software delivery workflow.

---

# Production Example

```
Developer

↓

GitHub

↓

Jenkins

↓

Docker Build

↓

Docker Hub

↓

AWS Server

↓

docker pull

↓

docker run
```

---

# Docker Hub Best Practices

✔ Use meaningful repository names.

✔ Version images.

✔ Remove outdated images when appropriate.

✔ Use private repositories for proprietary software.

✔ Automate image pushes through CI/CD.

---

# Common Beginner Mistakes

### Mistake 1

Using only the `latest` tag.

Always create versioned tags.

---

### Mistake 2

Pushing images without testing them.

Verify images before publishing.

---

### Mistake 3

Uploading sensitive configuration files inside Docker images.

Use environment variables or secrets instead.

---

### Mistake 4

Forgetting to authenticate before pushing.

Run

```bash
docker login
```

first.

---

### Mistake 5

Keeping unused image versions forever.

Clean old tags periodically according to your retention policy.

---

# Interview Questions

### Q1. What is Docker Hub?

Docker Hub is a cloud-based registry used to store, share and distribute Docker images.

---

### Q2. Which command logs into Docker Hub?

```bash
docker login
```

---

### Q3. Which command uploads an image?

```bash
docker push username/image:tag
```

---

### Q4. Which command downloads an image?

```bash
docker pull IMAGE_NAME
```

---

### Q5. Why should production images use version tags instead of `latest`?

Version tags provide predictable deployments and simplify rollbacks.

---

### Q6. What is the difference between a Public and a Private repository?

Public repositories are accessible to everyone, while private repositories require authorization.

---

# Production Best Practices

✔ Use semantic versioning.

✔ Automate pushes through CI/CD.

✔ Scan images before publishing.

✔ Use private repositories for internal applications.

✔ Restrict repository permissions.

✔ Remove deprecated image versions.

✔ Document release versions.

✔ Protect credentials used for registry access.

---

# Key Takeaways

- Docker Hub is the default public Docker registry.
- Images can be pushed and pulled from Docker Hub.
- Version tags improve deployment reliability.
- Public and private repositories support different collaboration needs.
- Docker Hub integrates seamlessly with modern CI/CD pipelines.

---

# Next Section

## 6.15 Multi-Container Applications

In the next section, we will learn:

- What are Multi-Container Applications?
- Service Separation
- Frontend, Backend and Database Architecture
- Container Communication
- Shared Networks
- Shared Volumes
- Real Production Architecture
- Best Practices
- Interview Questions
---

# 6.15 Multi-Container Applications

In the real world,

applications rarely consist of a single container.

Modern applications are divided into multiple independent services.

For example,

an E-Commerce application may have:

- Frontend
- Backend API
- Authentication Service
- Payment Service
- Notification Service
- Redis
- Database

Each service runs inside its own Docker container.

This architecture is called a **Multi-Container Application**.

---

# Why Multiple Containers?

Instead of placing everything inside one container,

each component runs independently.

Instead of

```
One Huge Container

↓

Frontend

↓

Backend

↓

Database

↓

Redis
```

Use

```
Frontend

↓

Backend

↓

Database

↓

Redis

↓

Separate Containers
```

This approach is easier to maintain and scale.

---

# Benefits of Multi-Container Applications

✔ Independent Deployment

✔ Better Scalability

✔ Fault Isolation

✔ Easier Updates

✔ Better Resource Utilization

✔ Team Independence

✔ Cloud Native Architecture

---

# Simple Architecture

```
Browser

↓

Frontend

↓

Backend API

↓

Database
```

Each block represents a separate container.

---

# Typical Production Architecture

```
Users

↓

Load Balancer

↓

Frontend Container

↓

Backend API

↓

Redis

↓

RabbitMQ

↓

MySQL
```

Each service has a dedicated responsibility.

---

# Service Separation

Example

```
Frontend

↓

React

-------------------

Backend

↓

Spring Boot

-------------------

Database

↓

MySQL

-------------------

Cache

↓

Redis
```

Every service can be updated independently.

---

# Why Not One Big Container?

Suppose one application contains:

- Nginx
- Java
- MySQL
- Redis
- RabbitMQ

If MySQL crashes,

the entire container may require restarting.

Separate containers improve fault isolation.

---

# Container Communication

Containers communicate over Docker Networks.

Example

```
Frontend

↓

Backend

↓

MySQL
```

The frontend communicates with the backend using:

```
http://backend:8080
```

The backend communicates with:

```
mysql:3306
```

Docker DNS resolves container names automatically.

---

# Shared Network

```
app-network

│

├── frontend

├── backend

├── redis

└── mysql
```

Containers connected to the same network can communicate securely.

---

# Shared Volumes

Some applications require persistent storage.

Example

```
MySQL

↓

Volume

↓

Persistent Data
```

Application containers remain stateless whenever possible.

---

# Example Compose File

```yaml
services:

  frontend:

    image: nginx

  backend:

    image: company-api

  redis:

    image: redis

  mysql:

    image: mysql:8.4
```

Each service runs in its own container.

---

# Request Flow

```
Browser

↓

Frontend

↓

Backend API

↓

Redis

↓

MySQL

↓

Response
```

Each service performs a specific function.

---

# Scaling Individual Services

Suppose the Backend receives heavy traffic.

Instead of scaling the entire application,

scale only the backend.

```
Frontend

↓

Backend-1

↓

Backend-2

↓

Backend-3

↓

Database
```

This improves efficiency.

---

# Independent Deployment

Suppose only the frontend changes.

Deploy only:

```
Frontend Container
```

The backend,

database,

and Redis remain unchanged.

---

# Fault Isolation

Suppose Redis crashes.

```
Frontend

↓

Backend

↓

Redis (Stopped)

↓

Database
```

Only the Redis service is affected.

Other services continue running if designed to handle Redis unavailability.

---

# Logging

Each container has its own logs.

```
Frontend Logs

↓

Backend Logs

↓

Redis Logs

↓

Database Logs
```

Troubleshooting becomes easier.

---

# Monitoring

Production systems monitor every container separately.

Common metrics include:

- CPU Usage
- Memory Usage
- Disk Usage
- Network Traffic
- Restart Count
- Health Status

---

# Health Checks

Applications should expose health endpoints.

Example

```
/health

↓

HTTP 200
```

Container orchestration platforms can automatically restart unhealthy services.

---

# Environment Variables

Each service has its own configuration.

Example

Frontend

```
API_URL=http://backend:8080
```

Backend

```
DB_HOST=mysql

REDIS_HOST=redis
```

---

# Real Production Example

Online Banking

```
Users

↓

Load Balancer

↓

Nginx

↓

Authentication API

↓

Account API

↓

Transaction API

↓

Notification Service

↓

Redis

↓

PostgreSQL
```

Every service is deployed independently.

---

# Microservices Architecture

Docker is widely used with Microservices.

```
Gateway

↓

Authentication

↓

Orders

↓

Payments

↓

Inventory

↓

Notifications
```

Each service has:

- Its own container
- Its own deployment
- Its own scaling strategy

---

# Development Workflow

```
Developer

↓

Code

↓

Docker Build

↓

Docker Compose

↓

Application Running
```

Developers can reproduce the complete environment on their local machines.

---

# Production Workflow

```
Git

↓

CI/CD

↓

Docker Image

↓

Container Registry

↓

Production

↓

Multiple Containers
```

---

# Security

Each container should have only the permissions it needs.

Examples

✔ Separate Networks

✔ Non-root Users

✔ Secrets Management

✔ Read-only Filesystems (where appropriate)

✔ Least Privilege

---

# Common Beginner Mistakes

### Mistake 1

Running every service inside one container.

Keep services separate.

---

### Mistake 2

Using one shared database volume for unrelated applications.

Use dedicated storage for each application.

---

### Mistake 3

Using hardcoded IP addresses.

Use Docker DNS and service names.

---

### Mistake 4

Ignoring health checks.

Applications should report their health status.

---

### Mistake 5

Scaling the entire application instead of only the busy service.

Scale individual services whenever possible.

---

# Interview Questions

### Q1. What is a Multi-Container Application?

A Multi-Container Application consists of multiple containers, each running a separate service that works together as one application.

---

### Q2. Why use multiple containers instead of one?

Multiple containers improve scalability, maintainability, fault isolation and independent deployment.

---

### Q3. How do containers communicate?

Containers communicate through Docker Networks using container or service names.

---

### Q4. Which tool is commonly used to manage Multi-Container Applications?

Docker Compose.

---

### Q5. Why should databases run in separate containers?

Databases have different storage, backup and scaling requirements than application services.

---

### Q6. What are the advantages of service separation?

- Independent Deployment
- Easier Scaling
- Better Fault Isolation
- Simpler Maintenance
- Improved Resource Utilization

---

# Production Best Practices

✔ One service per container.

✔ Use dedicated Docker networks.

✔ Store persistent data in volumes.

✔ Configure health checks.

✔ Monitor each container independently.

✔ Use environment variables for configuration.

✔ Implement centralized logging.

✔ Deploy services independently whenever possible.

---

# Key Takeaways

- Modern applications usually consist of multiple containers.
- Each container performs a single responsibility.
- Docker Networks enable service communication.
- Docker Volumes provide persistent storage for stateful services.
- Multi-Container Applications are the foundation of modern cloud-native architectures.

---

# Next Section

## 6.16 Docker Logs & Monitoring

In the next section, we will learn:

- Docker Logs
- Log Drivers
- Monitoring Containers
- Docker Stats
- Health Checks
- Resource Monitoring
- Centralized Logging
- Production Monitoring Tools
- Best Practices
- Interview Questions
---

# 6.16 Docker Logs & Monitoring

Running containers is only the first step.

In production,

you must continuously monitor your containers to answer questions such as:

- Is the application healthy?
- Is CPU usage too high?
- Is memory running out?
- Are users receiving errors?
- Why did a container stop?
- Is disk space almost full?

Docker provides several built-in tools for logging and monitoring,

and it also integrates with enterprise monitoring platforms.

---

# Why Monitoring is Important?

Suppose your application suddenly becomes slow.

Without monitoring,

you don't know whether the problem is:

- CPU
- Memory
- Network
- Database
- Disk
- Application Code

Monitoring helps identify the root cause quickly.

---

# Monitoring Workflow

```
Application

↓

Container

↓

Logs

↓

Metrics

↓

Alerts

↓

Engineer

↓

Fix Issue
```

---

# Docker Logs

Every container generates logs.

These logs include:

- Startup Messages
- Errors
- Warnings
- Requests
- Debug Information

---

# View Container Logs

```bash
docker logs CONTAINER_ID
```

Example

```bash
docker logs nginx
```

---

# Follow Logs

Display logs continuously.

```bash
docker logs -f nginx
```

Useful during troubleshooting.

---

# Display Last Few Lines

```bash
docker logs --tail 50 nginx
```

Only the most recent 50 lines are displayed.

---

# Display Logs with Timestamps

```bash
docker logs -t nginx
```

Example

```
2026-07-01T09:15:42Z
```

Timestamps simplify troubleshooting.

---

# Docker Log Flow

```
Application

↓

STDOUT / STDERR

↓

Docker Logging Driver

↓

Log File
```

Applications should normally write logs to standard output.

---

# Docker Logging Drivers

Docker supports multiple logging drivers.

Examples

- json-file
- journald
- syslog
- fluentd
- gelf
- awslogs
- splunk

---

# Default Logging Driver

Check the logging driver.

```bash
docker info
```

Look for

```
Logging Driver
```

The default on many Linux installations is:

```
json-file
```

---

# Configure Logging Driver

Example

```bash
docker run \

--log-driver json-file \

nginx
```

---

# Log Rotation

Without log rotation,

log files continue growing.

Example

```bash
docker run \

--log-opt max-size=10m \

--log-opt max-file=5 \

nginx
```

Meaning

```
Maximum Log Size

↓

10 MB

Maximum Files

↓

5
```

Older logs are rotated automatically.

---

# Container Resource Monitoring

Docker provides real-time monitoring.

```bash
docker stats
```

Displays:

- CPU Usage
- Memory Usage
- Network I/O
- Block I/O
- PIDs

---

# Example Output

```
CONTAINER

CPU %

MEMORY %

NETWORK

BLOCK I/O
```

Refreshes continuously.

---

# Inspect Container

```bash
docker inspect nginx
```

Displays

- Environment Variables
- Networks
- Mounts
- Restart Policy
- Labels
- Metadata

---

# Running Processes

```bash
docker top nginx
```

Shows processes running inside the container.

---

# Container Events

View live Docker events.

```bash
docker events
```

Example

```
Container Started

↓

Container Stopped

↓

Container Removed
```

Useful during debugging.

---

# Health Checks

Applications should expose health endpoints.

Example

```
GET

/health

↓

200 OK
```

Docker can periodically execute health checks.

Example

```dockerfile
HEALTHCHECK CMD curl -f http://localhost:8080/health || exit 1
```

---

# Check Health Status

```bash
docker inspect nginx
```

Look for

```
Health

↓

healthy
```

Possible states include:

- healthy
- unhealthy
- starting

---

# CPU Monitoring

High CPU usage may indicate:

- Infinite Loops
- Heavy Traffic
- Expensive Queries
- Poor Application Performance

Monitor using

```bash
docker stats
```

---

# Memory Monitoring

Containers have memory limits.

Monitor:

```
Memory Usage

↓

Memory Limit
```

High memory usage may eventually trigger an Out Of Memory (OOM) kill.

---

# Disk Usage

Check Docker disk usage.

```bash
docker system df
```

Shows usage for:

- Images
- Containers
- Volumes
- Build Cache

---

# Container Restart Count

Check whether a container repeatedly restarts.

```bash
docker ps
```

or

```bash
docker inspect CONTAINER_ID
```

Frequent restarts usually indicate application failures.

---

# Monitoring Multiple Containers

```
Docker Host

│

├── Frontend

├── Backend

├── Redis

├── MySQL

└── Prometheus
```

Every container should be monitored independently.

---

# Centralized Logging

Instead of checking logs on every server,

organizations centralize logs.

```
Containers

↓

Log Collector

↓

Central Log Server

↓

Dashboard
```

Benefits

- Faster Search
- Long-Term Storage
- Easier Troubleshooting

---

# Popular Logging Tools

Examples include:

- ELK Stack (Elasticsearch, Logstash, Kibana)
- OpenSearch
- Grafana Loki
- Fluent Bit
- Fluentd

---

# Popular Monitoring Tools

Common monitoring platforms:

- Prometheus
- Grafana
- Datadog
- Zabbix
- Nagios

These tools collect metrics and generate dashboards and alerts.

---

# Alerting

Monitoring is useful only if important events generate alerts.

Examples

```
CPU > 90%

↓

Alert

--------------------

Memory > 85%

↓

Alert

--------------------

Container Down

↓

Alert
```

Alerts enable faster incident response.

---

# Production Monitoring Architecture

```
Containers

↓

Prometheus

↓

Grafana

↓

Alerts

↓

DevOps Engineer
```

This architecture is common in Kubernetes environments.

---

# Log Management Best Practices

✔ Rotate Logs

✔ Archive Logs

✔ Centralize Logs

✔ Retain Logs According to Policy

✔ Protect Sensitive Data

---

# Real Production Example

```
Users

↓

Nginx

↓

Backend

↓

Docker Logs

↓

Fluent Bit

↓

Elasticsearch

↓

Kibana
```

Operations teams search logs through a centralized dashboard.

---

# Common Beginner Mistakes

### Mistake 1

Never checking container logs.

Always inspect logs first during troubleshooting.

---

### Mistake 2

Allowing log files to grow indefinitely.

Enable log rotation.

---

### Mistake 3

Ignoring unhealthy containers.

Investigate repeated health check failures promptly.

---

### Mistake 4

Monitoring only CPU.

Monitor memory, storage, network and application health as well.

---

### Mistake 5

Keeping logs only on individual servers.

Centralized logging simplifies operations.

---

# Interview Questions

### Q1. Which command displays container logs?

```bash
docker logs CONTAINER_ID
```

---

### Q2. Which command displays real-time resource usage?

```bash
docker stats
```

---

### Q3. Which command shows Docker events?

```bash
docker events
```

---

### Q4. Why are Health Checks important?

Health checks help detect unhealthy containers so they can be restarted or investigated automatically.

---

### Q5. Name three popular monitoring tools.

- Prometheus
- Grafana
- Datadog

---

### Q6. Why is centralized logging important?

It simplifies searching, troubleshooting, auditing and long-term log retention.

---

# Production Best Practices

✔ Enable log rotation.

✔ Centralize logs.

✔ Monitor CPU, memory and disk.

✔ Configure health checks.

✔ Set up alerts for critical failures.

✔ Monitor restart counts.

✔ Protect sensitive information in logs.

✔ Review monitoring dashboards regularly.

---

# Key Takeaways

- Logging records application events for troubleshooting.
- Monitoring tracks container health and resource usage.
- `docker logs` and `docker stats` are essential day-to-day commands.
- Centralized logging and monitoring are standard production practices.
- Effective monitoring helps detect and resolve problems before they impact users.

---

# Next Section

## 6.17 Docker Security

In the next section, we will learn:

- Docker Security Fundamentals
- Container Isolation
- Running as Non-Root
- Image Scanning
- Secrets Management
- Docker Bench Security
- Security Best Practices
- Production Hardening
- Interview Questions
---

# 6.17 Docker Security

Docker makes application deployment fast and efficient.

However,

running containers without proper security can expose your application,

servers,

and customer data to attackers.

Security should never be considered an optional feature.

It should be part of every Docker deployment from development to production.

---

# Why Docker Security Matters?

Imagine an attacker gains access to one container.

Without proper isolation,

they may attempt to:

- Access host files
- Access other containers
- Read sensitive data
- Escalate privileges
- Install malware
- Move laterally inside the infrastructure

Proper Docker security greatly reduces these risks.

---

# Security Layers

```
Internet

↓

Firewall

↓

Load Balancer

↓

Host OS

↓

Docker Engine

↓

Container

↓

Application
```

Security must exist at every layer.

---

# Docker Security Principles

Docker security is based on:

- Least Privilege
- Isolation
- Immutable Infrastructure
- Image Security
- Secrets Management
- Continuous Monitoring

---

# Container Isolation

Containers isolate:

- Processes
- Filesystems
- Networks
- Users
- Environment Variables

Isolation helps prevent one application from interfering with another.

---

# Linux Kernel Features

Docker relies on Linux technologies such as:

- Namespaces
- Control Groups (cgroups)
- Capabilities
- Seccomp
- AppArmor
- SELinux

These mechanisms provide isolation and resource control.

---

# Never Run as Root

One of the biggest Docker security mistakes is running applications as the root user.

Bad Example

```dockerfile
FROM ubuntu

CMD ["myapp"]
```

---

Better Example

```dockerfile
FROM ubuntu

RUN useradd -m appuser

USER appuser

CMD ["myapp"]
```

Applications should run with the minimum privileges required.

---

# Principle of Least Privilege

Grant only the permissions necessary.

Instead of

```
Full Access
```

Use

```
Only Required Permissions
```

This limits the impact of a compromise.

---

# Read-Only Containers

Some applications never modify their filesystem.

Run them as read-only.

```bash
docker run --read-only nginx
```

This reduces the risk of unauthorized file modifications.

---

# Drop Linux Capabilities

Containers receive a default set of Linux capabilities.

Remove unnecessary ones.

Example

```bash
docker run --cap-drop ALL nginx
```

Add back only the capabilities that the application actually needs.

---

# Avoid Privileged Containers

Avoid

```bash
docker run --privileged
```

unless absolutely necessary.

Privileged containers have extensive access to the host system.

---

# Image Security

Never trust unknown images.

Use:

✔ Official Images

✔ Verified Publisher Images

✔ Internal Company Images

Avoid downloading images from unknown publishers.

---

# Scan Images

Images should be scanned for vulnerabilities before deployment.

Example

```bash
docker scout quickview
```

Other common scanners include:

- Trivy
- Grype
- Clair
- Snyk Container

---

# Keep Images Updated

Older images may contain known vulnerabilities.

Instead of

```dockerfile
FROM ubuntu:20.04
```

consider using a supported version that meets your compatibility requirements.

Update images regularly after testing.

---

# Minimize Image Size

Smaller images reduce:

- Attack Surface
- Download Time
- Storage Usage

Prefer lightweight runtime images where appropriate.

---

# Secrets Management

Never store passwords inside Dockerfiles.

Bad Example

```dockerfile
ENV DB_PASSWORD=admin123
```

Instead,

use:

- Docker Secrets
- Environment Variables
- Secret Management Systems

Examples include:

- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault

---

# Protect Docker Socket

Docker daemon access is powerful.

Avoid exposing:

```
/var/run/docker.sock
```

to untrusted containers.

Anyone with unrestricted access to the Docker socket can often control the Docker host.

---

# Restrict Network Access

Create separate Docker networks.

Example

```
Frontend

↓

Backend

↓

Database
```

Only expose services that require external access.

---

# Resource Limits

Prevent one container from consuming all system resources.

Example

```bash
docker run \

--memory=512m \

--cpus=1 nginx
```

This limits memory and CPU usage.

---

# Read Environment Variables Carefully

Environment variables may contain:

- API Keys
- Database Passwords
- Tokens

Avoid exposing sensitive values in logs or images.

---

# File Permissions

Limit access to mounted files.

Example

```bash
docker run \

-v /secure:/data:ro
```

The `:ro` option mounts the directory as read-only.

---

# Enable Content Trust

Docker Content Trust helps verify image integrity.

Example

```bash
export DOCKER_CONTENT_TRUST=1
```

Signed images reduce the risk of using tampered content.

---

# Docker Bench Security

Docker provides a security auditing tool.

Example

```bash
docker run --net host --pid host --userns host \

--cap-add audit_control \

-v /var/lib:/var/lib \

-v /var/run/docker.sock:/var/run/docker.sock \

docker/docker-bench-security
```

It checks Docker configuration against security best practices.

---

# Logging & Auditing

Monitor:

- Login Attempts
- Container Creation
- Image Pulls
- Configuration Changes
- Security Events

Audit logs support incident investigations.

---

# Security Updates

Keep updated:

- Docker Engine
- Base Images
- Host Operating System
- Container Applications

Apply security patches after appropriate testing.

---

# Production Security Workflow

```
Build Image

↓

Scan Image

↓

Approve

↓

Push Registry

↓

Deploy

↓

Monitor

↓

Update
```

Security should be integrated into the deployment pipeline.

---

# Real Production Example

```
Internet

↓

Firewall

↓

Load Balancer

↓

Docker Host

↓

Docker Engine

↓

Frontend

↓

Backend

↓

Database
```

Every layer contributes to overall security.

---

# Common Beginner Mistakes

### Mistake 1

Running containers as the root user.

---

### Mistake 2

Using the `--privileged` option unnecessarily.

---

### Mistake 3

Hardcoding passwords inside Dockerfiles.

---

### Mistake 4

Using outdated images with known vulnerabilities.

---

### Mistake 5

Downloading images from untrusted sources.

---

### Mistake 6

Giving containers unrestricted access to the Docker socket.

---

# Interview Questions

### Q1. Why should containers avoid running as root?

Running as a non-root user limits the impact if the application is compromised.

---

### Q2. What is the Principle of Least Privilege?

Applications and containers should receive only the permissions required to perform their tasks.

---

### Q3. Why should Docker images be scanned?

To identify known vulnerabilities before deployment.

---

### Q4. What is Docker Content Trust?

It verifies the integrity and authenticity of Docker images using digital signatures.

---

### Q5. Why should `/var/run/docker.sock` be protected?

Because unrestricted access to the Docker socket can allow control over the Docker host.

---

### Q6. Name three Docker security best practices.

- Run as a non-root user
- Scan images regularly
- Keep images and Docker Engine updated

---

# Production Best Practices

✔ Use official images.

✔ Run containers as non-root.

✔ Minimize image size.

✔ Scan every image.

✔ Protect secrets.

✔ Limit CPU and memory.

✔ Avoid privileged containers.

✔ Keep Docker updated.

✔ Separate application networks.

✔ Monitor security events continuously.

---

# Key Takeaways

- Docker security begins with secure image creation.
- Containers should follow the Principle of Least Privilege.
- Images must be scanned and kept up to date.
- Secrets should never be embedded inside images.
- Security is a continuous process throughout the application lifecycle.

---

# Next Section

## 6.18 Docker Best Practices

In the next section, we will learn:

- Image Best Practices
- Container Best Practices
- Dockerfile Best Practices
- Networking Best Practices
- Storage Best Practices
- Security Best Practices
- Performance Optimization
- Production Checklist
- Interview Questions
---

# 6.18 Docker Best Practices

Learning Docker commands is only the beginning.

A professional DevOps Engineer must also know how to use Docker correctly in production.

Poor Docker practices can lead to:

- Slow Deployments
- Large Images
- Security Risks
- High Resource Usage
- Difficult Troubleshooting
- Downtime

This section covers industry-recommended Docker best practices.

---

# Docker Best Practices Overview

```
Docker

│

├── Image Best Practices

├── Dockerfile Best Practices

├── Container Best Practices

├── Networking Best Practices

├── Storage Best Practices

├── Security Best Practices

├── Performance Best Practices

└── Operational Best Practices
```

---

# Image Best Practices

Docker Images should be:

✔ Small

✔ Secure

✔ Versioned

✔ Reproducible

✔ Easy to Maintain

---

# Use Official Images

Prefer official images whenever possible.

Example

```dockerfile
FROM nginx:1.27
```

Instead of downloading images from unknown publishers.

---

# Pin Image Versions

Avoid

```dockerfile
FROM ubuntu:latest
```

Better

```dockerfile
FROM ubuntu:24.04
```

Specific versions produce predictable builds.

---

# Keep Images Small

Smaller images provide:

- Faster Downloads
- Faster Deployments
- Lower Storage Usage
- Reduced Attack Surface

---

# Use Multi-Stage Builds

Instead of shipping build tools,

copy only the application into the final image.

```
Builder Image

↓

Compile

↓

Runtime Image
```

The runtime image becomes much smaller.

---

# Use .dockerignore

Exclude unnecessary files.

Example

```
.git

node_modules

target

logs

*.tmp
```

This reduces build context size.

---

# Combine Related RUN Instructions

Instead of

```dockerfile
RUN apt update

RUN apt install nginx -y
```

Prefer

```dockerfile
RUN apt update && \
    apt install -y nginx
```

This reduces image layers.

---

# Clean Temporary Files

Remove package caches after installation.

Example

```dockerfile
RUN apt update && \
    apt install -y curl && \
    rm -rf /var/lib/apt/lists/*
```

This helps reduce image size.

---

# Run as Non-Root

Create a dedicated user.

```dockerfile
RUN useradd appuser

USER appuser
```

Running applications as a non-root user improves security.

---

# One Primary Process Per Container

Good

```
Container

↓

Nginx
```

Instead of

```
Container

↓

Nginx

↓

MySQL

↓

Redis

↓

Cron
```

Separate services into separate containers whenever practical.

---

# Use Environment Variables

Avoid hardcoding configuration.

Bad

```dockerfile
ENV DB_PASSWORD=admin123
```

Better

```
Environment Variables

↓

Runtime Configuration
```

or dedicated secrets management.

---

# Keep Containers Stateless

Containers should not permanently store important data.

Use

```
Container

↓

Docker Volume
```

for persistent storage.

---

# Health Checks

Every production application should expose a health endpoint.

Example

```dockerfile
HEALTHCHECK CMD curl -f http://localhost:8080/health || exit 1
```

Health checks improve automated recovery.

---

# Restart Policies

Example

```bash
docker run \
--restart unless-stopped \
nginx
```

Containers automatically restart after failures or reboots according to the configured policy.

---

# Resource Limits

Prevent resource exhaustion.

Example

```bash
docker run \
--memory=512m \
--cpus=2 \
nginx
```

Limits improve system stability.

---

# Network Isolation

Instead of placing every container on one network,

create dedicated networks.

```
Frontend Network

↓

Backend Network

↓

Database Network
```

This reduces unnecessary exposure.

---

# Expose Only Required Ports

Instead of

```
80

443

3306

6379

5672
```

Publish only the ports that users or other systems must access.

---

# Protect Secrets

Never store:

- Passwords
- Tokens
- API Keys

inside:

- Dockerfiles
- Images
- Git Repositories

Use secure secret management solutions.

---

# Monitor Containers

Monitor:

- CPU
- Memory
- Disk
- Network
- Restart Count
- Health Status

Continuous monitoring helps detect problems early.

---

# Centralized Logging

Collect logs in one location.

```
Containers

↓

Fluent Bit

↓

Elasticsearch

↓

Kibana
```

Centralized logging simplifies troubleshooting.

---

# Image Scanning

Scan images before deployment.

Examples

- Docker Scout
- Trivy
- Grype
- Snyk

Address high-severity vulnerabilities before production releases.

---

# Use Immutable Images

Never modify running containers manually.

Instead

```
Code Change

↓

Build New Image

↓

Deploy New Container
```

This ensures consistency.

---

# Version Images

Good

```
api:v1.0

api:v1.1

api:v2.0
```

Avoid relying solely on

```
latest
```

---

# Use CI/CD

Automate builds.

```
Git

↓

CI

↓

Docker Build

↓

Image Scan

↓

Push

↓

Deploy
```

Automation reduces manual errors.

---

# Clean Unused Resources

Regularly remove unused:

- Images
- Containers
- Networks
- Volumes

Example

```bash
docker system prune
```

Review the impact before cleanup in production.

---

# Backup Persistent Data

Back up:

- Docker Volumes
- Databases
- Configuration Files

Containers can be recreated,

but persistent data must be protected.

---

# Production Deployment Workflow

```
Developer

↓

Git

↓

CI/CD

↓

Docker Build

↓

Image Scan

↓

Registry

↓

Production

↓

Monitoring

↓

Alerts
```

---

# Real Production Example

```
Users

↓

Load Balancer

↓

Nginx

↓

Docker

│

├── Frontend

├── Backend

├── Redis

├── MySQL

└── Monitoring
```

Each service follows Docker best practices.

---

# Docker Best Practices Checklist

Before Production

✔ Official Images

✔ Versioned Images

✔ Multi-Stage Builds

✔ Non-Root User

✔ Health Checks

✔ Restart Policy

✔ Resource Limits

✔ Dedicated Networks

✔ Persistent Volumes

✔ Image Scanning

✔ Monitoring

✔ Centralized Logging

✔ Automated Backups

✔ CI/CD Pipeline

---

# Common Beginner Mistakes

### Mistake 1

Using `latest` in production.

---

### Mistake 2

Running containers as root.

---

### Mistake 3

Hardcoding credentials.

---

### Mistake 4

Ignoring health checks.

---

### Mistake 5

Keeping large unused images.

---

### Mistake 6

Making manual changes inside running containers.

---

### Mistake 7

Not backing up Docker volumes.

---

### Mistake 8

Ignoring resource limits.

---

# Interview Questions

### Q1. Why should Docker images use version tags?

Version tags provide predictable deployments and simplify rollbacks.

---

### Q2. Why should containers be stateless?

Stateless containers are easier to replace, scale and recover. Persistent data should be stored in volumes or external services.

---

### Q3. Why is `.dockerignore` important?

It reduces the build context, improving build speed and reducing image size.

---

### Q4. Why should production containers run as non-root?

Running as a non-root user limits the impact of a potential compromise.

---

### Q5. Why should Docker images be immutable?

Immutable images ensure deployments are consistent and reproducible.

---

### Q6. Name five Docker production best practices.

- Multi-Stage Builds
- Non-root Containers
- Health Checks
- Image Scanning
- Resource Limits

---

# Production Best Practices

✔ Keep images small.

✔ Version every image.

✔ Run as non-root.

✔ Use health checks.

✔ Limit CPU and memory.

✔ Scan every image.

✔ Use Docker Volumes.

✔ Keep containers immutable.

✔ Monitor continuously.

✔ Automate deployments.

---

# Key Takeaways

- Docker best practices improve security, performance and maintainability.
- Small, immutable and versioned images are easier to manage.
- Health checks, monitoring and resource limits improve reliability.
- Secrets should never be stored inside images.
- Production Docker environments rely heavily on automation and standardization.

---

# Next Section

## 6.19 Docker in Production

In the next section, we will learn:

- Real Production Architecture
- Docker in Enterprise Environments
- Deployment Strategies
- High Availability
- Scaling
- Disaster Recovery
- CI/CD Integration
- Production Checklist
- Interview Questions
---

# 6.19 Docker in Production

Learning Docker commands is important,

but running Docker in a **production environment** is a completely different challenge.

Production systems must provide:

- High Availability
- Scalability
- Security
- Monitoring
- Automated Deployment
- Backup
- Disaster Recovery

A DevOps Engineer must understand how Docker is used in real enterprise infrastructures.

---

# Typical Production Architecture

```
Users

↓

DNS

↓

CDN

↓

Load Balancer

↓

Reverse Proxy (Nginx)

↓

Docker Hosts

↓

Docker Containers

↓

Database

↓

Backup Storage
```

Every layer has a specific responsibility.

---

# Docker in Enterprise

Most organizations use Docker to run:

- Web Applications
- APIs
- Background Workers
- Message Queues
- Monitoring Tools
- CI/CD Components

Examples

```
Docker

│

├── Frontend

├── Backend

├── Redis

├── RabbitMQ

├── Jenkins Agent

└── Monitoring
```

---

# Production Request Flow

```
Browser

↓

DNS

↓

Load Balancer

↓

Nginx

↓

Docker Container

↓

Application

↓

Database

↓

Response
```

---

# High Availability

Never rely on a single Docker host.

Instead

```
Load Balancer

↓

Docker Host 1

↓

Docker Host 2

↓

Docker Host 3
```

If one server fails,

traffic is redirected to healthy servers.

---

# Horizontal Scaling

Instead of upgrading one server,

add more application containers.

```
Backend-1

↓

Backend-2

↓

Backend-3

↓

Backend-4
```

Traffic is distributed across all instances.

---

# Vertical Scaling

Increase server resources.

```
4 CPU

↓

8 CPU

↓

16 CPU
```

Vertical scaling is useful,

but hardware eventually reaches practical limits.

---

# Stateless Containers

Production containers should remain stateless whenever possible.

```
Application

↓

Docker Container

↓

Volume

↓

Database
```

Business data should not be stored inside containers.

---

# Persistent Storage

Stateful services such as:

- MySQL
- PostgreSQL
- MongoDB
- Redis (when persistence is enabled)

should use persistent storage.

```
Container

↓

Docker Volume

↓

Storage
```

---

# Private Image Registry

Instead of downloading images from public repositories,

many companies use private registries.

Examples

- Docker Hub Private Repositories
- Amazon ECR
- Azure Container Registry
- Google Artifact Registry
- Harbor

---

# CI/CD Workflow

```
Developer

↓

Git

↓

Jenkins / GitHub Actions

↓

Docker Build

↓

Image Scan

↓

Registry

↓

Production Deployment
```

Images are built and deployed automatically.

---

# Blue-Green Deployment

```
Production

↓

Blue Environment

↓

Green Environment

↓

Switch Traffic
```

This minimizes downtime during releases.

---

# Rolling Deployment

```
Container 1 Updated

↓

Container 2 Updated

↓

Container 3 Updated

↓

Deployment Complete
```

Users continue accessing the application during updates.

---

# Canary Deployment

```
100 Users

↓

10 Users

↓

New Version

↓

90 Users

↓

Old Version
```

If no issues are detected,

traffic gradually shifts to the new version.

---

# Health Checks

Containers should expose health endpoints.

Example

```
GET

/health

↓

200 OK
```

Unhealthy containers can be replaced automatically.

---

# Auto Restart

Example

```bash
docker run \
--restart unless-stopped \
myapp
```

Containers restart automatically after failures or host reboots.

---

# Resource Limits

Every production container should have limits.

Example

```bash
docker run \
--memory=1g \
--cpus=2 \
myapp
```

This prevents one container from exhausting system resources.

---

# Logging

Centralize logs.

```
Containers

↓

Fluent Bit

↓

Elasticsearch

↓

Kibana
```

Searching logs becomes much easier.

---

# Monitoring

Monitor

- CPU
- Memory
- Disk
- Network
- Restart Count
- Response Time
- Error Rate

Popular tools

- Prometheus
- Grafana
- Datadog
- Zabbix

---

# Security

Production environments should include

✔ Non-root Containers

✔ Image Scanning

✔ Secrets Management

✔ Private Networks

✔ TLS

✔ Firewall

✔ Resource Limits

✔ Regular Updates

---

# Backup Strategy

Regularly back up:

- Docker Volumes
- Databases
- Configuration Files
- Registry Images (if required)
- Application Data

Backups should be tested periodically.

---

# Disaster Recovery

Suppose a Docker host fails.

```
Failure

↓

Provision New Host

↓

Install Docker

↓

Pull Images

↓

Restore Volumes

↓

Start Containers

↓

Production Restored
```

Recovery procedures should be documented and tested.

---

# Production Checklist

Before Go-Live

✔ Official Images

✔ Version Tags

✔ Health Checks

✔ Restart Policies

✔ Resource Limits

✔ Volumes Configured

✔ Monitoring Enabled

✔ Logging Enabled

✔ Image Scan Completed

✔ Backups Verified

✔ Security Review Completed

---

# Example Enterprise Architecture

```
Internet

↓

Cloudflare

↓

AWS ALB

↓

Nginx

↓

Docker Hosts

↓

Containers

├── Frontend

├── Backend

├── Redis

├── RabbitMQ

└── PostgreSQL
```

---

# Docker + Kubernetes

In large organizations,

Docker (or OCI-compatible images) and Kubernetes are commonly used together.

```
Developer

↓

Docker Build

↓

Container Registry

↓

Kubernetes

↓

Pods

↓

Users
```

Docker packages the application,

while Kubernetes manages deployment and scaling.

---

# Common Beginner Mistakes

### Mistake 1

Running production with only one Docker host.

---

### Mistake 2

Not configuring restart policies.

---

### Mistake 3

Ignoring backups.

---

### Mistake 4

Deploying containers manually instead of using CI/CD.

---

### Mistake 5

Not monitoring container health.

---

### Mistake 6

Keeping sensitive data inside Docker images.

---

# Interview Questions

### Q1. Why are containers usually stateless?

Stateless containers are easier to replace, scale and recover. Persistent data should be stored externally.

---

### Q2. Why are private registries used?

To securely store proprietary application images and control access.

---

### Q3. Name three production deployment strategies.

- Blue-Green Deployment
- Rolling Deployment
- Canary Deployment

---

### Q4. Why are resource limits important?

They prevent individual containers from consuming excessive CPU or memory and affecting other workloads.

---

### Q5. Why should Docker be integrated with CI/CD?

Automation improves consistency, reduces manual errors and accelerates software delivery.

---

### Q6. What should always be backed up?

- Docker Volumes
- Databases
- Configuration Files
- Critical Application Data

---

# Production Best Practices

✔ Deploy multiple Docker hosts.

✔ Automate deployments.

✔ Monitor continuously.

✔ Back up persistent data.

✔ Configure restart policies.

✔ Scan every image.

✔ Limit container resources.

✔ Keep infrastructure documented.

✔ Test disaster recovery procedures.

✔ Follow the Principle of Least Privilege.

---

# Key Takeaways

- Production Docker environments require much more than running containers.
- High Availability, monitoring, backups and automation are essential.
- CI/CD and container registries simplify deployments.
- Stateless containers improve scalability and reliability.
- Production success depends on operational discipline as much as technical configuration.

---

# Chapter 6 Summary

Congratulations!

You have completed **Chapter 6 – Docker**.

You learned:

- Docker Fundamentals
- Why Docker
- Virtual Machines vs Containers
- Docker Architecture
- Installing Docker
- Docker Images
- Docker Containers
- Docker CLI Commands
- Dockerfile
- Building Images
- Docker Volumes
- Docker Networking
- Docker Compose
- Docker Hub
- Multi-Container Applications
- Docker Logs & Monitoring
- Docker Security
- Docker Best Practices
- Docker in Production

You now have a strong foundation in Docker and are ready to move toward container orchestration.

---

# Next Chapter

