# Chapter 9 – Kubernetes (K8s)

---

# Chapter Overview

Congratulations!

You have completed:

- Linux
- Networking
- Git & GitHub
- AWS Basics
- Nginx
- Docker
- Jenkins
- Terraform

Now it's time to learn the most important container orchestration platform used in modern DevOps:

# Kubernetes

Kubernetes (K8s) has become the industry standard for deploying, scaling and managing containerized applications.

Whether companies use:

- AWS
- Azure
- Google Cloud
- On-Premises
- Hybrid Cloud

most enterprise container platforms are powered by Kubernetes.

---

# Why Learn Kubernetes?

Docker can run one or a few containers easily.

But imagine a company running:

- 500 Applications
- 10,000 Containers
- Hundreds of Servers
- Millions of Users

Managing containers manually becomes impossible.

Kubernetes automates:

- Deployment
- Scaling
- Recovery
- Networking
- Load Balancing
- Rolling Updates

---

# Learning Objectives

By the end of this chapter you will be able to:

- Understand Kubernetes Architecture
- Install Kubernetes
- Create Pods
- Create Deployments
- Scale Applications
- Expose Applications
- Use ConfigMaps
- Use Secrets
- Manage Storage
- Deploy Applications
- Understand Helm
- Secure Kubernetes Clusters
- Operate Production Clusters

---

# Chapter Roadmap

This chapter contains the following sections.

```
9.1 Introduction to Kubernetes

9.2 Why Kubernetes?

9.3 Kubernetes Architecture

9.4 Installing Kubernetes

9.5 kubectl Basics

9.6 Pods

9.7 ReplicaSets

9.8 Deployments

9.9 Services

9.10 Namespaces

9.11 Labels & Selectors

9.12 ConfigMaps

9.13 Secrets

9.14 Volumes & Persistent Storage

9.15 Ingress

9.16 Helm

9.17 Kubernetes Best Practices

9.18 Kubernetes in Production

9.19 Chapter Summary
```

---

# Prerequisites

Before starting Kubernetes you should understand:

- Linux
- Networking
- Docker
- YAML Basics
- Terraform (Optional but Helpful)
- Cloud Fundamentals

The previous chapters have prepared you for these topics.

---

# Lab Environment

Operating System

- Ubuntu 24.04 LTS
- Rocky Linux 9
- Amazon Linux 2023
- Windows 11 (WSL2)

Tools

- Docker
- containerd
- kubectl
- kubeadm
- kubelet
- Helm
- Git

Cloud Platforms

- AWS
- Azure
- Google Cloud

---

# Learning Approach

Every section follows the same structure.

```
Concept

↓

Architecture

↓

Hands-on Lab

↓

Production Example

↓

Best Practices

↓

Interview Questions
```

Our goal is to understand not only **how Kubernetes works**, but **why enterprise companies use it**.

---

# What You Will Build

During this chapter,

you will deploy:

- Nginx
- Apache
- Node.js Applications
- Java Applications
- Python Applications

You will also learn how to:

- Scale Applications
- Perform Rolling Updates
- Roll Back Deployments
- Use Persistent Storage
- Configure Networking
- Deploy Applications using Helm

---

# Production Focus

Every topic includes:

✔ Architecture Diagrams

✔ Hands-on Labs

✔ Production Examples

✔ Best Practices

✔ Common Mistakes

✔ Interview Questions

---

# Skills You Will Gain

By the end of this chapter,

you will understand how DevOps Engineers:

- Deploy Applications
- Scale Containers
- Manage Clusters
- Configure Networking
- Handle Persistent Storage
- Secure Kubernetes
- Operate Enterprise Clusters

These are among the most valuable skills for modern DevOps and Cloud Engineers.

---

# Kubernetes Learning Journey

```
Docker

↓

Containers

↓

Multiple Containers

↓

Container Orchestration

↓

Kubernetes

↓

Production Cluster

↓

Enterprise Applications
```

---

# Real Enterprise Scenario

Imagine an e-commerce company.

It has:

- Frontend
- Backend
- Database
- Redis
- RabbitMQ
- Monitoring
- Logging

Each service runs inside containers.

Without Kubernetes,

Engineers manually restart failed containers and scale applications.

With Kubernetes,

everything is automated.

```
Developer

↓

Docker Image

↓

Kubernetes

↓

Production
```

---

# Production Benefits

Organizations choose Kubernetes because it provides:

✔ High Availability

✔ Self-Healing

✔ Auto Scaling

✔ Service Discovery

✔ Rolling Updates

✔ Rollbacks

✔ Load Balancing

✔ Declarative Deployments

---

# Next Section

## 9.1 Introduction to Kubernetes

In the next section, we will learn:

- What is Kubernetes?
- History of Kubernetes
- Why Google Created Kubernetes
- CNCF and Kubernetes
- Kubernetes Features
- Real Production Examples
- Interview Questions
---

# 9.1 Introduction to Kubernetes

Imagine your company has built an application using Docker.

Initially,

everything works perfectly.

```
Docker

↓

1 Container

↓

Application Running
```

As your business grows,

you now have:

- 500 Containers
- 100 Servers
- Millions of Users
- Multiple Development Teams

Managing all these containers manually becomes nearly impossible.

This is where **Kubernetes** comes in.

---

# What is Kubernetes?

Kubernetes (often abbreviated as **K8s**) is an **open-source container orchestration platform** used to deploy, manage, scale and automate containerized applications.

Instead of manually managing containers,

Kubernetes automatically:

- Deploys Containers
- Restarts Failed Containers
- Scales Applications
- Balances Traffic
- Performs Rolling Updates
- Monitors Application Health

---

# Simple Definition

```
Docker

↓

Containers

↓

Kubernetes

↓

Automation
```

Docker creates containers.

Kubernetes manages containers.

---

# Official Definition

Kubernetes is a portable, extensible platform for managing containerized workloads and services.

It provides automation for:

- Deployment
- Scaling
- Networking
- Recovery
- Scheduling

---

# Why the Name Kubernetes?

The word **Kubernetes** comes from Greek.

It means:

```
Helmsman

or

Ship Pilot
```

Just as a ship's captain manages ships,

Kubernetes manages containers.

---

# Why is it called K8s?

```
Kubernetes

K + 8 letters + s

↓

K8s
```

The "8" represents the eight letters between **K** and **s**.

---

# History of Kubernetes

Google has been running containers for many years.

Internally,

Google built a system called:

```
Borg
```

to manage millions of containers.

Later,

Google created Kubernetes based on lessons learned from Borg.

In 2014,

Google released Kubernetes as an open-source project.

Today,

it is maintained by the:

```
Cloud Native Computing Foundation (CNCF)
```

---

# Evolution

```
Physical Servers

↓

Virtual Machines

↓

Containers

↓

Docker

↓

Kubernetes
```

Each step improved efficiency and automation.

---

# Why Kubernetes was Created?

Docker solved the problem of packaging applications.

However,

Docker alone does not solve:

- Scaling
- Self-Healing
- Load Balancing
- Multi-Host Networking
- Automated Deployment

Kubernetes solves these operational challenges.

---

# Kubernetes Workflow

```
Developer

↓

Docker Image

↓

Kubernetes

↓

Containers Running

↓

Users
```

Kubernetes continuously manages the running application.

---

# What Problems Does Kubernetes Solve?

Without Kubernetes

```
Containers

↓

Manual Management

↓

Failures

↓

Downtime
```

With Kubernetes

```
Containers

↓

Automatic Management

↓

Recovery

↓

High Availability
```

---

# Kubernetes Features

Kubernetes provides:

✔ Container Orchestration

✔ Automatic Scheduling

✔ Self-Healing

✔ Auto Scaling

✔ Rolling Updates

✔ Rollbacks

✔ Service Discovery

✔ Load Balancing

✔ Storage Orchestration

✔ Secret Management

---

# Kubernetes Architecture Overview

```
Developer

↓

kubectl

↓

API Server

↓

Scheduler

↓

Worker Nodes

↓

Pods

↓

Containers
```

We will study each component in detail later.

---

# Kubernetes Components

A Kubernetes cluster contains:

```
Cluster

│

├── Control Plane

└── Worker Nodes
```

The Control Plane manages the cluster.

Worker Nodes run applications.

---

# Container Orchestration

Container Orchestration means:

Automatically managing

- Containers
- Networking
- Storage
- Scaling
- Scheduling

instead of performing these tasks manually.

---

# Kubernetes and Docker

A common misconception is:

"Kubernetes replaces Docker."

This is **not entirely accurate**.

Docker is used to build container images.

Kubernetes runs containerized workloads using a compatible container runtime.

Modern Kubernetes commonly uses runtimes such as:

- containerd
- CRI-O

Many existing Docker-built images continue to run without modification because they follow the OCI image standard.

---

# Kubernetes in Cloud

Most cloud providers offer managed Kubernetes services.

Examples

- Amazon EKS
- Azure AKS
- Google GKE

These services reduce operational overhead by managing much of the Kubernetes control plane.

---

# Kubernetes Use Cases

Organizations use Kubernetes for:

- Web Applications
- APIs
- Microservices
- AI/ML Workloads
- Batch Jobs
- Data Processing
- Enterprise Applications

---

# Real Production Example

Imagine an online shopping website.

It contains:

- Frontend
- Backend
- Authentication
- Payment
- Database
- Cache

Every service runs inside containers.

Kubernetes manages all of them automatically.

---

# Real Enterprise Workflow

```
Developer

↓

GitHub

↓

CI/CD

↓

Docker Image

↓

Container Registry

↓

Kubernetes

↓

Production
```

Every deployment becomes automated.

---

# Why Companies Love Kubernetes

Organizations choose Kubernetes because it provides:

- High Availability
- Scalability
- Reliability
- Automation
- Portability
- Cloud Independence

---

# Common Beginner Mistakes

### Mistake 1

Thinking Kubernetes replaces Docker.

Kubernetes manages containerized applications; Docker is commonly used to build container images.

---

### Mistake 2

Thinking Kubernetes is only for large companies.

Small applications can also benefit from Kubernetes depending on operational needs.

---

### Mistake 3

Trying to learn every Kubernetes object at once.

Learn one concept at a time.

---

### Mistake 4

Ignoring Linux fundamentals.

Strong Linux knowledge is essential for Kubernetes administration.

---

### Mistake 5

Memorizing commands without understanding cluster architecture.

Understanding architecture makes troubleshooting much easier.

---

# Interview Questions

### Q1. What is Kubernetes?

Kubernetes is an open-source container orchestration platform used to deploy, scale and manage containerized applications.

---

### Q2. Who originally created Kubernetes?

Google.

---

### Q3. What does Kubernetes mean?

It means "Helmsman" or "Ship Pilot."

---

### Q4. Why is Kubernetes called K8s?

Because there are eight letters between **K** and **s** in the word Kubernetes.

---

### Q5. Name five Kubernetes features.

- Self-Healing
- Auto Scaling
- Load Balancing
- Rolling Updates
- Service Discovery

---

### Q6. Which organization currently maintains Kubernetes?

The Cloud Native Computing Foundation (CNCF).

---

# Production Best Practices

✔ Learn Docker before Kubernetes.

✔ Understand Kubernetes architecture.

✔ Use declarative YAML manifests.

✔ Store manifests in Git.

✔ Automate deployments through CI/CD.

✔ Monitor cluster health.

✔ Keep Kubernetes updated.

✔ Learn one Kubernetes object at a time.

---

# Key Takeaways

- Kubernetes is the industry-standard platform for container orchestration.
- It automates deployment, scaling, recovery and networking.
- Kubernetes originated from Google's Borg system.
- Modern cloud-native applications commonly run on Kubernetes.
- Understanding Kubernetes fundamentals is essential before learning advanced concepts.

---

# Next Section

## 9.2 Why Kubernetes?

In the next section, we will learn:

- Problems Without Kubernetes
- Limitations of Docker Alone
- Why Container Orchestration is Needed
- Kubernetes vs Docker
- Business Benefits
- Enterprise Use Cases
- Best Practices
- Interview Questions
---

# 9.2 Why Kubernetes?

Before Kubernetes,

companies used Docker to package and run applications inside containers.

Docker solved many problems compared to Virtual Machines,

but as applications grew,

new operational challenges appeared.

Imagine a company running:

- 5,000 Containers
- Hundreds of Servers
- Multiple Data Centers
- Millions of Users

Managing all of these containers manually would be extremely difficult.

Kubernetes was created to solve these large-scale operational challenges.

---

# Life Before Kubernetes

A small application might look like this.

```
Server

↓

Docker

↓

Container 1

↓

Application
```

This setup works well for a few containers.

---

# As the Business Grows

Now imagine:

```
100 Servers

↓

5000 Containers

↓

Many Applications
```

Questions immediately arise:

- Which server should run each container?
- What happens if a server crashes?
- How should traffic be distributed?
- How do we scale applications?
- How do we perform updates without downtime?

Managing all of this manually is slow and error-prone.

---

# Problems Without Kubernetes

Without an orchestration platform,

teams must manually:

- Start Containers
- Stop Containers
- Restart Failed Containers
- Scale Applications
- Configure Networking
- Manage Storage
- Monitor Health
- Balance Traffic

As infrastructure grows,

manual management becomes increasingly difficult.

---

# Example Without Kubernetes

Suppose your application has:

```
Frontend

Backend

Database
```

Each component runs in separate Docker containers.

One Backend container crashes.

Without Kubernetes,

someone must:

```
Detect Failure

↓

SSH into Server

↓

Restart Container

↓

Verify Application
```

This increases recovery time.

---

# Example With Kubernetes

The same failure occurs.

```
Backend Container

↓

Crash

↓

Kubernetes Detects Failure

↓

Starts New Container

↓

Application Restored
```

No manual intervention is required for this recovery.

---

# Docker is Not Enough

Docker provides:

✔ Container Creation

✔ Image Building

✔ Container Execution

But Docker alone does not automatically provide:

- Self-Healing
- Auto Scaling
- Service Discovery
- Rolling Updates
- Cluster Scheduling
- Multi-Node Management

These capabilities are provided by Kubernetes.

---

# Docker vs Kubernetes

```
Docker

↓

Creates Containers

----------------

Kubernetes

↓

Manages Containers
```

Both technologies complement each other.

---

# Why Container Orchestration?

Imagine managing thousands of containers.

```
Container

Container

Container

Container

Container

...

5000 Containers
```

Manual management becomes impractical.

Container Orchestration automates:

- Deployment
- Scheduling
- Scaling
- Networking
- Recovery

---

# Kubernetes Solves These Problems

```
Problem

↓

Kubernetes Solution

--------------------

Container Crash

↓

Self-Healing

--------------------

High Traffic

↓

Auto Scaling

--------------------

Server Failure

↓

Rescheduling

--------------------

Application Update

↓

Rolling Update

--------------------

Network Access

↓

Service Discovery
```

---

# Automatic Scheduling

Suppose you have three servers.

```
Node-1

Node-2

Node-3
```

You deploy 50 containers.

Instead of choosing servers manually,

Kubernetes schedules containers automatically based on available resources and scheduling rules.

---

# Self-Healing

Suppose:

```
Pod

↓

Crash
```

Kubernetes automatically:

```
Detect Failure

↓

Create Replacement Pod

↓

Application Running
```

This feature greatly improves application availability.

---

# Auto Scaling

Traffic increases.

```
100 Users

↓

1000 Users

↓

10000 Users
```

Kubernetes can automatically increase the number of application instances when configured to do so.

When traffic decreases,

it can scale them back down.

---

# Load Balancing

Suppose five application Pods are running.

```
User Requests

↓

Kubernetes Service

↓

Pod 1

Pod 2

Pod 3

Pod 4

Pod 5
```

Traffic is distributed across available Pods.

---

# Rolling Updates

Without Kubernetes,

updating applications often causes downtime.

With Kubernetes:

```
Old Version

↓

New Version

↓

One Pod at a Time

↓

No Downtime
```

Users continue accessing the application during the rollout.

---

# Rollbacks

Suppose version 2.0 has a bug.

```
Version 2.0

↓

Failure

↓

Rollback

↓

Version 1.0
```

Kubernetes can restore the previous stable version.

---

# High Availability

Suppose:

```
Node-1

↓

Failure
```

Kubernetes schedules replacement Pods on healthy nodes when possible.

Applications remain available if sufficient cluster capacity exists.

---

# Efficient Resource Usage

Instead of dedicating one server to each application,

Kubernetes schedules multiple workloads efficiently across cluster nodes.

Benefits include:

- Better CPU Utilization
- Better Memory Utilization
- Lower Infrastructure Costs

---

# Declarative Management

Instead of manually creating containers,

Engineers define the desired state.

Example

```yaml
replicas: 3
```

Kubernetes continuously works to maintain that desired state.

---

# Kubernetes in Enterprise

Large companies commonly use Kubernetes for:

- E-Commerce Platforms
- Banking Applications
- Video Streaming
- Social Media
- SaaS Platforms
- AI/ML Platforms
- Financial Systems

---

# Real Production Example

Imagine an online shopping platform.

Services include:

- Login
- Product Catalog
- Cart
- Orders
- Payments
- Notifications

Each service runs independently.

Kubernetes deploys,

scales,

updates and monitors all services automatically.

---

# Business Benefits

Organizations adopt Kubernetes because it provides:

✔ Faster Deployments

✔ Higher Availability

✔ Better Resource Utilization

✔ Easier Scaling

✔ Reduced Operational Effort

✔ Consistent Deployments

✔ Cloud Portability

✔ Improved Reliability

---

# Enterprise Deployment Workflow

```
Developer

↓

GitHub

↓

CI/CD Pipeline

↓

Docker Image

↓

Container Registry

↓

Kubernetes Cluster

↓

Users
```

Every deployment becomes automated and repeatable.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Kubernetes is only for very large companies.

It can also benefit smaller environments when automation and scalability are important.

---

### Mistake 2

Trying to manage Kubernetes without understanding Docker.

Docker fundamentals make Kubernetes much easier to learn.

---

### Mistake 3

Assuming Kubernetes automatically fixes every application problem.

It manages infrastructure and workloads, but application bugs still need to be fixed.

---

### Mistake 4

Ignoring resource requests and limits.

Poor resource configuration can affect cluster stability.

---

### Mistake 5

Believing Kubernetes removes the need for monitoring.

Production Kubernetes clusters still require logging, monitoring and alerting.

---

# Interview Questions

### Q1. Why was Kubernetes created?

To automate the deployment, scaling, networking and management of containerized applications across multiple machines.

---

### Q2. What problem does Kubernetes solve that Docker alone does not?

Kubernetes provides orchestration features such as scheduling, self-healing, scaling and service discovery.

---

### Q3. What is Self-Healing?

It is Kubernetes' ability to detect failed workloads and replace or restart them automatically.

---

### Q4. What is a Rolling Update?

A deployment strategy that gradually replaces old application instances with new ones while minimizing downtime.

---

### Q5. Why is Auto Scaling important?

It allows applications to handle changing workloads by adjusting the number of running instances.

---

### Q6. Name five business benefits of Kubernetes.

- High Availability
- Auto Scaling
- Efficient Resource Usage
- Rolling Updates
- Automated Operations

---

# Production Best Practices

✔ Learn Docker before Kubernetes.

✔ Use declarative YAML configurations.

✔ Configure resource requests and limits.

✔ Monitor cluster health continuously.

✔ Implement rolling updates.

✔ Test rollback procedures.

✔ Automate deployments with CI/CD.

✔ Regularly update Kubernetes versions.

---

# Key Takeaways

- Kubernetes was created to solve large-scale container management challenges.
- Docker builds and runs containers, while Kubernetes orchestrates them.
- Kubernetes automates deployment, scaling, recovery and networking.
- Features such as self-healing and rolling updates improve application reliability.
- Kubernetes has become the standard platform for running containerized applications in production.

---

# Next Section

## 9.3 Kubernetes Architecture

In the next section, we will learn:

- Kubernetes Cluster
- Control Plane
- Worker Nodes
- API Server
- Scheduler
- Controller Manager
- etcd
- kubelet
- kube-proxy
- Container Runtime
- Production Architecture
- Interview Questions
---

# 9.3 Kubernetes Architecture

Kubernetes is much more than just running containers.

Behind every Kubernetes cluster are multiple components working together.

Each component has a specific responsibility.

Understanding the architecture is one of the most important topics for:

- DevOps Engineers
- Kubernetes Administrators
- Cloud Engineers
- Production Support Engineers

It is also one of the most frequently asked interview topics.

---

# What is Kubernetes Architecture?

Kubernetes Architecture refers to all the components that work together to manage containerized applications.

At a high level:

```
User

↓

kubectl

↓

API Server

↓

Scheduler

↓

Controller Manager

↓

Worker Nodes

↓

Pods

↓

Containers
```

Every deployment passes through these components.

---

# Kubernetes Cluster

The highest-level component is the **Cluster**.

A Kubernetes Cluster is a collection of machines working together.

```
Kubernetes Cluster

│

├── Control Plane

└── Worker Nodes
```

---

# Two Main Parts

Every Kubernetes cluster has two major parts.

```
Cluster

│

├── Control Plane

└── Worker Nodes
```

Control Plane manages the cluster.

Worker Nodes run applications.

---

# High-Level Architecture

```
                Kubernetes Cluster

        ┌─────────────────────────────┐
        │       Control Plane         │
        │                             │
        │ API Server                  │
        │ Scheduler                   │
        │ Controller Manager          │
        │ etcd                        │
        └─────────────┬───────────────┘
                      │
        ┌─────────────┼─────────────┐
        │             │             │
   Worker Node   Worker Node   Worker Node
        │             │             │
      Pods          Pods          Pods
        │             │             │
    Containers    Containers    Containers
```

---

# Control Plane

The Control Plane is the brain of Kubernetes.

It decides:

- Where Pods should run
- Which Node should execute workloads
- How failures should be handled
- Cluster health
- Desired state

Without the Control Plane,

the cluster cannot function.

---

# Components of Control Plane

```
Control Plane

│

├── API Server

├── Scheduler

├── Controller Manager

└── etcd
```

Each component performs a different task.

---

# API Server

The **API Server** is the front door of Kubernetes.

Every request goes through it.

Examples:

```
kubectl apply

↓

API Server
```

```
kubectl get pods

↓

API Server
```

Even the internal Kubernetes components communicate through the API Server.

---

# API Server Workflow

```
User

↓

kubectl

↓

API Server

↓

Cluster
```

The API Server validates requests and updates the cluster state.

---

# Scheduler

The Scheduler decides:

```
Which Pod

↓

Runs On

↓

Which Worker Node
```

It checks:

- CPU
- Memory
- Node Availability
- Scheduling Rules
- Resource Requests
- Affinity Rules

The Scheduler **does not** run Pods itself.

It only selects the most suitable Node.

---

# Scheduler Example

Imagine three worker nodes.

```
Worker-1

CPU: Busy

----------------

Worker-2

CPU: Free

----------------

Worker-3

Memory Full
```

A new Pod arrives.

The Scheduler chooses:

```
Worker-2
```

because it has sufficient resources.

---

# Controller Manager

Controllers continuously monitor the cluster.

Their job is to ensure that the actual state matches the desired state.

Example:

Desired State

```
3 Pods
```

Actual State

```
2 Pods
```

Controller detects the difference.

```
Missing Pod

↓

Create New Pod
```

---

# Common Controllers

Examples include:

- Deployment Controller
- ReplicaSet Controller
- Node Controller
- Job Controller
- Endpoint Controller

Each controller manages a different Kubernetes object.

---

# etcd

**etcd** is the Kubernetes database.

It stores:

- Cluster Configuration
- Nodes
- Pods
- Secrets
- ConfigMaps
- Services
- Deployments
- Cluster State

Everything important is stored inside etcd.

---

# etcd Workflow

```
API Server

↓

etcd

↓

Store Cluster Information
```

If etcd is lost and no backup exists,

the cluster cannot recover its state.

---

# Worker Node

Worker Nodes are the machines that actually run applications.

```
Worker Node

│

├── kubelet

├── kube-proxy

├── Container Runtime

└── Pods
```

---

# kubelet

The kubelet is an agent running on every Worker Node.

Its responsibilities include:

- Receiving instructions from the API Server
- Creating Pods
- Monitoring Pod Health
- Reporting Node Status

Without kubelet,

a Worker Node cannot participate in the cluster.

---

# kubelet Workflow

```
API Server

↓

kubelet

↓

Pod Created
```

---

# kube-proxy

kube-proxy manages networking on Worker Nodes.

Responsibilities:

- Service Networking
- Traffic Routing
- Load Balancing
- Network Rules

When users access a Service,

kube-proxy helps route traffic to the correct Pod.

---

# Container Runtime

The Container Runtime actually runs containers.

Common runtimes:

- containerd
- CRI-O

Earlier Kubernetes versions commonly used Docker through an intermediary component, but modern Kubernetes communicates directly with CRI-compatible runtimes.

---

# Pod

Pods are the smallest deployable unit in Kubernetes.

```
Worker Node

↓

Pod

↓

Container
```

Applications run inside Pods,

not directly on Nodes.

---

# Complete Request Flow

Suppose a developer deploys an application.

```
Developer

↓

kubectl apply

↓

API Server

↓

Scheduler

↓

Worker Node

↓

kubelet

↓

Container Runtime

↓

Pod Running
```

This is the basic lifecycle of a deployment.

---

# Kubernetes Communication

```
kubectl

↓

API Server

↓

Scheduler

↓

Worker Node

↓

kubelet

↓

Container Runtime

↓

Container
```

The API Server is the communication hub.

---

# Multiple Worker Nodes

A production cluster usually contains many Worker Nodes.

```
Cluster

│

├── Worker-1

├── Worker-2

├── Worker-3

├── Worker-4

└── Worker-5
```

Applications are distributed across them.

---

# High Availability

If one Worker Node fails,

```
Worker-2

↓

Failure

↓

Controller Detects Failure

↓

Scheduler Chooses New Node

↓

Pod Recreated
```

This provides self-healing capabilities when sufficient cluster capacity is available.

---

# Production Architecture

```
Users

↓

Load Balancer

↓

API Server

↓

Scheduler

↓

Worker Nodes

↓

Pods

↓

Containers
```

Large production environments may have multiple Control Plane nodes for high availability.

---

# Kubernetes Architecture Summary

```
Developer

↓

kubectl

↓

API Server

↓

Scheduler

↓

Controller Manager

↓

etcd

↓

Worker Nodes

↓

kubelet

↓

Container Runtime

↓

Pods

↓

Containers
```

Every Kubernetes deployment follows this architecture.

---

# Common Beginner Mistakes

### Mistake 1

Thinking the Scheduler creates Pods.

The Scheduler only selects the Node.

The kubelet creates the Pod on the assigned Node.

---

### Mistake 2

Thinking etcd stores container images.

It stores cluster state and metadata,

not application images.

---

### Mistake 3

Confusing Pods with Nodes.

Nodes are machines.

Pods run on Nodes.

---

### Mistake 4

Thinking the API Server is optional.

Every Kubernetes operation passes through the API Server.

---

### Mistake 5

Ignoring Control Plane availability.

A production cluster should protect the Control Plane with redundancy and backups.

---

# Interview Questions

### Q1. What are the two main components of a Kubernetes Cluster?

- Control Plane
- Worker Nodes

---

### Q2. What is the role of the API Server?

The API Server receives, validates and processes all Kubernetes API requests.

---

### Q3. What is the role of the Scheduler?

The Scheduler selects the most suitable Worker Node for new Pods.

---

### Q4. What is etcd?

etcd is Kubernetes' distributed key-value store that maintains the cluster state and configuration.

---

### Q5. What does kubelet do?

The kubelet runs on every Worker Node and ensures Pods are created and remain healthy.

---

### Q6. What is the role of kube-proxy?

kube-proxy manages Service networking and routes traffic to the appropriate Pods.

---

# Production Best Practices

✔ Protect the Control Plane with high availability.

✔ Back up etcd regularly.

✔ Monitor kubelet health.

✔ Keep Kubernetes components updated.

✔ Use secure API authentication and authorization.

✔ Monitor Node resource usage.

✔ Restrict access to the API Server.

✔ Document cluster architecture.

---

# Key Takeaways

- A Kubernetes Cluster consists of a Control Plane and Worker Nodes.
- The API Server is the central communication point.
- The Scheduler assigns Pods to appropriate Worker Nodes.
- etcd stores the cluster's state and configuration.
- Worker Nodes run Pods using kubelet, kube-proxy and a container runtime.
- Understanding Kubernetes Architecture is essential before learning Pods, Deployments and Services.

---

# Next Section

## 9.4 Installing Kubernetes

In the next section, we will learn:

- Kubernetes Installation Methods
- Minikube
- kubeadm
- Managed Kubernetes (EKS, AKS, GKE)
- Installing kubectl
- Installing kubelet
- Installing containerd
- Cluster Initialization
- Best Practices
- Interview Questions
---

# 9.4 Installing Kubernetes

Now that you understand Kubernetes Architecture,

it's time to install Kubernetes.

There are several ways to install Kubernetes,

and each method is used for different purposes.

For example:

- Learning Kubernetes
- Development
- Testing
- Production
- Enterprise Clusters

Choosing the right installation method is important.

---

# Kubernetes Installation Methods

The most common installation methods are:

- Minikube
- kubeadm
- Managed Kubernetes (EKS, AKS, GKE)
- Kind (Kubernetes in Docker)
- K3s
- MicroK8s

Each serves a different use case.

---

# Which Installation Should You Choose?

| Method | Best For |
|---------|-----------|
| Minikube | Beginners |
| Kind | Learning & CI/CD |
| kubeadm | Production Learning |
| K3s | Lightweight Clusters |
| MicroK8s | Local Development |
| Amazon EKS | AWS Production |
| Azure AKS | Azure Production |
| Google GKE | Google Cloud Production |

---

# Installation Decision

```
Want to Learn?

↓

Minikube

------------------

Want Production Knowledge?

↓

kubeadm

------------------

Want Enterprise Cloud?

↓

EKS / AKS / GKE
```

---

# Lab Environment

Throughout this book,

we will use:

- Ubuntu 24.04 LTS
- Rocky Linux 9
- Amazon Linux 2023
- Windows 11 (WSL2)

Container Runtime

```
containerd
```

Kubernetes Version

```
Latest Stable Release
```

---

# Hardware Requirements

Minimum

- 2 CPU
- 2 GB RAM
- 20 GB Disk

Recommended

- 4 CPU
- 8 GB RAM
- SSD Storage

Production clusters require significantly higher resources depending on workloads.

---

# Software Requirements

Before installing Kubernetes,

install:

- Docker (optional for image building)
- containerd
- kubectl
- kubeadm
- kubelet
- Git

---

# Install kubectl

Linux

Download the latest stable version.

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

Make it executable.

```bash
chmod +x kubectl
```

Move it into the system PATH.

```bash
sudo mv kubectl /usr/local/bin/
```

Verify installation.

```bash
kubectl version --client
```

---

# Install containerd

Ubuntu

```bash
sudo apt update

sudo apt install -y containerd
```

Enable the service.

```bash
sudo systemctl enable containerd

sudo systemctl start containerd
```

Verify.

```bash
systemctl status containerd
```

---

# Install kubeadm

Ubuntu

Update package index.

```bash
sudo apt update
```

Install packages.

```bash
sudo apt install -y kubelet kubeadm kubectl
```

Prevent automatic upgrades.

```bash
sudo apt-mark hold kubelet kubeadm kubectl
```

---

# Verify Installation

```bash
kubeadm version

kubectl version --client

kubelet --version
```

All commands should display version information.

---

# Disable Swap

Kubernetes requires swap to be disabled for kubeadm-based installations unless configured otherwise.

Check swap.

```bash
swapon --show
```

Disable swap.

```bash
sudo swapoff -a
```

Temporarily,

swap is disabled until reboot.

To disable permanently,

remove or comment the swap entry from:

```
/etc/fstab
```

---

# Enable Required Kernel Modules

Load modules.

```bash
sudo modprobe overlay

sudo modprobe br_netfilter
```

Verify.

```bash
lsmod | grep br_netfilter
```

---

# Configure Kernel Parameters

Create configuration.

```bash
sudo tee /etc/sysctl.d/kubernetes.conf <<EOF
net.bridge.bridge-nf-call-iptables=1
net.bridge.bridge-nf-call-ip6tables=1
net.ipv4.ip_forward=1
EOF
```

Apply settings.

```bash
sudo sysctl --system
```

---

# Configure containerd

Generate default configuration.

```bash
sudo mkdir -p /etc/containerd

containerd config default | sudo tee /etc/containerd/config.toml
```

Restart containerd.

```bash
sudo systemctl restart containerd
```

---

# Initialize Kubernetes Cluster

On the Control Plane node,

run:

```bash
sudo kubeadm init
```

Example workflow

```
Initialize Cluster

↓

Create Certificates

↓

Start Control Plane

↓

Generate Join Token
```

---

# Configure kubectl

After initialization,

copy the configuration.

```bash
mkdir -p $HOME/.kube

sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

Now verify.

```bash
kubectl get nodes
```

---

# Install Pod Network

A Kubernetes cluster requires a Container Network Interface (CNI) plugin.

Popular choices include:

- Calico
- Flannel
- Cilium
- Weave Net

Without a CNI,

Pods cannot communicate across Nodes.

---

# Example Using Calico

Apply the manifest.

```bash
kubectl apply -f calico.yaml
```

(Download the official manifest from the Calico project before applying.)

Wait until Pods become ready.

```bash
kubectl get pods -A
```

---

# Join Worker Node

Use the command generated by:

```bash
kubeadm init
```

Example

```bash
sudo kubeadm join CONTROL_PLANE_IP:6443 \
--token <token> \
--discovery-token-ca-cert-hash sha256:<hash>
```

The worker node joins the cluster.

---

# Verify Cluster

```bash
kubectl get nodes
```

Example

```
NAME        STATUS   ROLES           AGE

master      Ready    control-plane   5m

worker-1    Ready    <none>          2m
```

---

# Installation Workflow

```
Install containerd

↓

Install kubeadm

↓

Install kubelet

↓

Install kubectl

↓

Disable Swap

↓

Initialize Cluster

↓

Install CNI

↓

Join Worker Nodes

↓

Cluster Ready
```

---

# Managed Kubernetes

Cloud providers simplify installation.

Examples

```
AWS

↓

Amazon EKS

------------------

Azure

↓

AKS

------------------

Google Cloud

↓

GKE
```

The cloud provider manages much of the Control Plane infrastructure.

---

# Local Development Options

For learning,

popular options include:

- Minikube
- Kind
- MicroK8s

These require fewer resources than multi-node clusters.

---

# Real Production Installation

Large companies generally use:

```
Terraform

↓

AWS Infrastructure

↓

EKS

↓

Worker Nodes

↓

Applications
```

Infrastructure and Kubernetes clusters are commonly provisioned together.

---

# Common Beginner Mistakes

### Mistake 1

Forgetting to disable swap before using kubeadm.

---

### Mistake 2

Skipping CNI installation.

Pods remain in the `Pending` or `NotReady` state until networking is configured.

---

### Mistake 3

Ignoring container runtime configuration.

---

### Mistake 4

Not copying the kubeconfig file after cluster initialization.

---

### Mistake 5

Using outdated Kubernetes package versions without checking compatibility.

---

# Interview Questions

### Q1. Name three Kubernetes installation methods.

- kubeadm
- Minikube
- Amazon EKS

---

### Q2. Which command initializes a Kubernetes cluster?

```bash
kubeadm init
```

---

### Q3. Why must swap be disabled for kubeadm installations?

Because Kubernetes expects memory management behavior that is incompatible with swap in the default kubeadm setup.

---

### Q4. What is the purpose of a CNI plugin?

It provides networking so Pods can communicate within the cluster.

---

### Q5. Which command joins a Worker Node?

```bash
kubeadm join
```

---

### Q6. Which command displays cluster nodes?

```bash
kubectl get nodes
```

---

# Production Best Practices

✔ Use containerd as the container runtime.

✔ Keep Kubernetes components on compatible versions.

✔ Back up cluster configuration.

✔ Use a production-ready CNI plugin.

✔ Secure the Control Plane.

✔ Monitor Node health.

✔ Automate installation using Infrastructure as Code.

✔ Regularly upgrade Kubernetes following the supported upgrade path.

---

# Key Takeaways

- Kubernetes can be installed using kubeadm, Minikube, Kind or managed cloud services.
- A kubeadm installation requires containerd, kubelet, kubeadm, kubectl and a CNI plugin.
- Swap should be disabled for standard kubeadm deployments.
- Installing a CNI plugin is essential for Pod networking.
- Understanding the installation process helps troubleshoot and manage production clusters.

---

# Next Section

## 9.5 kubectl Basics

In the next section, we will learn:

- What is kubectl?
- kubectl Architecture
- Common kubectl Commands
- Creating Resources
- Viewing Resources
- Editing Resources
- Deleting Resources
- YAML Operations
- Best Practices
- Interview Questions
---

# 9.5 kubectl Basics

After installing Kubernetes,

the next tool every Kubernetes administrator must learn is:

```
kubectl
```

`kubectl` is the primary command-line interface (CLI) used to communicate with a Kubernetes cluster.

Almost every Kubernetes operation starts with `kubectl`.

---

# What is kubectl?

`kubectl` is the official Kubernetes command-line tool.

It allows you to:

- Create Resources
- Delete Resources
- Update Resources
- View Resources
- Debug Applications
- Monitor Cluster Health

Think of it as the interface between you and the Kubernetes API Server.

---

# kubectl Architecture

```
User

↓

kubectl

↓

API Server

↓

Kubernetes Cluster

↓

Pods
```

Every command passes through the API Server.

---

# How kubectl Works

Suppose you execute:

```bash
kubectl get pods
```

Workflow

```
kubectl

↓

API Server

↓

Query Cluster

↓

Return Pod Information
```

---

# Verify Cluster Connection

Before doing anything,

verify connectivity.

```bash
kubectl cluster-info
```

Example

```
Kubernetes control plane is running...
```

---

# Check Cluster Version

```bash
kubectl version
```

Client only

```bash
kubectl version --client
```

---

# Display Nodes

One of the most commonly used commands.

```bash
kubectl get nodes
```

Example

```
NAME          STATUS    ROLES

master        Ready     control-plane

worker-1      Ready     <none>
```

---

# Display Pods

```bash
kubectl get pods
```

Output

```
NAME

nginx

redis
```

---

# Display Pods in All Namespaces

```bash
kubectl get pods -A
```

or

```bash
kubectl get pods --all-namespaces
```

---

# Wide Output

```bash
kubectl get pods -o wide
```

Shows:

- Node
- IP Address
- Container Runtime
- Additional Details

---

# Describe Resource

Display complete information.

```bash
kubectl describe pod nginx
```

Information includes:

- Events
- Conditions
- Volumes
- Environment Variables
- IP Address
- Container Status

---

# View Logs

Display container logs.

```bash
kubectl logs nginx
```

For multi-container Pods,

specify the container.

```bash
kubectl logs POD_NAME -c CONTAINER_NAME
```

---

# Execute Commands Inside Pod

Open a shell.

```bash
kubectl exec -it nginx -- bash
```

If Bash is unavailable,

use:

```bash
kubectl exec -it nginx -- sh
```

---

# Create Resources

Apply YAML.

```bash
kubectl apply -f deployment.yaml
```

Workflow

```
YAML

↓

kubectl

↓

API Server

↓

Resource Created
```

---

# Delete Resource

```bash
kubectl delete pod nginx
```

Delete using YAML.

```bash
kubectl delete -f deployment.yaml
```

---

# Edit Resource

Modify an existing resource.

```bash
kubectl edit deployment nginx
```

An editor opens,

allowing live updates.

---

# Explain Resource

One of the most useful commands.

```bash
kubectl explain pod
```

Display a specific field.

```bash
kubectl explain pod.spec
```

This command is excellent for learning Kubernetes YAML.

---

# Resource Types

Common resources include:

```
Pods

Deployments

ReplicaSets

Services

Namespaces

ConfigMaps

Secrets

Ingress
```

---

# Get Deployments

```bash
kubectl get deployments
```

---

# Get Services

```bash
kubectl get svc
```

or

```bash
kubectl get services
```

---

# Get ReplicaSets

```bash
kubectl get rs
```

---

# Get Namespaces

```bash
kubectl get namespaces
```

---

# Get Events

Useful for troubleshooting.

```bash
kubectl get events
```

Sort by time.

```bash
kubectl get events --sort-by=.metadata.creationTimestamp
```

---

# Watch Resources

Continuously monitor changes.

```bash
kubectl get pods -w
```

New Pods appear automatically.

---

# Resource Output Formats

Default

```bash
kubectl get pods
```

Wide

```bash
kubectl get pods -o wide
```

YAML

```bash
kubectl get pod nginx -o yaml
```

JSON

```bash
kubectl get pod nginx -o json
```

---

# Generate YAML

Create YAML without creating the resource.

```bash
kubectl create deployment nginx \
--image=nginx \
--dry-run=client \
-o yaml
```

Useful for learning and version control.

---

# Apply vs Create

```
kubectl create

↓

Create Only

----------------

kubectl apply

↓

Create or Update
```

Production environments generally use declarative manifests with `kubectl apply`.

---

# Label Resources

Add a label.

```bash
kubectl label pod nginx app=web
```

---

# Annotate Resources

```bash
kubectl annotate pod nginx owner=devops
```

Annotations store additional metadata.

---

# Scale Deployment

```bash
kubectl scale deployment nginx --replicas=5
```

The Deployment now maintains five replicas.

---

# Rollout Status

Check deployment progress.

```bash
kubectl rollout status deployment nginx
```

---

# Rollout History

```bash
kubectl rollout history deployment nginx
```

---

# Restart Deployment

```bash
kubectl rollout restart deployment nginx
```

Useful after ConfigMap or Secret updates in some scenarios.

---

# Port Forward

Access an application locally.

```bash
kubectl port-forward pod/nginx 8080:80
```

Open:

```
http://localhost:8080
```

---

# Copy Files

Copy a file from a Pod.

```bash
kubectl cp nginx:/etc/nginx/nginx.conf .
```

Copy to a Pod.

```bash
kubectl cp localfile nginx:/tmp/
```

---

# Contexts

Display contexts.

```bash
kubectl config get-contexts
```

Switch context.

```bash
kubectl config use-context CONTEXT_NAME
```

Contexts help manage multiple clusters.

---

# Namespace Operations

Use a namespace.

```bash
kubectl get pods -n production
```

Create namespace.

```bash
kubectl create namespace production
```

---

# kubectl Workflow

```
Write YAML

↓

kubectl apply

↓

API Server

↓

Scheduler

↓

Worker Node

↓

Pod Running
```

---

# Real Production Workflow

```
Developer

↓

GitHub

↓

CI/CD

↓

kubectl apply

↓

API Server

↓

Production Cluster
```

Most organizations automate `kubectl` through CI/CD pipelines rather than running commands manually on production clusters.

---

# Common Beginner Mistakes

### Mistake 1

Deleting Pods instead of updating Deployments.

Controllers may recreate Pods automatically.

---

### Mistake 2

Editing production resources manually.

Prefer updating version-controlled YAML manifests.

---

### Mistake 3

Ignoring namespaces.

Many commands default to the `default` namespace.

---

### Mistake 4

Using `kubectl create` repeatedly for existing resources.

Use `kubectl apply` for declarative workflows.

---

### Mistake 5

Ignoring events while troubleshooting.

`kubectl get events` often provides valuable diagnostic information.

---

# Interview Questions

### Q1. What is kubectl?

`kubectl` is the official Kubernetes command-line tool used to manage Kubernetes clusters.

---

### Q2. Which command displays all Pods?

```bash
kubectl get pods
```

---

### Q3. Which command shows detailed Pod information?

```bash
kubectl describe pod POD_NAME
```

---

### Q4. Which command displays Pod logs?

```bash
kubectl logs POD_NAME
```

---

### Q5. What is the difference between `kubectl create` and `kubectl apply`?

`create` creates new resources only, while `apply` creates new resources or updates existing declarative configurations.

---

### Q6. Which command scales a Deployment?

```bash
kubectl scale deployment DEPLOYMENT_NAME --replicas=NUMBER
```

---

# Production Best Practices

✔ Store Kubernetes manifests in Git.

✔ Prefer `kubectl apply` for declarative deployments.

✔ Use namespaces to isolate workloads.

✔ Avoid manual production changes.

✔ Review rollout status after deployments.

✔ Use labels consistently.

✔ Monitor events during troubleshooting.

✔ Use contexts carefully when managing multiple clusters.

---

# Key Takeaways

- `kubectl` is the primary interface for interacting
---

# 9.6 Pods

After learning Kubernetes architecture and `kubectl`,

the next concept to understand is the **Pod**.

Pods are the **smallest deployable unit** in Kubernetes.

Every application running inside Kubernetes runs inside a Pod.

You never deploy a container directly to Kubernetes.

Instead,

you deploy a Pod,

and the Pod contains one or more containers.

---

# What is a Pod?

A Pod is the smallest object that Kubernetes creates and manages.

A Pod acts as a wrapper around one or more containers.

```
Pod

↓

Container
```

If you deploy an Nginx application,

Kubernetes creates:

```
Pod

↓

Nginx Container
```

---

# Why Pods?

You may wonder,

"Why doesn't Kubernetes run containers directly?"

Pods provide additional functionality such as:

- Shared Network
- Shared Storage
- Health Monitoring
- Scheduling
- Lifecycle Management

Containers inside the same Pod work together.

---

# Pod Architecture

```
Worker Node

↓

Pod

↓

Container

↓

Application
```

The Worker Node runs the Pod,

and the Pod runs one or more containers.

---

# Kubernetes Hierarchy

```
Cluster

↓

Node

↓

Pod

↓

Container

↓

Application
```

This hierarchy is fundamental to Kubernetes.

---

# Pod Components

A Pod consists of:

```
Pod

│

├── One or More Containers

├── Network Namespace

├── Shared Storage

└── Metadata
```

---

# Single-Container Pod

Most Pods contain only one container.

Example

```
Pod

↓

Nginx Container
```

This is the most common production pattern.

---

# Multi-Container Pod

Sometimes multiple containers work together.

Example

```
Pod

│

├── Main Application

└── Logging Sidecar
```

Both containers share the same Pod resources.

---

# Shared Network

All containers inside a Pod share:

- IP Address
- Port Space
- Hostname

Example

```
Pod

↓

Container A

↓

localhost

↓

Container B
```

Containers communicate using `localhost`.

---

# Shared Storage

Containers can also share volumes.

```
Pod

↓

Volume

↓

Container A

↓

Container B
```

This allows containers to exchange data.

---

# Pod Lifecycle

```
Pending

↓

Running

↓

Succeeded

↓

Failed

↓

Unknown
```

Each Pod moves through lifecycle phases.

---

# Pending

```
Pod Created

↓

Waiting
```

The Pod has been accepted,

but is waiting for scheduling or image download.

---

# Running

```
Node Selected

↓

Container Started

↓

Application Running
```

The application is operational.

---

# Succeeded

The Pod completed successfully.

Common example:

- Backup Job
- Batch Processing
- Data Import

---

# Failed

The Pod terminated unexpectedly.

Possible reasons:

- Application Crash
- Image Pull Failure
- Configuration Error
- Resource Exhaustion

---

# Unknown

Kubernetes cannot determine the Pod's current status,

usually due to communication issues with the Node.

---

# Create a Pod

Example YAML

```yaml
apiVersion: v1

kind: Pod

metadata:

  name: nginx

spec:

  containers:

  - name: nginx

    image: nginx
```

Create the Pod.

```bash
kubectl apply -f pod.yaml
```

---

# View Pods

```bash
kubectl get pods
```

Example

```
NAME      READY   STATUS

nginx     1/1     Running
```

---

# Describe Pod

```bash
kubectl describe pod nginx
```

Displays:

- Events
- Conditions
- Node
- Volumes
- Environment Variables
- Container Details

---

# View Pod Logs

```bash
kubectl logs nginx
```

---

# Execute Inside Pod

```bash
kubectl exec -it nginx -- bash
```

or

```bash
kubectl exec -it nginx -- sh
```

---

# Delete Pod

```bash
kubectl delete pod nginx
```

If the Pod is managed by a Deployment,

it will usually be recreated automatically.

---

# Pod Restart

Pods are generally treated as replaceable objects.

Instead of repairing a failed Pod,

Kubernetes typically creates a replacement.

---

# Pod Scheduling

Workflow

```
Pod Created

↓

API Server

↓

Scheduler

↓

Worker Node

↓

kubelet

↓

Pod Running
```

---

# Pod Networking

Every Pod receives:

- One IP Address
- One Hostname

Pods communicate directly with other Pods over the cluster network.

---

# Pod Storage

Pods can use:

- EmptyDir
- Persistent Volumes
- ConfigMaps
- Secrets

Storage options will be covered later.

---

# Init Containers

A Pod can contain Init Containers.

Workflow

```
Init Container

↓

Complete

↓

Main Container Starts
```

Init Containers perform setup tasks before application containers start.

---

# Sidecar Containers

Example

```
Pod

│

├── Web Server

└── Log Collector
```

The sidecar supports the main application.

---

# Resource Requests

Example

```yaml
resources:

  requests:

    cpu: "250m"

    memory: "256Mi"
```

Requests reserve resources for the Pod.

---

# Resource Limits

Example

```yaml
resources:

  limits:

    cpu: "500m"

    memory: "512Mi"
```

Limits prevent excessive resource consumption.

---

# Health Checks

Kubernetes supports:

- Liveness Probes
- Readiness Probes
- Startup Probes

These help determine application health.

---

# Pod Labels

Example

```yaml
labels:

  app: nginx

  env: production
```

Labels organize and identify Pods.

---

# Pod Workflow

```
Developer

↓

YAML

↓

kubectl apply

↓

API Server

↓

Scheduler

↓

Node

↓

Pod

↓

Container Running
```

---

# Real Production Example

An online banking application contains:

```
Pod

↓

Java Application

↓

Application Running
```

Another Pod

```
Pod

↓

Logging Sidecar
```

Another Pod

```
Pod

↓

Monitoring Agent
```

Each Pod performs a specific role.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Pods and Containers are the same.

Containers run **inside** Pods.

---

### Mistake 2

Creating standalone Pods for long-running applications.

Use Deployments instead.

---

### Mistake 3

Ignoring Pod Events during troubleshooting.

Use:

```bash
kubectl describe pod
```

---

### Mistake 4

Not defining resource requests and limits.

---

### Mistake 5

Trying to manually restart Pods.

Controllers usually replace Pods automatically.

---

# Interview Questions

### Q1. What is a Pod?

A Pod is the smallest deployable unit in Kubernetes that contains one or more containers.

---

### Q2. Can a Pod contain multiple containers?

Yes.

Multiple containers can run inside a single Pod and share networking and storage.

---

### Q3. Which command displays Pods?

```bash
kubectl get pods
```

---

### Q4. Which command displays Pod logs?

```bash
kubectl logs POD_NAME
```

---

### Q5. Why are Pods used instead of directly running containers?

Pods provide shared networking, storage, lifecycle management and scheduling.

---

### Q6. What are the common Pod lifecycle phases?

- Pending
- Running
- Succeeded
- Failed
- Unknown

---

# Production Best Practices

✔ Use Deployments instead of standalone Pods for applications.

✔ Configure resource requests and limits.

✔ Implement health probes.

✔ Use descriptive labels.

✔ Monitor Pod events.

✔ Keep Pods focused on a single responsibility.

✔ Use Init Containers for initialization tasks.

✔ Avoid manually managing Pods created by controllers.

---

# Key Takeaways

- Pods are the smallest deployable unit in Kubernetes.
- Every container runs inside a Pod.
- Pods provide shared networking and storage for containers.
- Kubernetes schedules Pods onto Worker Nodes.
- Understanding Pods is essential before learning ReplicaSets and Deployments.

---

# Next Section

## 9.7 ReplicaSets

In the next section, we will learn:

- What is a ReplicaSet?
- Why ReplicaSets are Needed
- ReplicaSet Architecture
- Scaling Pods
- Self-Healing
- ReplicaSet YAML
- ReplicaSet vs Pod
- Best Practices
- Interview Questions
---

# 9.7 ReplicaSets

In the previous section,

you learned that Pods are the smallest deployable units in Kubernetes.

But there is a problem.

Suppose you manually create one Pod.

```
Pod

↓

Running
```

Now imagine the Pod crashes.

```
Pod

↓

Crash

↓

Application Down
```

Who creates a new Pod?

This is where **ReplicaSets** become important.

ReplicaSets ensure that the desired number of Pods are always running.

---

# What is a ReplicaSet?

A ReplicaSet is a Kubernetes controller that maintains a specified number of identical Pods.

It continuously monitors Pods.

If a Pod fails,

the ReplicaSet automatically creates a replacement.

---

# Simple Definition

```
ReplicaSet

↓

Maintains

↓

Desired Number of Pods
```

---

# Why ReplicaSets?

Without a ReplicaSet,

```
Pod

↓

Crash

↓

Application Down
```

With a ReplicaSet,

```
Pod

↓

Crash

↓

ReplicaSet

↓

New Pod Created

↓

Application Running
```

---

# ReplicaSet Workflow

```
ReplicaSet

↓

Monitor Pods

↓

Detect Failure

↓

Create Replacement Pod
```

---

# ReplicaSet Architecture

```
ReplicaSet

│

├── Pod 1

├── Pod 2

└── Pod 3
```

Desired replicas:

```
3
```

ReplicaSet continuously maintains three Pods.

---

# Desired State

Suppose you specify:

```yaml
replicas: 3
```

Kubernetes understands:

```
Always Keep

↓

3 Pods

↓

Running
```

---

# Automatic Recovery

Current state

```
Pod-1

Pod-2

Pod-3
```

Pod-2 crashes.

Current state

```
Pod-1

Pod-3
```

ReplicaSet immediately creates:

```
Pod-4
```

Final state

```
Pod-1

Pod-3

Pod-4
```

The desired number of running Pods is restored.

---

# Scaling

Suppose you change:

```yaml
replicas: 5
```

ReplicaSet creates:

```
Pod-4

Pod-5
```

Now five Pods are running.

---

# Scale Down

Suppose:

```yaml
replicas: 2
```

ReplicaSet removes excess Pods.

Final state

```
Pod-1

Pod-2
```

---

# ReplicaSet YAML

Example

```yaml
apiVersion: apps/v1

kind: ReplicaSet

metadata:

  name: nginx-rs

spec:

  replicas: 3

  selector:

    matchLabels:

      app: nginx

  template:

    metadata:

      labels:

        app: nginx

    spec:

      containers:

      - name: nginx

        image: nginx
```

---

# Understanding the YAML

```
ReplicaSet

│

├── replicas

├── selector

└── template
```

Each section has a specific purpose.

---

# replicas

Example

```yaml
replicas: 3
```

Meaning

```
Maintain

↓

3 Running Pods
```

---

# Selector

Example

```yaml
selector:

  matchLabels:

    app: nginx
```

The selector identifies which Pods belong to the ReplicaSet.

---

# Pod Template

The template describes how new Pods should be created.

Example

```yaml
template:

  spec:

    containers:

    - image: nginx
```

Whenever a replacement Pod is required,

the ReplicaSet uses this template.

---

# Create ReplicaSet

Apply the YAML.

```bash
kubectl apply -f replicaset.yaml
```

---

# View ReplicaSets

```bash
kubectl get rs
```

Example

```
NAME

nginx-rs
```

---

# View Pods

```bash
kubectl get pods
```

Example

```
nginx-rs-abcde

nginx-rs-fghij

nginx-rs-klmno
```

Three Pods are running.

---

# Describe ReplicaSet

```bash
kubectl describe rs nginx-rs
```

Displays:

- Replicas
- Labels
- Events
- Pod Template
- Selector

---

# Delete One Pod

Delete a Pod.

```bash
kubectl delete pod POD_NAME
```

Immediately afterwards,

ReplicaSet creates a new Pod.

---

# Scale ReplicaSet

Increase replicas.

```bash
kubectl scale rs nginx-rs --replicas=5
```

Decrease replicas.

```bash
kubectl scale rs nginx-rs --replicas=2
```

---

# Delete ReplicaSet

```bash
kubectl delete rs nginx-rs
```

Unless configured otherwise,

the managed Pods are also removed.

---

# ReplicaSet Lifecycle

```
ReplicaSet Created

↓

Pods Created

↓

Pod Failure

↓

ReplicaSet Detects Failure

↓

Replacement Pod Created
```

---

# Labels and Selectors

ReplicaSets identify Pods using labels.

Pod

```yaml
labels:

  app: nginx
```

ReplicaSet

```yaml
selector:

  matchLabels:

    app: nginx
```

Labels must match,

otherwise the ReplicaSet cannot manage the Pod.

---

# ReplicaSet vs Pod

| Pod | ReplicaSet |
|------|------------|
| Runs Containers | Manages Pods |
| No Self-Healing | Self-Healing |
| Manual Scaling | Automatic Scaling |
| Single Object | Controller |

---

# ReplicaSet vs Deployment

```
Deployment

↓

ReplicaSet

↓

Pods
```

Deployments manage ReplicaSets.

In production,

Engineers usually create Deployments instead of creating ReplicaSets directly.

---

# Self-Healing Example

```
Desired

↓

3 Pods

----------------

Actual

↓

2 Pods

----------------

ReplicaSet

↓

Creates New Pod

----------------

Result

↓

3 Pods
```

---

# Scaling Example

```
replicas: 2

↓

2 Pods

----------------

Change

↓

replicas: 5

----------------

Result

↓

5 Pods
```

---

# Production Example

An e-commerce application requires:

```
Frontend

↓

3 Pods

Backend

↓

5 Pods

API

↓

4 Pods
```

ReplicaSets ensure that the required number of Pods always remain available.

---

# Common Beginner Mistakes

### Mistake 1

Creating standalone Pods for production applications.

Use Deployments instead.

---

### Mistake 2

Changing Pod labels without updating the ReplicaSet selector.

The ReplicaSet may stop managing those Pods.

---

### Mistake 3

Thinking ReplicaSets perform rolling updates.

Deployments provide rolling updates.

---

### Mistake 4

Deleting Pods to permanently reduce replicas.

ReplicaSets recreate deleted Pods unless the replica count is changed.

---

### Mistake 5

Confusing ReplicaSets with Deployments.

ReplicaSets maintain Pod count.

Deployments manage ReplicaSets and provide advanced deployment features.

---

# Interview Questions

### Q1. What is a ReplicaSet?

A ReplicaSet is a Kubernetes controller that maintains a specified number of identical Pods.

---

### Q2. What is the primary purpose of a ReplicaSet?

To ensure the desired number of Pods are always running.

---

### Q3. Which field specifies the number of Pods?

```yaml
replicas
```

---

### Q4. How does a ReplicaSet identify its Pods?

Using label selectors.

---

### Q5. Which command displays ReplicaSets?

```bash
kubectl get rs
```

---

### Q6. Why are Deployments generally preferred over ReplicaSets?

Deployments provide additional capabilities such as rolling updates, rollbacks and easier application lifecycle management.

---

# Production Best Practices

✔ Use Deployments instead of standalone ReplicaSets.

✔ Use meaningful labels.

✔ Keep selectors consistent.

✔ Scale applications using ReplicaSets through Deployments.

✔ Monitor Pod health.

✔ Configure resource requests and limits.

✔ Store ReplicaSet definitions in Git.

✔ Use CI/CD for deployments.

---

# Key Takeaways

- ReplicaSets maintain the desired number of running Pods.
- They provide self-healing by replacing failed Pods.
- ReplicaSets use labels and selectors to manage Pods.
- Scaling is achieved by changing the replica count.
- In production, ReplicaSets are typically managed through Deployments rather than created directly.

---

# Next Section

## 9.8 Deployments

In the next section, we will learn:

- What is a Deployment?
- Deployment Architecture
- Deployment YAML
- Rolling Updates
- Rollbacks
- Scaling Applications
- Deployment Strategies
- Best Practices
- Interview Questions
---

# 9.8 Deployments

In the previous section,

you learned that ReplicaSets ensure a desired number of Pods remain running.

However,

ReplicaSets alone are not enough for managing real-world applications.

Imagine a production application serving millions of users.

One day,

you release a new application version.

How do you:

- Update the application?
- Roll back if something fails?
- Scale the application?
- Avoid downtime?

These challenges are solved using **Deployments**.

Deployments are one of the most commonly used Kubernetes resources.

---

# What is a Deployment?

A Deployment is a Kubernetes object that manages ReplicaSets and Pods.

Instead of creating Pods directly,

or creating ReplicaSets manually,

Engineers create Deployments.

```
Deployment

↓

ReplicaSet

↓

Pods

↓

Containers
```

---

# Why Deployments?

Without Deployments

```
Pod

↓

ReplicaSet

↓

Manual Updates

↓

Manual Rollback
```

With Deployments

```
Deployment

↓

ReplicaSet

↓

Pods

↓

Automatic Updates

↓

Rollback Support
```

---

# Deployment Responsibilities

Deployments provide:

- Rolling Updates
- Rollbacks
- Scaling
- Self-Healing
- Version History
- Declarative Management

---

# Deployment Architecture

```
Deployment

↓

ReplicaSet

↓

Pod

↓

Container
```

The Deployment controls the ReplicaSet,

which controls the Pods.

---

# Deployment Workflow

```
Developer

↓

Deployment YAML

↓

kubectl apply

↓

API Server

↓

Deployment

↓

ReplicaSet

↓

Pods

↓

Application Running
```

---

# Deployment YAML

Example

```yaml
apiVersion: apps/v1

kind: Deployment

metadata:

  name: nginx-deployment

spec:

  replicas: 3

  selector:

    matchLabels:

      app: nginx

  template:

    metadata:

      labels:

        app: nginx

    spec:

      containers:

      - name: nginx

        image: nginx:latest
```

---

# YAML Components

```
Deployment

│

├── replicas

├── selector

└── template
```

These sections define the desired application state.

---

# Create Deployment

Apply the manifest.

```bash
kubectl apply -f deployment.yaml
```

---

# View Deployments

```bash
kubectl get deployments
```

or

```bash
kubectl get deploy
```

Example

```
NAME

nginx-deployment
```

---

# View ReplicaSets

```bash
kubectl get rs
```

Deployment automatically creates a ReplicaSet.

---

# View Pods

```bash
kubectl get pods
```

Example

```
nginx-deployment-7d8f9

nginx-deployment-2bc31

nginx-deployment-91af8
```

---

# Describe Deployment

```bash
kubectl describe deployment nginx-deployment
```

Displays:

- Replicas
- Strategy
- Events
- Conditions
- Pod Template
- Labels

---

# Scaling Deployment

Increase replicas.

```bash
kubectl scale deployment nginx-deployment --replicas=5
```

Decrease replicas.

```bash
kubectl scale deployment nginx-deployment --replicas=2
```

Deployment updates the ReplicaSet automatically.

---

# Rolling Updates

Suppose version 1.0 is running.

```
Version 1.0

↓

Users
```

A new image is deployed.

```
Version 2.0
```

Instead of replacing all Pods at once,

Deployment performs a Rolling Update.

```
Old Pod

↓

New Pod

↓

Old Pod

↓

New Pod
```

The application remains available throughout the update.

---

# Update Deployment

Update the image.

```bash
kubectl set image deployment/nginx-deployment \
nginx=nginx:1.27
```

Kubernetes starts a rolling update.

---

# Rolling Update Workflow

```
Deployment

↓

Create New ReplicaSet

↓

New Pods Created

↓

Old Pods Removed

↓

Deployment Complete
```

---

# Check Rollout Status

Monitor progress.

```bash
kubectl rollout status deployment nginx-deployment
```

Example

```
deployment successfully rolled out
```

---

# Rollout History

Display deployment history.

```bash
kubectl rollout history deployment nginx-deployment
```

Example

```
REVISION

1

2

3
```

---

# Rollback Deployment

Suppose version 2 fails.

Rollback.

```bash
kubectl rollout undo deployment nginx-deployment
```

Deployment returns to the previous revision.

---

# Rollback Workflow

```
Version 1

↓

Update

↓

Version 2

↓

Problem

↓

Rollback

↓

Version 1
```

---

# Update Strategy

Deployments support strategies.

```
Deployment

│

├── RollingUpdate

└── Recreate
```

---

# RollingUpdate Strategy

Default strategy.

```
Old Pods

↓

Replace Gradually

↓

New Pods
```

Users experience little or no downtime.

---

# Recreate Strategy

```
Old Pods Deleted

↓

New Pods Created
```

This may cause downtime,

so it is used only for workloads where brief interruption is acceptable.

---

# Deployment Strategy Example

```yaml
strategy:

  type: RollingUpdate
```

---

# Pause Deployment

Pause updates.

```bash
kubectl rollout pause deployment nginx-deployment
```

---

# Resume Deployment

```bash
kubectl rollout resume deployment nginx-deployment
```

---

# Restart Deployment

```bash
kubectl rollout restart deployment nginx-deployment
```

Useful after updating ConfigMaps or Secrets in many scenarios.

---

# Delete Deployment

```bash
kubectl delete deployment nginx-deployment
```

Deployment,

ReplicaSet

and managed Pods are removed.

---

# Deployment Lifecycle

```
Deployment Created

↓

ReplicaSet Created

↓

Pods Created

↓

Application Running

↓

Update

↓

Rolling Update

↓

New Version Running
```

---

# Deployment vs ReplicaSet

| Deployment | ReplicaSet |
|------------|------------|
| Manages ReplicaSets | Manages Pods |
| Rolling Updates | No Rolling Updates |
| Rollbacks | No Rollbacks |
| Version History | No Version History |
| Preferred for Applications | Usually Managed by Deployments |

---

# Deployment vs Pod

| Deployment | Pod |
|------------|-----|
| Production Ready | Basic Workload |
| Auto Healing | No Controller |
| Scaling | Manual |
| Updates | Manual |
| Rollbacks | Not Supported |

---

# Production Example

An online banking application runs:

```
Deployment

↓

5 Pods

↓

Users
```

A new version is released.

Deployment performs:

```
Rolling Update

↓

No Downtime

↓

Users Continue Working
```

If the release fails,

Deployment performs a rollback.

---

# Common Beginner Mistakes

### Mistake 1

Creating standalone Pods instead of Deployments.

---

### Mistake 2

Deleting Pods manually instead of updating the Deployment.

---

### Mistake 3

Using the `Recreate` strategy without understanding the downtime impact.

---

### Mistake 4

Not checking rollout status after deployments.

---

### Mistake 5

Ignoring rollout history before performing rollbacks.

---

# Interview Questions

### Q1. What is a Kubernetes Deployment?

A Deployment is a Kubernetes object that manages ReplicaSets and provides declarative updates for Pods.

---

### Q2. What object does a Deployment manage directly?

A ReplicaSet.

---

### Q3. Which command creates a Deployment?

```bash
kubectl apply -f deployment.yaml
```

---

### Q4. Which command checks rollout status?

```bash
kubectl rollout status deployment DEPLOYMENT_NAME
```

---

### Q5. Which command rolls back a Deployment?

```bash
kubectl rollout undo deployment DEPLOYMENT_NAME
```

---

### Q6. What is the default Deployment strategy?

```
RollingUpdate
```

---

# Production Best Practices

✔ Use Deployments for long-running applications.

✔ Prefer RollingUpdate for production.

✔ Verify rollout status after every deployment.

✔ Test rollback procedures regularly.

✔ Store Deployment manifests in Git.

✔ Configure readiness and liveness probes.

✔ Define resource requests and limits.

✔ Automate deployments through CI/CD.

---

# Key Takeaways

- Deployments are the preferred way to run applications in Kubernetes.
- Deployments manage ReplicaSets, which in turn manage Pods.
- Rolling Updates allow new versions to be deployed with minimal downtime.
- Rollbacks enable quick recovery from failed deployments.
- Deployments provide scalability, version history and declarative application management.

---

# Next Section

## 9.9 Services

In the next section, we will learn:

- What is a Kubernetes Service?
- Why Services are Needed
- Service Types
- ClusterIP
- NodePort
- LoadBalancer
- ExternalName
- Service Discovery
- Best Practices
- Interview Questions
---

# 9.9 Services

In the previous section,

you learned that Deployments create and manage Pods.

However,

there is a major problem.

Pods are **temporary**.

If a Pod crashes,

Kubernetes creates a new one.

The new Pod receives a **new IP address**.

Imagine your application is trying to communicate with a Pod using its old IP.

```
Old Pod

↓

Deleted

↓

New Pod

↓

New IP
```

Your application would lose connectivity.

To solve this problem,

Kubernetes provides **Services**.

---

# What is a Service?

A Kubernetes Service is a stable networking abstraction that provides a consistent way to access one or more Pods.

Instead of communicating with Pod IPs directly,

applications communicate with a Service.

The Service automatically forwards traffic to healthy Pods.

---

# Simple Definition

```
Pods

↓

Service

↓

Stable Access
```

Pods may change,

the Service remains.

---

# Why Services?

Without Services

```
Application

↓

Pod IP

↓

Pod Deleted

↓

Connection Failed
```

With Services

```
Application

↓

Service

↓

Current Running Pod

↓

Application Works
```

---

# Service Architecture

```
Client

↓

Service

↓

Pod 1

Pod 2

Pod 3
```

The Service distributes traffic among Pods.

---

# How Services Work

Every Service uses:

- Labels
- Selectors

Example

Pods

```yaml
labels:

  app: nginx
```

Service

```yaml
selector:

  app: nginx
```

The Service forwards requests to all matching Pods.

---

# Service Workflow

```
User

↓

Service

↓

Pod

↓

Container

↓

Application
```

The user never communicates directly with Pod IPs.

---

# Why Not Use Pod IP?

Because Pods are temporary.

```
Pod

↓

Crash

↓

New Pod

↓

Different IP
```

A Service provides a permanent endpoint.

---

# Types of Services

Kubernetes provides four primary Service types.

```
Services

│

├── ClusterIP

├── NodePort

├── LoadBalancer

└── ExternalName
```

Each type is designed for a different networking scenario.

---

# ClusterIP

ClusterIP is the **default** Service type.

It exposes the application only inside the cluster.

```
Pod

↓

ClusterIP Service

↓

Other Pods
```

External users cannot access it directly.

---

# ClusterIP Use Cases

Typical examples:

- Backend APIs
- Databases
- Redis
- Internal Microservices

---

# ClusterIP Example

```yaml
apiVersion: v1

kind: Service

metadata:

  name: nginx-service

spec:

  selector:

    app: nginx

  ports:

  - port: 80

    targetPort: 80
```

No `type` is specified,

so Kubernetes creates a ClusterIP Service.

---

# NodePort

NodePort exposes an application through a port on every Worker Node.

```
User

↓

Node IP:30080

↓

Service

↓

Pods
```

Default NodePort range:

```
30000–32767
```

---

# NodePort Example

```yaml
spec:

  type: NodePort

  selector:

    app: nginx

  ports:

  - port: 80

    targetPort: 80

    nodePort: 30080
```

Users access:

```
http://NODE_IP:30080
```

---

# LoadBalancer

LoadBalancer creates an external load balancer using the cloud provider.

```
Internet

↓

Load Balancer

↓

Service

↓

Pods
```

Supported on managed Kubernetes platforms like:

- Amazon EKS
- Azure AKS
- Google GKE

---

# LoadBalancer Example

```yaml
spec:

  type: LoadBalancer

  selector:

    app: nginx

  ports:

  - port: 80

    targetPort: 80
```

The cloud provider assigns a public IP or DNS name.

---

# ExternalName

ExternalName maps a Kubernetes Service to an external DNS name.

```
Application

↓

ExternalName

↓

api.example.com
```

No Pods are involved.

---

# ExternalName Example

```yaml
spec:

  type: ExternalName

  externalName: api.example.com
```

---

# Service Discovery

Every Service receives a DNS name.

Example

```
nginx-service.default.svc.cluster.local
```

Applications usually use the shorter Service name.

```
Frontend

↓

http://nginx-service
```

Kubernetes DNS resolves it automatically.

---

# Service Load Balancing

Suppose three Pods exist.

```
Service

↓

Pod-1

Pod-2

Pod-3
```

Incoming requests are distributed across healthy Pods.

---

# Endpoints

A Service tracks the Pods behind it.

```
Service

↓

Endpoints

↓

Pod-1

Pod-2

Pod-3
```

If a Pod becomes unavailable,

its endpoint is removed.

---

# Service YAML

Complete example

```yaml
apiVersion: v1

kind: Service

metadata:

  name: nginx-service

spec:

  selector:

    app: nginx

  ports:

  - protocol: TCP

    port: 80

    targetPort: 80

  type: ClusterIP
```

---

# Create Service

```bash
kubectl apply -f service.yaml
```

---

# View Services

```bash
kubectl get svc
```

or

```bash
kubectl get services
```

Example

```
NAME             TYPE

nginx-service    ClusterIP
```

---

# Describe Service

```bash
kubectl describe svc nginx-service
```

Displays:

- Endpoints
- Labels
- Selector
- Ports
- Events

---

# Delete Service

```bash
kubectl delete svc nginx-service
```

The Service is removed,

but the Pods continue running.

---

# Service Lifecycle

```
Deployment

↓

Pods

↓

Service Created

↓

Traffic Routed

↓

Pod Failure

↓

New Pod

↓

Service Continues Working
```

The Service remains stable even when Pods change.

---

# Service vs Pod

| Pod | Service |
|------|----------|
| Temporary | Stable |
| IP Changes | Stable IP & DNS |
| Runs Containers | Routes Traffic |
| Not Load Balanced | Load Balances Requests |

---

# Service vs Ingress

| Service | Ingress |
|-----------|---------|
| Internal or External Access | HTTP/HTTPS Entry Point |
| Connects to Pods | Routes External Traffic |
| Layer 4 (TCP/UDP) | Layer 7 (HTTP/HTTPS) |

Ingress will be covered later.

---

# Real Production Example

An e-commerce application consists of:

```
Frontend Pods

↓

Frontend Service

↓

Backend Service

↓

Backend Pods

↓

Database Service

↓

Database Pods
```

Every application communicates through Services,

never through Pod IPs.

---

# Common Beginner Mistakes

### Mistake 1

Accessing Pods directly using Pod IPs.

Always use Services.

---

### Mistake 2

Using NodePort for production internet-facing applications when a cloud LoadBalancer or Ingress is more appropriate.

---

### Mistake 3

Labels on Pods not matching the Service selector.

The Service will have no endpoints.

---

### Mistake 4

Confusing `port` and `targetPort`.

- `port` = Service port
- `targetPort` = Container port

---

### Mistake 5

Assuming deleting a Service deletes the Pods.

Services and Pods are separate resources.

---

# Interview Questions

### Q1. What is a Kubernetes Service?

A Service provides stable network access to one or more Pods.

---

### Q2. Why are Services needed?

Because Pod IP addresses are temporary and can change when Pods are recreated.

---

### Q3. Name the four Kubernetes Service types.

- ClusterIP
- NodePort
- LoadBalancer
- ExternalName

---

### Q4. Which is the default Service type?

```
ClusterIP
```

---

### Q5. Which Service type is commonly used on cloud platforms to expose applications externally?

```
LoadBalancer
```

---

### Q6. How does a Service identify the Pods it should send traffic to?

Using labels and selectors.

---

# Production Best Practices

✔ Use ClusterIP for internal communication.

✔ Use Ingress with LoadBalancer for HTTP/HTTPS applications.

✔ Avoid direct Pod IP communication.

✔ Use meaningful labels and selectors.

✔ Configure readiness probes so Services send traffic only to healthy Pods.

✔ Monitor Service endpoints.

✔ Use DNS instead of hardcoded IP addresses.

✔ Keep Service definitions in Git.

---

# Key Takeaways

- Services provide stable networking for Kubernetes applications.
- Pods are temporary, but Services provide permanent access.
- Services use labels and selectors to discover Pods.
- ClusterIP, NodePort, LoadBalancer and ExternalName each serve different networking needs.
- Services are a fundamental building block of Kubernetes networking.

---

# Next Section

## 9.10 Namespaces

In the next section, we will learn:

- What are Namespaces?
- Why Namespaces are Needed
- Default Namespaces
- Creating Namespaces
- Managing Resources in Namespaces
- Resource Isolation
- Best Practices
- Interview Questions
---

# 9.10 Namespaces

As Kubernetes clusters grow,

multiple teams begin using the same cluster.

For example,

one company may have:

- Development Team
- Testing Team
- QA Team
- Production Team
- DevOps Team

If everyone deploys applications into the same cluster without organization,

resource management quickly becomes difficult.

To solve this,

Kubernetes provides **Namespaces**.

---

# What is a Namespace?

A Namespace is a logical partition inside a Kubernetes cluster.

It allows multiple users, teams or applications to share the same cluster while keeping their resources logically separated.

Think of a Namespace as a folder inside a computer.

```
Computer

↓

Folders

↓

Files
```

Similarly,

```
Cluster

↓

Namespaces

↓

Resources
```

---

# Why Namespaces?

Without Namespaces

```
Cluster

↓

1000 Resources

↓

Everything Mixed Together
```

Finding resources becomes difficult.

---

With Namespaces

```
Cluster

│

├── Development

├── Testing

├── QA

└── Production
```

Resources remain organized.

---

# Namespace Architecture

```
Kubernetes Cluster

│

├── Namespace A

│      ├── Pods

│      ├── Services

│      └── Deployments

│

├── Namespace B

│      ├── Pods

│      ├── Services

│      └── Deployments

│

└── Namespace C
```

Each Namespace has its own resources.

---

# Default Namespaces

Every Kubernetes cluster contains several built-in Namespaces.

```
default

kube-system

kube-public

kube-node-lease
```

---

# default Namespace

If you do not specify a Namespace,

resources are created in:

```
default
```

Example

```bash
kubectl get pods
```

This command shows Pods in the default Namespace.

---

# kube-system Namespace

Contains Kubernetes system components.

Examples

- API Server
- CoreDNS
- Scheduler
- Controller Manager
- kube-proxy

View resources.

```bash
kubectl get pods -n kube-system
```

---

# kube-public Namespace

Stores publicly readable cluster information.

It is rarely modified by application developers.

---

# kube-node-lease Namespace

Stores Lease objects used by Nodes.

These help Kubernetes determine whether Nodes are still healthy.

---

# List Namespaces

```bash
kubectl get namespaces
```

or

```bash
kubectl get ns
```

Example

```
default

kube-system

kube-public

kube-node-lease
```

---

# Create Namespace

```bash
kubectl create namespace development
```

Verify

```bash
kubectl get ns
```

---

# Delete Namespace

```bash
kubectl delete namespace development
```

Deleting a Namespace deletes all resources within that Namespace.

Use this command carefully.

---

# Deploy to a Namespace

Example

```bash
kubectl apply -f deployment.yaml -n development
```

The Deployment is created inside the `development` Namespace.

---

# View Pods in a Namespace

```bash
kubectl get pods -n development
```

---

# View Services

```bash
kubectl get svc -n development
```

---

# View Deployments

```bash
kubectl get deployments -n development
```

---

# YAML Namespace

Specify the Namespace in the manifest.

```yaml
metadata:

  name: nginx

  namespace: development
```

The resource is created in the specified Namespace.

---

# Resource Isolation

Suppose:

Development Namespace

```
Frontend

Backend
```

Production Namespace

```
Frontend

Backend
```

Both can have resources with the same names because they are isolated by Namespace.

Example

```
development/nginx

production/nginx
```

These are different resources.

---

# Service Discovery Across Namespaces

Within the same Namespace,

applications can simply use:

```
http://backend
```

Across Namespaces,

use the fully qualified service name.

Example

```
backend.production.svc.cluster.local
```

---

# Set Default Namespace

Instead of typing `-n` every time,

change the current context.

```bash
kubectl config set-context --current --namespace=development
```

Verify

```bash
kubectl config view --minify
```

---

# Switch Namespace

Update the context.

```bash
kubectl config set-context --current --namespace=production
```

---

# Resource Quotas

Namespaces can limit resource usage.

Example

```
Development

↓

CPU

Memory

Pods

Storage
```

Each Namespace can have different limits.

---

# LimitRanges

A Namespace can define default resource requests and limits.

Example

```
Namespace

↓

LimitRange

↓

Default CPU

↓

Default Memory
```

This helps prevent applications from consuming excessive resources.

---

# Network Policies

Namespaces can also be used with Network Policies.

Example

```
Development

↓

Cannot Access

↓

Production
```

This improves security by controlling communication.

---

# RBAC with Namespaces

Permissions can be granted per Namespace.

Example

```
Developer

↓

Development Namespace

↓

Allowed

----------------

Production Namespace

↓

Denied
```

Role-Based Access Control (RBAC) is commonly combined with Namespaces.

---

# Namespace Workflow

```
Cluster

↓

Namespace

↓

Deployment

↓

ReplicaSet

↓

Pods
```

Every application belongs to a Namespace.

---

# Real Production Example

A company hosts multiple applications.

```
Cluster

│

├── dev

├── test

├── staging

├── production

└── monitoring
```

Each team works independently within its Namespace.

---

# Common Beginner Mistakes

### Mistake 1

Deploying everything into the `default` Namespace.

Create separate Namespaces for environments and teams.

---

### Mistake 2

Forgetting the `-n` option.

Commands may operate on the wrong Namespace.

---

### Mistake 3

Deleting an entire Namespace accidentally.

This deletes all resources inside it.

---

### Mistake 4

Assuming Namespaces provide complete security isolation.

They provide logical isolation and should be combined with RBAC, Network Policies and other security controls.

---

### Mistake 5

Using inconsistent Namespace names.

Use clear naming conventions such as:

- development
- testing
- staging
- production

---

# Interview Questions

### Q1. What is a Kubernetes Namespace?

A Namespace is a logical partition within a Kubernetes cluster that organizes and isolates resources.

---

### Q2. What is the default Namespace called?

```
default
```

---

### Q3. Which Namespace contains Kubernetes system components?

```
kube-system
```

---

### Q4. Which command creates a Namespace?

```bash
kubectl create namespace development
```

---

### Q5. How do you list all Namespaces?

```bash
kubectl get ns
```

---

### Q6. Why are Namespaces important?

They organize resources, enable multi-team usage, simplify management and support resource isolation.

---

# Production Best Practices

✔ Create separate Namespaces for each environment.

✔ Avoid deploying production workloads into the `default` Namespace.

✔ Combine Namespaces with RBAC.

✔ Use ResourceQuotas and LimitRanges.

✔ Apply Network Policies between sensitive Namespaces.

✔ Use meaningful Namespace names.

✔ Monitor Namespace resource usage.

✔ Store Namespace manifests in Git.

---

# Key Takeaways

- Namespaces logically separate resources inside a Kubernetes cluster.
- Every cluster contains several built-in Namespaces.
- Namespaces simplify organization, access control and resource management.
- ResourceQuotas, LimitRanges and RBAC are commonly applied at the Namespace level.
- Proper Namespace design is a key part of running Kubernetes in production.

---

# Next Section

## 9.11 Labels & Selectors

In the next section, we will learn:

- What are Labels?
- What are Selectors?
- MatchLabels
- MatchExpressions
- Label Best Practices
- Service Discovery
- Deployment Selection
- Production Examples
- Interview Questions
---

# 9.11 Labels & Selectors

As Kubernetes clusters grow,

they may contain:

- Hundreds of Pods
- Hundreds of Services
- Many Deployments
- Multiple Teams

How does Kubernetes know:

- Which Pods belong to a Deployment?
- Which Pods should receive Service traffic?
- Which Pods should be monitored?

The answer is:

**Labels and Selectors.**

They are among the most important concepts in Kubernetes.

---

# What are Labels?

Labels are key-value pairs attached to Kubernetes resources.

Example

```yaml
labels:

  app: nginx

  environment: production

  team: devops
```

Labels help identify and organize resources.

---

# Simple Analogy

Imagine a library.

Every book has labels.

```
Science

History

Programming

Mathematics
```

Instead of searching every book,

you search using labels.

Kubernetes works the same way.

---

# Why Labels?

Without labels,

Kubernetes cannot easily identify resources.

```
1000 Pods

↓

No Labels

↓

Hard to Manage
```

With labels,

```
1000 Pods

↓

Labels

↓

Easy Identification
```

---

# Label Architecture

```
Pod

│

├── app=nginx

├── env=production

└── team=devops
```

Every resource can have multiple labels.

---

# Common Labels

Examples

```yaml
labels:

  app: nginx

  version: v1

  environment: production

  tier: frontend

  team: devops
```

---

# Adding Labels

Example

```yaml
metadata:

  labels:

    app: nginx

    env: production
```

---

# View Labels

```bash
kubectl get pods --show-labels
```

Example

```
NAME      LABELS

nginx     app=nginx,env=production
```

---

# Add Label to Existing Resource

```bash
kubectl label pod nginx version=v1
```

Verify.

```bash
kubectl get pods --show-labels
```

---

# Update Label

```bash
kubectl label pod nginx version=v2 --overwrite
```

---

# Remove Label

```bash
kubectl label pod nginx version-
```

---

# What are Selectors?

Selectors are used to identify resources based on labels.

Labels identify resources.

Selectors find resources.

```
Labels

↓

Selectors

↓

Matching Resources
```

---

# Why Selectors?

Suppose you have:

```
Pod-1

app=nginx

----------------

Pod-2

app=nginx

----------------

Pod-3

app=apache
```

A Service wants only Nginx Pods.

Selector

```
app=nginx
```

Result

```
Pod-1

Pod-2
```

---

# Selector Architecture

```
Service

↓

Selector

↓

Matching Pods

↓

Traffic
```

---

# MatchLabels

The simplest selector.

Example

```yaml
selector:

  matchLabels:

    app: nginx
```

Only Pods with:

```
app=nginx
```

are selected.

---

# MatchExpressions

More advanced selection.

Example

```yaml
matchExpressions:

- key: environment

  operator: In

  values:

  - production

  - staging
```

Multiple matching rules can be defined.

---

# Selector Operators

Common operators

```
In

NotIn

Exists

DoesNotExist
```

These provide flexible selection logic.

---

# Service Example

Pods

```yaml
labels:

  app: nginx
```

Service

```yaml
selector:

  app: nginx
```

Traffic automatically reaches all matching Pods.

---

# Deployment Example

Deployment

```yaml
selector:

  matchLabels:

    app: nginx
```

Pod Template

```yaml
labels:

  app: nginx
```

The labels and selector must match.

---

# ReplicaSet Example

```
ReplicaSet

↓

Selector

↓

Matching Pods

↓

Maintain Replicas
```

ReplicaSets also rely on labels and selectors.

---

# Label Query

List Pods with a label.

```bash
kubectl get pods -l app=nginx
```

---

# Multiple Labels

Example

```bash
kubectl get pods -l app=nginx,env=production
```

Only Pods matching **both** labels are returned.

---

# Label Workflow

```
Pod

↓

Labels

↓

Selector

↓

Service

↓

Traffic
```

---

# Real Production Example

A company runs:

```
Frontend Pods

↓

app=frontend

----------------

Backend Pods

↓

app=backend

----------------

Database Pods

↓

app=mysql
```

Frontend Service

```
selector:

app=frontend
```

Backend Service

```
selector:

app=backend
```

Database Service

```
selector:

app=mysql
```

Each Service routes traffic only to the correct Pods.

---

# Recommended Labels

A common production convention:

```yaml
labels:

  app: payment

  environment: production

  version: v2

  team: fintech

  tier: backend
```

These labels improve searching, monitoring and automation.

---

# Labels vs Annotations

| Labels | Annotations |
|---------|-------------|
| Used for Selection | Not Used for Selection |
| Small Metadata | Additional Information |
| Indexed | Not Intended for Queries |
| Used by Controllers | Used by Humans and Tools |

---

# Common Beginner Mistakes

### Mistake 1

Changing Pod labels without updating the Deployment or ReplicaSet selector.

Controllers may stop managing the Pods.

---

### Mistake 2

Using inconsistent label names.

Example:

```
app=nginx

application=nginx

service=nginx
```

Choose one naming convention and follow it consistently.

---

### Mistake 3

Using labels to store large amounts of information.

Use annotations for descriptive metadata.

---

### Mistake 4

Forgetting that Services rely on matching labels.

A mismatch results in zero endpoints.

---

### Mistake 5

Using meaningless labels.

Prefer descriptive values such as:

- app
- environment
- version
- team
- tier

---

# Interview Questions

### Q1. What is a Kubernetes Label?

A Label is a key-value pair attached to a Kubernetes resource for identification and organization.

---

### Q2. What is a Selector?

A Selector identifies Kubernetes resources based on their labels.

---

### Q3. Why are Labels important?

They organize resources and allow controllers such as Services, ReplicaSets and Deployments to identify the correct objects.

---

### Q4. Which selector type performs exact label matching?

```
matchLabels
```

---

### Q5. Name four selector operators.

- In
- NotIn
- Exists
- DoesNotExist

---

### Q6. What is the difference between Labels and Annotations?

Labels are used for identifying and selecting resources, while annotations store additional metadata that is not used for selection.

---

# Production Best Practices

✔ Use consistent labeling conventions.

✔ Include labels such as app, environment, version and team.

✔ Keep labels short and meaningful.

✔ Use annotations for descriptive metadata.

✔ Verify Service selectors carefully.

✔ Document label standards for your organization.

✔ Avoid changing labels on managed Pods unnecessarily.

✔ Use labels to simplify monitoring and automation.

---

# Key Takeaways

- Labels are key-value pairs used to identify Kubernetes resources.
- Selectors locate resources based on matching labels.
- Services, Deployments and ReplicaSets depend on labels and selectors.
- Consistent labeling makes Kubernetes clusters easier to manage.
- Labels are one of the foundational concepts in Kubernetes and are heavily used in production.

---

# Next Section

## 9.12 ConfigMaps

In the next section, we will learn:

- What is a ConfigMap?
- Why ConfigMaps are Needed
- Creating ConfigMaps
- Using ConfigMaps
- Environment Variables
- Volume Mounts
- Updating Configurations
- Best Practices
- Interview Questions
---

# 9.12 ConfigMaps

Until now,

all of our Kubernetes applications have been simple.

Suppose an application connects to:

- Database
- Redis
- API Server
- Message Queue

The application needs configuration values such as:

- Database Host
- Database Port
- Environment Name
- API URL

One option is to hardcode these values inside the application.

However,

this creates many problems.

Kubernetes solves this using **ConfigMaps**.

---

# What is a ConfigMap?

A ConfigMap is a Kubernetes object used to store **non-sensitive configuration data**.

Instead of storing configuration inside the application,

the configuration is stored separately.

Applications read configuration from the ConfigMap.

---

# Simple Definition

```
Application

↓

ConfigMap

↓

Configuration
```

The application code remains unchanged,

only the configuration changes.

---

# Why ConfigMaps?

Without ConfigMaps

```
Application Code

↓

Database URL

↓

API URL

↓

Redis URL

↓

Rebuild Image
```

Every configuration change requires rebuilding the application image.

---

With ConfigMaps

```
Application

↓

ConfigMap

↓

Configuration Changed

↓

No Image Rebuild
```

Only the configuration changes.

---

# ConfigMap Architecture

```
ConfigMap

↓

Pod

↓

Container

↓

Application
```

The Pod reads configuration from the ConfigMap.

---

# What Can ConfigMaps Store?

ConfigMaps commonly store:

- Application Configuration
- Environment Variables
- Configuration Files
- Command-Line Arguments
- Feature Flags
- Service Endpoints

ConfigMaps should **not** store passwords or API keys.

---

# ConfigMap Example

```yaml
apiVersion: v1

kind: ConfigMap

metadata:

  name: app-config

data:

  APP_NAME: PaymentService

  ENVIRONMENT: Production

  DATABASE_HOST: mysql-service
```

---

# Create ConfigMap

Apply the manifest.

```bash
kubectl apply -f configmap.yaml
```

---

# View ConfigMaps

```bash
kubectl get configmaps
```

or

```bash
kubectl get cm
```

Example

```
NAME

app-config
```

---

# Describe ConfigMap

```bash
kubectl describe configmap app-config
```

Displays:

- Data
- Labels
- Events
- Metadata

---

# View YAML

```bash
kubectl get configmap app-config -o yaml
```

---

# Create ConfigMap from Command Line

```bash
kubectl create configmap app-config \
--from-literal=APP_NAME=PaymentService \
--from-literal=ENVIRONMENT=Production
```

---

# Create ConfigMap from File

Suppose:

```
config.properties
```

Create the ConfigMap.

```bash
kubectl create configmap app-config \
--from-file=config.properties
```

The file contents become part of the ConfigMap.

---

# Using ConfigMap as Environment Variables

Example

```yaml
envFrom:

- configMapRef:

    name: app-config
```

Every key becomes an environment variable inside the container.

---

# Using Individual Keys

Example

```yaml
env:

- name: DATABASE_HOST

  valueFrom:

    configMapKeyRef:

      name: app-config

      key: DATABASE_HOST
```

Only one value is imported.

---

# ConfigMap as Volume

ConfigMaps can also be mounted as files.

```
ConfigMap

↓

Volume

↓

Container

↓

Configuration File
```

---

# Volume Example

```yaml
volumes:

- name: config-volume

  configMap:

    name: app-config
```

Mount the volume.

```yaml
volumeMounts:

- mountPath: /etc/config

  name: config-volume
```

Every ConfigMap key becomes a file.

---

# ConfigMap Workflow

```
ConfigMap

↓

Pod

↓

Container

↓

Application Reads Configuration
```

---

# Updating ConfigMap

Update the YAML.

```yaml
data:

  ENVIRONMENT: Staging
```

Apply changes.

```bash
kubectl apply -f configmap.yaml
```

The ConfigMap is updated.

Depending on how the application consumes configuration,

a Pod restart or application reload may be required before changes take effect.

---

# Verify Environment Variables

```bash
kubectl exec -it POD_NAME -- env
```

Example

```
APP_NAME=PaymentService

ENVIRONMENT=Production
```

---

# Verify Mounted Files

```bash
kubectl exec -it POD_NAME -- ls /etc/config
```

Display a file.

```bash
kubectl exec -it POD_NAME -- cat /etc/config/DATABASE_HOST
```

---

# ConfigMap Lifecycle

```
Create ConfigMap

↓

Deploy Pod

↓

Read Configuration

↓

Application Running
```

---

# ConfigMap vs Hardcoding

| Hardcoding | ConfigMap |
|------------|-----------|
| Inside Code | Separate Object |
| Requires Image Rebuild | No Image Rebuild |
| Difficult to Maintain | Easy to Update |
| Less Flexible | Highly Flexible |

---

# ConfigMap vs Secret

| ConfigMap | Secret |
|------------|---------|
| Non-Sensitive Data | Sensitive Data |
| Plain Configuration | Passwords, Tokens, Keys |
| Environment Variables | Environment Variables |
| Files | Files |

Secrets will be covered in the next section.

---

# Real Production Example

A banking application uses:

```
Application

↓

ConfigMap

↓

DATABASE_HOST

↓

REDIS_HOST

↓

LOG_LEVEL

↓

Application Starts
```

The application reads all configuration during startup.

---

# Enterprise Workflow

```
Developer

↓

Git Repository

↓

ConfigMap YAML

↓

CI/CD

↓

Kubernetes

↓

Application
```

Configuration is managed independently from the application image.

---

# Common Beginner Mistakes

### Mistake 1

Storing passwords inside ConfigMaps.

Sensitive information belongs in Kubernetes Secrets.

---

### Mistake 2

Hardcoding configuration inside container images.

Keep configuration separate from application code.

---

### Mistake 3

Assuming every ConfigMap update is immediately visible to the application.

Some applications require a restart or reload.

---

### Mistake 4

Using one large ConfigMap for unrelated applications.

Create ConfigMaps per application or component.

---

### Mistake 5

Not version-controlling ConfigMap manifests.

Store ConfigMaps in Git with the rest of your Kubernetes manifests.

---

# Interview Questions

### Q1. What is a ConfigMap?

A ConfigMap stores non-sensitive configuration data for Kubernetes applications.

---

### Q2. Why are ConfigMaps used?

They separate configuration from application code, making applications easier to manage and deploy.

---

### Q3. Can ConfigMaps store passwords?

No.

Passwords and other sensitive information should be stored in Kubernetes Secrets.

---

### Q4. How can a Pod consume a ConfigMap?

- Environment Variables
- Mounted Volumes
- Individual Keys

---

### Q5. Which command displays ConfigMaps?

```bash
kubectl get configmaps
```

---

### Q6. What happens after a ConfigMap is updated?

The ConfigMap is updated, but applications may need to reload the configuration or restart, depending on how they consume it.

---

# Production Best Practices

✔ Store only non-sensitive configuration in ConfigMaps.

✔ Keep ConfigMaps application-specific.

✔ Use Git for version control.

✔ Mount configuration files when appropriate.

✔ Use environment variables for simple settings.

✔ Avoid hardcoded configuration in images.

✔ Test configuration changes before production.

✔ Document configuration keys and values.

---

# Key Takeaways

- ConfigMaps store non-sensitive application configuration.
- They separate configuration from application code.
- ConfigMaps can be consumed as environment variables or mounted files.
- Updating configuration is easier than rebuilding container images.
- ConfigMaps are a fundamental Kubernetes feature used in almost every production application.

---

# Next Section

## 9.13 Secrets

In the next section, we will learn:

- What are Kubernetes Secrets?
- Why Secrets are Needed
- Secret Types
- Creating Secrets
- Using Secrets
- Environment Variables
- Secret Volumes
- Security Best Practices
- Interview Questions
---

# 9.13 Secrets

In the previous section,

you learned how ConfigMaps store application configuration.

However,

some information should **never** be stored in plain text.

Examples include:

- Database Passwords
- API Keys
- JWT Secrets
- SSL Certificates
- Private Keys
- Cloud Credentials

Storing such information inside ConfigMaps or application code creates security risks.

To securely manage sensitive data,

Kubernetes provides **Secrets**.

---

# What is a Secret?

A Secret is a Kubernetes object used to store sensitive information.

Examples:

- Passwords
- API Tokens
- SSH Keys
- Certificates
- Private Keys

Applications can securely access this information without embedding it inside the application image.

---

# Simple Definition

```
Application

↓

Secret

↓

Sensitive Data
```

The application retrieves confidential information from the Secret.

---

# Why Secrets?

Without Secrets

```
Application Code

↓

Database Password

↓

Git Repository

↓

Security Risk
```

Anyone with access to the source code can view the credentials.

---

With Secrets

```
Application

↓

Secret

↓

Password

↓

Secure Access
```

Sensitive data is separated from application code.

---

# Secret Architecture

```
Secret

↓

Pod

↓

Container

↓

Application
```

The Pod reads the Secret at runtime.

---

# What Can Secrets Store?

Secrets commonly contain:

- Database Passwords
- API Tokens
- SSH Keys
- TLS Certificates
- OAuth Credentials
- Cloud Access Keys

Secrets are intended for **confidential** information.

---

# Secret Types

Kubernetes supports multiple Secret types.

```
Secrets

│

├── Opaque

├── kubernetes.io/tls

├── kubernetes.io/dockerconfigjson

├── kubernetes.io/basic-auth

├── kubernetes.io/ssh-auth

└── kubernetes.io/service-account-token
```

The default type is **Opaque**.

---

# Opaque Secret

Most application Secrets use:

```
Opaque
```

Example

```yaml
type: Opaque
```

---

# Secret YAML

Example

```yaml
apiVersion: v1

kind: Secret

metadata:

  name: db-secret

type: Opaque

stringData:

  DB_USERNAME: admin

  DB_PASSWORD: MyPassword123
```

Using `stringData` allows you to provide readable values, which Kubernetes converts appropriately when storing the Secret.

---

# Create Secret

Apply the manifest.

```bash
kubectl apply -f secret.yaml
```

---

# View Secrets

```bash
kubectl get secrets
```

Example

```
NAME

db-secret
```

---

# Describe Secret

```bash
kubectl describe secret db-secret
```

This displays metadata,

but not the Secret values.

---

# View Secret YAML

```bash
kubectl get secret db-secret -o yaml
```

The stored values appear encoded.

---

# Create Secret from Command Line

```bash
kubectl create secret generic db-secret \
--from-literal=DB_USERNAME=admin \
--from-literal=DB_PASSWORD=MyPassword123
```

---

# Create Secret from File

Suppose:

```
password.txt
```

Create the Secret.

```bash
kubectl create secret generic db-secret \
--from-file=password.txt
```

---

# Using Secrets as Environment Variables

Example

```yaml
envFrom:

- secretRef:

    name: db-secret
```

Every Secret key becomes an environment variable.

---

# Using Individual Secret Keys

```yaml
env:

- name: DB_PASSWORD

  valueFrom:

    secretKeyRef:

      name: db-secret

      key: DB_PASSWORD
```

Only one Secret value is imported.

---

# Mount Secret as Volume

Secrets can also be mounted as files.

```
Secret

↓

Volume

↓

Container

↓

Application
```

---

# Volume Example

```yaml
volumes:

- name: secret-volume

  secret:

    secretName: db-secret
```

Mount it.

```yaml
volumeMounts:

- name: secret-volume

  mountPath: /etc/secret
```

Each Secret key becomes a file inside the mounted directory.

---

# Secret Workflow

```
Secret

↓

Pod

↓

Container

↓

Application Reads Secret
```

---

# Verify Secret Environment Variables

```bash
kubectl exec -it POD_NAME -- env
```

Verify mounted files.

```bash
kubectl exec -it POD_NAME -- ls /etc/secret
```

---

# Updating Secrets

Update the Secret manifest.

```yaml
stringData:

  DB_PASSWORD: NewPassword456
```

Apply the changes.

```bash
kubectl apply -f secret.yaml
```

Depending on how the application consumes the Secret,

a restart or reload may be required before the updated value is used.

---

# Secret Lifecycle

```
Create Secret

↓

Deploy Pod

↓

Read Secret

↓

Application Running
```

---

# ConfigMap vs Secret

| ConfigMap | Secret |
|------------|---------|
| Non-Sensitive Data | Sensitive Data |
| Application Configuration | Passwords & Tokens |
| Feature Flags | Certificates |
| API URLs | Private Keys |

---

# Secret vs Hardcoding

| Hardcoded Credentials | Kubernetes Secret |
|------------------------|-------------------|
| Stored in Code | Stored Separately |
| Difficult to Rotate | Easier to Update |
| High Security Risk | Better Security Practice |
| May Leak in Git | Managed by Kubernetes |

---

# TLS Secret

TLS Secrets store certificates.

Example

```bash
kubectl create secret tls tls-secret \
--cert=server.crt \
--key=server.key
```

Commonly used with Ingress.

---

# Docker Registry Secret

Private container registries require authentication.

Create a registry Secret.

```bash
kubectl create secret docker-registry registry-secret \
--docker-server=myregistry.example.com \
--docker-username=user \
--docker-password=password
```

Pods can reference this Secret to pull private images.

---

# Real Production Example

An online banking application stores:

```
Application

↓

Secret

↓

Database Password

↓

JWT Secret

↓

TLS Certificate

↓

Application Starts Securely
```

Sensitive information never resides inside the container image.

---

# Enterprise Workflow

```
Security Team

↓

Secret Management

↓

GitOps / CI-CD

↓

Kubernetes Secret

↓

Application
```

In many organizations,

Secrets originate from external secret management systems.

---

# Security Considerations

Although Kubernetes Secrets improve organization,

they are **not automatically encrypted everywhere** by default.

For production environments:

✔ Enable Encryption at Rest

✔ Restrict RBAC Access

✔ Rotate Secrets Regularly

✔ Audit Secret Access

✔ Use External Secret Managers when appropriate

Examples include:

- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- Google Secret Manager

---

# Common Beginner Mistakes

### Mistake 1

Storing passwords inside ConfigMaps.

Use Secrets instead.

---

### Mistake 2

Committing Secret manifests containing real credentials to public Git repositories.

Use secure secret management practices.

---

### Mistake 3

Granting unrestricted access to Secrets through RBAC.

Follow the principle of least privilege.

---

### Mistake 4

Using the same Secret for unrelated applications.

Create separate Secrets for each application or service.

---

### Mistake 5

Never rotating credentials.

Regular credential rotation reduces security risk.

---

# Interview Questions

### Q1. What is a Kubernetes Secret?

A Secret is a Kubernetes object used to store sensitive information such as passwords, tokens and certificates.

---

### Q2. Why should Secrets be used instead of ConfigMaps?

Secrets are intended for sensitive information, while ConfigMaps are for non-sensitive configuration.

---

### Q3. How can a Pod consume a Secret?

- Environment Variables
- Mounted Volumes
- Individual Secret Keys

---

### Q4. Which is the default Secret type?

```
Opaque
```

---

### Q5. Can Secrets store TLS certificates?

Yes.

Kubernetes provides a dedicated TLS Secret type.

---

### Q6. Are Kubernetes Secrets sufficient by themselves for maximum security?

Secrets improve handling of sensitive data, but production environments should also use encryption at rest, RBAC, auditing and, where appropriate, external secret management systems.

---

# Production Best Practices

✔ Store only sensitive information in Secrets.

✔ Enable Encryption at Rest.

✔ Restrict Secret access using RBAC.

✔ Rotate credentials regularly.

✔ Avoid committing real Secrets to Git.

✔ Use external secret managers for highly sensitive environments.

✔ Audit Secret access.

✔ Keep Secrets application-specific.

---

# Key Takeaways

- Secrets store sensitive application data securely.
- They separate credentials from application code.
- Secrets can be consumed through environment variables or mounted volumes.
- Production clusters should combine Secrets with RBAC, encryption and secret rotation.
- Kubernetes Secrets are a core security feature used by nearly every production application.

---

# Next Section

## 9.14 Volumes & Persistent Storage

In the next section, we will learn:

- Why Pods Need Persistent Storage
- Volumes
- emptyDir
- hostPath
- Persistent Volumes (PV)
- Persistent Volume Claims (PVC)
- Storage Classes
- Dynamic Provisioning
- Best Practices
- Interview Questions
---

# 9.14 Volumes & Persistent Storage

Until now,

our applications have been running successfully inside Pods.

However,

there is one major problem.

Suppose your application writes important data.

For example:

- Database Records
- Uploaded Images
- Application Logs
- User Files
- Configuration Files

Now imagine the Pod crashes.

```
Pod

↓

Deleted

↓

New Pod

↓

Old Data Lost
```

This happens because containers use **ephemeral storage** by default.

To solve this,

Kubernetes provides **Volumes** and **Persistent Storage**.

---

# What is a Volume?

A Volume is a storage mechanism that allows data to be shared with containers inside a Pod.

Unlike the container filesystem,

a Volume exists independently of an individual container within the Pod.

```
Pod

↓

Volume

↓

Container
```

Containers read and write data through the Volume.

---

# Why Volumes?

Without Volumes

```
Container

↓

Store File

↓

Container Stops

↓

File Lost
```

With Volumes

```
Container

↓

Volume

↓

Container Restart

↓

File Still Available
```

(As long as the Pod and Volume still exist.)

---

# Storage Types

Kubernetes supports several storage options.

```
Storage

│

├── emptyDir

├── hostPath

├── Persistent Volume

├── Persistent Volume Claim

└── StorageClass
```

---

# emptyDir Volume

An `emptyDir` Volume is created when a Pod starts.

```
Pod Starts

↓

emptyDir Created

↓

Containers Share Data
```

If the Pod is deleted,

the `emptyDir` data is deleted.

---

# emptyDir Example

```yaml
volumes:

- name: cache-volume

  emptyDir: {}
```

Mount it.

```yaml
volumeMounts:

- mountPath: /cache

  name: cache-volume
```

---

# Use Cases for emptyDir

Typical examples:

- Temporary Files
- Cache
- Intermediate Processing
- Shared Files Between Containers

Do **not** use `emptyDir` for permanent application data.

---

# hostPath Volume

`hostPath` mounts a directory from the Worker Node into the Pod.

```
Worker Node

↓

/data

↓

Pod
```

---

# hostPath Example

```yaml
volumes:

- name: host-storage

  hostPath:

    path: /data
```

---

# hostPath Limitations

Since the data resides on one Worker Node,

it is generally not suitable for highly available production workloads.

It is mainly used for:

- Testing
- Development
- Special System Components

---

# Why Persistent Storage?

Imagine a MySQL database.

```
MySQL Pod

↓

Database Files
```

If the Pod is recreated,

the database should remain available.

Persistent storage keeps data beyond the life of individual Pods.

---

# Persistent Volume (PV)

A Persistent Volume (PV) is storage provided to the Kubernetes cluster.

The storage may come from:

- AWS EBS
- Azure Disk
- Google Persistent Disk
- NFS
- SAN
- NAS

```
Storage

↓

Persistent Volume

↓

Cluster
```

---

# Persistent Volume Characteristics

A PV exists independently of Pods.

```
PV

↓

Available

↓

Claimed

↓

Released
```

Multiple Pods can use storage according to the supported access modes.

---

# Persistent Volume Example

```yaml
apiVersion: v1

kind: PersistentVolume

metadata:

  name: app-pv

spec:

  capacity:

    storage: 10Gi

  accessModes:

  - ReadWriteOnce
```

---

# Persistent Volume Claim (PVC)

Applications usually do **not** use PVs directly.

Instead,

they request storage using a PVC.

```
Pod

↓

PVC

↓

PV

↓

Storage
```

---

# PVC Example

```yaml
apiVersion: v1

kind: PersistentVolumeClaim

metadata:

  name: app-pvc

spec:

  accessModes:

  - ReadWriteOnce

  resources:

    requests:

      storage: 10Gi
```

---

# How PVC Works

Workflow

```
Application

↓

PVC

↓

Matching PV

↓

Storage Attached

↓

Application Running
```

The Pod does not need to know where the storage is physically located.

---

# Using PVC in a Pod

```yaml
volumes:

- name: app-storage

  persistentVolumeClaim:

    claimName: app-pvc
```

Mount it.

```yaml
volumeMounts:

- mountPath: /data

  name: app-storage
```

---

# StorageClass

A StorageClass defines how storage should be created.

```
StorageClass

↓

Provision Storage

↓

Persistent Volume
```

StorageClasses enable automatic storage provisioning.

---

# Dynamic Provisioning

Without a StorageClass

```
Administrator

↓

Create PV

↓

Developer Uses PVC
```

With a StorageClass

```
Developer

↓

PVC

↓

StorageClass

↓

PV Created Automatically
```

This is called **Dynamic Provisioning**.

---

# StorageClass Example

```yaml
apiVersion: storage.k8s.io/v1

kind: StorageClass

metadata:

  name: fast-storage

provisioner: ebs.csi.aws.com
```

The exact provisioner depends on the storage platform.

---

# Access Modes

Common access modes:

```
ReadWriteOnce (RWO)

↓

One Node

----------------

ReadOnlyMany (ROX)

↓

Many Nodes Read Only

----------------

ReadWriteMany (RWX)

↓

Many Nodes Read & Write

----------------

ReadWriteOncePod (RWOP)

↓

One Pod
```

Choose the access mode supported by the underlying storage system.

---

# Volume Workflow

```
Application

↓

Pod

↓

PVC

↓

PV

↓

Storage Backend
```

---

# Storage Lifecycle

```
Create StorageClass

↓

PVC

↓

PV

↓

Pod

↓

Application

↓

Data Stored
```

---

# Reclaim Policy

A Persistent Volume defines what happens after a PVC is deleted.

Common policies:

```
Delete

↓

Underlying storage removed

----------------

Retain

↓

Storage preserved

----------------

Recycle (Deprecated)
```

`Retain` is often chosen when data must be protected.

---

# Real Production Example

An e-commerce application uses:

```
Application

↓

PVC

↓

AWS EBS Volume

↓

Customer Data
```

If the Pod restarts,

the data remains on the persistent storage.

---

# Enterprise Workflow

```
Developer

↓

Deployment

↓

PVC

↓

StorageClass

↓

Cloud Storage

↓

Persistent Data
```

Storage is provisioned automatically in many managed Kubernetes environments.

---

# Common Beginner Mistakes

### Mistake 1

Using `emptyDir` for databases.

Database storage should be persistent.

---

### Mistake 2

Deleting a PVC without understanding the associated reclaim policy.

Important data may become inaccessible or be deleted.

---

### Mistake 3

Using `hostPath` for production workloads.

It ties the workload to a specific node.

---

### Mistake 4

Assuming all storage supports `ReadWriteMany`.

Supported access modes depend on the storage backend.

---

### Mistake 5

Creating Pods before ensuring the PVC is successfully bound.

Always verify:

```bash
kubectl get pvc
```

---

# Interview Questions

### Q1. What is a Kubernetes Volume?

A Volume provides storage that containers in a Pod can access.

---

### Q2. What is the difference between a PV and a PVC?

A Persistent Volume (PV) is the storage resource, while a Persistent Volume Claim (PVC) is a request for that storage.

---

### Q3. Why is `emptyDir` not suitable for databases?

Because its data is removed when the Pod is deleted.

---

### Q4. What is a StorageClass?

A StorageClass defines how persistent storage is dynamically provisioned.

---

### Q5. What is Dynamic Provisioning?

Dynamic Provisioning automatically creates Persistent Volumes when a matching PVC is created.

---

### Q6. Which access mode allows multiple nodes to read and write the same volume?

```
ReadWriteMany (RWX)
```

(Only if the underlying storage backend supports it.)

---

# Production Best Practices

✔ Use PVCs instead of directly referencing PVs.

✔ Enable dynamic provisioning with StorageClasses.

✔ Choose appropriate access modes.

✔ Use cloud-native CSI drivers.

✔ Back up persistent data regularly.

✔ Avoid `hostPath` for production applications.

✔ Monitor storage usage.

✔ Test recovery procedures.

---

# Key Takeaways

- Volumes provide storage for Kubernetes Pods.
- `emptyDir` is temporary storage tied to a Pod's lifecycle.
- Persistent Volumes (PV) provide durable storage.
- Persistent Volume Claims (PVC) request storage for applications.
- StorageClasses enable automatic storage provisioning in production clusters.

---

# Next Section

## 9.15 Ingress

In the next section, we will learn:

- What is Ingress?
- Why Ingress is Needed
- Ingress Controller
- Path-Based Routing
- Host-Based Routing
- TLS Configuration
- Production Architecture
- Best Practices
- Interview Questions
---

# 9.15 Ingress

In the previous section,

you learned that Kubernetes Services expose applications.

However,

imagine a production cluster hosting multiple applications.

```
Frontend

Backend

Payment

Authentication

Reports

Admin
```

If every application uses a separate **LoadBalancer Service**,

the architecture becomes expensive and difficult to manage.

Instead,

Kubernetes provides **Ingress**.

Ingress acts like a smart traffic controller.

---

# What is Ingress?

Ingress is a Kubernetes API object that manages external HTTP and HTTPS access to applications inside a cluster.

Instead of exposing every Service individually,

Ingress routes requests to the correct Service.

---

# Simple Definition

```
Internet

↓

Ingress

↓

Services

↓

Pods
```

Ingress becomes the single entry point into the cluster.

---

# Why Ingress?

Without Ingress

```
Internet

↓

LoadBalancer 1

↓

Frontend

----------------

LoadBalancer 2

↓

Backend

----------------

LoadBalancer 3

↓

Payment
```

Multiple external load balancers increase cost and complexity.

---

With Ingress

```
Internet

↓

Ingress

↓

Frontend Service

↓

Backend Service

↓

Payment Service
```

One entry point serves multiple applications.

---

# Ingress Architecture

```
Internet

↓

Load Balancer

↓

Ingress Controller

↓

Ingress

↓

Services

↓

Pods
```

Notice that the **Ingress resource** itself does not process traffic.

The **Ingress Controller** does.

---

# Important Concept

Many beginners think:

```
Ingress

↓

Routes Traffic
```

Actually,

the process is:

```
Ingress Rules

↓

Ingress Controller

↓

Routes Traffic
```

The Ingress resource stores routing rules.

The Ingress Controller enforces them.

---

# What is an Ingress Controller?

An Ingress Controller is a Kubernetes application that watches Ingress resources and configures a reverse proxy or load balancer.

Popular Ingress Controllers include:

- NGINX Ingress Controller
- Traefik
- HAProxy
- Kong
- AWS Load Balancer Controller

Without an Ingress Controller,

Ingress resources do nothing.

---

# Ingress Workflow

```
User

↓

DNS

↓

Load Balancer

↓

Ingress Controller

↓

Ingress Rules

↓

Service

↓

Pod
```

---

# Basic Ingress YAML

```yaml
apiVersion: networking.k8s.io/v1

kind: Ingress

metadata:

  name: app-ingress

spec:

  rules:

  - host: example.com

    http:

      paths:

      - path: /

        pathType: Prefix

        backend:

          service:

            name: frontend-service

            port:

              number: 80
```

---

# Create Ingress

```bash
kubectl apply -f ingress.yaml
```

---

# View Ingress

```bash
kubectl get ingress
```

or

```bash
kubectl get ing
```

Example

```
NAME

app-ingress
```

---

# Describe Ingress

```bash
kubectl describe ingress app-ingress
```

Displays:

- Rules
- Hosts
- Paths
- Events
- Backend Services

---

# Path-Based Routing

Ingress can route requests based on URL paths.

Example

```
example.com/

↓

Frontend

----------------

example.com/api

↓

Backend

----------------

example.com/admin

↓

Admin Service
```

Single domain,

multiple applications.

---

# Path-Based Routing Example

```yaml
paths:

- path: /

  backend:

    service:

      name: frontend

- path: /api

  backend:

    service:

      name: backend
```

---

# Host-Based Routing

Ingress can also route using hostnames.

Example

```
shop.example.com

↓

Shopping Service

----------------

api.example.com

↓

API Service

----------------

admin.example.com

↓

Admin Service
```

---

# Host-Based YAML

```yaml
rules:

- host: api.example.com

  http:
```

Traffic is routed based on the requested hostname.

---

# TLS Support

Ingress supports HTTPS.

Example

```yaml
tls:

- hosts:

  - example.com

  secretName: tls-secret
```

The TLS certificate is stored as a Kubernetes Secret.

---

# HTTPS Workflow

```
Internet

↓

HTTPS Request

↓

Ingress Controller

↓

TLS Certificate

↓

Service

↓

Pod
```

---

# Multiple Services

One Ingress can expose many applications.

```
Internet

↓

Ingress

│

├── Frontend

├── Backend

├── Payment

├── Orders

└── Admin
```

---

# Ingress vs Service

| Ingress | Service |
|----------|----------|
| Layer 7 (HTTP/HTTPS) | Layer 4 (TCP/UDP) |
| URL Routing | Pod Access |
| SSL Termination | Stable Networking |
| Multiple Applications | Single Backend |

---

# Ingress vs LoadBalancer

| LoadBalancer | Ingress |
|---------------|----------|
| One Service | Multiple Services |
| Higher Cost | Lower Cost |
| Simple Exposure | Advanced Routing |
| No URL Routing | URL Routing |

---

# Ingress Lifecycle

```
Create Ingress

↓

Ingress Controller Reads Rules

↓

Configure Reverse Proxy

↓

Traffic Routed

↓

Application Available
```

---

# Ingress Class

Clusters can have multiple Ingress Controllers.

Specify which controller should process an Ingress.

Example

```yaml
spec:

  ingressClassName: nginx
```

---

# Default Backend

Ingress can define a default backend.

```
Unknown Request

↓

Default Backend

↓

404 Page

or

Default Application
```

---

# Real Production Example

An online shopping platform.

```
Internet

↓

NGINX Ingress

↓

shop.example.com

↓

Frontend Service

----------------

api.example.com

↓

Backend Service

----------------

payments.example.com

↓

Payment Service
```

One Ingress Controller manages all incoming traffic.

---

# Enterprise Workflow

```
Developer

↓

Git Repository

↓

Ingress YAML

↓

CI/CD

↓

Ingress Controller

↓

Production
```

---

# Benefits of Ingress

✔ Single Entry Point

✔ URL Routing

✔ Host-Based Routing

✔ HTTPS Support

✔ Lower Infrastructure Cost

✔ Centralized Traffic Management

✔ Better Security

✔ Easier Operations

---

# Common Beginner Mistakes

### Mistake 1

Creating an Ingress without installing an Ingress Controller.

The Ingress resource alone does not route traffic.

---

### Mistake 2

Using a separate LoadBalancer Service for every application.

Ingress is often a more efficient solution for HTTP/HTTPS workloads.

---

### Mistake 3

Forgetting DNS configuration.

The domain name must resolve to the external load balancer or Ingress endpoint.

---

### Mistake 4

Not configuring TLS for public applications.

Production web applications should use HTTPS.

---

### Mistake 5

Incorrect Service names or ports in Ingress rules.

Ingress cannot route traffic if the backend Service configuration is wrong.

---

# Interview Questions

### Q1. What is a Kubernetes Ingress?

An Ingress is a Kubernetes resource that defines HTTP/HTTPS routing rules for external access to Services.

---

### Q2. Does Ingress route traffic by itself?

No.

An Ingress Controller reads the Ingress rules and performs the routing.

---

### Q3. What are the two most common routing methods?

- Host-Based Routing
- Path-Based Routing

---

### Q4. Why is Ingress preferred over multiple LoadBalancer Services?

Ingress can expose multiple Services through a single entry point, reducing cost and simplifying management.

---

### Q5. Which Kubernetes object usually stores TLS certificates for Ingress?

```
Secret
```

---

### Q6. Name two popular Ingress Controllers.

- NGINX Ingress Controller
- Traefik

---

# Production Best Practices

✔ Install a production-ready Ingress Controller.

✔ Use HTTPS for all public applications.

✔ Store TLS certificates in Secrets.

✔ Configure DNS correctly.

✔ Use Host-Based Routing for multiple applications.

✔ Monitor Ingress Controller logs.

✔ Use IngressClass for multi-controller environments.

✔ Keep Ingress manifests under version control.

---

# Key Takeaways

- Ingress provides HTTP/HTTPS routing into Kubernetes clusters.
- An Ingress Controller is required for Ingress resources to function.
- Ingress supports host-based and path-based routing.
- TLS termination is commonly handled at the Ingress layer.
- Ingress simplifies external access and is widely used in production Kubernetes environments.

---

# Next Section

## 9.16 Helm

In the next section, we will learn:

- What is Helm?
- Why Helm is Needed
- Helm Architecture
- Charts
- Repositories
- Installing Helm
- Deploying Applications
- Upgrading Releases
- Rollbacks
- Best Practices
- Interview Questions
---

# 9.16 Helm

As Kubernetes applications become larger,

managing dozens or even hundreds of YAML files becomes difficult.

Imagine deploying an application like:

- Prometheus
- Grafana
- Jenkins
- Elasticsearch
- GitLab

Each application may contain:

- Deployments
- Services
- ConfigMaps
- Secrets
- Persistent Volumes
- Ingress
- RBAC Objects

Instead of manually applying every YAML file,

Kubernetes provides **Helm**.

Helm is the **package manager for Kubernetes**.

---

# What is Helm?

Helm is an open-source package manager that simplifies deploying and managing Kubernetes applications.

Think of Helm as:

```
apt

↓

Ubuntu

----------------

yum

↓

RHEL

----------------

Helm

↓

Kubernetes
```

Just as `apt` installs software packages,

Helm installs Kubernetes applications.

---

# Simple Definition

```
Helm

↓

Chart

↓

Kubernetes

↓

Application Running
```

---

# Why Helm?

Without Helm

```
Deployment.yaml

↓

Service.yaml

↓

ConfigMap.yaml

↓

Secret.yaml

↓

Ingress.yaml

↓

PVC.yaml

↓

Apply One by One
```

Managing large applications becomes time-consuming.

---

With Helm

```
Helm Chart

↓

helm install

↓

Everything Deployed
```

One command deploys the entire application.

---

# Helm Architecture

```
Developer

↓

Helm CLI

↓

Kubernetes API

↓

Cluster
```

Helm communicates with Kubernetes using the Kubernetes API.

---

# Helm Components

```
Helm

│

├── Helm CLI

├── Chart

├── Repository

└── Release
```

Each component has a specific role.

---

# What is a Chart?

A Chart is a package containing Kubernetes manifests and templates.

It defines everything required to deploy an application.

```
Chart

│

├── Deployments

├── Services

├── ConfigMaps

├── Secrets

├── Ingress

└── Templates
```

---

# Chart Structure

```
mychart/

│

├── Chart.yaml

├── values.yaml

├── templates/

├── charts/

└── README.md
```

---

# Chart.yaml

Contains metadata.

Example

```yaml
apiVersion: v2

name: myapp

version: 1.0.0
```

---

# values.yaml

Stores configurable values.

Example

```yaml
replicaCount: 3

image:

  repository: nginx

  tag: latest
```

Changing values here customizes the deployment.

---

# templates Directory

Contains Kubernetes manifest templates.

Example

```
templates/

↓

deployment.yaml

service.yaml

ingress.yaml
```

Helm renders these templates before deployment.

---

# What is a Release?

A Release is a running instance of a Helm Chart.

Example

```
Chart

↓

helm install

↓

Release
```

You can install the same Chart multiple times using different Release names.

---

# Helm Repository

A Helm Repository stores Charts.

Examples

- Bitnami
- Grafana
- Prometheus Community

Repositories simplify installing popular applications.

---

# Add Repository

Example

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

---

# Update Repository

```bash
helm repo update
```

Downloads the latest chart information.

---

# Search Charts

```bash
helm search repo nginx
```

Example

```
NAME

bitnami/nginx
```

---

# Install Chart

Example

```bash
helm install my-nginx bitnami/nginx
```

Helm creates a Release named:

```
my-nginx
```

---

# List Releases

```bash
helm list
```

Displays all installed Releases.

---

# View Release Status

```bash
helm status my-nginx
```

---

# Upgrade Release

Suppose a new chart version becomes available.

```bash
helm upgrade my-nginx bitnami/nginx
```

Helm updates the existing Release.

---

# Rollback Release

View revision history.

```bash
helm history my-nginx
```

Rollback.

```bash
helm rollback my-nginx 1
```

Release returns to Revision 1.

---

# Uninstall Release

```bash
helm uninstall my-nginx
```

The Release and its Kubernetes resources are removed.

---

# Install Using Custom Values

Override default values.

```bash
helm install my-nginx bitnami/nginx \
-f values.yaml
```

---

# Override Individual Values

Example

```bash
helm install my-nginx bitnami/nginx \
--set replicaCount=5
```

---

# Helm Workflow

```
Developer

↓

Helm Chart

↓

Values

↓

Templates

↓

Rendered YAML

↓

Kubernetes API

↓

Resources Created
```

---

# Helm Templating

Instead of hardcoding values,

Helm uses templates.

Example

```yaml
replicas: {{ .Values.replicaCount }}
```

Helm replaces the placeholder during installation.

---

# Helm Lifecycle

```
Chart

↓

Install

↓

Release

↓

Upgrade

↓

Rollback

↓

Uninstall
```

---

# Helm vs kubectl

| Helm | kubectl |
|-------|----------|
| Package Manager | Kubernetes CLI |
| Uses Charts | Uses YAML |
| Supports Releases | No Release Management |
| Built-in Rollback | Manual Resource Management |

---

# Helm vs Kustomize

| Helm | Kustomize |
|-------|------------|
| Templates | YAML Overlays |
| Package Manager | Configuration Customization |
| Chart Repositories | Native Kubernetes Tool |
| Release Management | No Release Tracking |

Both tools are widely used.

Some organizations use them together.

---

# Real Production Example

A company wants to deploy Prometheus.

Without Helm

```
50+ YAML Files
```

With Helm

```bash
helm install monitoring prometheus-community/prometheus
```

Entire monitoring stack is deployed automatically.

---

# Enterprise Workflow

```
Developer

↓

Git Repository

↓

Helm Chart

↓

CI/CD

↓

Helm Upgrade

↓

Production Cluster
```

---

# Helm Best Features

✔ Reusable Charts

✔ Easy Installation

✔ Parameterized Deployments

✔ Rollback Support

✔ Version Control

✔ Dependency Management

✔ Easy Upgrades

✔ Community Charts

---

# Common Beginner Mistakes

### Mistake 1

Editing Kubernetes resources manually after deploying with Helm.

Helm may overwrite manual changes during upgrades.

---

### Mistake 2

Changing template files directly inside downloaded Charts.

Prefer overriding values or maintaining your own chart.

---

### Mistake 3

Ignoring `values.yaml`.

Use values instead of modifying templates whenever possible.

---

### Mistake 4

Forgetting to update repositories.

Run:

```bash
helm repo update
```

regularly.

---

### Mistake 5

Deleting Kubernetes resources manually instead of uninstalling the Helm Release.

Use:

```bash
helm uninstall
```

---

# Interview Questions

### Q1. What is Helm?

Helm is the package manager for Kubernetes that simplifies deploying and managing applications.

---

### Q2. What is a Helm Chart?

A Chart is a package containing Kubernetes manifests, templates and metadata.

---

### Q3. What is a Helm Release?

A Release is a deployed instance of a Helm Chart.

---

### Q4. Which command installs a Helm Chart?

```bash
helm install RELEASE_NAME CHART_NAME
```

---

### Q5. Which command upgrades an existing Release?

```bash
helm upgrade
```

---

### Q6. Which command rolls back a Release?

```bash
helm rollback
```

---

# Production Best Practices

✔ Keep custom values in `values.yaml`.

✔ Store Helm Charts in Git.

✔ Use versioned Charts.

✔ Test upgrades in non-production environments.

✔ Use Helm rollback when deployments fail.

✔ Keep repositories updated.

✔ Avoid manual modifications to Helm-managed resources.

✔ Automate Helm deployments through CI/CD.

---

# Key Takeaways

- Helm is the package manager for Kubernetes.
- Helm Charts package Kubernetes applications.
- Releases represent deployed Chart instances.
- Helm simplifies installation, upgrades and rollbacks.
- Helm is one of the most widely used tools for deploying production Kubernetes applications.

---

# Next Section

## 9.17 Kubernetes Best Practices

In the next section, we will learn:

- Cluster Design
- Resource Requests & Limits
- Security Best Practices
- RBAC
- Monitoring
- Logging
- High Availability
- Upgrade Strategy
- Production Recommendations
- Interview Questions
---

# 9.17 Kubernetes Best Practices

Building a Kubernetes cluster is only the first step.

Running Kubernetes successfully in production requires following industry best practices.

A cluster may have:

- Hundreds of Nodes
- Thousands of Pods
- Multiple Development Teams
- Continuous Deployments
- Millions of Users

Without proper practices,

the cluster can become:

- Difficult to Manage
- Insecure
- Expensive
- Unstable

This chapter focuses on production-ready Kubernetes operations.

---

# What are Kubernetes Best Practices?

Best Practices are proven methods that improve:

- Reliability
- Security
- Performance
- Scalability
- Maintainability

Most production outages occur because basic best practices are ignored.

---

# Production Cluster Design

A production cluster should be designed for:

✔ High Availability

✔ Scalability

✔ Security

✔ Monitoring

✔ Disaster Recovery

✔ Automation

---

# Recommended Cluster Architecture

```
                Load Balancer

                      │

        ┌─────────────┴─────────────┐

        │                           │

 Control Plane 1              Control Plane 2

        │                           │

        └─────────────┬─────────────┘

                      │

              Worker Nodes

      ┌────────┬────────┬────────┐

     Node1    Node2    Node3   Node4

          │        │        │

         Pods     Pods     Pods
```

Multiple Control Plane nodes improve availability.

---

# Use Deployments

Avoid running standalone Pods.

Preferred hierarchy:

```
Deployment

↓

ReplicaSet

↓

Pods
```

Deployments provide:

- Rolling Updates
- Rollbacks
- Self-Healing
- Scaling

---

# Use Namespaces

Separate workloads.

Example

```
development

testing

staging

production

monitoring
```

Never place every application inside the `default` Namespace.

---

# Use Labels Consistently

Recommended labels:

```yaml
labels:

  app: payment

  environment: production

  version: v2

  team: devops

  tier: backend
```

Consistent labels simplify:

- Monitoring
- Automation
- Troubleshooting
- Service Selection

---

# Configure Resource Requests

Every production Pod should specify CPU and memory requests.

Example

```yaml
resources:

  requests:

    cpu: "250m"

    memory: "256Mi"
```

Requests help the Scheduler make better placement decisions.

---

# Configure Resource Limits

Example

```yaml
resources:

  limits:

    cpu: "500m"

    memory: "512Mi"
```

Limits prevent a single application from consuming excessive cluster resources.

---

# Use Health Probes

Configure:

- Liveness Probe
- Readiness Probe
- Startup Probe

These probes help Kubernetes detect unhealthy applications and control traffic flow.

---

# Keep Images Small

Prefer minimal base images.

Examples:

- Alpine Linux (when compatible)
- Distroless Images

Smaller images:

- Download Faster
- Start Faster
- Reduce Attack Surface

---

# Use Image Tags Carefully

Avoid:

```yaml
image: nginx:latest
```

Prefer:

```yaml
image: nginx:1.27.2
```

Versioned images improve reproducibility and rollback safety.

---

# Avoid Running as Root

Containers should run as non-root users whenever possible.

Example

```yaml
securityContext:

  runAsNonRoot: true
```

This reduces security risks.

---

# Use Secrets Properly

Store:

- Passwords
- Tokens
- Certificates
- Keys

inside Kubernetes Secrets.

Never store sensitive information in:

- ConfigMaps
- Source Code
- Docker Images

---

# Enable RBAC

Role-Based Access Control limits permissions.

Example

```
Developer

↓

Development Namespace

↓

Allowed

----------------

Production Namespace

↓

Read Only
```

Grant only the permissions users require.

---

# Use Network Policies

Restrict Pod-to-Pod communication.

Example

```
Frontend

↓

Allowed

↓

Backend

----------------

Unknown Pod

↓

Blocked
```

Network Policies improve cluster security.

---

# Enable Audit Logging

Audit logs record Kubernetes API activity.

Useful for:

- Security
- Compliance
- Troubleshooting
- Incident Investigation

---

# Use Persistent Storage

Applications storing data should use:

```
PVC

↓

Persistent Volume

↓

Storage
```

Avoid using `emptyDir` for databases.

---

# Back Up etcd

The cluster state is stored in:

```
etcd
```

Regular backups are essential for disaster recovery.

---

# Monitor Cluster Health

Use monitoring tools such as:

- Prometheus
- Grafana
- Alertmanager

Monitor:

- CPU
- Memory
- Disk
- Pod Health
- Node Health
- API Server

---

# Centralize Logging

Collect logs using tools like:

- Fluent Bit
- Fluentd
- Loki
- Elasticsearch

Centralized logging simplifies troubleshooting.

---

# Automate Deployments

Avoid manual production deployments.

Recommended workflow:

```
Git

↓

CI/CD

↓

Helm

↓

Kubernetes
```

Automation reduces human error.

---

# Use Version Control

Store all Kubernetes manifests in Git.

Examples:

- Deployments
- Services
- ConfigMaps
- Secrets (encrypted or externally managed)
- Ingress
- Helm Charts

Git becomes the source of truth.

---

# Regularly Upgrade Kubernetes

Stay on supported Kubernetes releases.

Upgrade:

- Control Plane
- Worker Nodes
- kubectl
- Helm
- CSI Drivers
- CNI Plugins

Always test upgrades in non-production environments first.

---

# Scan Container Images

Use image scanning tools to detect vulnerabilities before deployment.

Examples:

- Trivy
- Grype

Integrate scanning into the CI/CD pipeline.

---

# High Availability

Ensure critical components are redundant.

```
Load Balancer

↓

Multiple Control Plane Nodes

↓

Multiple Worker Nodes

↓

Multiple Replicas
```

Avoid single points of failure.

---

# Disaster Recovery

Prepare for failures.

Maintain:

- etcd Backups
- Infrastructure as Code
- Backup Procedures
- Recovery Documentation
- Restore Testing

Backups are valuable only if restoration procedures are tested.

---

# Production Deployment Workflow

```
Developer

↓

Git Push

↓

CI Pipeline

↓

Docker Build

↓

Image Scan

↓

Container Registry

↓

Helm Upgrade

↓

Kubernetes

↓

Monitoring

↓

Alerts
```

This represents a common production pipeline.

---

# Security Checklist

✔ Enable RBAC

✔ Use Network Policies

✔ Run Containers as Non-Root

✔ Rotate Secrets

✔ Use TLS

✔ Scan Images

✔ Audit API Access

✔ Keep Kubernetes Updated

---

# Performance Checklist

✔ Configure Requests & Limits

✔ Use Horizontal Scaling

✔ Optimize Images

✔ Monitor Resource Usage

✔ Remove Unused Resources

✔ Tune Storage

✔ Tune Networking

✔ Scale Based on Metrics

---

# Common Beginner Mistakes

### Mistake 1

Deploying applications without resource requests and limits.

---

### Mistake 2

Running everything inside the `default` Namespace.

---

### Mistake 3

Using `latest` image tags in production.

---

### Mistake 4

Skipping backups for etcd and persistent data.

---

### Mistake 5

Ignoring monitoring and alerting until a failure occurs.

---

### Mistake 6

Granting cluster-admin privileges to every user.

Follow the principle of least privilege.

---

### Mistake 7

Making manual production changes instead of using Git and CI/CD.

---

# Interview Questions

### Q1. Why should Deployments be preferred over standalone Pods?

Deployments provide self-healing, scaling, rolling updates and rollbacks.

---

### Q2. Why should image tags be versioned instead of using `latest`?

Versioned tags improve consistency, reproducibility and rollback capabilities.

---

### Q3. Why are resource requests and limits important?

They help Kubernetes schedule workloads efficiently and prevent resource contention.

---

### Q4. Why should etcd be backed up?

Because it stores the cluster state and configuration required to recover the cluster.

---

### Q5. Which tools are commonly used for Kubernetes monitoring?

- Prometheus
- Grafana
- Alertmanager

---

### Q6. Name five Kubernetes production best practices.

- Use Deployments
- Configure Resource Requests & Limits
- Enable RBAC
- Back up etcd
- Monitor the Cluster

---

# Kubernetes Production Checklist

✅ Use Deployments

✅ Configure Requests & Limits

✅ Use Namespaces

✅ Enable RBAC

✅ Use Network Policies

✅ Back Up etcd

✅ Monitor the Cluster

✅ Centralize Logs

✅ Use Helm

✅ Automate Deployments

✅ Scan Images

✅ Keep Kubernetes Updated

---

# Key Takeaways

- Production Kubernetes requires strong operational practices, not just correct YAML.
- Security, monitoring, backups and automation are essential.
- GitOps, CI/CD and Helm improve deployment consistency.
- Proper resource management improves stability and efficiency.
- Following Kubernetes best practices reduces outages and simplifies long-term maintenance.

---

# Next Section

## 9.18 Kubernetes Interview Questions & Scenario-Based Questions

In the next section, we will cover:

- Beginner Interview Questions
- Intermediate Interview Questions
- Advanced Interview Questions
- Real Production Scenarios
- Troubleshooting Questions
- Architecture-Based Questions
- Hands-on Interview Tasks
- Frequently Asked Kubernetes Commands
- Expert Tips for Kubernetes Interviews
---

# 9.18 Kubernetes Interview Questions & Scenario-Based Questions

This chapter contains some of the most frequently asked Kubernetes interview questions.

Questions are divided into:

- Beginner Level
- Intermediate Level
- Advanced Level
- Production Scenarios
- Troubleshooting Scenarios
- Architecture Questions
- Hands-on Tasks

These questions are commonly asked for:

- DevOps Engineer
- Kubernetes Administrator
- Cloud Engineer
- Platform Engineer
- Site Reliability Engineer (SRE)

---

# Beginner Interview Questions

---

## Q1. What is Kubernetes?

**Answer**

Kubernetes is an open-source container orchestration platform used to deploy, manage, scale and automate containerized applications.

---

## Q2. Why is Kubernetes used?

It provides:

- Auto Scaling
- Self-Healing
- Load Balancing
- Rolling Updates
- Service Discovery
- High Availability

---

## Q3. What is a Pod?

A Pod is the smallest deployable unit in Kubernetes.

A Pod contains one or more containers.

---

## Q4. What is a Deployment?

A Deployment manages ReplicaSets and Pods.

It provides:

- Rolling Updates
- Rollbacks
- Scaling
- Self-Healing

---

## Q5. What is a ReplicaSet?

A ReplicaSet maintains the desired number of running Pods.

---

## Q6. What is a Service?

A Service provides stable network access to Pods.

---

## Q7. What is kubectl?

kubectl is the Kubernetes command-line tool.

---

## Q8. What is a Namespace?

A Namespace logically separates resources inside a cluster.

---

## Q9. What is ConfigMap?

Stores non-sensitive configuration.

---

## Q10. What is Secret?

Stores sensitive information.

---

# Intermediate Interview Questions

---

## Q11. Explain Kubernetes Architecture.

A Kubernetes Cluster contains:

```
Control Plane

↓

Worker Nodes

↓

Pods
```

Control Plane components:

- API Server
- Scheduler
- Controller Manager
- etcd

Worker Node components:

- kubelet
- kube-proxy
- Container Runtime

---

## Q12. What is etcd?

etcd is the distributed key-value database storing Kubernetes cluster state.

---

## Q13. What is kubelet?

kubelet runs on every Worker Node.

Responsibilities:

- Create Pods
- Monitor Pods
- Report Node Status

---

## Q14. What is kube-proxy?

Handles Service networking and traffic routing.

---

## Q15. Difference Between Pod and Deployment?

| Pod | Deployment |
|------|------------|
| Runs Containers | Manages Pods |
| No Rolling Updates | Rolling Updates |
| Manual Scaling | Automatic Scaling |
| No Rollback | Rollback Support |

---

## Q16. Difference Between ConfigMap and Secret?

| ConfigMap | Secret |
|------------|---------|
| Non-sensitive Data | Sensitive Data |
| Plain Configuration | Passwords |
| Feature Flags | Certificates |

---

## Q17. Difference Between PV and PVC?

PV

```
Storage Resource
```

PVC

```
Storage Request
```

---

## Q18. Difference Between ClusterIP and NodePort?

ClusterIP

```
Internal Access
```

NodePort

```
External Access Using Node IP
```

---

## Q19. Difference Between Ingress and LoadBalancer?

Ingress

- One Entry Point
- Multiple Services
- URL Routing

LoadBalancer

- One Service
- External IP
- No URL Routing

---

## Q20. What is Helm?

Helm is the package manager for Kubernetes.

---

# Advanced Interview Questions

---

## Q21. Explain Rolling Updates.

Deployment gradually replaces old Pods with new Pods while keeping the application available.

---

## Q22. Explain Rollbacks.

Rollback restores the previous Deployment revision if an update fails.

---

## Q23. What happens when a Pod crashes?

```
Pod Crash

↓

ReplicaSet Detects Failure

↓

New Pod Created

↓

Application Restored
```

---

## Q24. Explain Self-Healing.

Kubernetes automatically recreates failed Pods to maintain the desired state.

---

## Q25. Explain Service Discovery.

Pods communicate using Service DNS names instead of Pod IP addresses.

---

## Q26. Explain Kubernetes Scheduler.

Scheduler selects the best Worker Node based on available resources and scheduling rules.

---

## Q27. Explain Resource Requests and Limits.

Requests reserve CPU and memory.

Limits restrict maximum CPU and memory usage.

---

## Q28. Explain Readiness Probe.

Determines when a Pod is ready to receive traffic.

---

## Q29. Explain Liveness Probe.

Checks whether a container is healthy.

If it fails repeatedly,

Kubernetes restarts the container.

---

## Q30. Explain Startup Probe.

Allows slow-starting applications additional startup time before liveness checks begin.

---

# Production Scenario Questions

---

## Scenario 1

One Pod suddenly crashes.

What happens?

**Answer**

ReplicaSet creates a replacement Pod.

---

## Scenario 2

Traffic suddenly increases 10x.

How do you handle it?

Possible approaches:

- Increase replicas
- Use Horizontal Pod Autoscaler (HPA)
- Scale Nodes if required

---

## Scenario 3

A Deployment update fails.

What do you do?

```
Check Rollout

↓

View Events

↓

Rollback
```

Useful commands:

```bash
kubectl rollout status deployment APP

kubectl rollout undo deployment APP
```

---

## Scenario 4

A Service has no endpoints.

Possible causes:

- Wrong Labels
- Wrong Selector
- Pods Not Running
- Namespace Mismatch

---

## Scenario 5

A Pod remains in Pending state.

Possible reasons:

- Insufficient CPU
- Insufficient Memory
- PVC Not Bound
- Node Selector Constraints
- Taints and Tolerations
- Missing Resources

---

## Scenario 6

ImagePullBackOff error.

Possible reasons:

- Wrong Image Name
- Private Registry Authentication
- Network Issues
- Image Does Not Exist

---

## Scenario 7

CrashLoopBackOff.

Possible causes:

- Application Crash
- Missing Configuration
- Invalid Command
- Secret Missing
- Health Probe Failure

---

## Scenario 8

Node becomes NotReady.

Possible reasons:

- kubelet Stopped
- Network Failure
- Disk Full
- Resource Exhaustion

---

## Scenario 9

Pods cannot communicate.

Check:

- Service
- Endpoints
- DNS
- Network Policies
- CNI Plugin

---

## Scenario 10

Persistent Volume is not attached.

Check:

- PVC Status
- StorageClass
- CSI Driver
- Events

---

# Troubleshooting Questions

---

## Pod Not Starting

Commands

```bash
kubectl get pods

kubectl describe pod POD

kubectl logs POD
```

---

## Deployment Failed

```bash
kubectl rollout status deployment APP

kubectl rollout history deployment APP
```

---

## Node Health

```bash
kubectl get nodes

kubectl describe node NODE_NAME
```

---

## Events

```bash
kubectl get events

kubectl get events --sort-by=.metadata.creationTimestamp
```

---

## Cluster Information

```bash
kubectl cluster-info
```

---

# Hands-on Interview Tasks

Candidates may be asked to:

- Create a Namespace
- Deploy Nginx
- Scale a Deployment
- Expose a Service
- Create a ConfigMap
- Create a Secret
- Mount a Volume
- Roll Back a Deployment
- Create an Ingress
- Install an application using Helm

---

# Frequently Used Commands

```bash
kubectl get pods

kubectl get deploy

kubectl get svc

kubectl get nodes

kubectl describe pod

kubectl logs POD

kubectl exec -it POD -- bash

kubectl apply -f file.yaml

kubectl delete -f file.yaml

kubectl rollout status deployment APP

kubectl rollout undo deployment APP

helm install

helm upgrade

helm rollback
```

---

# Architecture Interview Question

Draw Kubernetes Architecture.

```
Developer

↓

kubectl

↓

API Server

↓

Scheduler

↓

Controller Manager

↓

etcd

↓

Worker Nodes

↓

Pods

↓

Containers
```

Candidates are often asked to explain the responsibility of each component.

---

# HR + Technical Combination Questions

### Why Kubernetes instead of Docker alone?

Because Docker creates containers, while Kubernetes manages containerized applications across multiple machines with automation, scaling and self-healing.

---

### Why do companies use Helm?

To simplify deployment, upgrades and rollback of complex Kubernetes applications.

---

### Why use Deployments instead of Pods?

Deployments provide production-ready lifecycle management.

---

### Why are Services required?

Pods are temporary and their IP addresses can change.

Services provide stable networking.

---

### Why use ConfigMaps?

To separate configuration from application code.

---

### Why use Secrets?

To securely store sensitive information.

---

# Real Interview Tips

✔ Explain concepts using architecture diagrams.

✔ Describe production use cases.

✔ Mention relevant Kubernetes objects.

✔ Use proper terminology.

✔ Explain troubleshooting steps before giving commands.

✔ Be familiar with common `kubectl` commands.

✔ Understand how different Kubernetes resources work together.

✔ Practice deploying applications in a lab environment.

---

# 30-Second Kubernetes Interview Summary

```
Developer

↓

Git

↓

CI/CD

↓

Docker Image

↓

Container Registry

↓

Deployment

↓

ReplicaSet

↓

Pods

↓

Service

↓

Ingress

↓

Users
```

This end-to-end workflow demonstrates how a modern Kubernetes application is deployed and exposed.

---

# Final Kubernetes Learning Roadmap

```
Linux

↓

Docker

↓

Kubernetes Architecture

↓

Pods

↓

ReplicaSets

↓

Deployments

↓

Services

↓

Namespaces

↓

Labels

↓

ConfigMaps

↓

Secrets

↓

Storage

↓

Ingress

↓

Helm

↓

Monitoring

↓

CI/CD

↓

Production Kubernetes
```

Following this sequence builds a strong foundation before moving into advanced topics such as Operators, GitOps and service meshes.

---

# Chapter 9 Summary

By completing this chapter, you have learned:

✅ Kubernetes Fundamentals

✅ Cluster Architecture

✅ Installation

✅ kubectl

✅ Pods

✅ ReplicaSets

✅ Deployments

✅ Services

✅ Namespaces

✅ Labels & Selectors

✅ ConfigMaps

✅ Secrets

✅ Persistent Storage

✅ Ingress

✅ Helm

✅ Production Best Practices

✅ Interview Preparation

You now have a strong foundation for working with Kubernetes in real-world DevOps and Cloud environments.

---

# Next Chapter

# Chapter 10 – Monitoring & Logging

In the next chapter, we will learn:

- Why Monitoring is Important
- Prometheus
- Grafana
- Alertmanager
- Node Exporter
- kube-state-metrics
- Fluent Bit
- Fluentd
- Loki
- Elasticsearch
- Kibana
- Centralized Logging
- Dashboards
- Alerts
- Production Monitoring Best Practices
- Interview Questions