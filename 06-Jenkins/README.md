# Chapter 7 – Jenkins (CI/CD)

In the next chapter, we will learn:

- Introduction to Jenkins
- Continuous Integration (CI)
- Continuous Delivery (CD)
- Continuous Deployment
- Jenkins Architecture
- Installing Jenkins
- Jenkins Dashboard
- Jobs & Pipelines
- Declarative Pipeline
- Scripted Pipeline
- Jenkinsfile
- Integrating Git & Docker
- Build Automation
- Production CI/CD
- Best Practices
- Interview Questions
# Chapter 7 – Jenkins (CI/CD)

---

# Chapter Overview

Welcome to **Chapter 7**.

So far, you have learned:

- Linux
- Networking
- Git & GitHub
- AWS Basics
- Nginx
- Docker

Now it's time to learn the heart of modern DevOps—

# Jenkins

Jenkins is one of the world's most popular **Continuous Integration and Continuous Delivery (CI/CD)** tools.

Almost every software company automates application builds, testing and deployments using CI/CD pipelines.

Jenkins helps achieve that automation.

---

# Why Learn Jenkins?

Imagine a development team with:

- 20 Developers
- 100 Code Commits Every Day
- Multiple Applications
- Frequent Releases

Without automation,

developers would manually:

- Download Code
- Compile Code
- Run Tests
- Package Application
- Deploy Application

This process is slow and error-prone.

Jenkins automates the entire workflow.

---

# Learning Objectives

After completing this chapter, you will be able to:

- Understand CI/CD
- Install Jenkins
- Configure Jenkins
- Create Jobs
- Create Pipelines
- Write Jenkinsfiles
- Integrate GitHub
- Integrate Docker
- Build Java Applications
- Deploy Applications
- Configure Agents
- Secure Jenkins
- Troubleshoot Jenkins
- Implement Production CI/CD Pipelines

---

# Chapter Roadmap

This chapter contains the following sections.

```
7.1 Introduction to Jenkins

7.2 What is CI/CD?

7.3 Why Jenkins?

7.4 Jenkins Architecture

7.5 Installing Jenkins

7.6 Jenkins Dashboard

7.7 Jenkins Jobs

7.8 Jenkins Pipelines

7.9 Jenkinsfile

7.10 Git Integration

7.11 Docker Integration

7.12 Build Automation

7.13 Jenkins Agents

7.14 Plugins

7.15 Credentials Management

7.16 Jenkins Security

7.17 Jenkins Best Practices

7.18 Jenkins in Production

7.19 Chapter Summary
```

---

# Prerequisites

Before learning Jenkins,

you should understand:

- Linux Commands
- Git
- GitHub
- Docker
- Basic Networking
- Java (Basic Knowledge)

If you completed the previous chapters,

you are ready.

---

# Lab Environment

Operating System

- Ubuntu 24.04 LTS
- Rocky Linux 9
- Amazon Linux 2023

Cloud Platform

- AWS EC2

Software

- Java 21
- Jenkins LTS
- Git
- Docker

---

# Learning Approach

Each topic follows this structure:

```
Concept

↓

Visualization

↓

Hands-on Practical

↓

Production Example

↓

Interview Questions

↓

Best Practices
```

This approach ensures that you understand both theory and practical implementation.

---

# Real DevOps Scenario

A developer pushes code to GitHub.

Without Jenkins:

```
Developer

↓

Manual Build

↓

Manual Test

↓

Manual Deployment

↓

Production
```

With Jenkins:

```
Developer

↓

Git Push

↓

Jenkins

↓

Automatic Build

↓

Automatic Test

↓

Automatic Deployment
```

Everything happens automatically.

---

# What You Will Build

During this chapter,

you will create:

- Jenkins Jobs
- Freestyle Projects
- Pipelines
- Jenkinsfiles
- GitHub Integration
- Docker Builds
- CI/CD Pipelines

By the end,

you will build a complete automated software delivery pipeline.

---

# Production Focus

Every section includes:

✔ Real-world Examples

✔ Architecture Diagrams

✔ Practical Commands

✔ Best Practices

✔ Common Mistakes

✔ Interview Questions

---

# Skills You Will Gain

After this chapter,

you will understand how professional DevOps Engineers:

- Automate Builds
- Run Automated Tests
- Package Applications
- Build Docker Images
- Deploy Applications
- Monitor Pipelines
- Troubleshoot Build Failures

These are essential skills for modern DevOps roles.

---

# Next Section

## 7.1 Introduction to Jenkins

In the next section, we will learn:

- What is Jenkins?
- History of Jenkins
- Why Jenkins was Created
- Jenkins Features
- Jenkins Ecosystem
- Real Production Examples
- Interview Questions
---

# 7.2 What is CI/CD?

Before learning Jenkins,

you must understand the most important concept in DevOps:

# CI/CD

Jenkins was built primarily to automate CI/CD.

If you understand CI/CD,

learning Jenkins becomes much easier.

---

# What is CI?

CI stands for

# Continuous Integration

Continuous Integration is the practice of **frequently merging code changes into a shared repository**.

Every code change is automatically:

- Downloaded
- Built
- Tested
- Verified

before being merged into the main branch.

---

# Simple Definition

```
Developer

↓

Code Commit

↓

Git

↓

Jenkins

↓

Build

↓

Test

↓

Feedback
```

This process happens continuously.

---

# Why Continuous Integration?

Imagine five developers working on the same application.

```
Developer A

Developer B

Developer C

Developer D

Developer E
```

Each developer changes different parts of the code.

Without CI,

all code is merged after several days.

Problems appear:

- Build Failure
- Merge Conflicts
- Hidden Bugs
- Deployment Delays

---

# With Continuous Integration

Every commit automatically triggers:

```
Git Push

↓

Jenkins

↓

Compile

↓

Run Tests

↓

Report Results
```

Problems are detected immediately.

---

# Benefits of CI

✔ Early Bug Detection

✔ Faster Feedback

✔ Better Code Quality

✔ Fewer Merge Conflicts

✔ Faster Development

✔ Stable Main Branch

---

# What is Continuous Delivery?

CD also stands for

# Continuous Delivery

After CI succeeds,

the application is automatically prepared for deployment.

Workflow

```
Build

↓

Test

↓

Package

↓

Deploy to Staging

↓

Ready for Production
```

A human still decides **when** to release to production.

---

# Continuous Delivery Example

```
Developer

↓

Git Push

↓

Jenkins

↓

Build

↓

Tests

↓

Docker Image

↓

Deploy to Staging

↓

Manual Approval

↓

Production
```

Production deployment requires approval.

---

# What is Continuous Deployment?

Continuous Deployment goes one step further.

If every automated check passes,

deployment to production happens automatically.

```
Git Push

↓

Build

↓

Tests

↓

Production
```

No manual approval is required.

---

# Continuous Deployment Example

```
Developer

↓

Git Push

↓

Jenkins

↓

Build

↓

Tests

↓

Docker Build

↓

Deploy Production

↓

Users
```

Everything is automated.

---

# CI vs Continuous Delivery vs Continuous Deployment

| Continuous Integration | Continuous Delivery | Continuous Deployment |
|------------------------|---------------------|-----------------------|
| Build & Test Code | Prepare for Release | Automatically Release |
| Frequent Code Integration | Manual Approval Before Production | No Manual Approval |
| Developer Focus | Release Readiness | Full Automation |

---

# CI/CD Pipeline

A pipeline is a sequence of automated steps.

```
Code

↓

Build

↓

Unit Tests

↓

Integration Tests

↓

Package

↓

Docker Build

↓

Push Registry

↓

Deploy

↓

Monitoring
```

Each stage runs automatically.

---

# Typical CI/CD Workflow

```
Developer

↓

Git Commit

↓

Git Push

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Checkout Code

↓

Compile

↓

Run Tests

↓

Create Artifact

↓

Docker Build

↓

Push Registry

↓

Deploy

↓

Users
```

---

# Build Stage

Jenkins downloads source code.

Example

```bash
git clone https://github.com/company/project.git
```

---

# Test Stage

Automated tests execute.

Examples

- Unit Tests
- Integration Tests
- API Tests

If tests fail,

the pipeline stops.

---

# Package Stage

Application is packaged.

Examples

```
JAR

WAR

ZIP

Docker Image
```

Artifacts are generated for deployment.

---

# Deploy Stage

Deployment targets may include:

- Development
- QA
- Staging
- Production

Deployment should be automated and repeatable.

---

# Feedback Stage

After every build,

Jenkins can send notifications.

Examples

- Email
- Slack
- Microsoft Teams
- Discord

Developers receive immediate feedback.

---

# Pipeline Visualization

```
Developer

↓

Commit

↓

Build

↓

Test

↓

Package

↓

Deploy

↓

Success
```

or

```
Developer

↓

Commit

↓

Test Failed

↓

Fix Code

↓

Commit Again
```

Fast feedback shortens development cycles.

---

# Why CI/CD is Important?

Without CI/CD

```
Manual Build

↓

Manual Test

↓

Manual Deployment

↓

Manual Verification
```

Slow,

repetitive,

and error-prone.

---

With CI/CD

```
Automatic Build

↓

Automatic Test

↓

Automatic Deployment

↓

Automatic Notifications
```

Faster and more reliable.

---

# Real Production Example

An online banking application receives hundreds of commits daily.

```
Developers

↓

GitHub

↓

Jenkins

↓

Tests

↓

Docker

↓

Kubernetes

↓

Production
```

The release process remains consistent regardless of the number of commits.

---

# Advantages of CI/CD

✔ Faster Releases

✔ Higher Quality

✔ Early Bug Detection

✔ Reduced Manual Work

✔ Consistent Deployments

✔ Better Collaboration

✔ Improved Customer Satisfaction

✔ Faster Recovery from Failures

---

# Challenges

CI/CD also requires:

- Good Test Coverage
- Reliable Infrastructure
- Secure Credential Management
- Pipeline Maintenance
- Monitoring

Automation should be trusted, but also continuously improved.

---

# CI/CD Tools

Popular tools include:

- Jenkins
- GitHub Actions
- GitLab CI/CD
- Azure DevOps
- CircleCI
- Bamboo
- TeamCity

Each tool supports CI/CD automation.

---

# Common Beginner Mistakes

### Mistake 1

Thinking CI and CD are the same.

CI focuses on integrating and validating code.

CD focuses on preparing or deploying releases.

---

### Mistake 2

Deploying without automated testing.

Every pipeline should include meaningful tests.

---

### Mistake 3

Running manual deployments while claiming to have CI/CD.

Automation is a key characteristic of CI/CD.

---

### Mistake 4

Ignoring failed pipeline stages.

Every failed build should be investigated promptly.

---

### Mistake 5

Skipping staging environments.

Production deployments should be validated whenever appropriate.

---

# Interview Questions

### Q1. What is Continuous Integration?

Continuous Integration is the practice of frequently integrating code changes and automatically building and testing them.

---

### Q2. What is Continuous Delivery?

Continuous Delivery automatically prepares software for release, with production deployment typically requiring manual approval.

---

### Q3. What is Continuous Deployment?

Continuous Deployment automatically deploys successful changes to production without manual approval.

---

### Q4. What is a CI/CD Pipeline?

A CI/CD Pipeline is a sequence of automated stages that build, test, package and deploy software.

---

### Q5. Why is CI important?

CI detects issues early, reduces integration problems and improves software quality.

---

### Q6. Name five popular CI/CD tools.

- Jenkins
- GitHub Actions
- GitLab CI/CD
- Azure DevOps
- CircleCI

---

# Production Best Practices

✔ Commit code frequently.

✔ Automate builds.

✔ Automate testing.

✔ Keep pipelines fast.

✔ Use staging environments.

✔ Secure credentials.

✔ Monitor pipeline health.

✔ Treat pipeline definitions as code.

---

# Key Takeaways

- CI continuously integrates and validates code changes.
- Continuous Delivery prepares applications for reliable release.
- Continuous Deployment automates production releases.
- Jenkins is one of the most widely used tools for implementing CI/CD.
- Well-designed CI/CD pipelines improve software quality, speed and reliability.

---

# Next Section

## 7.3 Why Jenkins?

In the next section, we will learn:

- Why Jenkins is Popular
- Problems Jenkins Solves
- Jenkins vs Manual Process
- Jenkins vs Other CI/CD Tools
- Enterprise Use Cases
- Best Practices
- Interview Questions
---

# 7.3 Why Jenkins?

Now that you understand **CI/CD**,

the next question is:

> **Why do companies choose Jenkins?**

Today,

there are many CI/CD tools available.

Examples include:

- GitHub Actions
- GitLab CI/CD
- Azure DevOps
- CircleCI
- TeamCity

Yet,

thousands of companies still use Jenkins.

Let's understand why.

---

# The Problem Before Jenkins

Imagine a company with

- 30 Developers
- 5 Projects
- Hundreds of Code Commits

Every code change requires:

```
Download Code

↓

Compile

↓

Run Tests

↓

Package

↓

Deploy
```

If all of this is done manually,

the team wastes hours every day.

---

# Manual Software Delivery

Without Jenkins

```
Developer

↓

Git Pull

↓

Compile

↓

Run Tests

↓

Fix Errors

↓

Package

↓

Deploy

↓

Notify Team
```

Every step depends on humans.

Problems include:

- Human Errors
- Missed Steps
- Slow Releases
- Inconsistent Builds

---

# Software Delivery with Jenkins

```
Developer

↓

Git Push

↓

Webhook

↓

Jenkins

↓

Checkout Code

↓

Build

↓

Run Tests

↓

Package

↓

Deploy

↓

Notification
```

Everything happens automatically.

---

# Why Jenkins Became Popular

Jenkins gained popularity because it offers:

✔ Free and Open Source

✔ Easy Installation

✔ Large Plugin Ecosystem

✔ Cross-Platform Support

✔ Strong Community

✔ Flexible Pipelines

✔ Integration with Almost Every DevOps Tool

---

# Jenkins Solves Real Problems

Without Jenkins

```
Manual Build

↓

Manual Testing

↓

Manual Deployment
```

With Jenkins

```
Automatic Build

↓

Automatic Testing

↓

Automatic Deployment
```

Automation saves time and reduces errors.

---

# Problem 1 — Human Errors

Imagine a release engineer forgets to run tests.

```
Developer

↓

Deploy

↓

Production Failure
```

With Jenkins,

tests are executed automatically.

No deployment occurs if tests fail.

---

# Problem 2 — Slow Releases

Manual deployments may take hours.

With Jenkins,

deployments can begin automatically after every successful build.

Release frequency increases significantly.

---

# Problem 3 — Inconsistent Builds

Developer A builds using Java 17.

Developer B builds using Java 21.

Results may differ.

Jenkins uses a standardized build environment,

ensuring consistent builds.

---

# Problem 4 — No Build History

Manual processes often lack proper records.

Jenkins stores:

- Build History
- Console Output
- Test Results
- Build Artifacts
- Execution Time

This simplifies troubleshooting.

---

# Problem 5 — No Automation

Without Jenkins,

engineers repeatedly execute the same commands.

Example

```bash
git pull

mvn clean package

docker build

docker push
```

Jenkins performs these tasks automatically.

---

# Jenkins Workflow

```
Developer

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Build

↓

Test

↓

Docker Build

↓

Push Image

↓

Deploy
```

This workflow is used by many organizations.

---

# Jenkins Saves Time

Manual Process

```
30 Minutes
```

Automated Process

```
5 Minutes
```

Automation reduces repetitive work and accelerates releases.

---

# Jenkins Improves Quality

Every build can automatically execute:

- Unit Tests
- Integration Tests
- Static Code Analysis
- Security Scans

Issues are detected earlier in the development cycle.

---

# Jenkins Integrates Everything

Jenkins supports integrations with:

- Git
- GitHub
- GitLab
- Bitbucket
- Maven
- Gradle
- Docker
- Kubernetes
- SonarQube
- Nexus
- Slack
- AWS
- Azure
- GCP

This flexibility is one of Jenkins' biggest strengths.

---

# Jenkins Plugin Ecosystem

Jenkins has thousands of plugins.

Examples

```
Git Plugin

↓

Docker Plugin

↓

Pipeline Plugin

↓

Maven Plugin

↓

Slack Plugin
```

Plugins allow Jenkins to integrate with many technologies.

---

# Jenkins vs Manual Process

| Manual Process | Jenkins |
|---------------|----------|
| Manual Build | Automated Build |
| Manual Testing | Automated Testing |
| Manual Deployment | Automated Deployment |
| Slow | Fast |
| Error-Prone | Consistent |
| Difficult to Scale | Highly Scalable |

---

# Jenkins vs Other CI/CD Tools

| Feature | Jenkins | GitHub Actions | GitLab CI/CD |
|----------|----------|----------------|--------------|
| Open Source | ✔ | Partially (service-based) | Community & Enterprise Editions |
| Self-Hosted | ✔ | ✔ | ✔ |
| Plugin Ecosystem | Excellent | Limited Extensions | Integrated Features |
| Flexibility | Very High | High | High |
| Learning Curve | Moderate | Moderate | Moderate |

Each tool has strengths.

The right choice depends on organizational requirements.

---

# Real Production Example

A software company has:

```
100 Developers

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
```

Every code commit automatically:

- Builds the application
- Runs tests
- Creates Docker Images
- Pushes images to the registry
- Deploys to Kubernetes

Developers focus on writing code,

not manual deployment tasks.

---

# Enterprise Use Cases

Jenkins is commonly used for:

- Java Applications
- Python Projects
- Microservices
- Mobile Applications
- Infrastructure Automation
- Database Automation
- Scheduled Maintenance Jobs
- Security Scanning

---

# When Should You Use Jenkins?

Jenkins is a strong choice when you need:

- Highly customizable pipelines
- Self-hosted CI/CD
- Extensive plugin support
- Complex enterprise workflows
- Integration with diverse tools

---

# Common Beginner Mistakes

### Mistake 1

Thinking Jenkins only builds code.

Jenkins can automate almost any repetitive task.

---

### Mistake 2

Installing every available plugin.

Install only the plugins you actually need.

---

### Mistake 3

Running builds manually even after configuring Jenkins.

Automation should be used consistently.

---

### Mistake 4

Ignoring failed builds.

Every failed pipeline should be investigated promptly.

---

### Mistake 5

Using Jenkins without version-controlling pipeline definitions.

Store pipeline configurations as code using `Jenkinsfile`.

---

# Interview Questions

### Q1. Why is Jenkins widely used?

Because it automates software build, testing and deployment while integrating with many DevOps tools.

---

### Q2. What problems does Jenkins solve?

- Manual Builds
- Human Errors
- Slow Releases
- Inconsistent Deployments
- Lack of Automation

---

### Q3. Why does Jenkins have a large ecosystem?

Because of its extensive plugin architecture, which supports integration with many technologies.

---

### Q4. Can Jenkins automate tasks other than software builds?

Yes. Jenkins can automate infrastructure tasks, scheduled jobs, testing, deployments and many other workflows.

---

### Q5. Why do companies still use Jenkins despite newer CI/CD tools?

Because it is highly flexible, mature, extensible and suitable for complex enterprise environments.

---

### Q6. What is one major advantage of Jenkins over manual deployment?

It provides repeatable, automated and consistent software delivery.

---

# Production Best Practices

✔ Automate repetitive tasks.

✔ Keep pipelines version-controlled.

✔ Install only necessary plugins.

✔ Monitor Jenkins performance.

✔ Keep Jenkins updated.

✔ Use build agents for scalability.

✔ Back up Jenkins configuration.

✔ Review pipeline failures promptly.

---

# Key Takeaways

- Jenkins eliminates repetitive manual work.
- Automation improves speed, consistency and software quality.
- Jenkins integrates with nearly every major DevOps tool.
- The plugin ecosystem makes Jenkins highly extensible.
- Jenkins remains a popular choice for enterprise CI/CD due to its flexibility and maturity.

---

# Next Section

## 7.4 Jenkins Architecture

In the next section, we will learn:

- Jenkins Architecture
- Controller (Master)
- Agents (Nodes)
- Executors
- Build Queue
- Workspaces
- Distributed Builds
- Production Architecture
- Best Practices
- Interview Questions
---

# 7.4 Jenkins Architecture

Before installing Jenkins,

you should understand how Jenkins works internally.

Knowing the architecture helps you:

- Design scalable CI/CD systems
- Troubleshoot build failures
- Configure distributed builds
- Optimize performance
- Prepare for DevOps interviews

---

# What is Jenkins Architecture?

Jenkins Architecture defines how different Jenkins components work together to execute automated jobs.

At a high level,

it consists of:

```
Developer

↓

Git Repository

↓

Jenkins Controller

↓

Build Queue

↓

Agents

↓

Build

↓

Artifacts

↓

Deployment
```

---

# Main Components

A Jenkins installation consists of:

- Jenkins Controller
- Jenkins Agents
- Executors
- Build Queue
- Workspace
- Plugins
- Jobs
- Pipelines

Each component has a specific responsibility.

---

# High-Level Architecture

```
               Developer

                    │

                    ▼

              GitHub / GitLab

                    │

                    ▼

           Jenkins Controller

                    │

      ┌─────────────┼─────────────┐

      ▼             ▼             ▼

 Agent-1        Agent-2       Agent-3

      │             │             │

      ▼             ▼             ▼

 Build         Test          Deploy
```

The Controller manages the entire system,

while Agents perform the actual work.

---

# Jenkins Controller (Master)

Earlier versions used the term:

```
Master
```

Modern Jenkins documentation uses:

```
Controller
```

The Controller is the central server.

Responsibilities include:

- Manage Jobs
- Schedule Builds
- Store Configuration
- Install Plugins
- Manage Users
- Communicate with Agents
- Display Dashboard
- Store Build History

Think of it as the "brain" of Jenkins.

---

# Controller Workflow

```
Git Push

↓

Controller Receives Trigger

↓

Schedules Build

↓

Assigns Agent

↓

Collects Results

↓

Displays Build Status
```

---

# Jenkins Agents

Agents are worker machines that execute builds.

They may be:

- Linux Servers
- Windows Servers
- Virtual Machines
- Docker Containers
- Kubernetes Pods

The Controller delegates work to Agents.

---

# Why Agents?

Imagine:

```
500 Builds

↓

One Jenkins Server
```

A single machine becomes overloaded.

Instead,

```
Controller

↓

Agent-1

↓

Agent-2

↓

Agent-3

↓

Agent-4
```

Builds run in parallel.

---

# Distributed Builds

```
Controller

│

├── Java Agent

├── Python Agent

├── Windows Agent

├── Docker Agent

└── Kubernetes Agent
```

Each Agent specializes in a different workload.

---

# Executors

An Executor is a worker thread inside an Agent.

Example

```
Agent

↓

Executor-1

Executor-2

Executor-3
```

Each executor runs one build at a time.

If an agent has:

```
4 Executors
```

it can execute:

```
4 Builds

Simultaneously
```

---

# Build Queue

Suppose:

```
20 Jobs

↓

2 Executors
```

Only two jobs run immediately.

The remaining jobs wait in the Build Queue.

```
Job

↓

Queue

↓

Executor Available

↓

Run
```

---

# Workspace

Every Jenkins Job gets a Workspace.

```
Workspace

↓

Clone Source Code

↓

Compile

↓

Test

↓

Artifacts
```

Typical Linux location:

```
/var/lib/jenkins/workspace/
```

Each job normally has its own workspace.

---

# Build Artifacts

After a successful build,

Jenkins generates artifacts.

Examples

```
JAR

WAR

ZIP

Docker Image
```

Artifacts may be archived,

published,

or deployed.

---

# Jenkins Home Directory

The Jenkins Home directory stores:

- Jobs
- Plugins
- Build History
- Credentials
- Logs
- Configuration
- Users

Default Linux location:

```
/var/lib/jenkins
```

Always back up this directory.

---

# Plugins

Plugins extend Jenkins functionality.

Examples

```
Git Plugin

↓

Pipeline Plugin

↓

Docker Plugin

↓

Maven Plugin

↓

Slack Plugin
```

Plugins integrate Jenkins with external tools.

---

# Job Execution Flow

```
Developer

↓

Git Push

↓

Webhook

↓

Controller

↓

Queue

↓

Agent

↓

Workspace

↓

Build

↓

Test

↓

Artifact

↓

Deploy
```

---

# Communication Between Controller and Agents

The Controller communicates with Agents using secure channels.

Supported connection methods include:

- SSH
- Inbound Agent (JNLP/WebSocket)
- Cloud-based provisioning (such as Kubernetes)

The Controller sends build instructions,

and the Agent returns build results.

---

# Single Node Architecture

Small environments often use one server.

```
Jenkins

↓

Controller

↓

Build

↓

Deploy
```

Simple,

but not highly scalable.

---

# Distributed Architecture

Large companies use distributed Jenkins.

```
Controller

│

├── Linux Agent

├── Windows Agent

├── Docker Agent

├── Test Agent

└── Deployment Agent
```

This architecture supports parallel execution and better scalability.

---

# Cloud Architecture

Modern Jenkins environments may provision Agents dynamically.

```
Developer

↓

GitHub

↓

Jenkins Controller

↓

Kubernetes

↓

Temporary Build Pod

↓

Build Complete

↓

Pod Removed
```

Resources are used efficiently.

---

# Real Production Example

An enterprise application contains:

```
GitHub

↓

Jenkins

↓

Build Agent

↓

SonarQube

↓

Docker Build

↓

Docker Registry

↓

Kubernetes

↓

Production
```

Each stage executes automatically.

---

# Controller Responsibilities

✔ Manage Users

✔ Store Jobs

✔ Schedule Builds

✔ Install Plugins

✔ Maintain Build History

✔ Coordinate Agents

---

# Agent Responsibilities

✔ Clone Code

✔ Compile

✔ Execute Tests

✔ Build Docker Images

✔ Deploy Applications

✔ Return Results

---

# Benefits of Distributed Architecture

✔ Faster Builds

✔ Parallel Execution

✔ Better Resource Utilization

✔ Platform Independence

✔ Easier Maintenance

✔ High Scalability

---

# Common Beginner Mistakes

### Mistake 1

Running every build on the Controller.

The Controller should primarily coordinate builds.

---

### Mistake 2

Giving every Agent administrator privileges.

Grant only the permissions required.

---

### Mistake 3

Not backing up the Jenkins Home directory.

This directory contains critical Jenkins configuration.

---

### Mistake 4

Installing unnecessary plugins.

Too many plugins increase maintenance complexity.

---

### Mistake 5

Configuring too many executors for limited hardware.

Executors should match available CPU and memory resources.

---

# Interview Questions

### Q1. What is the Jenkins Controller?

The Controller is the central Jenkins server that manages jobs, users, plugins, scheduling and communication with agents.

---

### Q2. What is a Jenkins Agent?

A Jenkins Agent is a machine that executes build, test and deployment tasks assigned by the Controller.

---

### Q3. What is an Executor?

An Executor is a worker thread that runs one build at a time on an Agent.

---

### Q4. What is a Workspace?

A Workspace is the directory where Jenkins checks out source code and performs build operations for a job.

---

### Q5. Why use distributed builds?

Distributed builds improve scalability, reduce build time and allow different workloads to run on specialized agents.

---

### Q6. Which directory should always be backed up?

```
/var/lib/jenkins
```

(or the configured `JENKINS_HOME` directory)

---

# Production Best Practices

✔ Keep the Controller dedicated to orchestration.

✔ Run builds on Agents.

✔ Back up `JENKINS_HOME`.

✔ Monitor Agent health.

✔ Secure communication between Controller and Agents.

✔ Use dedicated Agents for specialized workloads.

✔ Configure executors according to available resources.

✔ Remove unused Agents regularly.

---

# Key Takeaways

- The Jenkins Controller coordinates the entire CI/CD environment.
- Agents execute build workloads.
- Executors enable parallel job execution.
- Workspaces isolate build files for each job.
- Distributed Jenkins architectures provide better scalability, performance and reliability.

---

# Next Section

## 7.5 Installing Jenkins

In the next section, we will learn:

- Jenkins Installation Prerequisites
- Installing Java
- Installing Jenkins on Ubuntu
- Installing Jenkins on Rocky Linux
- Installing Jenkins on Amazon Linux
- Starting Jenkins
- Accessing the Dashboard
- Unlocking Jenkins
- Installing Recommended Plugins
- Interview Questions
---

# 7.5 Installing Jenkins

Now that you understand Jenkins Architecture,

it's time to install Jenkins.

In this section,

we will install Jenkins on:

- Ubuntu 24.04 LTS
- Rocky Linux 9
- Amazon Linux 2023

We will also learn:

- Install Java
- Install Jenkins
- Start Jenkins
- Enable Jenkins
- Unlock Jenkins
- Install Recommended Plugins
- Verify Installation

---

# Jenkins Installation Requirements

Before installing Jenkins,

ensure your system has:

- Java 21 (Recommended)
- 2 CPU
- 4 GB RAM (Minimum Recommended)
- Internet Connection
- Sudo Access

---

# Lab Environment

```
Ubuntu 24.04 LTS

or

Rocky Linux 9

or

Amazon Linux 2023
```

Supported Platforms

- Physical Machine
- Virtual Machine
- AWS EC2
- Azure VM
- Google Cloud VM

---

# Step 1 – Update System

Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

Rocky Linux

```bash
sudo dnf update -y
```

Amazon Linux

```bash
sudo dnf update -y
```

---

# Step 2 – Verify Java

Check Java.

```bash
java -version
```

Example

```text
openjdk version "21"
```

If Java is not installed,

install it.

---

# Install Java (Ubuntu)

```bash
sudo apt install openjdk-21-jdk -y
```

Verify

```bash
java -version
```

---

# Install Java (Rocky Linux)

```bash
sudo dnf install java-21-openjdk -y
```

---

# Install Java (Amazon Linux)

```bash
sudo dnf install java-21-amazon-corretto -y
```

---

# Verify JAVA_HOME

```bash
echo $JAVA_HOME
```

If empty,

configure it.

Example

```bash
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
```

---

# Step 3 – Add Jenkins Repository (Ubuntu)

Import Jenkins key.

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | \
sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

Add repository.

```bash
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | \
sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
```

Update packages.

```bash
sudo apt update
```

---

# Install Jenkins (Ubuntu)

```bash
sudo apt install jenkins -y
```

---

# Install Jenkins (Rocky Linux)

Import repository.

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

Import key.

```bash
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

Install.

```bash
sudo dnf install jenkins -y
```

---

# Install Jenkins (Amazon Linux)

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

sudo dnf install jenkins -y
```

---

# Step 4 – Start Jenkins

```bash
sudo systemctl start jenkins
```

---

# Verify Service

```bash
sudo systemctl status jenkins
```

Expected

```
Active: active (running)
```

---

# Enable Jenkins at Boot

```bash
sudo systemctl enable jenkins
```

Verify

```bash
systemctl is-enabled jenkins
```

Expected

```
enabled
```

---

# Restart Jenkins

```bash
sudo systemctl restart jenkins
```

---

# Stop Jenkins

```bash
sudo systemctl stop jenkins
```

---

# Check Jenkins Port

Jenkins listens on

```
8080
```

Verify

```bash
ss -tulpn | grep 8080
```

Expected

```
LISTEN

8080
```

---

# Open Firewall (Rocky / Amazon Linux)

```bash
sudo firewall-cmd --permanent --add-port=8080/tcp

sudo firewall-cmd --reload
```

---

# Access Jenkins

Open browser

```
http://SERVER-IP:8080
```

Example

```
http://192.168.1.100:8080
```

or

```
http://AWS-PUBLIC-IP:8080
```

---

# Unlock Jenkins

The first screen asks for

```
Administrator Password
```

Retrieve it.

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Example

```
4d7b57eab....

```

Copy the password into the browser.

---

# Install Plugins

Choose

```
Install Suggested Plugins
```

Jenkins installs commonly used plugins automatically.

Examples include:

- Git Plugin
- Pipeline Plugin
- Credentials Plugin
- SSH Plugin

---

# Create Admin User

Provide

- Username
- Password
- Full Name
- Email Address

Save and continue.

---

# Configure Jenkins URL

Example

```
http://SERVER-IP:8080
```

or

```
http://jenkins.company.com
```

---

# Jenkins Dashboard

After setup,

you will see

```
Dashboard

↓

Jobs

↓

Build Queue

↓

Manage Jenkins

↓

Manage Nodes
```

Installation is complete.

---

# Verify Jenkins Version

```bash
jenkins --version
```

or

```
Manage Jenkins

↓

System Information
```

---

# Jenkins Service Management

Start

```bash
sudo systemctl start jenkins
```

Stop

```bash
sudo systemctl stop jenkins
```

Restart

```bash
sudo systemctl restart jenkins
```

Status

```bash
sudo systemctl status jenkins
```

---

# Log Files

View Jenkins logs.

```bash
journalctl -u jenkins
```

Follow logs.

```bash
journalctl -fu jenkins
```

---

# Jenkins Directory Structure

```
/var/lib/jenkins

│

├── jobs

├── plugins

├── users

├── workspace

├── secrets

└── logs
```

---

# Real Installation Workflow

```
Install Java

↓

Install Jenkins

↓

Start Service

↓

Open Browser

↓

Unlock Jenkins

↓

Install Plugins

↓

Create Admin

↓

Dashboard Ready
```

---

# Common Installation Problems

### Java Not Installed

```bash
java -version
```

Install Java first.

---

### Jenkins Service Failed

```bash
sudo systemctl status jenkins
```

Check the logs.

---

### Port Already in Use

```bash
ss -tulpn | grep 8080
```

Either stop the conflicting application or change the Jenkins port.

---

### Firewall Blocking Access

Allow port

```
8080
```

through the firewall or cloud security group.

---

### Forgot Admin Password

Reset credentials using Jenkins administrative recovery procedures or create a new administrator if appropriate.

---

# Interview Questions

### Q1. Which port does Jenkins use by default?

```
8080
```

---

### Q2. Which command starts Jenkins?

```bash
sudo systemctl start jenkins
```

---

### Q3. Where is the initial administrator password stored?

```text
/var/lib/jenkins/secrets/initialAdminPassword
```

---

### Q4. Which command checks Jenkins service status?

```bash
sudo systemctl status jenkins
```

---

### Q5. Which software must be installed before Jenkins?

Java (JDK), such as Java 21.

---

### Q6. Which directory contains Jenkins configuration and jobs?

```text
/var/lib/jenkins
```

---

# Production Best Practices

✔ Install the latest Jenkins LTS release.

✔ Keep Java updated.

✔ Change the default administrator credentials.

✔ Back up `JENKINS_HOME`.

✔ Restrict access using a firewall or reverse proxy.

✔ Enable HTTPS in production.

✔ Monitor Jenkins logs.

✔ Keep plugins updated.

---

# Key Takeaways

- Jenkins requires Java before installation.
- Jenkins runs as a system service.
- The default web interface is available on port **8080**.
- The initial administrator password is stored in `JENKINS_HOME`.
- A secure production installation includes HTTPS, backups and controlled access.

---

# Next Section

## 7.6 Jenkins Dashboard

In the next section, we will learn:

- Jenkins Dashboard Overview
- Home Page
- Build Queue
- Build History
- Manage Jenkins
- Manage Nodes
- User Management
- Dashboard Navigation
- Best Practices
- Interview Questions
---

# 7.6 Jenkins Dashboard

After installing Jenkins,

the first screen you will use every day is the **Jenkins Dashboard**.

The Dashboard is the central place from which you:

- Create Jobs
- Monitor Builds
- View Pipelines
- Configure Jenkins
- Manage Users
- Manage Agents
- Install Plugins
- Check Build History

Every DevOps Engineer spends a significant amount of time working with the Jenkins Dashboard.

---

# What is the Jenkins Dashboard?

The Jenkins Dashboard is the main web interface used to manage Jenkins.

Think of it as the control center of your CI/CD environment.

```
Browser

↓

Jenkins Dashboard

↓

Jobs

↓

Pipelines

↓

Agents

↓

Plugins

↓

Users
```

---

# Dashboard Layout

A typical Jenkins Dashboard looks like:

```
--------------------------------------------

Jenkins Logo

--------------------------------------------

Dashboard

Build Queue

Build Executor Status

Manage Jenkins

Manage Nodes

My Views

Credentials

--------------------------------------------

Jobs

Pipelines

Build History

--------------------------------------------
```

---

# Main Dashboard Components

The Dashboard contains:

- Navigation Menu
- Jobs
- Pipelines
- Build Queue
- Build Executor Status
- Search Bar
- User Menu
- System Messages

---

# Dashboard Workflow

```
Login

↓

Dashboard

↓

Select Job

↓

Run Build

↓

View Console

↓

Check Result
```

---

# Navigation Menu

The left-side menu usually contains:

```
New Item

People

Build History

Manage Jenkins

Manage Nodes

Credentials

My Views
```

Each option performs a different administrative function.

---

# New Item

Click

```
New Item
```

to create a new Jenkins Job.

Available job types include:

- Freestyle Project
- Pipeline
- Folder
- Multibranch Pipeline

We will study each type later.

---

# People

Displays Jenkins users.

Example

```
Administrator

Developer1

Developer2
```

Useful for environments with multiple users.

---

# Build History

Shows recent builds.

Example

```
Build #51

SUCCESS

-------------------

Build #52

FAILED

-------------------

Build #53

SUCCESS
```

You can quickly identify successful and failed builds.

---

# Build Queue

Whenever a build is triggered,

it first enters the Build Queue.

```
Job

↓

Waiting

↓

Executor Available

↓

Running
```

If no executor is available,

the job remains queued.

---

# Build Executor Status

Shows which executors are currently busy.

Example

```
Agent-1

Running Build

--------------------

Agent-2

Idle

--------------------

Agent-3

Running Tests
```

Useful for monitoring build capacity.

---

# Dashboard Search

Modern Jenkins versions include a search feature.

You can quickly search for:

- Jobs
- Pipelines
- Nodes
- Views

instead of manually browsing.

---

# Job List

The dashboard displays all jobs.

Example

```
Frontend Build

SUCCESS

--------------------

Backend Build

FAILED

--------------------

Docker Build

RUNNING
```

Each job displays its current status.

---

# Build Status Icons

Common status indicators:

| Icon Meaning | Description |
|-------------|-------------|
| Blue/Green | Successful Build |
| Red | Failed Build |
| Yellow | Unstable Build |
| Grey | Disabled / Never Built |
| Animated | Build Running |

*(The exact colors may vary depending on the Jenkins theme and version.)*

---

# Job Details

Click a job.

You can view:

- Build History
- Console Output
- Workspace
- Artifacts
- Configuration

---

# Console Output

Every build generates logs.

Example

```
Git Clone

↓

Maven Build

↓

Tests

↓

Docker Build

↓

Success
```

Console logs are the first place to investigate failures.

---

# Workspace

Every job has a workspace.

Example

```
Workspace

↓

Source Code

↓

Compilation

↓

Temporary Files
```

Jenkins stores build files here during execution.

---

# Build Artifacts

Successful jobs can archive:

- JAR Files
- WAR Files
- ZIP Files
- Reports
- Docker Metadata

Artifacts can later be downloaded or deployed.

---

# Dashboard Views

Views help organize jobs.

Example

```
Development

↓

Testing

↓

Production
```

Large Jenkins environments often use multiple views.

---

# My Views

Developers can create personalized dashboards.

Example

```
My Java Jobs

↓

Backend Pipelines

↓

Production Deployments
```

This makes navigation easier.

---

# Manage Jenkins

One of the most important menu options.

It contains:

- System Configuration
- Plugin Manager
- Credentials
- Security
- Tools
- Nodes
- System Information

Administrators use this section frequently.

---

# Manage Nodes

Displays all Jenkins Agents.

Example

```
Controller

↓

Linux-Agent

↓

Windows-Agent

↓

Docker-Agent
```

You can:

- Add Nodes
- Remove Nodes
- Monitor Nodes
- Configure Executors

---

# Credentials

Stores:

- GitHub Tokens
- SSH Keys
- AWS Credentials
- Docker Registry Passwords
- API Keys

Never hardcode credentials inside jobs.

---

# System Information

Shows:

- Java Version
- Jenkins Version
- Operating System
- Environment Variables
- Installed Plugins

Useful for troubleshooting.

---

# Plugin Manager

Install,

update,

or remove plugins.

Examples

- Git Plugin
- Docker Plugin
- Pipeline Plugin
- Blue Ocean
- Slack Plugin

Only install trusted plugins.

---

# User Menu

The top-right menu allows users to:

- View Profile
- Change Password
- Configure User Settings
- Logout

---

# Dashboard Navigation Flow

```
Login

↓

Dashboard

↓

Job

↓

Build

↓

Console Output

↓

Artifacts

↓

Success
```

---

# Real Production Example

A company has

```
250 Jenkins Jobs

↓

Views

├── Frontend

├── Backend

├── DevOps

├── Production

└── Infrastructure
```

Views help administrators quickly locate jobs.

---

# Dashboard Best Practices

✔ Organize jobs using folders and views.

✔ Remove unused jobs.

✔ Name jobs clearly.

✔ Monitor failed builds daily.

✔ Archive important artifacts.

✔ Secure administrator access.

---

# Common Beginner Mistakes

### Mistake 1

Creating hundreds of jobs without folders or views.

---

### Mistake 2

Ignoring failed builds on the dashboard.

---

### Mistake 3

Leaving unused jobs indefinitely.

---

### Mistake 4

Saving passwords directly inside job configurations instead of using Credentials.

---

### Mistake 5

Installing unnecessary plugins that clutter the dashboard.

---

# Interview Questions

### Q1. What is the Jenkins Dashboard?

The Jenkins Dashboard is the main web interface used to manage jobs, pipelines, builds, users and system configuration.

---

### Q2. What is the Build Queue?

The Build Queue temporarily holds jobs until an executor becomes available.

---

### Q3. What is Build Executor Status?

It shows which Jenkins executors are currently running builds and which are idle.

---

### Q4. Where can you install Jenkins plugins?

```
Manage Jenkins

↓

Plugins
```

---

### Q5. Where are credentials stored?

Inside the Jenkins **Credentials** store.

---

### Q6. Why should Views be used?

Views organize jobs, making large Jenkins environments easier to manage.

---

# Production Best Practices

✔ Use folders and views.

✔ Keep job names meaningful.

✔ Secure administrator accounts.

✔ Use the Credentials Manager.

✔ Review build failures daily.

✔ Archive important build artifacts.

✔ Remove unused jobs.

✔ Keep plugins updated.

---

# Key Takeaways

- The Jenkins Dashboard is the central control panel for CI/CD operations.
- It provides access to jobs, pipelines, agents, credentials and plugins.
- Build Queue and Executor Status help monitor build activity.
- Console Output is the first place to troubleshoot build failures.
- A clean and organized dashboard improves productivity and maintainability.

---

# Next Section

## 7.7 Jenkins Jobs

In the next section, we will learn:

- What is a Jenkins Job?
- Types of Jobs
- Freestyle Projects
- Pipeline Jobs
- Folder Jobs
- Multibranch Pipelines
- Creating Your First Job
- Best Practices
- Interview Questions
---

# 7.7 Jenkins Jobs

A Jenkins installation without Jobs is like a computer without programs.

The primary purpose of Jenkins is to execute **Jobs**.

Every time Jenkins builds code,

runs tests,

creates Docker images,

or deploys an application,

it is executing a **Job**.

---

# What is a Jenkins Job?

A Jenkins Job is an automated task that Jenkins executes.

Examples include:

- Compile Code
- Run Tests
- Build Docker Images
- Deploy Applications
- Execute Shell Scripts
- Backup Databases
- Run Scheduled Tasks

Think of a Job as a reusable automation workflow.

---

# Simple Definition

```
User

↓

Run Job

↓

Jenkins

↓

Execute Tasks

↓

Result
```

---

# Real-Life Analogy

Imagine a washing machine.

You select a program:

```
Cotton

↓

Wash

↓

Rinse

↓

Dry
```

Similarly,

a Jenkins Job performs a predefined sequence of actions.

---

# Jenkins Job Workflow

```
Developer

↓

Git Push

↓

Jenkins Job

↓

Build

↓

Test

↓

Deploy

↓

Success
```

---

# Types of Jenkins Jobs

Jenkins supports multiple job types.

```
Jobs

│

├── Freestyle Project

├── Pipeline

├── Multibranch Pipeline

├── Folder

└── Organization Folder
```

Each type is designed for different use cases.

---

# Freestyle Project

The simplest Jenkins Job.

It allows you to configure:

- Source Code
- Build Steps
- Post-Build Actions

without writing pipeline code.

Freestyle projects are good for learning Jenkins.

---

# Pipeline Job

Pipeline Jobs define automation using code.

Instead of configuring everything through the UI,

you write a:

```
Jenkinsfile
```

Advantages:

✔ Version Controlled

✔ Reusable

✔ Easier to Maintain

✔ Supports Complex Workflows

---

# Multibranch Pipeline

Automatically discovers branches from Git repositories.

Example

```
Git Repository

│

├── main

├── develop

├── feature-login

└── feature-payment
```

Each branch receives its own pipeline automatically.

---

# Folder

Folders organize Jenkins Jobs.

Example

```
Development

│

├── Frontend

├── Backend

└── Database
```

Useful for large Jenkins environments.

---

# Organization Folder

Used for GitHub Organizations or GitLab Groups.

Automatically scans repositories and creates pipelines.

Suitable for enterprises managing hundreds of repositories.

---

# Freestyle Job Example

```
Git Clone

↓

Compile

↓

Run Tests

↓

Create Artifact
```

Everything is configured using the Jenkins UI.

---

# Pipeline Example

```
Checkout

↓

Build

↓

Test

↓

Docker Build

↓

Deploy
```

Defined inside a Jenkinsfile.

---

# Creating Your First Job

Dashboard

↓

```
New Item
```

↓

Enter Job Name

↓

Select

```
Freestyle Project
```

↓

Click

```
OK
```

---

# Configure Source Code

Under

```
Source Code Management
```

Select

```
Git
```

Enter repository URL.

Example

```
https://github.com/company/project.git
```

---

# Configure Build Trigger

Choose when the Job should run.

Options include:

- Build Now (Manual)
- GitHub Webhook
- Poll SCM
- Scheduled (CRON)

---

# Build Steps

Add one or more build steps.

Example

```bash
echo "Hello Jenkins"
```

Another example

```bash
mvn clean package
```

---

# Post Build Actions

After the build,

Jenkins can:

- Archive Artifacts
- Send Email
- Trigger Another Job
- Publish Reports
- Deploy Application

---

# Save the Job

Click

```
Save
```

The Job is now ready.

---

# Run the Job

Click

```
Build Now
```

Jenkins immediately starts the Job.

---

# Build Status

Possible results:

```
SUCCESS

↓

FAILED

↓

UNSTABLE

↓

ABORTED
```

---

# Console Output

Every Job generates logs.

```
Checkout Code

↓

Compile

↓

Tests

↓

Success
```

Use Console Output to diagnose failures.

---

# Workspace

Each Job receives its own workspace.

Example

```
workspace/

↓

project/

↓

source code
```

Temporary build files are stored here.

---

# Build History

Every execution creates a build number.

Example

```
#1

SUCCESS

-----------------

#2

FAILED

-----------------

#3

SUCCESS
```

Older builds remain available for review.

---

# Parameters

Jobs can accept user input.

Example

```
Application Version

↓

v1.2.0
```

or

```
Environment

↓

Development

↓

Testing

↓

Production
```

Parameterized builds improve flexibility.

---

# Scheduled Jobs

Jobs can run automatically.

Example

```
Every Night

↓

02:00 AM

↓

Backup Database
```

No manual intervention is required.

---

# Chained Jobs

One Job can trigger another.

```
Build

↓

Unit Tests

↓

Docker Build

↓

Deployment
```

Complex workflows can be built by chaining Jobs.

---

# Job Execution Lifecycle

```
Trigger

↓

Queue

↓

Executor

↓

Workspace

↓

Build

↓

Artifacts

↓

Result
```

---

# Real Production Example

A banking application uses separate Jobs for:

```
Frontend Build

↓

Backend Build

↓

Security Scan

↓

Docker Build

↓

Deploy QA

↓

Deploy Production
```

Each Job has a dedicated responsibility.

---

# Naming Convention

Good

```
frontend-build

backend-test

docker-image

deploy-prod
```

Avoid

```
test1

job2

newjob

finaljob
```

Meaningful names improve maintenance.

---

# Common Beginner Mistakes

### Mistake 1

Putting every task inside one huge Job.

Break work into logical Jobs or Pipelines.

---

### Mistake 2

Ignoring Console Output after failures.

Logs are the primary troubleshooting tool.

---

### Mistake 3

Hardcoding credentials inside Job configurations.

Use Jenkins Credentials instead.

---

### Mistake 4

Using Freestyle Jobs for very complex workflows.

Prefer Pipelines for advanced automation.

---

### Mistake 5

Creating jobs with unclear names.

Use descriptive naming conventions.

---

# Interview Questions

### Q1. What is a Jenkins Job?

A Jenkins Job is an automated task executed by Jenkins.

---

### Q2. Name three common Jenkins Job types.

- Freestyle Project
- Pipeline
- Multibranch Pipeline

---

### Q3. Which Job type is recommended for modern CI/CD?

Pipeline Jobs using a `Jenkinsfile`.

---

### Q4. Where can you see build logs?

```
Console Output
```

---

### Q5. What is Build History?

It is the record of all previous executions of a Jenkins Job.

---

### Q6. Why should Jobs use parameters?

Parameters make Jobs reusable across different versions, environments and deployment targets.

---

# Production Best Practices

✔ Prefer Pipeline Jobs over large Freestyle Projects.

✔ Use descriptive Job names.

✔ Store pipelines in source control.

✔ Avoid hardcoded credentials.

✔ Review build history regularly.

✔ Archive important artifacts.

✔ Keep Jobs focused on a single responsibility.

✔ Delete obsolete Jobs periodically.

---

# Key Takeaways

- Jenkins Jobs are the building blocks of automation.
- Different Job types support different workflows.
- Pipeline Jobs are preferred for modern DevOps.
- Console Output and Build History are essential for troubleshooting.
- Well-designed Jobs improve automation, maintainability and scalability.

---

# Next Section

## 7.8 Jenkins Pipelines

In the next section, we will learn:

- What is a Jenkins Pipeline?
- Pipeline Stages
- Declarative Pipeline
- Scripted Pipeline
- Pipeline Syntax
- Pipeline Execution
- Production Examples
- Best Practices
- Interview Questions
---

# 7.8 Jenkins Pipelines

As applications grow,

Freestyle Jobs become difficult to maintain.

Imagine an application that must:

- Download Source Code
- Build Application
- Run Unit Tests
- Run Security Scan
- Build Docker Image
- Push Docker Image
- Deploy to Kubernetes

Managing all these steps manually inside a Freestyle Job becomes complicated.

Jenkins solves this problem using **Pipelines**.

Pipelines define the entire CI/CD process as code.

---

# What is a Jenkins Pipeline?

A Jenkins Pipeline is a collection of automated stages that define the complete software delivery process.

Instead of clicking buttons in the Jenkins UI,

you write automation using code.

This approach is called:

```
Pipeline as Code
```

---

# Simple Definition

```
Code

↓

Pipeline

↓

Build

↓

Test

↓

Deploy
```

Everything is automated.

---

# Why Pipelines?

Without Pipelines

```
Many Manual Steps

↓

Hard to Maintain

↓

Error Prone
```

With Pipelines

```
Pipeline Code

↓

Automatic Execution

↓

Repeatable

↓

Reliable
```

---

# Pipeline Workflow

```
Developer

↓

Git Push

↓

Pipeline

↓

Checkout Code

↓

Build

↓

Test

↓

Docker Build

↓

Deploy

↓

Success
```

---

# Pipeline Advantages

✔ Pipeline as Code

✔ Version Controlled

✔ Reusable

✔ Easy to Maintain

✔ Automated

✔ Supports Complex Workflows

✔ Better Collaboration

✔ Scalable

---

# Pipeline Components

A Jenkins Pipeline consists of:

```
Pipeline

│

├── Agent

├── Stages

├── Steps

├── Environment

├── Post Actions

└── Parameters
```

---

# Pipeline Stages

A stage represents one phase of execution.

Example

```
Checkout

↓

Build

↓

Test

↓

Package

↓

Deploy
```

Stages make pipelines easier to understand.

---

# Example Pipeline

```
Stage 1

↓

Checkout

-------------------

Stage 2

↓

Build

-------------------

Stage 3

↓

Test

-------------------

Stage 4

↓

Deploy
```

Each stage performs a specific task.

---

# Pipeline Execution

```
Pipeline

↓

Stage

↓

Step

↓

Command

↓

Result
```

---

# Types of Pipelines

Jenkins supports two pipeline styles.

```
Declarative Pipeline

↓

Scripted Pipeline
```

Both use Groovy,

but Declarative is generally preferred for most projects.

---

# Declarative Pipeline

Declarative Pipelines use a structured syntax.

Example

```groovy
pipeline {

    agent any

    stages {

        stage('Build') {

            steps {

                echo 'Building Application'
            }
        }
    }
}
```

This syntax is easier to read and maintain.

---

# Scripted Pipeline

Scripted Pipelines provide greater flexibility.

Example

```groovy
node {

    stage('Build') {

        echo 'Building'
    }
}
```

Useful for advanced workflows,

but usually more complex.

---

# Declarative vs Scripted

| Declarative | Scripted |
|-------------|-----------|
| Easier | More Flexible |
| Structured | Programmatic |
| Recommended for Most Projects | Better for Advanced Logic |
| Easier to Maintain | Requires More Groovy Knowledge |

---

# Pipeline Block

Every Declarative Pipeline starts with

```groovy
pipeline {

}
```

This is the root of the pipeline.

---

# Agent Block

Specifies where the pipeline executes.

Example

```groovy
agent any
```

Meaning

```
Run

↓

Any Available Agent
```

You can also specify a labeled agent.

---

# Stages Block

Stages contain the major phases.

```groovy
stages {

}
```

---

# Stage Block

Example

```groovy
stage('Build')
```

Represents one logical step.

---

# Steps Block

Inside each stage,

actual commands execute.

Example

```groovy
steps {

    echo "Hello Jenkins"
}
```

---

# Complete Pipeline Example

```groovy
pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {

                echo 'Downloading Source Code'
            }
        }

        stage('Build') {

            steps {

                echo 'Building Application'
            }
        }

        stage('Test') {

            steps {

                echo 'Running Tests'
            }
        }

        stage('Deploy') {

            steps {

                echo 'Deploying'
            }
        }
    }
}
```

---

# Pipeline Visualization

```
Checkout

↓

Build

↓

Test

↓

Deploy

↓

Completed
```

Each stage appears separately in Jenkins.

---

# Environment Variables

Define variables once.

Example

```groovy
environment {

    APP_NAME = "Inventory"
}
```

Use them throughout the pipeline.

---

# Parameters

Pipelines can accept user input.

Example

```groovy
parameters {

    string(name: 'VERSION')
}
```

Users enter the version before execution.

---

# Post Section

The `post` block runs after pipeline execution.

Example

```groovy
post {

    always {

        echo "Pipeline Finished"
    }
}
```

Useful for cleanup and notifications.

---

# Pipeline Failure

Suppose

```
Checkout

↓

Build

↓

Tests

↓

FAILED

↓

Pipeline Stops
```

By default,

later stages do not execute after a failure.

---

# Parallel Stages

Independent tasks can run simultaneously.

Example

```
Build

↓

Unit Test

Integration Test

↓

Merge Results
```

Parallel execution reduces pipeline duration.

---

# Real Production Pipeline

```
Checkout

↓

Compile

↓

Unit Tests

↓

SonarQube Scan

↓

Docker Build

↓

Docker Push

↓

Deploy QA

↓

Approval

↓

Deploy Production
```

---

# Pipeline Stored in Git

The recommended approach is:

```
Git Repository

│

├── Source Code

└── Jenkinsfile
```

Every code change updates the pipeline together with the application.

---

# Benefits of Pipeline as Code

✔ Version Controlled

✔ Easy Rollback

✔ Peer Review

✔ Reusable

✔ Repeatable

✔ Auditable

---

# Common Beginner Mistakes

### Mistake 1

Creating one extremely large stage.

Break work into logical stages.

---

### Mistake 2

Hardcoding credentials.

Use Jenkins Credentials instead.

---

### Mistake 3

Not storing the Jenkinsfile in Git.

Always version-control pipelines.

---

### Mistake 4

Ignoring failed stages.

Investigate failures before proceeding.

---

### Mistake 5

Using Scripted Pipelines unnecessarily.

Prefer Declarative Pipelines unless advanced logic is required.

---

# Interview Questions

### Q1. What is a Jenkins Pipeline?

A Jenkins Pipeline is a code-defined workflow that automates build, test and deployment processes.

---

### Q2. What are the two Pipeline types?

- Declarative Pipeline
- Scripted Pipeline

---

### Q3. Which Pipeline type is recommended for most projects?

Declarative Pipeline.

---

### Q4. What is a Stage?

A Stage is a logical phase of a Jenkins Pipeline, such as Build or Test.

---

### Q5. Why store the Jenkinsfile in Git?

It enables version control, collaboration, auditing and reproducible builds.

---

### Q6. What is the purpose of the `post` section?

It defines actions that run after the pipeline completes, such as cleanup or notifications.

---

# Production Best Practices

✔ Store Jenkinsfiles in Git.

✔ Use Declarative Pipelines whenever possible.

✔ Keep stages focused and meaningful.

✔ Avoid hardcoded values.

✔ Use environment variables and credentials.

✔ Execute independent tasks in parallel when appropriate.

✔ Add post-build cleanup and notifications.

✔ Keep pipelines simple, modular and reusable.

---

# Key Takeaways

- Jenkins Pipelines automate complete CI/CD workflows.
- Pipelines are written as code and stored in version control.
- Declarative Pipelines are recommended for most teams.
- Stages improve readability and troubleshooting.
- Pipeline as Code is a core DevOps practice for reliable and repeatable software delivery.

---

# Next Section

## 7.9 Jenkinsfile

In the next section, we will learn:

- What is a Jenkinsfile?
- Jenkinsfile Structure
- Declarative Jenkinsfile
- Scripted Jenkinsfile
- Environment Variables
- Parameters
- Post Actions
- Production Examples
- Best Practices
- Interview Questions
---

# 7.9 Jenkinsfile

Now that you understand Jenkins Pipelines,

the next step is learning the **Jenkinsfile**.

A Jenkins Pipeline is executed using a file called:

```
Jenkinsfile
```

This file contains the complete CI/CD workflow.

Instead of configuring jobs manually through the Jenkins UI,

the entire automation is written as code.

This approach is called:

# Pipeline as Code

---

# What is a Jenkinsfile?

A Jenkinsfile is a text file written in **Groovy-based Pipeline Syntax**.

It defines:

- Build Steps
- Test Steps
- Deployment Steps
- Environment Variables
- Parameters
- Notifications
- Post Actions

Everything required to execute the CI/CD pipeline.

---

# Why Use a Jenkinsfile?

Without a Jenkinsfile

```
Pipeline

↓

Stored Inside Jenkins

↓

Hard to Track

↓

Hard to Reuse
```

With a Jenkinsfile

```
Pipeline Code

↓

Git Repository

↓

Version Controlled

↓

Easy Collaboration
```

---

# Jenkinsfile Workflow

```
Developer

↓

Update Jenkinsfile

↓

Git Commit

↓

Git Push

↓

Jenkins

↓

Pipeline Executes
```

Every pipeline change is version-controlled.

---

# Where is Jenkinsfile Stored?

The recommended location is:

```
Project

│

├── src/

├── pom.xml

├── Dockerfile

└── Jenkinsfile
```

The Jenkinsfile is usually stored in the root directory of the project.

---

# Basic Jenkinsfile Structure

```groovy
pipeline {

    agent any

    stages {

    }

}
```

Every Declarative Jenkinsfile starts with:

```
pipeline
```

---

# Components of Jenkinsfile

A Jenkinsfile usually contains:

```
Pipeline

│

├── Agent

├── Environment

├── Parameters

├── Stages

├── Steps

└── Post
```

---

# Agent

Specifies where the pipeline runs.

Example

```groovy
agent any
```

Meaning

```
Any Available Jenkins Agent
```

---

# Environment Variables

Store reusable values.

Example

```groovy
environment {

    APP_NAME = "Inventory"

    ENVIRONMENT = "Development"
}
```

Variables can be referenced throughout the pipeline.

---

# Parameters

Allow user input before execution.

Example

```groovy
parameters {

    string(name: 'VERSION')

    choice(name: 'ENV',

           choices: ['Dev','QA','Prod'])
}
```

Users select values when starting the build.

---

# Stages

Stages divide the pipeline into logical sections.

Example

```
Checkout

↓

Build

↓

Test

↓

Deploy
```

---

# Steps

Each stage contains steps.

Example

```groovy
steps {

    echo "Building Application"

}
```

Steps execute actual commands.

---

# Complete Declarative Jenkinsfile

```groovy
pipeline {

    agent any

    environment {

        APP_NAME = "Inventory"
    }

    stages {

        stage('Checkout') {

            steps {

                echo 'Downloading Source Code'
            }
        }

        stage('Build') {

            steps {

                echo 'Compiling'
            }
        }

        stage('Test') {

            steps {

                echo 'Running Tests'
            }
        }

        stage('Deploy') {

            steps {

                echo 'Deploying'
            }
        }

    }

    post {

        always {

            echo 'Pipeline Completed'

        }

    }

}
```

---

# Jenkinsfile Execution

```
Read Jenkinsfile

↓

Allocate Agent

↓

Run Stages

↓

Execute Steps

↓

Run Post Actions

↓

Finish
```

---

# Running Shell Commands

Use

```groovy
sh
```

on Linux.

Example

```groovy
steps {

    sh 'pwd'

    sh 'ls -la'

}
```

---

# Windows Commands

Use

```groovy
bat
```

Example

```groovy
steps {

    bat 'dir'

}
```

---

# Using Git

Example

```groovy
steps {

    git 'https://github.com/company/project.git'

}
```

Jenkins clones the repository automatically.

---

# Environment Variable Example

```groovy
environment {

    JAVA_HOME="/usr/lib/jvm/java-21"

}
```

Access variable

```groovy
echo "${JAVA_HOME}"
```

---

# Credentials

Never hardcode passwords.

Example

```groovy
environment {

    GITHUB_TOKEN = credentials('github-token')

}
```

Jenkins securely retrieves stored credentials.

---

# Conditional Execution

Example

```groovy
when {

    branch 'main'

}
```

Stage runs only on:

```
main
```

branch.

---

# Parallel Stages

Example

```
Build

↓

Unit Test

Integration Test

↓

Continue
```

Parallel execution reduces build time.

---

# Post Actions

Common options

```
always

success

failure

unstable

cleanup
```

Example

```groovy
post {

    success {

        echo "Deployment Successful"

    }

}
```

---

# Archiving Artifacts

Example

```groovy
archiveArtifacts artifacts: '*.jar'
```

Artifacts remain available after the build.

---

# Pipeline Options

Example

```groovy
options {

    timeout(time:30,

            unit:'MINUTES')

}
```

Protects pipelines from running indefinitely.

---

# Build Triggers

Automatically trigger pipelines.

Examples

- GitHub Webhook
- Poll SCM
- CRON Schedule

No manual execution required.

---

# Real Production Jenkinsfile

```
Checkout

↓

Compile

↓

Unit Tests

↓

SonarQube

↓

Docker Build

↓

Docker Push

↓

Deploy QA

↓

Approval

↓

Deploy Production
```

Entire workflow exists inside one Jenkinsfile.

---

# Jenkinsfile Benefits

✔ Version Controlled

✔ Easy Rollback

✔ Easy Review

✔ Reusable

✔ Repeatable

✔ Transparent

✔ Automation as Code

---

# Repository Example

```
Inventory-App

│

├── src/

├── Dockerfile

├── pom.xml

├── compose.yaml

└── Jenkinsfile
```

Every project should contain its own Jenkinsfile.

---

# Common Beginner Mistakes

### Mistake 1

Keeping pipeline configuration only inside Jenkins.

Always version-control Jenkinsfiles.

---

### Mistake 2

Hardcoding passwords.

Use Jenkins Credentials.

---

### Mistake 3

Creating one enormous Jenkinsfile.

Break complex logic into shared libraries or reusable functions where appropriate.

---

### Mistake 4

Ignoring failed stages.

Always investigate failures before rerunning pipelines.

---

### Mistake 5

Writing unreadable pipeline code.

Use meaningful stage names and consistent formatting.

---

# Interview Questions

### Q1. What is a Jenkinsfile?

A Jenkinsfile is a text file that defines a Jenkins Pipeline using Groovy-based syntax.

---

### Q2. Where should a Jenkinsfile be stored?

In the root directory of the project's source code repository.

---

### Q3. Why should Jenkinsfiles be version-controlled?

To enable collaboration, auditing, rollback and reproducible pipelines.

---

### Q4. Which command executes Linux shell commands?

```groovy
sh
```

---

### Q5. Which command executes Windows commands?

```groovy
bat
```

---

### Q6. Why should credentials never be hardcoded?

Hardcoded credentials create security risks. Jenkins Credentials securely manages sensitive information.

---

# Production Best Practices

✔ Store Jenkinsfiles in Git.

✔ Keep pipelines modular.

✔ Use environment variables.

✔ Store secrets in Jenkins Credentials.

✔ Use meaningful stage names.

✔ Archive important artifacts.

✔ Configure timeouts.

✔ Keep pipeline code readable and maintainable.

---

# Key Takeaways

- A Jenkinsfile defines the complete CI/CD pipeline as code.
- Declarative Pipelines are recommended for most projects.
- Jenkinsfiles should always be stored in the source repository.
- Credentials and configuration should be managed securely.
- Pipeline as Code improves automation, consistency and collaboration.

---

# Next Section

## 7.10 Git Integration

In the next section, we will learn:

- Connecting Jenkins with Git
- GitHub Integration
- Webhooks
- Poll SCM
- Automatic Builds
- Branch Management
- Git Credentials
- Production Workflow
- Best Practices
- Interview Questions
---

# 7.10 Git Integration

Jenkins becomes truly powerful when it is connected to a **Git Repository**.

Instead of manually downloading source code,

Jenkins automatically retrieves the latest code from Git whenever a build starts.

This integration is the foundation of modern CI/CD.

---

# What is Git Integration?

Git Integration allows Jenkins to communicate with Git repositories such as:

- GitHub
- GitLab
- Bitbucket
- Azure Repos
- Self-hosted Git Servers

Jenkins can automatically:

- Clone Repositories
- Fetch Updates
- Build Specific Branches
- Trigger Pipelines
- Deploy Applications

---

# Simple Workflow

```
Developer

↓

Git Commit

↓

Git Push

↓

Git Repository

↓

Jenkins

↓

Clone Code

↓

Build

↓

Deploy
```

---

# Why Integrate Git?

Without Git Integration

```
Developer

↓

Download ZIP

↓

Copy Files

↓

Build

↓

Deploy
```

Manual,

slow,

and error-prone.

---

With Git Integration

```
Git Push

↓

Webhook

↓

Jenkins

↓

Automatic Build
```

Everything happens automatically.

---

# Supported Git Platforms

Jenkins integrates with:

- GitHub
- GitLab
- Bitbucket
- Azure Repos
- AWS CodeCommit
- Self-hosted Git Servers

---

# Git Integration Workflow

```
Developer

↓

Git Push

↓

Webhook

↓

Jenkins

↓

Checkout Code

↓

Compile

↓

Run Tests

↓

Deploy
```

---

# Install Git Plugin

Most Jenkins installations already include the Git Plugin.

Verify

```
Manage Jenkins

↓

Plugins

↓

Installed Plugins

↓

Git Plugin
```

Install it if missing.

---

# Install Git on Jenkins Server

Ubuntu

```bash
sudo apt install git -y
```

Rocky Linux

```bash
sudo dnf install git -y
```

Amazon Linux

```bash
sudo dnf install git -y
```

---

# Verify Git

```bash
git --version
```

Example

```
git version 2.54.0
```

---

# Configure Git in Jenkins

Navigate to

```
Manage Jenkins

↓

Tools

↓

Git Installations
```

Configure:

```
Name

↓

Git

Path

↓

/usr/bin/git
```

---

# Creating a Git Job

Dashboard

↓

```
New Item
```

↓

Pipeline

↓

Source Code Management

↓

Git

↓

Repository URL

---

# Repository URL

Example

```
https://github.com/company/inventory-app.git
```

Jenkins clones this repository before every build.

---

# Clone Process

```
Git Repository

↓

Clone

↓

Workspace

↓

Source Code Ready
```

---

# Branch Selection

Specify which branch Jenkins should build.

Example

```
main
```

or

```
develop
```

or

```
feature-login
```

Example configuration

```
Branches to build

↓

*/main
```

---

# Checkout Stage

Example Pipeline

```groovy
stage('Checkout') {

    steps {

        git branch: 'main',

            url: 'https://github.com/company/project.git'

    }

}
```

---

# Authentication

Public repositories

```
No Credentials Required
```

Private repositories

```
Credentials Required
```

---

# Git Credentials

Store credentials securely.

Navigate

```
Manage Jenkins

↓

Credentials

↓

Global

↓

Add Credentials
```

Supported credentials include:

- Username & Password
- Personal Access Token
- SSH Private Key

---

# Using Personal Access Token

Instead of passwords,

GitHub recommends:

```
Personal Access Token (PAT)
```

Store the PAT in Jenkins Credentials.

---

# Using SSH Authentication

Generate SSH key.

```bash
ssh-keygen
```

Add:

```
Public Key

↓

GitHub
```

Store:

```
Private Key

↓

Jenkins Credentials
```

SSH authentication avoids exposing passwords.

---

# Git Polling

Jenkins periodically checks Git for changes.

Example

```
Every 5 Minutes

↓

Check Repository

↓

Changes?

↓

Build
```

Configuration

```
Poll SCM
```

Example schedule

```
H/5 * * * *
```

---

# Webhooks

A better approach is using Webhooks.

```
Developer Push

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Immediate Build
```

No polling delay exists.

---

# GitHub Webhook Configuration

GitHub Repository

↓

Settings

↓

Webhooks

↓

Add Webhook

Payload URL

```
http://JENKINS-IP:8080/github-webhook/
```

Content Type

```
application/json
```

Events

```
Just the push event
```

---

# Poll SCM vs Webhook

| Poll SCM | Webhook |
|----------|----------|
| Jenkins checks Git periodically | Git immediately notifies Jenkins |
| Slight Delay | Instant Trigger |
| More Server Load | More Efficient |
| Easier Initial Setup | Preferred for Production |

---

# Branch-Based Builds

Example

```
main

↓

Production

------------------

develop

↓

Testing

------------------

feature/*

↓

Developer Testing
```

Different branches can trigger different pipelines.

---

# Multibranch Pipelines

Repository

```
main

develop

feature-auth

feature-payment
```

Jenkins automatically creates a pipeline for each branch.

---

# Git Tags

Build only tagged releases.

Example

```
v1.0

↓

Release Pipeline
```

Useful for production deployments.

---

# Pipeline Example

```groovy
pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {

                git branch: 'main',

                credentialsId: 'github-token',

                url: 'https://github.com/company/project.git'

            }

        }

    }

}
```

---

# Build Flow

```
Developer

↓

Commit

↓

Push

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Checkout

↓

Build

↓

Deploy
```

---

# Real Production Example

```
Developers

↓

GitHub Enterprise

↓

Webhook

↓

Jenkins

↓

Maven Build

↓

Docker Build

↓

Docker Hub

↓

Kubernetes
```

Every push automatically starts the pipeline.

---

# Git Best Practices

✔ One Repository Per Application

✔ Protect Main Branch

✔ Use Pull Requests

✔ Commit Frequently

✔ Use Branch Naming Standards

✔ Tag Releases

---

# Common Beginner Mistakes

### Mistake 1

Hardcoding Git passwords.

Always use Jenkins Credentials.

---

### Mistake 2

Building directly from developer laptops.

Always build from the Git repository.

---

### Mistake 3

Using Poll SCM when Webhooks are available.

Prefer Webhooks for faster and more efficient builds.

---

### Mistake 4

Building every experimental branch.

Configure branch filters appropriately.

---

### Mistake 5

Committing directly to the production branch.

Use feature branches and code reviews.

---

# Interview Questions

### Q1. Why integrate Git with Jenkins?

Git Integration enables Jenkins to automatically retrieve source code and trigger builds.

---

### Q2. Which Git hosting platforms does Jenkins support?

GitHub, GitLab, Bitbucket, Azure Repos, AWS CodeCommit and self-hosted Git servers.

---

### Q3. What is a Webhook?

A Webhook is an HTTP callback that immediately notifies Jenkins when repository events occur.

---

### Q4. Which is better for production: Poll SCM or Webhooks?

Webhooks, because they provide immediate builds and reduce unnecessary polling.

---

### Q5. Where should Git credentials be stored?

Inside the Jenkins Credentials Manager.

---

### Q6. Why are Multibranch Pipelines useful?

They automatically discover branches and create separate pipelines for each one.

---

# Production Best Practices

✔ Use Webhooks.

✔ Secure Git credentials.

✔ Protect important branches.

✔ Use Multibranch Pipelines.

✔ Build only trusted branches.

✔ Tag production releases.

✔ Keep repositories clean.

✔ Store the Jenkinsfile in Git.

---

# Key Takeaways

- Git Integration is fundamental to Jenkins automation.
- Webhooks provide fast and efficient build triggers.
- Jenkins securely stores Git credentials.
- Multibranch Pipelines simplify branch-based development.
- A properly integrated Git workflow enables reliable, automated CI/CD.

---

# Next Section

## 7.11 Docker Integration

In the next section, we will learn:

- Why Integrate Docker with Jenkins?
- Building Docker Images
- Docker Pipeline
- Docker Registry Integration
- Docker Hub Authentication
- Pushing Images
- Deploying Containers
- Production Workflow
- Best Practices
- Interview Questions
---

# 7.11 Docker Integration

Modern applications are usually deployed as Docker containers.

Instead of manually installing software on servers,

organizations build Docker images,

store them in a container registry,

and deploy them automatically.

Jenkins integrates seamlessly with Docker to automate this entire process.

---

# Why Integrate Docker with Jenkins?

Suppose every developer builds Docker images manually.

```
Developer

↓

docker build

↓

docker push

↓

Deploy
```

Different developers may produce different results.

With Jenkins,

the process becomes standardized.

```
Git Push

↓

Jenkins

↓

Docker Build

↓

Docker Push

↓

Deployment
```

---

# What is Docker Integration?

Docker Integration allows Jenkins to:

- Build Docker Images
- Run Docker Containers
- Push Images to Registries
- Pull Images
- Deploy Containers
- Execute Docker Commands
- Automate Container-Based CI/CD

---

# Docker Integration Workflow

```
Developer

↓

Git Push

↓

Jenkins

↓

Checkout Code

↓

Docker Build

↓

Docker Image

↓

Docker Registry

↓

Deployment
```

---

# Prerequisites

Before integrating Docker with Jenkins:

✔ Docker Installed

✔ Jenkins Installed

✔ Git Installed

✔ Dockerfile Available

✔ Docker Hub Account (or Private Registry)

---

# Install Docker on Jenkins Server

Ubuntu

```bash
sudo apt install docker.io -y
```

Rocky Linux

```bash
sudo dnf install docker -y
```

Amazon Linux

```bash
sudo dnf install docker -y
```

---

# Start Docker

```bash
sudo systemctl start docker
```

Enable Docker

```bash
sudo systemctl enable docker
```

Verify

```bash
docker --version
```

---

# Allow Jenkins to Use Docker

By default,

the Jenkins user cannot execute Docker commands.

Add Jenkins to the Docker group.

```bash
sudo usermod -aG docker jenkins
```

Restart services.

```bash
sudo systemctl restart docker

sudo systemctl restart jenkins
```

Verify.

```bash
sudo su - jenkins

docker ps
```

---

# Verify Docker Access

Inside Jenkins,

create a simple Pipeline.

```groovy
pipeline {

    agent any

    stages {

        stage('Docker Version') {

            steps {

                sh 'docker --version'

            }

        }

    }

}
```

If Docker is configured correctly,

the version is displayed.

---

# Docker Pipeline Workflow

```
Checkout Code

↓

Build Application

↓

Docker Build

↓

Docker Image

↓

Push Registry

↓

Deploy
```

---

# Dockerfile

Every application requires a Dockerfile.

Example

```dockerfile
FROM nginx:1.27

COPY . /usr/share/nginx/html
```

Jenkins uses this Dockerfile to build the image.

---

# Build Docker Image

Pipeline example

```groovy
stage('Docker Build') {

    steps {

        sh 'docker build -t inventory:v1 .'

    }

}
```

Jenkins executes

```bash
docker build
```

automatically.

---

# Tag Docker Image

Example

```groovy
sh 'docker tag inventory:v1 username/inventory:v1'
```

Image becomes ready for upload.

---

# Login to Docker Hub

Store Docker Hub credentials inside Jenkins.

Navigate

```
Manage Jenkins

↓

Credentials

↓

Global

↓

Add Credentials
```

Store:

- Username
- Password or Personal Access Token

---

# Docker Login in Pipeline

Example

```groovy
withCredentials([usernamePassword(

credentialsId: 'dockerhub',

usernameVariable: 'USERNAME',

passwordVariable: 'PASSWORD'

)]) {

    sh 'echo $PASSWORD | docker login -u $USERNAME --password-stdin'

}
```

Credentials remain protected.

---

# Push Docker Image

Example

```groovy
sh 'docker push username/inventory:v1'
```

Image uploads to Docker Hub.

---

# Pull Docker Image

Deployment server executes:

```bash
docker pull username/inventory:v1
```

Latest image becomes available.

---

# Run Container

```bash
docker run -d -p 80:80 username/inventory:v1
```

Application starts.

---

# Complete Pipeline

```
Checkout

↓

Compile

↓

Tests

↓

Docker Build

↓

Docker Tag

↓

Docker Push

↓

Deployment
```

---

# Pipeline Example

```groovy
pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {

                git 'https://github.com/company/app.git'

            }

        }

        stage('Docker Build') {

            steps {

                sh 'docker build -t app:v1 .'

            }

        }

        stage('Docker Push') {

            steps {

                sh 'docker push username/app:v1'

            }

        }

    }

}
```

---

# Docker Registry

Jenkins can push images to:

- Docker Hub
- Amazon ECR
- Azure Container Registry
- Google Artifact Registry
- Harbor
- GitHub Container Registry

---

# Private Registry Workflow

```
Jenkins

↓

Docker Build

↓

Private Registry

↓

Production Server

↓

Docker Pull

↓

Deploy
```

Private registries are commonly used in enterprises.

---

# Automatic Deployment

After pushing the image,

Jenkins can execute:

```bash
docker stop app

docker rm app

docker run -d app:v2
```

The application is updated automatically.

---

# Production CI/CD Flow

```
Developer

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Build

↓

Tests

↓

Docker Build

↓

Image Scan

↓

Push Registry

↓

Deploy Kubernetes

↓

Production
```

---

# Security

Never expose:

- Docker Passwords
- Registry Tokens
- API Keys

Use:

```
Jenkins Credentials
```

instead of hardcoding secrets.

---

# Image Versioning

Good

```
inventory:v1.0

inventory:v1.1

inventory:v2.0
```

Avoid relying only on

```
latest
```

---

# Build Cleanup

Remove unused images periodically.

```bash
docker image prune
```

This helps manage disk usage.

---

# Real Production Example

```
Developer

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Maven Build

↓

Docker Build

↓

Docker Hub

↓

Kubernetes

↓

Users
```

Every deployment is fully automated.

---

# Common Beginner Mistakes

### Mistake 1

Running Jenkins without Docker permissions.

Add the Jenkins user to the Docker group.

---

### Mistake 2

Hardcoding Docker Hub passwords.

Use Jenkins Credentials.

---

### Mistake 3

Using only the `latest` image tag.

Use versioned image tags.

---

### Mistake 4

Building Docker images without testing the application first.

Run automated tests before creating images.

---

### Mistake 5

Leaving old Docker images on the Jenkins server.

Clean up unused images regularly.

---

# Interview Questions

### Q1. Why integrate Docker with Jenkins?

To automatically build, package and deploy containerized applications.

---

### Q2. Which command builds a Docker image?

```bash
docker build
```

---

### Q3. Why must the Jenkins user join the Docker group?

So Jenkins can execute Docker commands without using the root account.

---

### Q4. Where should Docker Hub credentials be stored?

Inside the Jenkins Credentials Manager.

---

### Q5. Name three Docker registries.

- Docker Hub
- Amazon ECR
- GitHub Container Registry

---

### Q6. Why should Docker images use version tags?

Version tags make deployments predictable and simplify rollbacks.

---

# Production Best Practices

✔ Build Docker images only after successful tests.

✔ Store registry credentials securely.

✔ Scan images for vulnerabilities.

✔ Use versioned image tags.

✔ Push images to trusted registries.

✔ Remove unused images.

✔ Keep Docker updated.

✔ Automate deployments using Jenkins Pipelines.

---

# Key Takeaways

- Jenkins and Docker work together to automate container-based deployments.
- Docker images are built, tagged and pushed automatically.
- Jenkins securely manages registry credentials.
- Versioned Docker images improve deployment reliability.
- Docker Integration is a fundamental part of modern CI/CD pipelines.

---

# Next Section

## 7.12 Build Automation

In the next section, we will learn:

- What is Build Automation?
- Maven Integration
- Gradle Integration
- Node.js Builds
- Python Builds
- Build Artifacts
- Artifact Repositories
- Production Workflow
- Best Practices
- Interview Questions
---

# 7.12 Build Automation

One of the biggest responsibilities of Jenkins is **Build Automation**.

Before Jenkins,

developers had to manually:

- Download Source Code
- Compile Application
- Resolve Dependencies
- Package Application
- Create Release Files

This process was repetitive,

slow,

and error-prone.

Jenkins automates the complete build process.

---

# What is Build Automation?

Build Automation is the process of automatically:

- Downloading Source Code
- Installing Dependencies
- Compiling Code
- Running Tests
- Packaging Applications
- Generating Build Artifacts

without manual intervention.

---

# Simple Workflow

```
Developer

↓

Git Push

↓

Jenkins

↓

Build

↓

Artifact

↓

Deployment
```

---

# Why Build Automation?

Without automation

```
Developer

↓

Compile

↓

Package

↓

Deploy
```

Every developer performs the same repetitive work.

---

With automation

```
Git Push

↓

Jenkins

↓

Automatic Build
```

Builds become consistent and repeatable.

---

# Build Automation Workflow

```
Git Repository

↓

Checkout

↓

Dependencies

↓

Compile

↓

Unit Tests

↓

Package

↓

Artifact

↓

Deploy
```

---

# Common Build Tools

Different programming languages use different build tools.

| Language | Build Tool |
|-----------|------------|
| Java | Maven |
| Java | Gradle |
| Node.js | npm / pnpm / Yarn |
| Python | pip / Poetry |
| Go | go build |
| .NET | dotnet CLI |

Jenkins supports all of them.

---

# Java Build Using Maven

Typical commands

```bash
mvn clean

mvn compile

mvn test

mvn package
```

Pipeline

```
Checkout

↓

Compile

↓

Test

↓

Package

↓

JAR
```

---

# Maven Pipeline Example

```groovy
stage('Build') {

    steps {

        sh 'mvn clean package'

    }

}
```

Jenkins automatically builds the application.

---

# Maven Build Lifecycle

```
Validate

↓

Compile

↓

Test

↓

Package

↓

Verify

↓

Install

↓

Deploy
```

Understanding the lifecycle helps troubleshoot build issues.

---

# Gradle Build

Gradle is another popular Java build tool.

Commands

```bash
./gradlew build
```

or

```bash
gradle build
```

Pipeline

```groovy
stage('Build') {

    steps {

        sh './gradlew build'

    }

}
```

---

# Node.js Build

Example

```bash
npm install

npm test

npm run build
```

Pipeline

```groovy
stage('Build') {

    steps {

        sh 'npm install'

        sh 'npm run build'

    }

}
```

---

# Python Build

Example

```bash
python -m venv venv

pip install -r requirements.txt

pytest
```

Jenkins automates Python application builds in the same way.

---

# Go Build

Example

```bash
go build
```

Produces

```
Binary Executable
```

---

# .NET Build

Example

```bash
dotnet restore

dotnet build

dotnet test

dotnet publish
```

---

# Dependency Management

Applications require external libraries.

Example

```
Application

↓

Dependencies

↓

Build
```

Examples

- Maven Dependencies
- npm Packages
- Python Packages
- Gradle Dependencies

Jenkins automatically downloads required dependencies.

---

# Build Artifacts

A successful build produces artifacts.

Examples

```
JAR

WAR

ZIP

Docker Image

Executable
```

Artifacts are used for deployment.

---

# Archive Artifacts

Example

```groovy
archiveArtifacts artifacts: 'target/*.jar'
```

Artifacts remain available inside Jenkins.

---

# Artifact Repository

Large organizations store artifacts in repositories.

Examples

- Nexus Repository
- JFrog Artifactory
- GitHub Packages
- AWS CodeArtifact

Workflow

```
Build

↓

Artifact

↓

Repository

↓

Deployment
```

---

# Build Numbers

Every Jenkins build receives a unique number.

Example

```
Build #100

↓

Build #101

↓

Build #102
```

This helps with traceability.

---

# Build Environment

A build environment includes:

- Java
- Maven
- Git
- Docker
- Environment Variables
- Credentials

Jenkins prepares this environment before starting the build.

---

# Environment Variables

Example

```groovy
environment {

    JAVA_HOME="/usr/lib/jvm/java-21"

}
```

Used during compilation.

---

# Parallel Builds

Independent tasks can execute simultaneously.

Example

```
Backend Build

↓

Frontend Build

↓

Integration
```

Parallel execution reduces build time.

---

# Build Failure

Suppose compilation fails.

```
Checkout

↓

Compile

↓

FAILED

↓

Pipeline Stops
```

Deployment should not continue after a failed build.

---

# Build Logs

Every build generates logs.

Example

```
Compile Started

↓

Dependency Download

↓

Packaging

↓

Build Successful
```

Logs are essential for troubleshooting.

---

# Incremental Builds

Some tools rebuild only changed components.

Benefits

- Faster Builds
- Less Resource Usage
- Improved Developer Productivity

---

# Clean Builds

Example

```bash
mvn clean package
```

or

```bash
./gradlew clean build
```

Clean builds remove old compiled files before rebuilding.

---

# Real Production Workflow

```
GitHub

↓

Webhook

↓

Jenkins

↓

Checkout

↓

Maven Build

↓

Unit Tests

↓

SonarQube

↓

Docker Build

↓

Push Registry

↓

Deploy
```

---

# Build Optimization

Improve build performance by:

✔ Caching Dependencies

✔ Parallel Builds

✔ Incremental Compilation

✔ Fast Test Suites

✔ Dedicated Build Agents

---

# Common Beginner Mistakes

### Mistake 1

Skipping automated tests.

Always run tests before packaging.

---

### Mistake 2

Ignoring build logs.

Logs contain the first clues when builds fail.

---

### Mistake 3

Hardcoding environment-specific paths.

Use environment variables or tool configuration.

---

### Mistake 4

Building directly on production servers.

Always build in Jenkins or another CI environment.

---

### Mistake 5

Not archiving build artifacts.

Artifacts should be retained for deployment and rollback.

---

# Interview Questions

### Q1. What is Build Automation?

Build Automation is the automatic process of compiling, testing and packaging software.

---

### Q2. Name three popular build tools.

- Maven
- Gradle
- npm

---

### Q3. What is a build artifact?

A build artifact is the output of a successful build, such as a JAR, WAR, ZIP or Docker image.

---

### Q4. Why should artifacts be archived?

To make them available for deployment, auditing and rollback.

---

### Q5. Why should builds stop after compilation or test failures?

Deploying failed builds increases the risk of production issues.

---

### Q6. Name two artifact repository solutions.

- Nexus Repository
- JFrog Artifactory

---

# Production Best Practices

✔ Automate every build.

✔ Run automated tests.

✔ Archive build artifacts.

✔ Store artifacts in a repository.

✔ Use dedicated build agents.

✔ Optimize dependency downloads.

✔ Monitor build duration.

✔ Keep build environments consistent.

---

# Key Takeaways

- Build Automation is one of Jenkins' primary responsibilities.
- Jenkins supports build tools for many programming languages.
- Successful builds generate deployable artifacts.
- Artifact repositories improve software distribution and traceability.
- Automated, repeatable builds are a fundamental DevOps practice.

---

# Next Section

## 7.13 Jenkins Agents

In the next section, we will learn:

- What are Jenkins Agents?
- Why Agents are Needed
- Static vs Dynamic Agents
- Agent Labels
- Connecting Agents
- SSH Agents
- Docker Agents
- Kubernetes Agents
- Production Best Practices
- Interview Questions
---

# 7.13 Jenkins Agents

As your CI/CD environment grows,

running every build on a single Jenkins server becomes inefficient.

Imagine a company with:

- 200 Developers
- 500 Builds Every Day
- Java Projects
- Python Projects
- Docker Builds
- Windows Applications

One Jenkins server cannot efficiently handle all these workloads.

This is why **Jenkins Agents** exist.

---

# What are Jenkins Agents?

A Jenkins Agent is a machine that performs build, test and deployment tasks assigned by the Jenkins Controller.

The Controller coordinates the work,

while Agents execute it.

```
Developer

↓

Jenkins Controller

↓

Jenkins Agent

↓

Build

↓

Result
```

---

# Why Do We Need Agents?

Without Agents

```
Controller

↓

Build Everything

↓

Slow

↓

High CPU Usage

↓

Build Queue
```

The Controller becomes overloaded.

---

With Agents

```
Controller

↓

Agent 1

↓

Agent 2

↓

Agent 3

↓

Parallel Builds
```

Builds finish much faster.

---

# Controller vs Agent

| Controller | Agent |
|------------|--------|
| Manages Jenkins | Executes Jobs |
| Schedules Builds | Runs Build Steps |
| Stores Configuration | Uses Workspace |
| Controls Plugins | Returns Build Results |

---

# Jenkins Agent Workflow

```
Developer

↓

Git Push

↓

Controller

↓

Assign Job

↓

Agent

↓

Build

↓

Test

↓

Artifact

↓

Controller
```

---

# Types of Jenkins Agents

Jenkins supports multiple Agent types.

```
Agents

│

├── Static Agent

├── Dynamic Agent

├── SSH Agent

├── Windows Agent

├── Docker Agent

└── Kubernetes Agent
```

---

# Static Agent

A Static Agent is a permanently configured machine.

Example

```
Controller

↓

Linux Server

↓

Agent
```

The Agent remains available all the time.

---

# Dynamic Agent

Dynamic Agents are created only when needed.

Example

```
Build Request

↓

Create Agent

↓

Run Build

↓

Delete Agent
```

Cloud environments frequently use dynamic agents.

---

# SSH Agent

The Controller connects to a remote server using SSH.

```
Controller

↓

SSH

↓

Linux Server

↓

Build
```

This is one of the most common Agent configurations.

---

# Windows Agent

Some software can only be built on Windows.

Example

```
Controller

↓

Windows Agent

↓

.NET Build
```

---

# Docker Agent

Each build runs inside a Docker container.

```
Controller

↓

Docker Container

↓

Build

↓

Container Removed
```

Benefits:

- Clean Environment
- Consistent Builds
- Easy Maintenance

---

# Kubernetes Agent

Modern Jenkins deployments often use Kubernetes.

```
Controller

↓

Kubernetes

↓

Temporary Pod

↓

Build

↓

Pod Deleted
```

Resources are created only when required.

---

# Agent Labels

Agents can have labels.

Example

```
linux

windows

docker

kubernetes

java

python
```

Jobs can target specific labels.

Example

```groovy
agent {

    label 'docker'

}
```

---

# Number of Executors

Each Agent can execute multiple Jobs simultaneously.

Example

```
Agent

↓

Executor 1

Executor 2

Executor 3
```

If an Agent has:

```
4 Executors
```

it can execute:

```
4 Builds

At the Same Time
```

---

# Workspace

Each Agent has a workspace.

Example

```
Workspace

↓

Checkout Code

↓

Compile

↓

Tests

↓

Artifacts
```

Every Job usually receives its own workspace.

---

# Connecting an SSH Agent

Install Java on the remote server.

Generate an SSH key.

```bash
ssh-keygen
```

Copy the public key.

```bash
ssh-copy-id jenkins@agent-server
```

Add the server in Jenkins.

```
Manage Jenkins

↓

Nodes

↓

New Node
```

Provide:

- Hostname
- Credentials
- Remote Root Directory
- Labels

---

# Agent Connection

```
Controller

↓

SSH

↓

Authentication

↓

Connected

↓

Ready
```

---

# Offline Agent

Sometimes an Agent becomes unavailable.

Example

```
Controller

↓

Agent

↓

Offline
```

Possible reasons:

- Network Failure
- SSH Failure
- Java Not Running
- Disk Full
- System Shutdown

---

# Monitor Agent Health

Monitor:

- CPU Usage
- Memory Usage
- Disk Space
- Network Connectivity
- Executor Utilization

Healthy Agents improve build reliability.

---

# Real Production Architecture

```
Developers

↓

GitHub

↓

Jenkins Controller

│

├── Linux Agent

├── Windows Agent

├── Docker Agent

├── Kubernetes Agent

└── Deployment Agent
```

Each Agent performs specialized tasks.

---

# Agent Selection Example

```
Java Build

↓

Java Agent

----------------

Docker Build

↓

Docker Agent

----------------

Windows Build

↓

Windows Agent
```

Jobs execute on the most appropriate Agent.

---

# Security

Do not grant unnecessary permissions.

Best practices:

✔ Dedicated Build Users

✔ SSH Keys

✔ Restricted Network Access

✔ Least Privilege

✔ Regular Updates

---

# Scaling with Agents

Instead of upgrading one server,

add more Agents.

```
Controller

↓

Agent 1

↓

Agent 2

↓

Agent 3

↓

Agent 4
```

Horizontal scaling improves throughput.

---

# Common Beginner Mistakes

### Mistake 1

Running every build on the Controller.

Use dedicated Agents.

---

### Mistake 2

Giving every Agent administrator privileges.

Grant only required permissions.

---

### Mistake 3

Using one Agent for every technology.

Create specialized Agents.

---

### Mistake 4

Ignoring offline Agents.

Investigate connectivity and resource issues immediately.

---

### Mistake 5

Configuring too many Executors.

Match executor count to available CPU and memory.

---

# Interview Questions

### Q1. What is a Jenkins Agent?

A Jenkins Agent is a machine that executes build, test and deployment tasks assigned by the Jenkins Controller.

---

### Q2. Why are Jenkins Agents needed?

They distribute workloads, improve scalability and reduce build times.

---

### Q3. Name four types of Jenkins Agents.

- Static Agent
- SSH Agent
- Docker Agent
- Kubernetes Agent

---

### Q4. What is an Agent Label?

A label identifies an Agent so jobs can run on the correct machine.

---

### Q5. What is an Executor?

An Executor is a worker thread that runs one Jenkins Job at a time.

---

### Q6. Why are Docker and Kubernetes Agents popular?

They provide clean, isolated and scalable build environments.

---

# Production Best Practices

✔ Keep Controllers dedicated to orchestration.

✔ Use specialized Agents.

✔ Secure Agents with SSH keys.

✔ Monitor Agent health continuously.

✔ Configure appropriate executor counts.

✔ Use Docker or Kubernetes Agents where appropriate.

✔ Keep Agent software updated.

✔ Remove unused Agents regularly.

---

# Key Takeaways

- Jenkins Agents execute workloads while the Controller manages the system.
- Distributed builds improve performance and scalability.
- Docker and Kubernetes Agents provide modern, reproducible build environments.
- Labels allow jobs to target the correct Agent.
- A well-designed Agent architecture is essential for enterprise Jenkins deployments.

---

# Next Section

## 7.14 Jenkins Plugins

In the next section, we will learn:

- What are Jenkins Plugins?
- Plugin Architecture
- Installing Plugins
- Updating Plugins
- Popular Jenkins Plugins
- Plugin Management
- Security Considerations
- Production Best Practices
- Interview Questions
---

# 7.14 Jenkins Plugins

Jenkins is powerful by itself,

but its real strength comes from its **Plugin Ecosystem**.

Plugins allow Jenkins to integrate with almost every DevOps tool,

including:

- Git
- Docker
- Kubernetes
- Maven
- Gradle
- SonarQube
- AWS
- Azure
- Slack
- Terraform
- Ansible

Without plugins,

Jenkins would only provide basic automation.

---

# What is a Jenkins Plugin?

A Jenkins Plugin is an extension that adds new features and integrations to Jenkins.

Plugins enable Jenkins to:

- Connect with external tools
- Add new build capabilities
- Improve the user interface
- Support additional programming languages
- Automate deployments

Think of plugins as apps installed on a smartphone.

---

# Plugin Architecture

```
Jenkins Core

↓

Plugins

├── Git

├── Docker

├── Pipeline

├── Maven

├── Kubernetes

├── Slack

└── SonarQube
```

The Jenkins Core provides the foundation,

while plugins extend functionality.

---

# Why Plugins are Needed?

Without plugins

```
Jenkins

↓

Limited Features
```

With plugins

```
Jenkins

↓

Thousands of Integrations
```

Plugins make Jenkins highly flexible.

---

# Popular Jenkins Plugins

Some of the most commonly used plugins are:

| Plugin | Purpose |
|---------|----------|
| Git Plugin | Git Integration |
| Pipeline Plugin | Pipeline Support |
| Docker Plugin | Docker Integration |
| Kubernetes Plugin | Kubernetes Integration |
| Maven Integration Plugin | Maven Builds |
| SSH Agent Plugin | SSH Authentication |
| Credentials Plugin | Secure Credential Management |
| Blue Ocean | Modern Pipeline UI |
| Email Extension Plugin | Email Notifications |
| Slack Notification Plugin | Slack Alerts |
| SonarQube Scanner Plugin | Code Quality Analysis |
| Workspace Cleanup Plugin | Workspace Cleanup |

---

# Plugin Workflow

```
Developer

↓

Jenkins

↓

Plugin

↓

External Tool

↓

Result
```

Example

```
Git Plugin

↓

GitHub

↓

Clone Repository
```

---

# Plugin Manager

Plugins are managed from:

```
Manage Jenkins

↓

Plugins
```

The Plugin Manager allows you to:

- Install Plugins
- Update Plugins
- Remove Plugins
- View Installed Plugins

---

# Plugin Sections

The Plugin Manager contains:

```
Available Plugins

↓

Installed Plugins

↓

Updates

↓

Advanced
```

Each section serves a different purpose.

---

# Installing a Plugin

Navigate to:

```
Manage Jenkins

↓

Plugins

↓

Available Plugins
```

Search for the desired plugin.

Example

```
Docker
```

Select it and click:

```
Install
```

---

# Restart After Installation

Some plugins become available immediately.

Others require:

```
Restart Jenkins
```

Always verify plugin documentation.

---

# Updating Plugins

Regularly update plugins.

Navigate to:

```
Manage Jenkins

↓

Plugins

↓

Updates
```

Select the required updates.

Click:

```
Update
```

---

# Removing Plugins

Unused plugins should be removed.

Navigate to:

```
Manage Jenkins

↓

Plugins

↓

Installed Plugins
```

Select the plugin.

Click:

```
Uninstall
```

Only remove plugins after confirming that no jobs depend on them.

---

# Git Plugin

Purpose

```
Git Repository

↓

Checkout Code

↓

Build
```

Almost every Jenkins installation uses this plugin.

---

# Pipeline Plugin

Enables

```
Jenkinsfile

↓

Pipeline Execution
```

Without this plugin,

Pipeline Jobs cannot run.

---

# Docker Plugin

Provides Docker integration.

Example

```
Pipeline

↓

Docker Build

↓

Docker Push

↓

Deployment
```

---

# Kubernetes Plugin

Automatically creates temporary build agents.

```
Jenkins

↓

Kubernetes

↓

Temporary Pod

↓

Build

↓

Pod Removed
```

This improves scalability.

---

# Credentials Plugin

Securely stores:

- Passwords
- Tokens
- SSH Keys
- API Keys

Never store secrets directly inside jobs.

---

# Blue Ocean Plugin

Provides a modern pipeline visualization interface.

Features include:

- Visual Pipeline View
- Build History
- Stage Progress
- Easy Navigation

Note:

Blue Ocean is still widely used, but it is in maintenance mode and many teams continue using the classic Jenkins UI or alternative visualization plugins.

---

# SonarQube Plugin

Automatically performs code quality analysis.

Workflow

```
Build

↓

SonarQube Scan

↓

Quality Report
```

---

# Slack Plugin

Automatically sends notifications.

Example

```
Build Failed

↓

Slack Message
```

Teams receive immediate updates.

---

# Email Extension Plugin

Sends emails such as:

```
Build Successful

↓

Developer

------------------

Build Failed

↓

Development Team
```

---

# Plugin Dependencies

Some plugins require other plugins.

Example

```
Plugin A

↓

Plugin B

↓

Plugin C
```

The Plugin Manager installs required dependencies automatically.

---

# Plugin Compatibility

Always verify compatibility before updating.

Check:

- Jenkins Version
- Java Version
- Plugin Version

Incompatible plugins may cause build failures or startup issues.

---

# Plugin Security

Plugins execute code inside Jenkins.

Only install plugins from trusted sources.

Keep plugins updated to receive security fixes.

---

# Plugin Backup

Before major plugin upgrades,

back up:

```
JENKINS_HOME
```

This allows recovery if an update causes problems.

---

# Real Production Example

```
GitHub

↓

Git Plugin

↓

Pipeline Plugin

↓

Docker Plugin

↓

SonarQube Plugin

↓

Slack Plugin

↓

Deployment
```

Multiple plugins work together during one CI/CD pipeline.

---

# Plugin Lifecycle

```
Install

↓

Configure

↓

Use

↓

Update

↓

Monitor

↓

Replace or Remove
```

Plugins should be reviewed periodically.

---

# Common Beginner Mistakes

### Mistake 1

Installing every available plugin.

Install only what is actually needed.

---

### Mistake 2

Ignoring plugin updates.

Outdated plugins may contain security vulnerabilities.

---

### Mistake 3

Updating all plugins directly in production.

Test updates in a non-production environment whenever possible.

---

### Mistake 4

Installing plugins from untrusted sources.

Use trusted plugins from the official Jenkins Update Center.

---

### Mistake 5

Removing plugins without checking dependencies.

This can break existing jobs and pipelines.

---

# Interview Questions

### Q1. What is a Jenkins Plugin?

A Jenkins Plugin extends Jenkins by adding new features or integrations.

---

### Q2. Where are plugins managed?

```
Manage Jenkins

↓

Plugins
```

---

### Q3. Which plugin enables Git integration?

```
Git Plugin
```

---

### Q4. Why is the Credentials Plugin important?

It securely stores sensitive information such as passwords, API tokens and SSH keys.

---

### Q5. Why should plugins be updated regularly?

To receive bug fixes, compatibility improvements and security patches.

---

### Q6. Why should unnecessary plugins be removed?

They increase maintenance complexity, consume resources and may introduce security risks.

---

# Production Best Practices

✔ Install only required plugins.

✔ Keep plugins updated.

✔ Test plugin updates before production.

✔ Back up `JENKINS_HOME` before major upgrades.

✔ Use trusted plugins.

✔ Monitor plugin compatibility.

✔ Remove unused plugins.

✔ Review security advisories regularly.

---

# Key Takeaways

- Plugins make Jenkins highly extensible.
- The Plugin Manager simplifies installation and maintenance.
- Popular plugins integrate Jenkins with Git, Docker, Kubernetes and many other tools.
- Plugin security and compatibility are important operational concerns.
- A carefully managed plugin ecosystem improves both functionality and stability.

---

# Next Section

## 7.15 Jenkins Credentials Management

In the next section, we will learn:

- What are Jenkins Credentials?
- Types of Credentials
- Username & Password
- SSH Keys
- API Tokens
- Secret Text
- Secret Files
- Using Credentials in Pipelines
- Best Practices
- Interview Questions
---

# 7.15 Jenkins Credentials Management

Modern CI/CD pipelines interact with many external systems.

For example,

- GitHub
- Docker Hub
- AWS
- Azure
- Kubernetes
- Databases
- APIs
- SSH Servers

These systems require authentication.

A common beginner mistake is storing usernames and passwords directly inside Jenkins Jobs or Jenkinsfiles.

This is insecure.

Jenkins solves this problem using **Credentials Management**.

---

# What are Jenkins Credentials?

Jenkins Credentials are secure objects used to store sensitive information.

Examples include:

- Username
- Password
- SSH Private Keys
- API Tokens
- Secret Text
- Secret Files
- Certificates

Instead of exposing secrets inside pipeline code,

Jenkins retrieves them securely during execution.

---

# Why Credentials are Needed?

Without Credentials Management

```
Pipeline

↓

Username

↓

Password

↓

Visible to Everyone
```

Major security risk.

---

With Jenkins Credentials

```
Pipeline

↓

Credentials ID

↓

Secure Storage

↓

Authentication
```

Passwords remain hidden.

---

# Credentials Workflow

```
Developer

↓

Pipeline

↓

Credentials ID

↓

Jenkins Credentials Store

↓

External System

↓

Authentication Successful
```

---

# Types of Jenkins Credentials

Jenkins supports several credential types.

```
Credentials

│

├── Username & Password

├── SSH Username with Private Key

├── Secret Text

├── Secret File

├── Certificate

└── Docker Registry Credentials
```

Each type is designed for different authentication methods.

---

# Username & Password

Most commonly used.

Examples

- GitHub
- Docker Hub
- Nexus Repository
- Database Login

Stored securely.

---

# SSH Private Key

Used for

- Linux Servers
- Git Repositories
- Deployment Servers

Instead of passwords,

SSH Keys provide stronger authentication.

---

# Secret Text

Stores

- API Keys
- Tokens
- License Keys
- Access Tokens

Example

```
GitHub Personal Access Token

AWS Token

Slack Token
```

---

# Secret File

Stores secure files.

Examples

- Kubernetes kubeconfig
- SSL Certificates
- JSON Service Accounts
- License Files

Jenkins temporarily makes the file available during pipeline execution.

---

# Certificate Credentials

Used for:

- SSL Certificates
- PKCS#12 Certificates
- Mutual TLS Authentication

Common in enterprise environments.

---

# Docker Registry Credentials

Store:

- Docker Username
- Docker Password
- Docker Personal Access Token

Used during:

```
docker login
```

inside Jenkins Pipelines.

---

# Credentials Scope

Credentials can be stored in different scopes.

```
Global

↓

Folder

↓

System
```

---

# Global Credentials

Available to all Jobs.

Example

```
GitHub Token

↓

Every Pipeline
```

Use carefully.

---

# Folder Credentials

Available only inside a specific Folder.

Example

```
Production Folder

↓

Production Credentials
```

Improves security through isolation.

---

# System Credentials

Used internally by Jenkins.

Normally,

users do not reference these credentials directly.

---

# Adding Credentials

Navigate to

```
Manage Jenkins

↓

Credentials

↓

System

↓

Global Credentials

↓

Add Credentials
```

Choose:

- Type
- Username
- Password / Secret
- ID
- Description

Save.

---

# Credential ID

Every credential has an ID.

Example

```
github-token

dockerhub

aws-prod

kubeconfig-prod
```

Pipelines reference this ID.

---

# Using Credentials in Pipeline

Example

```groovy
environment {

    GITHUB_TOKEN = credentials('github-token')

}
```

Jenkins securely injects the credential.

---

# Username & Password Example

```groovy
withCredentials([

usernamePassword(

credentialsId: 'dockerhub',

usernameVariable: 'USER',

passwordVariable: 'PASS'

)

]) {

    sh 'echo $PASS | docker login -u $USER --password-stdin'

}
```

Credentials remain masked in logs.

---

# Secret Text Example

```groovy
withCredentials([

string(

credentialsId: 'api-token',

variable: 'TOKEN'

)

]) {

    sh 'curl -H "Authorization: Bearer $TOKEN" https://api.example.com'

}
```

Useful for REST APIs.

---

# SSH Key Example

```groovy
withCredentials([

sshUserPrivateKey(

credentialsId: 'ssh-key',

keyFileVariable: 'SSH_KEY'

)

]) {

    sh 'ssh -i $SSH_KEY server'

}
```

---

# Secret File Example

```groovy
withCredentials([

file(

credentialsId: 'kubeconfig',

variable: 'KUBECONFIG'

)

]) {

    sh 'kubectl get pods'

}
```

---

# Credentials Masking

Suppose password is

```
Admin123
```

Console Output

```
******
```

Jenkins automatically masks many secrets to reduce accidental exposure in logs.

---

# Credentials in Environment Variables

Instead of

```groovy
PASSWORD="Admin123"
```

Use

```groovy
credentials('db-password')
```

Much safer.

---

# Credentials with Git

Example

```
GitHub

↓

Personal Access Token

↓

Jenkins Credentials

↓

Git Clone
```

No password appears inside the pipeline.

---

# Credentials with Docker

```
Docker Hub

↓

Credentials

↓

docker login

↓

docker push
```

Everything is automated securely.

---

# Credentials with AWS

Store

- Access Key ID
- Secret Access Key

Use them inside deployment pipelines.

Never commit AWS keys into Git repositories.

---

# Credentials with Kubernetes

Store

```
kubeconfig
```

as a Secret File.

Jenkins loads it only during pipeline execution.

---

# Real Production Example

```
GitHub

↓

Git Token

↓

Jenkins

↓

Docker Hub

↓

Docker Credentials

↓

AWS

↓

AWS Credentials

↓

Production
```

Each system has its own dedicated credentials.

---

# Security Best Practices

✔ Separate Development and Production Credentials

✔ Rotate Secrets Regularly

✔ Use Least Privilege

✔ Remove Unused Credentials

✔ Audit Credential Usage

✔ Use Folder-Level Credentials Where Appropriate

---

# Credential Rotation

Old Token

↓

Generate New Token

↓

Update Jenkins Credentials

↓

Test Pipeline

↓

Delete Old Token

Regular rotation reduces long-term risk.

---

# Common Beginner Mistakes

### Mistake 1

Hardcoding passwords inside Jenkinsfiles.

---

### Mistake 2

Committing secrets into Git repositories.

---

### Mistake 3

Sharing one credential across every project.

---

### Mistake 4

Using administrator credentials for every pipeline.

---

### Mistake 5

Never rotating API tokens.

---

# Interview Questions

### Q1. What are Jenkins Credentials?

Jenkins Credentials securely store sensitive information used by jobs and pipelines.

---

### Q2. Name four Jenkins credential types.

- Username & Password
- SSH Private Key
- Secret Text
- Secret File

---

### Q3. Why should passwords never be hardcoded inside Jenkinsfiles?

Hardcoded passwords expose sensitive information and create security risks.

---

### Q4. What is a Credentials ID?

A unique identifier used by pipelines to securely reference stored credentials.

---

### Q5. Why should production and development credentials be separated?

To reduce security risks and limit access to sensitive production systems.

---

### Q6. How does Jenkins help protect credentials in console logs?

Jenkins masks supported secrets so they are not displayed in plain text.

---

# Production Best Practices

✔ Use Jenkins Credentials for every secret.

✔ Never hardcode passwords.

✔ Rotate credentials regularly.

✔ Apply the Principle of Least Privilege.

✔ Audit credential usage.

✔ Use Folder-level credentials where appropriate.

✔ Separate development and production secrets.

✔ Remove unused credentials immediately.

---

# Key Takeaways

- Jenkins Credentials securely manage sensitive information.
- Pipelines should reference Credentials IDs instead of embedding secrets.
- Different credential types support different authentication methods.
- Secure credential management is essential for production CI/CD.
- Proper credential handling significantly reduces security risks.

---

# Next Section

## 7.16 Jenkins Security

In the next section, we will learn:

- Jenkins Security Fundamentals
- Authentication
- Authorization
- Matrix-Based Security
- Role-Based Access Control (RBAC)
- CSRF Protection
- Agent Security
- Backup & Recovery
- Best Practices
- Interview Questions
---

# 7.16 Jenkins Security

Jenkins is one of the most powerful automation tools,

which also makes it an attractive target for attackers.

A compromised Jenkins server can expose:

- Source Code
- Credentials
- Production Servers
- Docker Registries
- Cloud Infrastructure
- Kubernetes Clusters

For this reason,

security should be considered from the very first installation.

---

# Why Jenkins Security Matters?

Imagine this scenario:

```
Internet

↓

Jenkins

↓

GitHub

↓

AWS

↓

Production
```

If an attacker gains access to Jenkins,

they may also gain access to every connected system.

---

# Security Goals

A secure Jenkins environment should provide:

✔ Authentication

✔ Authorization

✔ Encryption

✔ Auditability

✔ Backup

✔ Secure Credentials

✔ Secure Agents

✔ Secure Pipelines

---

# Jenkins Security Workflow

```
User

↓

Authentication

↓

Authorization

↓

Jenkins

↓

Pipeline

↓

Deployment
```

Only authenticated and authorized users should perform actions.

---

# Authentication

Authentication answers the question:

> **Who are you?**

Examples

- Username & Password
- LDAP
- Active Directory
- OAuth
- GitHub Login
- SAML

---

# Authorization

Authorization answers:

> **What are you allowed to do?**

Example

```
Developer

↓

Build Jobs

----------------

Administrator

↓

Everything

----------------

Viewer

↓

Read Only
```

---

# Security Realm

The Security Realm defines how users log in.

Common options:

- Jenkins User Database
- LDAP
- Active Directory
- GitHub OAuth
- SAML

Small organizations often use the built-in database.

Enterprises commonly integrate with centralized identity providers.

---

# Authorization Strategies

Jenkins supports multiple authorization models.

Examples

- Logged-in Users
- Matrix-based Security
- Project-based Matrix Security
- Role-Based Access Control (RBAC)

---

# Matrix-Based Security

Permissions are granted individually.

Example

| User | Read | Build | Configure | Admin |
|------|------|-------|-----------|-------|
| Developer | ✔ | ✔ | ✖ | ✖ |
| Tester | ✔ | ✔ | ✖ | ✖ |
| Admin | ✔ | ✔ | ✔ | ✔ |

---

# Role-Based Access Control (RBAC)

Instead of assigning permissions one by one,

assign roles.

```
Admin

↓

Developer

↓

Tester

↓

Viewer
```

Users inherit permissions from their assigned role.

---

# Principle of Least Privilege

Every user should receive only the permissions required.

Example

Bad

```
Everyone

↓

Administrator
```

Good

```
Developer

↓

Build Permission Only
```

---

# Secure Credentials

Never store:

- Passwords
- Tokens
- API Keys
- SSH Keys

inside:

- Jenkinsfiles
- Job Configurations
- Shell Scripts

Use Jenkins Credentials Manager instead.

---

# Enable HTTPS

Never expose Jenkins using plain HTTP in production.

Instead

```
Browser

↓

HTTPS

↓

Reverse Proxy

↓

Jenkins
```

Common reverse proxies:

- Nginx
- Apache HTTP Server

HTTPS protects authentication and session data.

---

# Reverse Proxy

Production deployments usually place Jenkins behind:

```
Internet

↓

Nginx

↓

Jenkins
```

Benefits:

- HTTPS
- Rate Limiting
- Access Control
- Better Security

---

# CSRF Protection

Jenkins supports protection against:

```
Cross-Site Request Forgery (CSRF)
```

Enable CSRF protection in:

```
Manage Jenkins

↓

Security
```

---

# Agent Security

Only trusted Agents should connect.

Best practices:

✔ SSH Authentication

✔ Agent Isolation

✔ Firewall Rules

✔ Dedicated Build Users

---

# Secure Plugins

Plugins execute code.

Therefore:

✔ Install only trusted plugins.

✔ Remove unused plugins.

✔ Keep plugins updated.

---

# Secure Pipelines

Avoid

```groovy
sh "echo MyPassword"
```

Instead

```groovy
withCredentials(...)
```

Never expose secrets in pipeline logs.

---

# Build Isolation

Each build should run in an isolated environment.

Examples:

- Docker Containers
- Kubernetes Pods
- Dedicated Virtual Machines

Isolation prevents one build from affecting another.

---

# Audit Logs

Track:

- User Logins
- Configuration Changes
- Job Executions
- Plugin Installations
- Failed Login Attempts

Audit logs help investigate incidents.

---

# Backup Strategy

Back up:

```
JENKINS_HOME

↓

Jobs

↓

Credentials

↓

Plugins

↓

Configuration
```

Regular backups reduce recovery time after failures.

---

# Disaster Recovery

Example

```
Server Failure

↓

Restore Backup

↓

Start Jenkins

↓

Resume Pipelines
```

Recovery procedures should be tested periodically.

---

# Secure Network Design

```
Internet

↓

Firewall

↓

Reverse Proxy

↓

Jenkins

↓

Private Agents

↓

Private Network
```

Avoid exposing internal build agents directly to the internet.

---

# User Management

Regularly review:

- Active Users
- Administrator Accounts
- API Tokens
- SSH Keys

Remove inactive accounts promptly.

---

# Password Policy

Use strong passwords.

Example requirements:

- Minimum 12 Characters
- Uppercase Letters
- Lowercase Letters
- Numbers
- Special Characters

Prefer Multi-Factor Authentication (MFA) when supported by the authentication provider.

---

# Security Updates

Keep updated:

- Jenkins LTS
- Java
- Plugins
- Operating System

Security patches should be applied regularly after testing.

---

# Real Production Architecture

```
Developer

↓

GitHub

↓

Jenkins (HTTPS)

↓

Docker Build

↓

Image Scan

↓

Kubernetes

↓

Production
```

Every component follows security best practices.

---

# Common Security Risks

- Weak Passwords
- Exposed API Tokens
- Public Jenkins Server
- Outdated Plugins
- Hardcoded Secrets
- Excessive Administrator Privileges

---

# Common Beginner Mistakes

### Mistake 1

Running Jenkins without authentication.

---

### Mistake 2

Giving administrator access to every user.

---

### Mistake 3

Disabling CSRF protection.

---

### Mistake 4

Keeping secrets inside Git repositories.

---

### Mistake 5

Ignoring Jenkins and plugin updates.

---

# Interview Questions

### Q1. Why is Jenkins security important?

Because Jenkins often has access to source code, credentials and production infrastructure.

---

### Q2. What is the difference between authentication and authorization?

Authentication verifies identity.

Authorization determines permissions.

---

### Q3. What is the Principle of Least Privilege?

Users should receive only the permissions necessary to perform their work.

---

### Q4. Why should Jenkins use HTTPS?

HTTPS encrypts communication and protects user credentials.

---

### Q5. Why should Jenkins be placed behind a reverse proxy?

To improve security, enable HTTPS and provide better access control.

---

### Q6. What should always be backed up?

`JENKINS_HOME`, including jobs, credentials, plugins and configuration.

---

# Production Best Practices

✔ Enable authentication.

✔ Use Role-Based Access Control.

✔ Enable HTTPS.

✔ Store secrets in Jenkins Credentials.

✔ Keep plugins updated.

✔ Back up Jenkins regularly.

✔ Audit user activity.

✔ Use isolated build agents.

✔ Follow the Principle of Least Privilege.

✔ Perform regular security reviews.

---

# Key Takeaways

- Jenkins security protects your CI/CD infrastructure and connected systems.
- Authentication and authorization should always be enabled.
- Secrets must be managed through the Credentials Manager.
- HTTPS, backups and regular updates are essential for production environments.
- A secure Jenkins installation is critical for reliable enterprise DevOps.

---

# Next Section

## 7.17 Jenkins Best Practices

In the next section, we will learn:

- Project Organization
- Pipeline Design
- Folder Structure
- Agent Strategy
- Build Optimization
- Security Best Practices
- Backup Strategy
- Monitoring
- Enterprise Recommendations
- Interview Questions
---

# 7.17 Jenkins Best Practices

Installing Jenkins is only the first step.

A production Jenkins environment should be:

- Reliable
- Secure
- Scalable
- Maintainable
- Fast

Following best practices helps teams avoid failures, reduce maintenance effort and improve software delivery.

---

# Why Best Practices Matter?

Imagine two organizations.

Company A

```
No Standards

↓

Random Jobs

↓

Hardcoded Passwords

↓

Manual Deployments

↓

Frequent Failures
```

Company B

```
Standard Pipelines

↓

Version Control

↓

Automation

↓

Monitoring

↓

Reliable Deployments
```

The difference is good engineering practices.

---

# Organize Projects

Avoid placing every Job on the Jenkins home page.

Instead organize projects.

```
Jenkins

│

├── Development

├── Testing

├── Staging

├── Production

└── Infrastructure
```

Folders improve navigation and access control.

---

# Use Pipelines Instead of Freestyle Jobs

For production environments,

prefer:

```
Pipeline Jobs
```

instead of

```
Freestyle Jobs
```

Pipelines are:

- Version Controlled
- Reusable
- Easier to Maintain
- Better for Complex Workflows

---

# Store Jenkinsfiles in Git

Good

```
Project

│

├── Source Code

└── Jenkinsfile
```

Avoid storing pipeline logic only inside Jenkins.

---

# Use Meaningful Names

Good

```
frontend-build

backend-test

docker-build

deploy-production
```

Bad

```
job1

newjob

test

final-final
```

Clear naming improves maintenance.

---

# Use Build Agents

Never overload the Jenkins Controller.

Instead

```
Controller

↓

Linux Agent

↓

Docker Agent

↓

Windows Agent
```

The Controller should coordinate builds,

not perform every task itself.

---

# Keep Pipelines Small

Large monolithic pipelines are difficult to maintain.

Instead

```
Checkout

↓

Build

↓

Test

↓

Security Scan

↓

Package

↓

Deploy
```

Each stage should have one clear responsibility.

---

# Version Everything

Version control:

- Source Code
- Jenkinsfile
- Infrastructure Code
- Deployment Scripts
- Configuration Files

Everything should be reproducible.

---

# Secure Credentials

Never write:

```groovy
PASSWORD="admin123"
```

Use:

```
Jenkins Credentials
```

All secrets should remain outside the source code.

---

# Keep Plugins Minimal

Only install required plugins.

Benefits:

- Better Performance
- Reduced Security Risks
- Easier Maintenance

Review plugins regularly.

---

# Keep Jenkins Updated

Regularly update:

- Jenkins LTS
- Java
- Plugins
- Operating System

Always test updates before applying them to production.

---

# Monitor Build Health

Track:

- Build Success Rate
- Build Failures
- Build Duration
- Queue Length
- Agent Utilization

Monitoring helps detect problems early.

---

# Archive Artifacts

Important artifacts should be archived.

Examples

```
JAR

WAR

ZIP

Reports

Test Results
```

Artifacts support deployment, auditing and rollback.

---

# Backup Jenkins

Regularly back up:

```
JENKINS_HOME

↓

Jobs

↓

Credentials

↓

Plugins

↓

Configuration
```

Store backups securely and test restoration procedures.

---

# Use Separate Environments

Do not deploy directly to production.

Typical workflow

```
Development

↓

Testing

↓

Staging

↓

Production
```

Each environment validates the application before the next stage.

---

# Automate Testing

Every pipeline should include automated tests.

Examples

- Unit Tests
- Integration Tests
- Security Scans
- Code Quality Checks

Failures should stop the deployment process.

---

# Use Parallel Stages

Independent tasks can run simultaneously.

```
Backend Tests

↓

Frontend Tests

↓

Security Scan

↓

Merge Results
```

Parallel execution reduces total pipeline time.

---

# Keep Logs

Retain:

- Build Logs
- Test Reports
- Deployment Logs
- Audit Logs

Logs are essential for troubleshooting.

---

# Clean Workspaces

Temporary files should be removed after builds.

Example

```groovy
post {

    always {

        cleanWs()

    }

}
```

A clean workspace reduces disk usage and prevents stale files from affecting future builds.

---

# Implement Notifications

Notify teams when builds:

- Succeed
- Fail
- Become Unstable

Common channels:

- Email
- Slack
- Microsoft Teams

Fast feedback improves response time.

---

# Standardize Pipeline Templates

Large organizations often create reusable pipeline templates.

```
Shared Library

↓

Pipeline

↓

Application
```

This reduces duplication and promotes consistency.

---

# Use Shared Libraries

Avoid copying identical pipeline code into many repositories.

Instead,

store reusable functions in Jenkins Shared Libraries.

Benefits include:

- Easier maintenance
- Code reuse
- Standardized practices

---

# Manage Resource Usage

Monitor:

- CPU
- Memory
- Disk
- Executors
- Network

Avoid oversubscribing build agents.

---

# Secure Jenkins

Security best practices include:

✔ HTTPS

✔ RBAC

✔ Credential Management

✔ Secure Agents

✔ Least Privilege

✔ Regular Updates

---

# Disaster Recovery Plan

Always prepare for failures.

```
Server Failure

↓

Restore Backup

↓

Start Jenkins

↓

Verify Jobs

↓

Resume CI/CD
```

Test recovery procedures periodically.

---

# Real Enterprise Workflow

```
Developer

↓

GitHub

↓

Webhook

↓

Jenkins

↓

Unit Tests

↓

SonarQube

↓

Docker Build

↓

Image Scan

↓

Deploy Staging

↓

Approval

↓

Deploy Production
```

Each stage follows organizational standards.

---

# Common Beginner Mistakes

### Mistake 1

Creating hundreds of unmanaged jobs.

---

### Mistake 2

Running every build on the Controller.

---

### Mistake 3

Ignoring failed builds.

---

### Mistake 4

Never cleaning workspaces.

---

### Mistake 5

Installing unnecessary plugins.

---

### Mistake 6

Skipping backups.

---

### Mistake 7

Hardcoding credentials.

---

### Mistake 8

Deploying directly to production without testing.

---

# Interview Questions

### Q1. Why are Jenkins Pipelines preferred over Freestyle Jobs?

Pipelines are version-controlled, reusable, easier to maintain and better suited for complex CI/CD workflows.

---

### Q2. Why should Jenkinsfiles be stored in Git?

To enable version control, collaboration, auditing and reproducible builds.

---

### Q3. Why should the Jenkins Controller avoid running builds?

Running builds on dedicated agents improves scalability, performance and reliability.

---

### Q4. Why should workspaces be cleaned after builds?

Cleaning workspaces prevents stale files from affecting future builds and helps manage disk usage.

---

### Q5. Why should organizations use Shared Libraries?

Shared Libraries reduce duplicated pipeline code and standardize CI/CD practices.

---

### Q6. What are the most important Jenkins production practices?

- Secure credentials
- Regular backups
- Monitoring
- Automated testing
- Version-controlled pipelines

---

# Production Best Practices

✔ Use Pipeline as Code.

✔ Store Jenkinsfiles in Git.

✔ Organize jobs into folders.

✔ Run builds on Agents.

✔ Automate testing.

✔ Archive artifacts.

✔ Monitor build health.

✔ Back up Jenkins regularly.

✔ Keep plugins updated.

✔ Apply security best practices.

---

# Key Takeaways

- Well-designed Jenkins environments are reliable, secure and maintainable.
- Pipeline as Code improves collaboration and reproducibility.
- Monitoring, backups and security are as important as automation.
- Build agents improve scalability and performance.
- Following best practices leads to faster, safer and more predictable software delivery.

---

# Next Section

## 7.18 Jenkins in Production

In the next section, we will learn:

- Enterprise Jenkins Architecture
- High Availability
- Scaling Jenkins
- Backup & Disaster Recovery
- Monitoring & Logging
- CI/CD at Scale
- Security Hardening
- Production Checklist
- Interview Questions
- Chapter Summary
---

# 7.18 Jenkins in Production

Installing Jenkins is easy.

Running Jenkins reliably for hundreds of developers,

thousands of builds,

and multiple production deployments every day

is a completely different challenge.

Enterprise Jenkins environments require:

- High Availability
- Scalability
- Security
- Monitoring
- Backup
- Disaster Recovery
- Standardized Pipelines

This section explains how Jenkins is used in real production environments.

---

# Enterprise Jenkins Architecture

A typical enterprise architecture looks like this:

```
Developers

↓

GitHub / GitLab

↓

Load Balancer

↓

Jenkins Controller

↓

Build Queue

↓

Linux Agents

↓

Windows Agents

↓

Docker Agents

↓

Kubernetes Agents

↓

Artifact Repository

↓

Production
```

Each component has a dedicated responsibility.

---

# High Availability

The Jenkins Controller is a critical service.

If it becomes unavailable,

builds and deployments stop.

Organizations improve availability by using:

- Reliable Infrastructure
- Frequent Backups
- Fast Recovery Procedures
- External Storage
- Monitoring

Although Jenkins does not provide built-in active-active controller clustering,

high availability is commonly achieved through infrastructure resilience and recovery planning.

---

# Scaling Jenkins

As build demand increases,

instead of using one powerful server,

organizations add more build agents.

```
Controller

↓

Agent-1

↓

Agent-2

↓

Agent-3

↓

Agent-4
```

This enables parallel builds.

---

# Dynamic Cloud Agents

Modern Jenkins installations use cloud-based agents.

Example

```
Pipeline Starts

↓

Kubernetes Pod Created

↓

Build Executes

↓

Pod Deleted
```

Resources are created only when required.

---

# Production Pipeline

```
Developer

↓

Git Push

↓

Webhook

↓

Jenkins

↓

Checkout

↓

Build

↓

Unit Tests

↓

Security Scan

↓

Docker Build

↓

Push Registry

↓

Deploy Staging

↓

Approval

↓

Deploy Production
```

Every stage is automated and auditable.

---

# Artifact Management

Successful builds create artifacts.

Examples

- JAR
- WAR
- Docker Images
- ZIP Files

Artifacts are stored in repositories such as:

- Nexus Repository
- JFrog Artifactory
- GitHub Packages
- AWS CodeArtifact

Applications are deployed from artifacts,

not rebuilt on production servers.

---

# Build Isolation

Each build should execute in an isolated environment.

Examples

```
Docker Container

or

Kubernetes Pod

or

Dedicated Build Agent
```

Isolation improves consistency and security.

---

# Monitoring Jenkins

Monitor:

- Controller Health
- Agent Health
- CPU Usage
- Memory Usage
- Disk Usage
- Queue Length
- Build Duration
- Build Failure Rate

Monitoring helps identify bottlenecks before they impact developers.

---

# Logging

Collect logs centrally.

```
Jenkins

↓

Log Collector

↓

Elasticsearch

↓

Kibana
```

or

```
Jenkins

↓

Promtail

↓

Loki

↓

Grafana
```

Centralized logs simplify troubleshooting.

---

# Backup Strategy

Regularly back up:

```
JENKINS_HOME

↓

Jobs

↓

Plugins

↓

Credentials

↓

Users

↓

Configuration
```

Also back up:

- Shared Libraries
- Pipeline Code
- External Configuration

Test backups by performing restoration exercises.

---

# Disaster Recovery

Example

```
Controller Failure

↓

Provision New Server

↓

Install Jenkins

↓

Restore JENKINS_HOME

↓

Reconnect Agents

↓

Resume Pipelines
```

Document recovery procedures and test them periodically.

---

# Security Hardening

Production Jenkins should include:

✔ HTTPS

✔ RBAC

✔ Secure Credentials

✔ Agent Isolation

✔ Plugin Updates

✔ Audit Logging

✔ Firewall Rules

✔ Multi-Factor Authentication (through the organization's identity provider where supported)

---

# Network Architecture

```
Internet

↓

Reverse Proxy

↓

Firewall

↓

Jenkins Controller

↓

Private Agents

↓

Private Network
```

Avoid exposing the Controller directly to the internet whenever possible.

---

# Agent Strategy

Large organizations often dedicate agents for different workloads.

Example

```
Java Builds

↓

Java Agent

----------------

Docker Builds

↓

Docker Agent

----------------

Windows Builds

↓

Windows Agent

----------------

Deployment

↓

Deployment Agent
```

This improves efficiency.

---

# Shared Libraries

Instead of copying pipeline code into every repository,

organizations use:

```
Shared Library

↓

Reusable Functions

↓

Standard Pipelines
```

This improves consistency across teams.

---

# Build Governance

Production environments should enforce:

- Branch Protection
- Mandatory Code Reviews
- Automated Testing
- Security Scanning
- Approval Gates (where required)

These controls reduce deployment risk.

---

# Production Deployment Strategies

Common deployment strategies include:

- Rolling Deployment
- Blue-Green Deployment
- Canary Deployment

The appropriate strategy depends on application requirements and risk tolerance.

---

# Enterprise Toolchain

A typical enterprise CI/CD ecosystem:

```
GitHub

↓

Jenkins

↓

SonarQube

↓

Nexus

↓

Docker

↓

Kubernetes

↓

Prometheus

↓

Grafana
```

Jenkins orchestrates the workflow between these tools.

---

# Production Checklist

Before deploying Jenkins to production:

✔ HTTPS Enabled

✔ Authentication Enabled

✔ RBAC Configured

✔ Agents Configured

✔ Credentials Stored Securely

✔ Monitoring Enabled

✔ Logging Configured

✔ Backups Scheduled

✔ Disaster Recovery Documented

✔ Plugins Updated

✔ Pipelines Version Controlled

✔ Security Review Completed

---

# Real Enterprise Example

An e-commerce company has:

```
500 Developers

↓

GitHub Enterprise

↓

Jenkins

↓

300+ Pipelines

↓

Kubernetes

↓

AWS Production
```

Every code change automatically:

- Builds the application
- Runs unit tests
- Performs security scanning
- Creates Docker images
- Publishes artifacts
- Deploys to staging
- Waits for approval
- Deploys to production

Thousands of deployments can occur each month with minimal manual intervention.

---

# Common Beginner Mistakes

### Mistake 1

Running production Jenkins without backups.

---

### Mistake 2

Running every workload on the Controller.

---

### Mistake 3

Ignoring monitoring and alerting.

---

### Mistake 4

Allowing every developer administrator access.

---

### Mistake 5

Deploying directly to production without automated testing.

---

### Mistake 6

Keeping outdated plugins in production.

---

# Interview Questions

### Q1. Why do production Jenkins environments use build agents?

To distribute workloads, improve scalability and reduce build times.

---

### Q2. Why should artifacts be stored externally?

Artifacts become immutable deployment packages that support traceability and rollback.

---

### Q3. Why is monitoring important?

Monitoring detects failures, performance issues and resource bottlenecks before they affect CI/CD.

---

### Q4. Why should Jenkins use HTTPS?

HTTPS encrypts traffic and protects authentication credentials.

---

### Q5. Name three production deployment strategies.

- Rolling Deployment
- Blue-Green Deployment
- Canary Deployment

---

### Q6. What should always be backed up?

- `JENKINS_HOME`
- Jobs
- Plugins
- Credentials
- Configuration
- Shared Libraries

---

# Production Best Practices

✔ Use dedicated build agents.

✔ Store pipelines in Git.

✔ Monitor controller and agents.

✔ Schedule regular backups.

✔ Secure credentials.

✔ Keep plugins updated.

✔ Automate testing.

✔ Use deployment approval gates where appropriate.

✔ Document disaster recovery.

✔ Review security regularly.

---

# Key Takeaways

- Production Jenkins environments prioritize reliability, scalability and security.
- Build agents improve performance and parallelism.
- Monitoring, logging and backups are essential operational practices.
- Deployment pipelines should be automated, version-controlled and secure.
- A well-managed Jenkins platform enables consistent and reliable software delivery at enterprise scale.

---

# Chapter 7 Summary

Congratulations!

You have completed **Chapter 7 – Jenkins (CI/CD)**.

You learned:

- Jenkins Fundamentals
- CI/CD Concepts
- Why Jenkins
- Jenkins Architecture
- Installing Jenkins
- Jenkins Dashboard
- Jenkins Jobs
- Jenkins Pipelines
- Jenkinsfile
- Git Integration
- Docker Integration
- Build Automation
- Jenkins Agents
- Jenkins Plugins
- Jenkins Credentials Management
- Jenkins Security
- Jenkins Best Practices
- Jenkins in Production

You now understand how enterprise organizations build, test and deploy applications using Jenkins.

---

# Next Chapter

# Chapter 8 – Terraform (Infrastructure as Code)

In the next chapter, we will learn:

- What is Terraform?
- Why Infrastructure as Code (IaC)?
- Terraform Architecture
- Installing Terraform
- Providers
- Resources
- Variables
- State File
- Modules
- Provisioners
- Workspaces
- Remote State
- Terraform with AWS
- Best Practices
- Production Architecture
- Interview Questions
- Hands-on Projects
```