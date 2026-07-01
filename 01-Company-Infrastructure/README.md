# Chapter 1

# Company Infrastructure & DevOps Fundamentals

---

# Chapter Objectives

After completing this chapter, you will be able to understand:

- What is Company Infrastructure?
- Why Infrastructure is required before application deployment.
- Different teams inside a software company.
- Responsibilities of a DevOps Engineer.
- How an application reaches production.
- How Infrastructure, Developers and DevOps work together.

---

# 1.1 Introduction

Before learning Linux, Docker, Kubernetes, Jenkins or AWS, it is important to understand how a software company actually works.

Many beginners start learning DevOps by installing Docker or Kubernetes without understanding the environment in which these technologies are used.

As a result, they know commands but fail to understand the complete software delivery process.

This chapter builds the foundation required for every DevOps Engineer.

---

# 1.2 What is a Software Company?

A software company develops applications that solve business problems.

Examples include:

- Amazon
- Flipkart
- Netflix
- Swiggy
- Zomato
- Banking Applications
- Hospital Management Systems
- ERP Software

Customers only see a website or a mobile application.

Behind that application, hundreds of servers, databases, networking devices, and automation tools work together.

---

# Example

Suppose ShopKart Pvt. Ltd. is an online shopping company.

The customer opens:

```
https://www.shopkart.com
```

The customer can:

- Login
- Search products
- Add products to cart
- Make payment
- Track orders

Although it looks like a single application, internally it consists of multiple services.

```
Customer

        │

        ▼

Website

        │

        ▼

Login Service

Product Service

Cart Service

Payment Service

Order Service

Notification Service
```

Each service performs a separate task.

This architecture makes applications easier to develop, maintain and scale.

---

# 1.3 Teams Inside a Software Company

A modern software company contains multiple teams.

```
CEO

│

├── HR

├── Finance

├── Sales

├── Marketing

└── Technical Department

      │

      ├── Developers

      ├── QA Engineers

      ├── DevOps Engineers

      ├── Cloud Engineers

      ├── Database Administrators

      ├── Security Team

      └── Support Team
```

Each team has specific responsibilities.

---

# Development Team

Developers build software.

Their responsibilities include:

- Writing source code.
- Fixing bugs.
- Developing new features.
- Maintaining applications.

Developers primarily work with programming languages such as:

- Java
- Python
- Go
- PHP
- Node.js
- .NET

---

# QA Team

Quality Assurance Engineers verify that the application works correctly.

Their responsibilities include:

- Functional Testing
- Regression Testing
- Performance Testing
- Security Testing
- Bug Reporting

The application cannot move to production until testing is completed successfully.

---

# DevOps Team

The DevOps team automates software delivery.

Responsibilities include:

- Build Automation
- Continuous Integration
- Continuous Deployment
- Infrastructure Automation
- Monitoring
- Backup
- Recovery
- Scaling

A DevOps Engineer is responsible for ensuring that software can be deployed reliably and repeatedly.

---

# Cloud Team

The Cloud Team manages infrastructure.

Responsibilities include:

- Virtual Machines
- Networking
- Storage
- Security Groups
- Load Balancers
- Cloud Services

Common cloud platforms:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)

---

# Database Team

The Database Team manages data.

Examples:

- MySQL
- PostgreSQL
- Oracle
- MongoDB

Responsibilities include:

- Database installation
- Backup
- Performance tuning
- Disaster recovery

---

# Security Team

The Security Team protects the organization.

Responsibilities include:

- Firewall
- Identity Management
- SSL Certificates
- Access Control
- Security Audits
- Vulnerability Assessment

---

# Summary

In this chapter, we learned:

- What a software company is.
- Different technical teams.
- The responsibility of each team.
- The role of a DevOps Engineer within an organization.

In the next section, we will understand **Company Infrastructure** and learn how companies prepare servers before deploying applications.
---

# 1.4 What is Company Infrastructure?

Infrastructure is the complete technical environment required to run a software application.

Just as a building cannot exist without land, foundation, pillars, electricity and water, a software application cannot run without servers, networking, storage and operating systems.

Infrastructure is the foundation on which every application runs.

Without infrastructure, no website, mobile application or enterprise software can function.

---

# Real World Example

Suppose ShopKart Pvt. Ltd. wants to launch a new online shopping website.

The management cannot simply ask developers to write code.

Before developers start coding, the company must prepare the complete infrastructure.

The first task is to build the environment where the application will eventually run.

---

# Components of Infrastructure

A modern software infrastructure usually contains the following components.

```
Internet

↓

Firewall

↓

Router

↓

Core Switch

↓

Load Balancer

↓

Application Servers

↓

Database Servers

↓

Storage

↓

Backup Server

↓

Monitoring Server
```

Every component performs a specific task.

Removing any one of them may affect the entire application.

---

# Example

Imagine an online shopping website receives 5 million visitors every day.

The company requires:

- Powerful Servers
- High-Speed Internet
- Multiple Databases
- Backup Systems
- Security Devices
- Monitoring Tools

All these resources together form the company's infrastructure.

---

# Infrastructure Types

Infrastructure can be deployed in different ways.

## 1. On-Premises Infrastructure

The company purchases and manages its own hardware.

```
Company

↓

Own Building

↓

Own Server Room

↓

Own Servers

↓

Own Network
```

Advantages

- Full control
- High security
- Suitable for banks and government organizations

Disadvantages

- High initial cost
- Maintenance responsibility
- Hardware replacement cost

---

## 2. Cloud Infrastructure

Instead of purchasing servers, companies rent infrastructure from cloud providers.

Popular providers include:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)

```
Company

↓

Cloud Provider

↓

Virtual Servers

↓

Applications
```

Advantages

- Lower initial investment
- Easy scaling
- High availability
- Faster deployment

---

## 3. Hybrid Infrastructure

Some resources remain inside the company.

Some resources are hosted in the cloud.

```
Company Data Center

↓

VPN

↓

AWS

↓

Applications
```

Many banking and enterprise organizations use hybrid infrastructure.

---

# Why Infrastructure Comes Before Development

Many beginners think the sequence is:

```
Developer

↓

Application

↓

Server
```

This is incorrect.

The correct sequence is:

```
Business Requirement

↓

Infrastructure Planning

↓

Servers

↓

Operating System

↓

Networking

↓

Security

↓

Development

↓

Testing

↓

Deployment
```

Infrastructure is prepared before production deployment so that the application has a reliable environment to run.

---

# Infrastructure Responsibilities

Infrastructure must provide:

- Compute Power
- Memory
- Storage
- Network Connectivity
- Security
- Backup
- Monitoring
- High Availability
- Disaster Recovery

Without these services, applications cannot run reliably.

---

# Key Takeaways

- Infrastructure is the foundation of every software application.
- Infrastructure includes servers, networking, storage and security.
- Applications are deployed on infrastructure.
- Companies may use On-Premises, Cloud or Hybrid Infrastructure.
- Infrastructure planning happens before production deployment.

---

# What's Next?

In the next section, we will enter a real Data Center and understand every component inside it, including:

- Rack
- Physical Server
- UPS
- Switch
- Router
- Firewall
- Cooling System
- Cabling
- Storage Systems

This knowledge forms the foundation for Linux, Docker, Kubernetes and Cloud Computing.
---

# 1.5 Infrastructure Planning Before Development

One of the biggest misconceptions among beginners is that developers start coding immediately after receiving a project.

In reality, professional software companies spend significant time planning the infrastructure before development begins.

The infrastructure must be capable of handling current users as well as future growth.

---

# Real Company Scenario

Suppose ShopKart Pvt. Ltd. plans to launch a new E-Commerce platform.

The management estimates that the platform will receive:

- 50,000 users on Day 1
- 5 lakh users within 6 months
- 50 lakh users within 2 years

Before a single line of code is written, several technical discussions take place.

Questions include:

- Where will the application run?
- How many servers are required?
- Which operating system will be used?
- Which database should be selected?
- How much storage is required?
- How will backups be taken?
- How will security be implemented?
- How will future scaling be handled?

Infrastructure planning answers these questions.

---

# Typical Planning Meeting

The following teams participate.

```
Business Team

↓

Project Manager

↓

Solution Architect

↓

Infrastructure Team

↓

Cloud Team

↓

Network Team

↓

Security Team

↓

DevOps Team

↓

Development Team
```

Each team contributes according to its responsibility.

---

# Infrastructure Planning Checklist

Before development begins, companies usually finalize the following.

## Compute

- Number of Servers
- CPU Configuration
- RAM
- Operating System

---

## Storage

- SSD or HDD
- Storage Capacity
- Backup Storage
- Disaster Recovery Storage

---

## Network

- Public IP
- Private IP
- Firewall
- Load Balancer
- DNS
- Internet Bandwidth

---

## Database

- MySQL
- PostgreSQL
- Oracle
- MongoDB

Database size and expected growth are also estimated.

---

## Security

Security planning includes:

- SSL Certificates
- IAM
- Firewall Rules
- VPN
- Access Policies
- Password Management

---

## Monitoring

The infrastructure team also decides how servers will be monitored.

Examples:

- CPU Usage
- Memory Usage
- Disk Usage
- Network Usage
- Application Health
- Database Health

Monitoring is discussed at the planning stage instead of after deployment.

---

# High Availability Planning

Production applications must remain available even if hardware fails.

Example.

Instead of deploying one application server:

```
Application Server
```

Companies deploy multiple servers.

```
Load Balancer

      │

 ┌────┴────┐

Server-1   Server-2

      │

 Database
```

If Server-1 fails,

Server-2 continues serving users.

Users do not experience downtime.

This concept is called **High Availability (HA)**.

---

# Scalability Planning

Companies also plan for future growth.

Instead of purchasing extremely large servers initially, they design infrastructure that can grow gradually.

Example:

```
Current Users

↓

10,000

↓

1 Server

----------------

Future Users

↓

1,00,000

↓

3 Servers

----------------

Future Users

↓

10,00,000

↓

10 Servers
```

This ability to increase capacity is known as **Scalability**.

---

# Disaster Recovery Planning

Every company prepares for unexpected failures.

Possible failures include:

- Hard Disk Failure
- Server Failure
- Power Failure
- Network Failure
- Fire
- Flood
- Cyber Attack

To reduce business impact, companies maintain:

- Regular Backups
- Secondary Data Centers
- Disaster Recovery Sites
- Replication

---

# Key Points

Infrastructure planning ensures that:

- Applications perform efficiently.
- Data remains secure.
- Downtime is minimized.
- Future growth is supported.
- Business continuity is maintained.

Infrastructure planning is one of the first technical activities performed in any software project.

---

# Summary

In this section, we learned:

- Why infrastructure planning happens before development.
- Which teams participate in planning.
- What decisions are made before coding starts.
- Why High Availability, Scalability and Disaster Recovery are essential.

---

# Next Chapter Section

**1.6 Inside a Real Data Center**

In the next section, we will physically enter a Data Center and understand:

- Server Rack
- Physical Server
- UPS
- Cooling System
- Patch Panel
- Switch
- Router
- Firewall
- Storage
- Cabling

This is the place where the entire infrastructure actually exists.
---

# 1.6 Inside a Real Data Center

Now that we understand why infrastructure is required, let us visit a real Data Center.

A Data Center is a secure facility where all company servers, networking devices, storage systems, and security equipment are installed.

It is considered the heart of any IT organization.

Without a Data Center, business applications cannot operate.

---

# What is a Data Center?

A Data Center is a dedicated location designed to host IT infrastructure.

It provides:

- Continuous Power Supply
- High-Speed Network
- Physical Security
- Cooling System
- Fire Protection
- Backup Power
- Internet Connectivity
- Monitoring

Every production application ultimately runs inside a Data Center or on a Cloud Data Center.

---

# Real Company Example

Suppose ShopKart Pvt. Ltd. receives nearly 20 lakh users every day.

Every customer action depends on the Data Center.

Examples:

- User Login
- Product Search
- Payment
- Order Placement
- Email Notifications
- Invoice Generation

If the Data Center stops working, the entire business stops.

---

# Typical Data Center Layout

```
                    INTERNET
                        │
                ISP Connection
                        │
                   Firewall
                        │
                     Router
                        │
                 Core Network Switch
                        │
        ┌───────────────┼───────────────┐
        │               │               │
   Server Rack 1   Server Rack 2   Server Rack 3
        │               │               │
        │               │               │
  Linux Servers    Windows Servers   Storage
        │
   VMware / Hyper-V
        │
 Virtual Machines
        │
 Applications
```

This is a simplified representation of a production Data Center.

---

# Main Components of a Data Center

Every professional Data Center contains several important components.

## 1. Server Racks

Servers are not placed randomly.

They are mounted inside metal cabinets called **Server Racks**.

Each rack contains multiple servers.

```
+----------------------+
|      Rack 42U        |
|----------------------|
| Server 1             |
| Server 2             |
| Server 3             |
| Server 4             |
| Storage              |
| Network Switch       |
+----------------------+
```

---

## 2. Physical Servers

A Physical Server is a powerful computer designed to run continuously.

Typical configuration:

- Dual CPU
- 256 GB RAM
- Multiple SSDs
- RAID Controller
- Dual Power Supply
- Multiple Network Ports

Unlike personal computers, servers are optimized for reliability and performance.

---

## 3. Storage Systems

Applications generate huge amounts of data.

Storage systems keep:

- Databases
- Images
- Videos
- Application Files
- Backups
- Logs

Examples include:

- SAN (Storage Area Network)
- NAS (Network Attached Storage)

---

## 4. Network Switch

A Switch connects multiple devices within the Data Center.

Examples:

- Servers
- Storage
- Firewalls
- Routers

Without a switch, servers cannot communicate with each other.

---

## 5. Router

The Router connects the internal network to external networks.

Its responsibilities include:

- Routing packets
- Connecting different networks
- Internet communication

---

## 6. Firewall

The Firewall protects the company network.

It decides:

- Which traffic is allowed.
- Which traffic should be blocked.

It is one of the most critical security components.

---

## 7. UPS (Uninterruptible Power Supply)

Electricity failures are common.

Servers cannot shut down suddenly.

UPS provides temporary power during outages.

Benefits:

- Prevents sudden shutdown
- Protects data
- Prevents hardware damage

---

## 8. Generator

If the power outage continues for several minutes, diesel generators automatically start.

This ensures uninterrupted business operations.

---

## 9. Cooling System

Servers generate significant heat.

A production server room maintains a controlled temperature.

Cooling systems:

- Precision Air Conditioners
- Cooling Units
- Temperature Sensors

Without cooling, servers may overheat and fail.

---

## 10. Monitoring System

Every device inside the Data Center is monitored continuously.

Examples:

- CPU Usage
- Memory Usage
- Disk Health
- Temperature
- Fan Speed
- Power Status
- Network Connectivity

If any abnormality occurs, alerts are generated immediately.

---

# Data Center Security

Only authorized personnel can enter the server room.

Common security measures include:

- Biometric Access
- RFID Cards
- CCTV Cameras
- Security Guards
- Visitor Logs

Physical security is as important as cybersecurity.

---

# Important Observation

Many beginners believe applications run directly on laptops.

In reality, production applications run inside professional Data Centers or Cloud Data Centers.

A developer's laptop is used only for writing code.

The actual application is deployed to dedicated production servers.

---

# Summary

In this section, we learned:

- What a Data Center is.
- Why it is required.
- The major components inside a Data Center.
- How production servers are organized.
- Why power, cooling, networking and security are essential.

The Data Center forms the physical foundation of every production environment.

---

# Next Section

## 1.7 Physical Server

In the next section, we will open a server rack and study a Physical Server in detail.

We will understand:

- Server Hardware
- CPU
- RAM
- Storage
- RAID
- Network Cards
- Power Supply
- Server Boot Process

This knowledge is essential before learning Virtual Machines, Docker and Kubernetes.
---

# 1.7 Physical Server

A **Physical Server** is a high-performance computer designed to run business applications continuously, 24 hours a day, 365 days a year.

Unlike a desktop computer, a server is designed for:

- High Performance
- High Availability
- Continuous Operation
- Redundant Hardware
- Remote Management

Servers are installed inside Data Center racks.

---

# Desktop Computer vs Physical Server

| Desktop Computer | Physical Server |
|------------------|-----------------|
| Home or Office Use | Data Center Use |
| 8–32 GB RAM | 64 GB to 4 TB RAM |
| Single CPU | Multiple CPUs |
| Single Power Supply | Dual Redundant Power Supply |
| One Hard Disk | RAID Storage |
| One Network Port | Multiple Network Ports |
| Manual Maintenance | Remote Management |

---

# Example Configuration

A production server may have the following hardware.

| Component | Example |
|-----------|----------|
| CPU | Dual Intel Xeon |
| RAM | 256 GB DDR5 |
| Storage | 4 × 2 TB SSD |
| RAID | RAID 10 |
| Network | 4 × 10 Gbps NIC |
| Power Supply | Dual Redundant PSU |

---

# Physical Server Architecture

```
+----------------------------------------+
|            Physical Server             |
+----------------------------------------+
| CPU 1      CPU 2                       |
|                                        |
| 256 GB RAM                             |
|                                        |
| RAID Controller                        |
|                                        |
| SSD / HDD Storage                      |
|                                        |
| Network Cards                          |
|                                        |
| Power Supply 1                          |
| Power Supply 2                          |
+----------------------------------------+
```

---

# Major Components

## CPU

The CPU executes instructions.

Responsibilities:

- Process Requests
- Execute Applications
- Perform Calculations

More users require more CPU resources.

---

## RAM

RAM temporarily stores running programs and data.

If RAM becomes full:

- Applications become slow.
- Database performance decreases.
- System may become unstable.

Large production servers commonly have:

- 128 GB
- 256 GB
- 512 GB
- 1 TB RAM

---

## Storage

Servers store:

- Operating System
- Applications
- Databases
- Logs
- User Files

Storage types include:

- HDD
- SSD
- NVMe SSD

Modern production environments prefer SSD or NVMe for better performance.

---

# RAID

Production servers rarely use a single hard disk.

Instead, they use **RAID (Redundant Array of Independent Disks).**

Benefits:

- Data Protection
- Improved Performance
- Fault Tolerance

Common RAID Levels:

| RAID | Purpose |
|------|---------|
| RAID 1 | Mirroring |
| RAID 5 | Performance + Redundancy |
| RAID 10 | High Performance + High Availability |

---

# Network Interface Card (NIC)

Every server communicates through Network Interface Cards.

Example:

```
Internet

↓

Firewall

↓

Switch

↓

NIC

↓

Server
```

Production servers usually have multiple NICs.

Reasons:

- Redundancy
- Higher Bandwidth
- Separate Management Network

---

# Power Supply

Enterprise servers normally have two power supplies.

```
Power Supply A

      +

Power Supply B

↓

Server
```

If one power supply fails, the server continues running.

This eliminates single points of failure.

---

# Remote Management

Servers often include dedicated management ports.

Examples:

- iLO (HPE)
- iDRAC (Dell)
- XClarity (Lenovo)

Administrators can:

- Power On
- Power Off
- Restart
- Install Operating System
- View Console

without physically visiting the Data Center.

---

# Why Not Deploy Applications Directly?

A common beginner question is:

> Why can't we install our application directly on one Physical Server?

Example.

```
Server

↓

Java Application

↓

Python Application

↓

NodeJS Application

↓

PHP Application

↓

MySQL

↓

MongoDB

↓

Redis
```

Problems:

- Resource Conflicts
- Different Software Versions
- Difficult Maintenance
- Poor Scalability
- Higher Downtime

This challenge led to the adoption of **Virtual Machines**, followed later by **Containers**.

---

# Key Takeaways

- A Physical Server is the hardware foundation of modern IT infrastructure.
- Enterprise servers are designed for continuous operation.
- Servers contain redundant hardware for high availability.
- Multiple applications can run on a server, but direct deployment creates management challenges.
- These challenges eventually led to virtualization and containerization technologies.

---

# What's Next?

## 1.8 Virtual Machine

In the next section, we will answer one of the most important questions in DevOps:

> **How can one Physical Server safely run multiple independent operating systems?**

This concept introduces **Virtual Machines (VMs)** and lays the foundation for VMware, Hyper-V, KVM, Cloud Computing, Docker and Kubernetes.
---

# 1.8 Virtual Machine (VM)

Until now we have learned that a Physical Server is a very powerful computer.

Now imagine the following situation.

A company has purchased one server with the following configuration.

| Component | Specification |
|-----------|---------------|
| CPU | 32 Core |
| RAM | 256 GB |
| Storage | 4 TB SSD |

The company installs only one application on this server.

Result?

```
CPU Usage      : 8%

RAM Usage      : 20 GB / 256 GB

Storage Usage  : 150 GB / 4 TB
```

More than **90% of the hardware remains unused.**

This is a waste of money.

---

# The Problem

Suppose the company has five applications.

```
Payroll

CRM

ERP

Website

Monitoring
```

Should the company purchase five separate servers?

```
Application 1

↓

Server 1

----------------

Application 2

↓

Server 2

----------------

Application 3

↓

Server 3

----------------

Application 4

↓

Server 4

----------------

Application 5

↓

Server 5
```

This approach creates several problems.

- High Cost
- Higher Electricity Consumption
- More Rack Space
- Higher Maintenance
- Low Resource Utilization

Companies needed a better solution.

---

# The Solution

The solution was **Virtualization**.

Instead of purchasing five physical servers,

one powerful server can be divided into multiple virtual servers.

Each virtual server behaves like an independent computer.

These virtual computers are called **Virtual Machines (VMs).**

---

# What is a Virtual Machine?

A Virtual Machine is a software-based computer running inside a Physical Server.

Every VM has its own:

- Operating System
- CPU Allocation
- RAM Allocation
- Storage
- Network Interface
- IP Address

Although multiple VMs share the same hardware,

each VM behaves as an independent server.

---

# Example

One Physical Server

```
CPU : 32 Core

RAM : 256 GB

Storage : 4 TB
```

can be divided into

```
VM-1

Ubuntu

4 CPU

16 GB RAM

----------------

VM-2

Windows Server

8 CPU

32 GB RAM

----------------

VM-3

Red Hat Linux

8 CPU

64 GB RAM

----------------

VM-4

Ubuntu

4 CPU

16 GB RAM

----------------

VM-5

Rocky Linux

8 CPU

64 GB RAM
```

All these machines run independently.

---

# Virtualization Architecture

```
Applications

↓

Guest Operating Systems

↓

Virtual Machines

↓

Hypervisor

↓

Physical Server

↓

CPU

RAM

Storage

Network
```

---

# Hypervisor

The software responsible for creating and managing Virtual Machines is called a **Hypervisor**.

It divides hardware resources among multiple VMs.

Popular Hypervisors include:

- VMware ESXi
- Microsoft Hyper-V
- KVM
- Xen

---

# Real Company Example

Suppose ShopKart has purchased one server costing ₹15,00,000.

Instead of buying ten more servers,

the company creates ten Virtual Machines.

```
Physical Server

↓

VM 1 → Jenkins

VM 2 → GitLab

VM 3 → Docker Host

VM 4 → Kubernetes Master

VM 5 → Worker Node

VM 6 → Monitoring

VM 7 → Database

VM 8 → Backup

VM 9 → QA

VM 10 → Development
```

The company saves:

- Hardware Cost
- Electricity
- Cooling Cost
- Rack Space
- Maintenance Cost

---

# Advantages of Virtual Machines

- Better Hardware Utilization
- Lower Cost
- Easy Backup
- Easy Migration
- Easy Cloning
- Better Isolation
- Independent Operating Systems

---

# Disadvantages of Virtual Machines

Although Virtual Machines solved many problems,

they introduced new challenges.

Every VM requires:

- Complete Operating System
- Separate Kernel
- Separate Boot Process
- More RAM
- More Storage

Example

```
VM 1

Ubuntu

↓

2 GB OS

----------------

VM 2

Ubuntu

↓

2 GB OS

----------------

VM 3

Ubuntu

↓

2 GB OS
```

Even before installing applications,

each VM consumes resources.

Companies again started asking:

> "Do we really need an entire Operating System for every application?"

This question led to the invention of **Containers**.

Docker was created to solve this problem.

---

# Interview Questions

### Q1. What is Virtualization?

**Answer**

Virtualization is the process of creating multiple Virtual Machines on a single Physical Server using a Hypervisor.

---

### Q2. What is a Virtual Machine?

**Answer**

A Virtual Machine is a software-based computer that behaves like an independent Physical Server.

---

### Q3. What is a Hypervisor?

**Answer**

A Hypervisor is software that creates and manages Virtual Machines.

---

### Q4. Name some Hypervisors.

- VMware ESXi
- Hyper-V
- KVM
- Xen

---

# Summary

In this section, we learned:

- Why Virtual Machines were introduced.
- How virtualization works.
- What a Hypervisor does.
- Advantages and disadvantages of Virtual Machines.
- Why companies later moved towards Containers.

---

# Next Section

## 1.9 Containers – Why Docker Was Invented

In the next section, we will understand why Virtual Machines were not enough and how Containers changed modern application deployment forever.
---

# 1.9 Why Containers Were Invented

Virtual Machines solved many infrastructure problems.

However, as software companies started adopting Microservices Architecture, another challenge appeared.

A single business application was no longer a single program.

Instead, it consisted of dozens or even hundreds of independent services.

Example:

```
ShopKart Application

│

├── Login Service

├── Product Service

├── Cart Service

├── Payment Service

├── Order Service

├── Inventory Service

├── Notification Service

├── Recommendation Service

└── Analytics Service
```

Each service required its own runtime environment.

Running every service inside a separate Virtual Machine became expensive.

---

# Problem with Virtual Machines

Suppose one Java application requires only:

```
2 CPU

2 GB RAM

10 GB Storage
```

A Virtual Machine still requires:

```
Operating System

Kernel

Drivers

Libraries

Boot Process
```

Even before the application starts, the Operating System consumes system resources.

Now imagine running 100 applications.

```
100 Applications

↓

100 Virtual Machines

↓

100 Operating Systems
```

The company wastes:

- CPU
- RAM
- Storage
- Boot Time

Infrastructure becomes difficult to manage.

---

# Real Company Example

Suppose ShopKart has 50 microservices.

Using Virtual Machines:

```
50 Applications

↓

50 Virtual Machines

↓

50 Operating Systems
```

Memory consumption becomes very high.

Boot time becomes slow.

Maintenance becomes difficult.

Updates take more time.

---

# Engineers Started Asking

Can we run applications

without installing a complete Operating System every time?

The answer became

**Containers.**

---

# What is a Container?

A Container is an isolated environment that contains:

- Application
- Runtime
- Libraries
- Dependencies
- Configuration Files

A Container **does not include a complete Operating System.**

Instead,

all Containers share the host Operating System Kernel.

---

# Virtual Machine Architecture

```
Application

↓

Guest Operating System

↓

Hypervisor

↓

Physical Server
```

Every Virtual Machine has its own Operating System.

---

# Container Architecture

```
Application

↓

Libraries

↓

Container Runtime

↓

Docker Engine

↓

Host Operating System

↓

Physical Server
```

All Containers share the same Operating System Kernel.

This makes Containers:

- Smaller
- Faster
- More Efficient

---

# Difference Between Virtual Machine and Container

| Virtual Machine | Container |
|-----------------|-----------|
| Full Operating System | Shares Host Kernel |
| Large Size | Lightweight |
| Slow Boot | Starts in Seconds |
| Higher Resource Usage | Low Resource Usage |
| Hypervisor Required | Docker Engine Required |
| Heavy Maintenance | Easy Maintenance |

---

# Example

Virtual Machine

```
Ubuntu

↓

Java

↓

Application
```

Container

```
Application

↓

Java Runtime

↓

Docker Engine

↓

Ubuntu Kernel
```

Notice that the Container does not require another complete Operating System.

---

# Why Containers Became Popular

Companies adopted Containers because they provide:

- Faster Deployment
- Lower Memory Usage
- Better Resource Utilization
- Easy Scaling
- Consistent Runtime Environment
- Portable Applications

Containers solved the famous problem:

> "It works on my laptop but not on the production server."

---

# Real Production Example

Developer Laptop

```
Ubuntu

Java 21

Application

↓

Docker Image
```

Production Server

```
Ubuntu

Docker

↓

Same Docker Image

↓

Application Runs Successfully
```

The environment remains identical.

No version mismatch occurs.

---

# Important Point

A Container is **not** a Virtual Machine.

A Container is an isolated process running on the Host Operating System.

Containers start much faster than Virtual Machines.

---

# But Another Problem Appeared...

Companies started creating hundreds of Containers.

Example:

```
Login Container

Payment Container

Order Container

Inventory Container

Notification Container

Analytics Container

Recommendation Container

...

200 Containers
```

A new question appeared.

Who will:

- Start Containers?
- Stop Containers?
- Restart Failed Containers?
- Scale Containers?
- Perform Rolling Updates?
- Balance Traffic?

Docker alone could not manage thousands of Containers.

A new technology was required.

That technology is

# Kubernetes.

---

# Interview Questions

## Q1 What problem did Containers solve?

Containers reduced resource consumption by sharing the Host Operating System Kernel instead of running separate Operating Systems.

---

## Q2 Why are Containers faster than Virtual Machines?

Because Containers do not boot a complete Operating System.

---

## Q3 Can Containers run different applications?

Yes.

Each Container runs its own isolated application and dependencies.

---

## Q4 Why did Docker become popular?

Because Docker made Container creation, packaging and deployment simple and consistent across environments.

---

# Summary

In this section, we learned:

- Why Virtual Machines were not sufficient.
- Why Containers were introduced.
- Difference between Virtual Machines and Containers.
- Why Docker became popular.
- Why companies adopted Containers.

---

# Next Section

## 1.10 Why Kubernetes Was Invented

In the next section we will answer one of the biggest questions in DevOps.

> If Docker can create Containers, then why do companies still need Kubernetes?
---

# 1.10 Why Kubernetes Was Invented

By now, we have learned the following journey.

```

Physical Server

↓

Virtual Machine

↓

Container

```

Containers solved many infrastructure problems.

Applications became lightweight.

Deployments became faster.

Resource utilization improved.

Companies quickly adopted Docker.

However, another challenge appeared.

---

# The New Problem

Imagine ShopKart has become one of the largest e-commerce companies.

Instead of 5 applications,

it now has 500 microservices.

```

Login

Cart

Order

Payment

Inventory

Shipping

Notification

Coupon

Search

Analytics

Recommendation

Review

Support

...

500 Containers

```

Every application is running inside its own Docker Container.

Now imagine one container crashes.

Who will restart it?

---

# Daily Production Problems

Suppose the following containers are running.

```

Login Container

Running

-------------------

Payment Container

Running

-------------------

Order Container

Running

-------------------

Inventory Container

Running

-------------------

Notification Container

Running

```

Everything is working.

Suddenly,

```

Payment Container

↓

CRASHED

```

Questions.

- Who detects the failure?
- Who restarts the container?
- Who informs the DevOps Team?
- Who ensures customers can still make payments?

Docker does **not** automatically manage production at this scale.

---

# Another Problem

Today,

ShopKart receives

```

10,000 Users

↓

5 Containers
```

Tomorrow,

during Diwali Sale,

the traffic becomes

```

20,00,000 Users
```

Can one container handle this traffic?

No.

The company must create more containers.

Example.

```

Payment

↓

Container 1

Container 2

Container 3

Container 4

Container 5

Container 6

```

Now another question appears.

How will user requests be distributed?

---

# Another Real Production Problem

Suppose one Physical Server crashes.

```

Server 1

↓

50 Containers

↓

Server Failure
```

Result.

All 50 Containers stop.

Entire application becomes unavailable.

Business loss.

Customer complaints.

Revenue loss.

---

# Rolling Update Problem

Suppose developers release Version 2.

Current Production

```

Payment v1
```

New Version

```

Payment v2
```

Question.

Can we stop Version 1 immediately?

No.

Thousands of users are making payments.

The update must happen without downtime.

This is called

**Rolling Update.**

Docker alone cannot perform this efficiently.

---

# Scaling Problem

Morning

```

2 Containers
```

Afternoon

```

8 Containers
```

Night

```

3 Containers
```

Containers must automatically increase and decrease according to traffic.

This is called

**Auto Scaling.**

Docker alone cannot manage this.

---

# Self-Healing Problem

Suppose a container crashes.

```

Container

↓

Application Crash

↓

Stopped
```

Someone must restart it automatically.

This feature is called

**Self-Healing.**

Docker does not provide complete orchestration for this.

---

# Container Scheduling

Suppose the company has

```

20 Physical Servers
```

and

```

1000 Containers
```

Question.

On which server should each container run?

Example.

```

Server 1

↓

Login

Cart

Search

----------------

Server 2

↓

Payment

Order

Inventory

----------------

Server 3

↓

Notification

Analytics

Review

```

Someone must decide the placement.

This process is called

**Scheduling.**

---

# Kubernetes Solves These Problems

Kubernetes automatically performs:

- Container Scheduling
- Auto Scaling
- Self-Healing
- Rolling Updates
- Rollback
- Load Balancing
- Service Discovery
- Health Checks

This makes Kubernetes the operating platform for containers.

---

# Simple Analogy

Docker is like manufacturing cars.

Kubernetes is like managing an entire city's traffic system.

Docker creates containers.

Kubernetes manages thousands of containers.

---

# Complete Evolution

```

Physical Server

↓

Virtual Machine

↓

Docker Container

↓

Kubernetes Cluster

```

Every technology solved a problem that the previous technology could not solve efficiently.

---

# Interview Questions

## Q1 Why was Kubernetes created?

Kubernetes was created to manage containers at scale.

---

## Q2 Can Docker replace Kubernetes?

No.

Docker creates and runs containers.

Kubernetes manages containers across multiple servers.

---

## Q3 What is Container Orchestration?

Container Orchestration is the automated management of containers, including deployment, scaling, networking, monitoring and recovery.

---

## Q4 Name some Kubernetes features.

- Auto Scaling
- Self-Healing
- Rolling Updates
- Rollback
- Scheduling
- Service Discovery
- Load Balancing

---

# Summary

In this section we learned:

- Why Docker alone is not enough.
- Production challenges of container management.
- Why Kubernetes was introduced.
- What problems Kubernetes solves.
- The evolution from Physical Servers to Kubernetes.

---

# Next Section

## 1.11 The Complete DevOps Workflow

In the next section, we will connect everything together and understand the complete journey:

```

Developer

↓

Git

↓

GitHub

↓

Jenkins

↓

Docker

↓

Docker Registry

↓

Kubernetes

↓

AWS

↓

Customer

```

After this section, the complete DevOps workflow will become clear.
---

# 1.11 The Complete DevOps Workflow

Until now we have learned the following technologies individually.

```
Physical Server

↓

Virtual Machine

↓

Container

↓

Kubernetes
```

Now let us connect everything together.

This is the complete journey of an application inside a real software company.

---

# Step 1 – Business Requirement

Every software project starts with a business requirement.

Example.

```
Customer Requirement

↓

ShopKart wants Online Payment
```

Management approves the requirement.

The Project Manager creates user stories.

The work is assigned to the Development Team.

---

# Step 2 – Development

The developer starts writing source code.

Example

```
PaymentService.java

CartService.java

OrderService.java
```

The code is tested locally.

If everything works correctly,

the developer commits the code.

---

# Step 3 – Git

The developer saves source code into Git.

```
Developer Laptop

↓

git add

↓

git commit
```

Git maintains the complete version history.

Developers can safely modify the project without losing previous versions.

---

# Step 4 – GitHub

The developer pushes the code to GitHub.

```
Developer

↓

Git

↓

GitHub Repository
```

GitHub becomes the central repository.

Every developer works from the same repository.

---

# Step 5 – Jenkins

Jenkins continuously monitors GitHub.

Whenever new code is pushed,

Jenkins automatically starts the pipeline.

Typical Jenkins pipeline:

```
GitHub

↓

Download Source Code

↓

Compile

↓

Run Unit Tests

↓

Create Build

↓

Create Docker Image

↓

Push Docker Image

↓

Deploy
```

This process is called Continuous Integration (CI).

---

# Step 6 – Docker

After a successful build,

Docker packages the application.

```
Application

↓

Dockerfile

↓

Docker Build

↓

Docker Image
```

The Docker Image contains:

- Application
- Runtime
- Libraries
- Dependencies

This image can run on any Docker-enabled server.

---

# Step 7 – Docker Registry

The Docker Image is uploaded to a registry.

Example:

```
Docker Hub

Amazon ECR

Harbor

GitHub Container Registry
```

```
Docker Image

↓

Registry
```

The registry stores application images securely.

---

# Step 8 – Kubernetes

Kubernetes downloads the Docker Image from the Registry.

```
Docker Registry

↓

Kubernetes Cluster

↓

Pod

↓

Container
```

If more users arrive,

Kubernetes automatically creates additional Pods.

If a Pod crashes,

Kubernetes creates a new Pod automatically.

---

# Step 9 – Production

The application is now available for customers.

```
Customer

↓

Internet

↓

Load Balancer

↓

Kubernetes

↓

Application

↓

Database
```

Customers do not know that hundreds of servers and containers are working behind the scenes.

They simply use the application.

---

# Complete End-to-End Workflow

```
Business Requirement

↓

Developer

↓

Git

↓

GitHub

↓

Jenkins

↓

Build

↓

Docker Image

↓

Docker Registry

↓

Kubernetes

↓

Pod

↓

Container

↓

Application

↓

Customer
```

This is the complete DevOps delivery pipeline used by modern software companies.

---

# Responsibilities of Each Tool

| Tool | Responsibility |
|------|----------------|
| Git | Version Control |
| GitHub | Central Code Repository |
| Jenkins | CI/CD Automation |
| Docker | Create Application Image |
| Docker Registry | Store Images |
| Kubernetes | Deploy and Manage Containers |
| Monitoring | Observe Infrastructure |
| AWS | Provide Cloud Infrastructure |

---

# Example Production Flow

Suppose a developer fixes a payment bug.

```
Developer fixes code

↓

git commit

↓

git push

↓

GitHub

↓

Jenkins Pipeline

↓

Docker Image Created

↓

Docker Registry

↓

Kubernetes Rolling Update

↓

Payment Service Updated

↓

Customers Continue Shopping
```

Notice that customers experience **no downtime** during the update.

This is the power of modern DevOps.

---

# Key Takeaways

- Development starts with a business requirement.
- Git tracks source code.
- GitHub stores source code centrally.
- Jenkins automates build and testing.
- Docker packages applications.
- Docker Registry stores images.
- Kubernetes deploys and manages containers.
- Customers access applications without knowing the complexity behind the infrastructure.

---

# Summary of Chapter 1

In this chapter, we learned:

- Company Infrastructure
- Data Centers
- Physical Servers
- Virtual Machines
- Containers
- Kubernetes
- Complete DevOps Workflow

This chapter provides the foundation required to understand every technology discussed in the remaining chapters.

---

# Next Chapter

# Chapter 2 – Linux

Before deploying applications, every DevOps Engineer must understand Linux because most production servers run Linux operating systems.

In the next chapter, we will learn Linux from a DevOps Engineer's perspective using real production examples.
---

# 1.12 Why DevOps Was Created?

One of the most common interview questions is:

> **Why was DevOps created?**

To answer this question, we must first understand how software was delivered before DevOps existed.

---

# Traditional Software Delivery

Earlier, every department worked independently.

```
Business Team

↓

Development Team

↓

Testing Team

↓

Operations Team

↓

Customer
```

Each team completed its work and passed it to the next team.

There was very little communication between teams.

---

# Real Production Problem

Imagine a banking application.

The Development Team completed a new feature in 30 days.

The application was handed over to the Operations Team.

The Operations Team tried to deploy the application.

Deployment failed.

Reason:

```
Production Server

Java 11

----------------

Application Built Using

Java 21
```

Result:

```
Application Failed to Start
```

The Operations Team informed the Development Team.

The Development Team replied:

> "It works perfectly on my laptop."

This situation became very common.

---

# Another Problem

Developers wanted to release software every week.

Operations Team preferred releasing software once every three months.

Why?

Because every deployment involved risk.

If deployment failed,

the complete production environment could become unavailable.

---

# Common Problems Before DevOps

- Manual Deployment
- Manual Testing
- Manual Backup
- Long Release Cycle
- Human Errors
- Poor Communication
- Environment Differences
- Slow Recovery
- Frequent Production Failures

---

# Example

```
Developer Laptop

↓

Application Works

-------------------

Production Server

↓

Application Fails
```

Both environments were different.

Different Java versions.

Different Libraries.

Different Configuration.

Different Operating Systems.

---

# Business Impact

Every production issue affected the business.

Examples:

- Online Payments Failed
- Orders Could Not Be Placed
- Customers Left the Website
- Revenue Decreased
- Company Reputation Suffered

For companies like Amazon or Flipkart,

even a few minutes of downtime can result in huge financial losses.

---

# The Solution

Companies realized that

Development and Operations must work together.

Instead of separate teams,

they introduced a collaborative culture.

This approach became known as:

# DevOps

---

# What is DevOps?

DevOps is a combination of:

```
Development

+

Operations
```

Its objective is to deliver software:

- Faster
- More Reliably
- More Securely
- With Minimum Manual Work

---

# DevOps Principles

Modern DevOps is based on:

- Collaboration
- Automation
- Continuous Integration
- Continuous Delivery
- Continuous Monitoring
- Continuous Improvement

---

# DevOps Workflow

```
Plan

↓

Develop

↓

Build

↓

Test

↓

Release

↓

Deploy

↓

Monitor

↓

Feedback

↓

Improve
```

This cycle repeats continuously.

---

# Benefits of DevOps

Companies adopting DevOps experience:

- Faster Releases
- Fewer Production Errors
- Better Collaboration
- Reduced Downtime
- Easier Rollback
- Better Customer Satisfaction
- Improved Business Growth

---

# Real Example

Without DevOps:

```
Feature Completed

↓

Deployment After 3 Months
```

With DevOps:

```
Feature Completed

↓

Automatic Build

↓

Automatic Testing

↓

Automatic Deployment

↓

Production Within Minutes
```

---

# Interview Questions

## Q1. What is DevOps?

DevOps is a culture and set of practices that combines Development and Operations to deliver software faster, more reliably and with greater automation.

---

## Q2. Why was DevOps introduced?

To solve communication gaps, manual deployment problems, slow releases and production failures between Development and Operations teams.

---

## Q3. Is DevOps a Tool?

No.

DevOps is a culture supported by tools such as Git, Jenkins, Docker, Kubernetes, Terraform and Ansible.

---

## Key Takeaways

- DevOps was created to solve software delivery problems.
- It improves collaboration between Development and Operations.
- Automation is a core principle of DevOps.
- DevOps focuses on faster and safer software delivery.
- DevOps is a culture, not a single technology.

---

# Next Section

## 1.13 DevOps Life Cycle

In the next section, we will study the complete DevOps Life Cycle and understand where Git, Jenkins, Docker, Kubernetes, Terraform, Ansible and Monitoring fit into the overall workflow.
---

# 1.13 DevOps Life Cycle

Now that we understand why DevOps was introduced, let us understand how a software company continuously develops, tests, deploys and improves an application.

This complete process is called the **DevOps Life Cycle**.

Unlike the traditional model, DevOps is not a one-time activity.

It is a continuous cycle.

Every new feature, bug fix or improvement follows the same workflow.

---

# DevOps Life Cycle Overview

```
Business Requirement

↓

Planning

↓

Development

↓

Version Control

↓

Continuous Integration

↓

Testing

↓

Containerization

↓

Deployment

↓

Monitoring

↓

Feedback

↓

Next Release
```

This cycle repeats throughout the life of the application.

---

# Phase 1 – Planning

Every project starts with a business requirement.

Example:

```
Customers want UPI Payments.
```

The Product Manager creates requirements.

The Project Manager divides them into tasks.

These tasks are assigned to developers.

Popular planning tools include:

- Jira
- Azure Boards
- Trello
- Asana

---

# Phase 2 – Development

Developers write source code.

Example:

```
PaymentService.java

OrderService.java

InventoryService.java
```

They test the application locally before committing the code.

---

# Phase 3 – Version Control

The code is committed into Git.

Example:

```
git add

↓

git commit

↓

git push
```

Git stores every version of the application.

If something goes wrong, previous versions can be restored.

---

# Phase 4 – Continuous Integration (CI)

Once code reaches GitHub,

Jenkins automatically starts the build process.

Typical CI Pipeline:

```
Download Code

↓

Compile

↓

Unit Testing

↓

Code Quality Check

↓

Package Build
```

If any step fails,

the pipeline stops immediately.

Developers fix the issue before deployment.

---

# Phase 5 – Containerization

Once the build is successful,

Docker packages the application.

```
Application

↓

Dockerfile

↓

Docker Build

↓

Docker Image
```

The Docker Image contains everything required to run the application.

---

# Phase 6 – Continuous Deployment (CD)

The Docker Image is deployed into Kubernetes.

```
Docker Registry

↓

Kubernetes Cluster

↓

Pod

↓

Application Running
```

Deployment can be:

- Manual
- Automatic
- Scheduled

---

# Phase 7 – Monitoring

Deployment is not the final step.

The application must be monitored continuously.

Monitoring includes:

- CPU Usage
- Memory Usage
- Disk Usage
- Response Time
- Application Logs
- Error Rate
- Network Traffic

Popular Monitoring Tools:

- Prometheus
- Grafana
- Zabbix
- Nagios
- Datadog

---

# Phase 8 – Feedback

Users report:

- Bugs
- New Features
- Performance Issues

The Development Team receives feedback.

The next development cycle begins.

```
Feedback

↓

Planning

↓

Development

↓

Deployment

↓

Monitoring

↓

Feedback
```

This loop continues throughout the life of the application.

---

# Complete DevOps Life Cycle

```
Business Requirement

↓

Planning

↓

Development

↓

Git

↓

GitHub

↓

Jenkins

↓

Build

↓

Testing

↓

Docker

↓

Docker Registry

↓

Kubernetes

↓

Production

↓

Monitoring

↓

Feedback

↓

Next Release
```

---

# Role of DevOps Engineer in Each Phase

| Phase | DevOps Responsibility |
|--------|-----------------------|
| Planning | Infrastructure Planning |
| Development | Development Environment Support |
| Version Control | Git Repository Management |
| CI | Jenkins Pipeline |
| Containerization | Docker Image Creation |
| Deployment | Kubernetes Deployment |
| Monitoring | Infrastructure & Application Monitoring |
| Feedback | Performance Improvement |

---

# Key Takeaways

- DevOps is a continuous process.
- Automation is present in every phase.
- Monitoring is as important as deployment.
- Feedback drives continuous improvement.
- The life cycle never ends while the application is active.

---

# Interview Questions

### Q1. What are the phases of the DevOps Life Cycle?

Planning, Development, Version Control, Continuous Integration, Testing, Containerization, Continuous Deployment, Monitoring and Feedback.

---

### Q2. What is Continuous Integration?

Continuous Integration is the practice of automatically building and testing code whenever developers push changes to the repository.

---

### Q3. Why is Monitoring important?

Monitoring helps detect failures, performance issues and abnormal behavior before they affect customers.

---

# Chapter Progress

✅ Company Infrastructure

✅ Software Company

✅ Technical Teams

✅ Data Center

✅ Physical Server

✅ Virtual Machine

✅ Containers

✅ Kubernetes

✅ Complete DevOps Workflow

✅ Why DevOps

✅ DevOps Life Cycle

---

# Next Section

## 1.14 DevOps Engineer Roles and Responsibilities

In the next section, we will understand the daily responsibilities of a Production DevOps Engineer and what work is actually performed during a normal working day.
---

# 1.14 DevOps Engineer Roles and Responsibilities

Many beginners think that a DevOps Engineer spends the entire day writing Docker commands or Kubernetes YAML files.

In reality, the work of a DevOps Engineer is much broader.

A DevOps Engineer is responsible for ensuring that software moves safely, quickly and reliably from development to production.

---

# Primary Responsibilities

A Production DevOps Engineer is responsible for:

- Infrastructure Management
- CI/CD Pipeline Management
- Cloud Administration
- Container Platform Management
- Monitoring
- Automation
- Security
- Backup & Recovery
- Incident Response
- Performance Optimization

---

# Daily Activities of a DevOps Engineer

A typical working day may include the following tasks.

### Morning

- Check monitoring dashboards.
- Verify production health.
- Review overnight alerts.
- Check failed pipelines.
- Verify backups.

---

### Development Support

Developers may request:

- New Virtual Machine
- New Kubernetes Namespace
- Database Access
- SSL Certificate
- DNS Entry
- Storage Expansion

The DevOps Engineer provides these resources.

---

### CI/CD Maintenance

Responsibilities include:

- Maintaining Jenkins Pipelines
- Fixing Build Failures
- Managing Git Repositories
- Updating Build Agents
- Managing Credentials

---

### Docker Administration

Daily activities include:

- Building Docker Images
- Updating Base Images
- Removing Unused Images
- Image Security Scanning
- Container Troubleshooting

---

### Kubernetes Administration

Typical responsibilities:

- Deploy Applications
- Scale Pods
- Check Pod Health
- Investigate CrashLoopBackOff
- Rolling Updates
- Rollbacks
- Cluster Maintenance

---

### Cloud Administration

Cloud-related activities include:

- Launch EC2 Instances
- Configure Security Groups
- Manage IAM Users
- Create Load Balancers
- Configure Auto Scaling
- Manage Storage

---

### Infrastructure Monitoring

The DevOps Engineer continuously monitors:

- CPU Usage
- Memory Usage
- Disk Usage
- Application Health
- Database Health
- SSL Certificate Expiry
- Backup Status
- Network Connectivity

---

### Automation

One of the major responsibilities of DevOps Engineers is automation.

Examples include:

- Automated Server Provisioning
- Automated Deployment
- Automated Backup
- Automated Monitoring
- Automated Scaling
- Automated Notifications

Automation reduces manual work and minimizes human errors.

---

# Production Incident Example

Suppose the monitoring system generates the following alert.

```
ALERT

Payment Service

Status : DOWN
```

The DevOps Engineer immediately investigates.

Possible reasons:

- Application Crash
- Server Failure
- Database Issue
- Network Failure
- Disk Full
- Memory Exhausted

The engineer identifies the root cause and restores the service.

The objective is to minimize downtime.

---

# Skills Required

A Production DevOps Engineer should understand:

- Linux
- Networking
- Git
- GitHub
- Jenkins
- Docker
- Kubernetes
- AWS
- Terraform
- Ansible
- Monitoring
- Bash Scripting
- Security Fundamentals

---

# Soft Skills

Technical knowledge alone is not enough.

A DevOps Engineer should also possess:

- Problem Solving
- Communication
- Documentation
- Time Management
- Team Collaboration
- Incident Handling

---

# Example Daily Workflow

```
09:00

↓

Check Monitoring

↓

Review Alerts

↓

Resolve Production Issues

↓

Support Developers

↓

Review Pull Requests

↓

Run Jenkins Pipelines

↓

Deploy Applications

↓

Verify Deployment

↓

Monitor Production

↓

End of Day Report
```

---

# DevOps Engineer Mindset

A successful DevOps Engineer always asks:

- Can this process be automated?
- Can downtime be reduced?
- Can deployment become safer?
- Can monitoring improve?
- Can recovery become faster?

Automation and reliability are the core mindset of DevOps.

---

# Interview Questions

### Q1. What does a DevOps Engineer do?

A DevOps Engineer automates software delivery, manages infrastructure, maintains CI/CD pipelines, deploys applications, monitors systems and improves operational reliability.

---

### Q2. Is a DevOps Engineer responsible only for deployment?

No.

Deployment is only one responsibility.

A DevOps Engineer also manages infrastructure, monitoring, automation, cloud services, containers, security and incident response.

---

### Q3. Which skills are mandatory for a DevOps Engineer?

- Linux
- Networking
- Git
- Jenkins
- Docker
- Kubernetes
- Cloud Computing
- Infrastructure Automation
- Monitoring

---

# Key Takeaways

- DevOps is a multidisciplinary role.
- Automation is a major responsibility.
- Monitoring is a continuous activity.
- Production stability is the highest priority.
- DevOps Engineers work closely with Developers, QA, Security and Cloud Teams.

---

# Next Section

## 1.15 Infrastructure Evolution

In the next section, we will study how infrastructure evolved over the last 30 years—from Physical Servers to Virtual Machines, Cloud Computing, Containers and Kubernetes—using a timeline and real industry examples.
---

# 1.15 Evolution of IT Infrastructure

Technology has continuously evolved over the past three decades.

Every new technology was introduced to solve a limitation of the previous one.

Understanding this evolution helps us understand why Linux, Docker, Kubernetes and Cloud Computing became essential.

---

# Stage 1 - Physical Servers (1990s)

Initially, every application was installed on its own dedicated Physical Server.

Example:

```
Payroll

↓

Physical Server

-----------------------

ERP

↓

Physical Server

-----------------------

Email Server

↓

Physical Server
```

## Advantages

- Simple Architecture
- Complete Hardware Control
- Easy Troubleshooting

## Problems

- Expensive Hardware
- Low Resource Utilization
- High Electricity Cost
- Large Data Center Space
- Difficult Maintenance

---

# Stage 2 - Virtualization (2000s)

Companies started using VMware, Hyper-V and KVM.

Instead of purchasing multiple servers,

one Physical Server hosted multiple Virtual Machines.

```
Physical Server

↓

Hypervisor

↓

VM1

VM2

VM3

VM4
```

## Benefits

- Better Resource Utilization
- Lower Cost
- Easier Backup
- Live Migration
- Reduced Hardware Purchase

## Problems

Each VM required its own Operating System.

Memory consumption remained high.

Boot time remained slow.

---

# Stage 3 - Cloud Computing (2006 onwards)

Cloud providers introduced Infrastructure as a Service.

Instead of purchasing servers,

companies rented Virtual Machines.

Examples

- AWS
- Azure
- Google Cloud

```
Company

↓

Cloud Provider

↓

Virtual Machines
```

Benefits

- No Hardware Purchase
- Pay As You Use
- Fast Deployment
- Global Availability

---

# Stage 4 - Containers (2013 onwards)

Docker simplified application packaging.

Instead of packaging the Operating System,

only the application and its dependencies were packaged.

```
Application

↓

Docker Image

↓

Container
```

Benefits

- Lightweight
- Fast Startup
- Portable
- Consistent Environment

---

# Stage 5 - Container Orchestration

As companies started running hundreds of Containers,

manual management became impossible.

Kubernetes solved this challenge.

```
Docker Images

↓

Containers

↓

Kubernetes

↓

Production
```

Benefits

- Self-Healing
- Auto Scaling
- Rolling Updates
- Service Discovery
- High Availability

---

# Stage 6 - Infrastructure as Code (IaC)

Infrastructure also became programmable.

Instead of manually creating servers,

Infrastructure was created using code.

Example

Terraform

```
Terraform Code

↓

AWS Infrastructure

↓

EC2

VPC

Subnets

Security Groups
```

Benefits

- Automation
- Version Control
- Repeatability
- Faster Provisioning

---

# Stage 7 - Configuration Management

Managing hundreds of Linux servers manually became difficult.

Configuration Management tools solved this problem.

Examples

- Ansible
- Puppet
- Chef

```
Ansible Playbook

↓

100 Linux Servers

↓

Automatic Configuration
```

---

# Stage 8 - Monitoring & Observability

Deployment is not the final step.

Modern infrastructure requires continuous monitoring.

Examples

- Prometheus
- Grafana
- ELK Stack
- Datadog

Monitoring tracks:

- CPU
- Memory
- Disk
- Network
- Logs
- Application Health

---

# Infrastructure Evolution Timeline

```
1990

↓

Physical Servers

↓

2000

↓

Virtual Machines

↓

2006

↓

Cloud Computing

↓

2013

↓

Docker Containers

↓

2015

↓

Kubernetes

↓

2016

↓

Terraform

↓

2017

↓

Ansible

↓

Today

↓

Cloud Native Infrastructure
```

---

# Why This Evolution Matters

Every technology solved a real business problem.

| Technology | Problem Solved |
|------------|----------------|
| Physical Server | Dedicated Computing |
| Virtual Machine | Hardware Utilization |
| Cloud | Hardware Cost |
| Docker | Environment Consistency |
| Kubernetes | Container Management |
| Terraform | Infrastructure Automation |
| Ansible | Server Configuration |
| Monitoring | Production Visibility |

---

# Chapter Summary

In this chapter, we built the foundation of DevOps.

We learned:

- Software Company Structure
- Company Infrastructure
- Data Center
- Physical Servers
- Virtual Machines
- Containers
- Kubernetes
- Complete DevOps Workflow
- DevOps Culture
- DevOps Life Cycle
- DevOps Engineer Responsibilities
- Evolution of Infrastructure

This chapter provides the conceptual foundation required before learning Linux, Networking, Git, Docker and Kubernetes.

---

# What's Next?

# Chapter 2 - Linux

In the next chapter, we will enter a Linux Production Server and learn Linux exactly as a DevOps Engineer uses it in real companies.

We will start from the Linux file system and gradually move towards user management, permissions, services, processes, networking, storage and shell scripting.
---

# 1.16 Case Study – Building ShopKart from Scratch

Until now we have studied individual concepts.

Now let us combine everything using one complete production example.

Suppose a company named **ShopKart Pvt. Ltd.** wants to launch a new E-Commerce platform.

The management announces the project.

The target is:

- 1 Million Users
- Android App
- iOS App
- Website
- 99.99% Availability

The first question is:

> **Where will this application run?**

The answer is:

**Infrastructure must be prepared first.**

---

# Step 1 – Infrastructure Planning

The Infrastructure Team prepares the architecture.

```
Internet

↓

Firewall

↓

Load Balancer

↓

Application Servers

↓

Database Server

↓

Storage

↓

Backup Server

↓

Monitoring Server
```

At this stage no application exists.

Only infrastructure planning is completed.

---

# Step 2 – Cloud Infrastructure

The company decides to use AWS.

Resources created:

- VPC
- Public Subnet
- Private Subnet
- Internet Gateway
- NAT Gateway
- Route Table
- Security Groups
- EC2 Instances

Now the infrastructure is ready.

---

# Step 3 – Linux Installation

Ubuntu Server LTS is installed on every EC2 instance.

Example:

```
Server 1

Ubuntu

--------------------

Server 2

Ubuntu

--------------------

Server 3

Ubuntu
```

The servers are updated.

SSH access is configured.

Firewall rules are applied.

---

# Step 4 – Git Repository

Developers begin writing source code.

```
Developer Laptop

↓

Git

↓

GitHub Repository
```

Every code change is pushed to GitHub.

---

# Step 5 – Jenkins Pipeline

Jenkins continuously watches GitHub.

Whenever new code is pushed,

Jenkins automatically starts:

```
Download Code

↓

Compile

↓

Unit Testing

↓

Package Build

↓

Docker Build

↓

Push Image
```

No manual intervention is required.

---

# Step 6 – Docker Image

Jenkins creates a Docker Image.

Example:

```
shopkart/payment:v1.0
```

The image contains:

- Application
- Java Runtime
- Libraries
- Configuration

The image is identical everywhere.

---

# Step 7 – Docker Registry

The Docker Image is uploaded.

Example:

```
Amazon ECR

or

Docker Hub
```

Every deployment uses this image.

No source code is copied directly to production.

---

# Step 8 – Kubernetes Deployment

The Kubernetes Cluster downloads the image.

```
Docker Registry

↓

Kubernetes

↓

Deployment

↓

ReplicaSet

↓

Pods
```

The application starts running.

---

# Step 9 – Production Traffic

Customers access the application.

```
Customer

↓

Internet

↓

Load Balancer

↓

Kubernetes

↓

Pods

↓

Database
```

Everything works automatically.

---

# Step 10 – Monitoring

Monitoring tools continuously observe:

- CPU
- Memory
- Pod Health
- Node Health
- Network
- Storage
- Database
- Application Logs

If any problem occurs,

the DevOps Team receives an alert immediately.

---

# Example Production Incident

Suppose the Payment Service crashes.

```
Payment Pod

↓

Crash
```

Kubernetes detects the failure.

Immediately,

```
Old Pod

↓

Terminated

↓

New Pod Created

↓

Application Running
```

Customers continue using the website.

This process is called:

**Self-Healing.**

---

# Example Traffic Spike

Diwali Sale begins.

Traffic increases from

```
10,000 Users

↓

5,00,000 Users
```

Kubernetes automatically increases the number of Pods.

```
Before

Payment Pod ×2

↓

After

Payment Pod ×10
```

This process is called:

**Auto Scaling.**

---

# Example Software Update

Developers release Version 2.

```
Version 1

↓

Version 2
```

Kubernetes updates Pods one by one.

```
Pod 1

↓

Updated

↓

Pod 2

↓

Updated

↓

Pod 3

↓

Updated
```

Customers never notice the deployment.

This process is called:

**Rolling Update.**

---

# Complete Production Workflow

```
Business Requirement

↓

Infrastructure Team

↓

AWS

↓

Linux

↓

Developer

↓

Git

↓

GitHub

↓

Jenkins

↓

Docker

↓

Docker Registry

↓

Kubernetes

↓

Pods

↓

Application

↓

Monitoring

↓

Customer
```

---

# Important Learning

You have now reached the most important understanding of this chapter.

A DevOps Engineer does **not** start with Docker or Kubernetes.

A DevOps Engineer starts with **understanding the complete production infrastructure**.

Once the infrastructure is understood, every tool naturally fits into its correct place.

This is the mindset required to become a Production DevOps Engineer.
---

# 1.17 Production Environment vs Development Environment

One of the biggest mistakes beginners make is assuming that the application running on a developer's laptop is the same as the application running in production.

In reality, these environments are completely different.

Understanding this difference is one of the most important responsibilities of a DevOps Engineer.

---

# Development Environment

This environment is used by developers.

Typical characteristics:

- Personal Laptop or Desktop
- Visual Studio Code / IntelliJ IDEA
- Local Database
- Debugging Enabled
- Test Data
- Frequent Code Changes

Example:

```
Developer Laptop

↓

Ubuntu / Windows

↓

Java

↓

VS Code

↓

Application

↓

Local MySQL
```

The objective is fast development.

---

# Testing Environment

After development, the application is deployed to the Testing Environment.

Purpose:

- Verify new features
- Execute QA Test Cases
- Perform Integration Testing
- Validate Bug Fixes

Example:

```
GitHub

↓

Jenkins

↓

Test Server

↓

QA Team
```

Customers never access this environment.

---

# Staging Environment

The Staging Environment is an exact copy of Production.

Everything is configured exactly like Production.

Examples:

- Same Operating System
- Same Java Version
- Same Database Version
- Same Kubernetes Version
- Same Network Configuration

Purpose:

- Final Verification
- User Acceptance Testing (UAT)
- Release Approval

---

# Production Environment

Production is the environment used by real customers.

Example:

```
Customer

↓

Internet

↓

Load Balancer

↓

Kubernetes

↓

Application

↓

Database
```

Any failure here directly affects the business.

Therefore, Production changes are carefully controlled.

---

# Environment Comparison

| Environment | Used By | Purpose |
|-------------|----------|---------|
| Development | Developers | Write Code |
| Testing | QA Team | Test Features |
| Staging | Business & QA | Final Validation |
| Production | Customers | Live Application |

---

# Why Multiple Environments?

Suppose a developer accidentally introduces a bug.

If the application is deployed directly to Production,

customers may experience failures.

Instead, the application passes through:

```
Development

↓

Testing

↓

Staging

↓

Production
```

Errors are identified before customers are affected.

---

# Example Deployment Flow

```
Developer

↓

Git Commit

↓

GitHub

↓

Jenkins

↓

Testing Environment

↓

QA Approval

↓

Staging Environment

↓

Business Approval

↓

Production Deployment
```

This controlled release process minimizes production risk.

---

# Role of DevOps Engineer

The DevOps Engineer is responsible for maintaining all environments.

Typical responsibilities include:

- Provision Servers
- Configure Operating Systems
- Deploy Applications
- Manage Kubernetes Clusters
- Configure Networking
- Maintain CI/CD Pipelines
- Monitor Environment Health

---

# Production Rules

Production environments follow strict operational rules.

Examples:

- No direct code changes.
- No manual database modifications without approval.
- Every deployment is logged.
- Every deployment is reversible.
- Every server is monitored continuously.

---

# Key Takeaways

- Development is for coding.
- Testing is for verification.
- Staging is for final validation.
- Production is for real users.
- A DevOps Engineer manages the movement of applications across all environments.

---

# Next Section

## 1.18 Chapter Review & Infrastructure Checklist

In the next section, we will summarize the entire chapter and create an Infrastructure Checklist that every DevOps Engineer should understand before moving to Linux.
---

# 1.18 Chapter Review & Infrastructure Checklist

Congratulations!

You have completed the first and most important chapter of this handbook.

Before moving to Linux, let us review everything we learned.

This review will help you connect every concept into one complete picture.

---

# Complete Infrastructure Flow

```
Business Requirement

↓

Infrastructure Planning

↓

Cloud / Data Center

↓

Physical Server

↓

Virtual Machine

↓

Linux Operating System

↓

Application

↓

Git

↓

GitHub

↓

Jenkins

↓

Docker

↓

Docker Registry

↓

Kubernetes

↓

Monitoring

↓

Customer
```

Every technology exists for a reason.

Nothing is used without solving a business problem.

---

# What Happens Inside a Real Company?

Suppose a customer opens:

```
https://www.shopkart.com
```

The request follows this path.

```
Customer

↓

Internet

↓

DNS

↓

Firewall

↓

Load Balancer

↓

Kubernetes Cluster

↓

Pod

↓

Container

↓

Application

↓

Database

↓

Response Returned
```

This entire process usually completes within a few milliseconds.

---

# Infrastructure Checklist

Before deploying any application, verify the following.

## Infrastructure

- Server Available
- CPU Capacity
- RAM Capacity
- Storage Available
- Network Connectivity
- Internet Access
- DNS Configured

---

## Operating System

- Linux Installed
- Packages Updated
- Firewall Configured
- SSH Enabled
- Required Users Created

---

## Application

- Source Code Available
- Dependencies Installed
- Configuration Verified
- Environment Variables Configured

---

## Version Control

- Git Repository Created
- Branch Strategy Defined
- Repository Access Configured

---

## CI/CD

- Jenkins Installed
- Pipeline Created
- Credentials Configured
- Build Successful

---

## Docker

- Docker Installed
- Dockerfile Created
- Image Built Successfully
- Image Tested

---

## Registry

- Docker Image Pushed
- Image Version Tagged
- Registry Access Verified

---

## Kubernetes

- Cluster Healthy
- Nodes Ready
- Deployment Created
- Service Created
- Ingress Configured
- Pods Running

---

## Monitoring

- Prometheus Configured
- Grafana Dashboard Ready
- Alerts Configured
- Log Collection Enabled

---

# Common Beginner Mistakes

Many beginners think:

```
Install Docker

↓

Learn Kubernetes

↓

Become DevOps Engineer
```

This approach creates confusion.

The correct learning path is:

```
Infrastructure

↓

Linux

↓

Networking

↓

Git

↓

GitHub

↓

Jenkins

↓

Docker

↓

Kubernetes

↓

AWS

↓

Terraform

↓

Ansible

↓

Monitoring
```

Every chapter in this handbook follows this sequence.

---

# Knowledge Check

You should now be able to answer the following questions.

- What is Infrastructure?
- What is a Data Center?
- What is a Physical Server?
- What is a Virtual Machine?
- Why was Virtualization introduced?
- Why were Containers invented?
- Why do companies use Docker?
- Why do companies use Kubernetes?
- What is the role of Jenkins?
- What is the responsibility of a DevOps Engineer?
- What is the DevOps Life Cycle?
- How does an application reach Production?

If you can confidently answer these questions, you are ready to move to Linux.

---

# Chapter Conclusion

This chapter established the foundation of the entire DevOps ecosystem.

In the next chapter, we will step inside a Linux production server.

Every DevOps Engineer spends a significant portion of the day working on Linux systems.

Understanding Linux is therefore the first technical skill required before learning Git, Jenkins, Docker, Kubernetes and Cloud technologies.

The next chapter focuses on Linux from a DevOps Engineer's perspective—not from a system administration textbook.

You will learn:

- Linux File System
- File Management
- Users and Groups
- Permissions
- Processes
- Services
- Networking
- Package Management
- Storage
- Logs
- Shell Scripting

Everything will be explained using real production examples.

---

# End of Chapter 1