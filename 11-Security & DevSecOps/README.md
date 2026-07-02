# Chapter 11 – Security & DevSecOps

---

# Chapter Overview

Security is no longer a responsibility of only the Security Team.

Modern software is deployed:

- Multiple times a day
- Across Cloud Platforms
- Inside Containers
- On Kubernetes
- Using CI/CD Pipelines

If security is performed only at the end of development,

many vulnerabilities reach production.

To solve this problem,

organizations follow **DevSecOps**.

DevSecOps integrates security into every phase of the software development lifecycle.

Instead of treating security as a separate activity,

security becomes everyone's responsibility.

---

# What You Will Learn

In this chapter, you will learn:

- Security Fundamentals
- DevSecOps
- CIA Triad
- Authentication
- Authorization
- Encryption
- Hashing
- SSL/TLS
- Certificates
- Secrets Management
- HashiCorp Vault
- IAM
- Docker Security
- Kubernetes Security
- Image Scanning
- Vulnerability Management
- SAST
- DAST
- SCA
- Trivy
- OWASP Top 10
- Supply Chain Security
- Runtime Security
- Compliance
- Security Best Practices
- Production Scenarios
- Interview Questions

---

# Why Security Matters

Imagine a company launches an online banking application.

Thousands of users log in every minute.

They perform:

- Money Transfers
- Bill Payments
- Credit Card Payments
- Investments

Now imagine an attacker gains access to the application.

Possible consequences:

- Customer Data Theft
- Financial Loss
- Legal Penalties
- Reputation Damage
- Service Downtime

Security protects both businesses and customers from these risks.

---

# Evolution of Security

Initially,

security was performed only after software development.

```
Development

↓

Testing

↓

Security

↓

Production
```

Problems:

- Vulnerabilities discovered too late
- Expensive fixes
- Delayed releases

---

Modern DevSecOps integrates security throughout the lifecycle.

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

Operate

↓

Monitor

↓

Security Everywhere
```

---

# What is DevSecOps?

DevSecOps stands for:

```
Development

+

Security

+

Operations
```

It is the practice of integrating security into every stage of software delivery.

Security is automated and continuous rather than performed only before release.

---

# Traditional DevOps

```
Developers

↓

CI/CD

↓

Production

↓

Security Check (Late)
```

---

# DevSecOps

```
Developers

↓

Secure Coding

↓

Build

↓

Security Scan

↓

Testing

↓

Container Scan

↓

Deployment

↓

Runtime Security
```

Security checks happen continuously.

---

# DevSecOps Goals

A successful DevSecOps strategy aims to:

- Detect vulnerabilities early
- Automate security checks
- Reduce business risk
- Improve compliance
- Secure cloud infrastructure
- Protect applications
- Secure containers
- Protect customer data

---

# Why Companies Adopt DevSecOps

Organizations benefit from:

✔ Faster Secure Releases

✔ Early Vulnerability Detection

✔ Automated Security

✔ Compliance Support

✔ Reduced Risk

✔ Improved Customer Trust

✔ Lower Cost of Fixes

✔ Continuous Security

---

# DevSecOps Lifecycle

```
Plan

↓

Code

↓

Build

↓

Test

↓

Release

↓

Deploy

↓

Operate

↓

Monitor

↓

Improve
```

Security is integrated into every stage.

---

# Security Across the SDLC

| Phase | Security Activity |
|--------|-------------------|
| Planning | Threat Modeling |
| Coding | Secure Coding |
| Build | Dependency Scanning |
| Testing | SAST & DAST |
| Deployment | Image Scanning |
| Runtime | Monitoring & Protection |

---

# Shift Left Security

One of the most important DevSecOps concepts is:

```
Shift Left
```

Instead of finding security issues late,

find them earlier.

```
Traditional

↓

Production

↓

Bug Found

----------------

Shift Left

↓

Developer

↓

Bug Found Early
```

Fixing vulnerabilities early is faster and less expensive.

---

# Security Layers

Modern systems require multiple layers of protection.

```
Users

↓

Application

↓

Container

↓

Kubernetes

↓

Cloud

↓

Network

↓

Infrastructure
```

Each layer requires different security controls.

---

# Security Automation

Manual security reviews cannot keep up with modern delivery speeds.

Automation is used for:

- Code Scanning
- Dependency Scanning
- Container Image Scanning
- Secrets Detection
- Compliance Checks
- Infrastructure Scanning

These checks are integrated into CI/CD pipelines.

---

# Enterprise Example

A company deploys software 50 times per day.

Every deployment automatically performs:

```
Git Commit

↓

SAST

↓

Dependency Scan

↓

Docker Image Scan

↓

Unit Tests

↓

Deployment

↓

Runtime Monitoring
```

If a critical vulnerability is found,

the deployment is blocked.

---

# Common Beginner Mistakes

### Mistake 1

Thinking security is only the Security Team's responsibility.

Security is a shared responsibility across development, operations and security teams.

---

### Mistake 2

Adding security only before production.

Security should begin during planning and development.

---

### Mistake 3

Ignoring dependency vulnerabilities.

Third-party libraries can introduce significant risk.

---

### Mistake 4

Hardcoding secrets in source code.

Use secure secrets management solutions instead.

---

### Mistake 5

Assuming cloud providers secure everything.

Cloud security follows the Shared Responsibility Model.

---

# Interview Questions

### Q1. What is DevSecOps?

DevSecOps integrates security into every stage of the software development lifecycle.

---

### Q2. Why is DevSecOps important?

It identifies security issues earlier, reduces risk and enables secure software delivery.

---

### Q3. What is Shift Left Security?

Shift Left means moving security activities earlier in the development lifecycle.

---

### Q4. What are the goals of DevSecOps?

- Early vulnerability detection
- Security automation
- Compliance
- Secure software delivery

---

### Q5. Why is automation important in DevSecOps?

Automation enables consistent and scalable security checks in fast-moving CI/CD pipelines.

---

### Q6. Is DevSecOps a tool?

No.

DevSecOps is a culture, methodology and set of practices supported by various security tools.

---

# Production Best Practices

✔ Integrate security into every SDLC phase.

✔ Automate security testing.

✔ Scan dependencies regularly.

✔ Scan container images before deployment.

✔ Use secrets management.

✔ Monitor runtime security.

✔ Train developers in secure coding.

✔ Continuously improve security processes.

---

# Key Takeaways

- DevSecOps integrates security throughout software delivery.
- Security is a shared responsibility across teams.
- Shift Left helps detect vulnerabilities earlier.
- Automation is essential for modern DevSecOps.
- DevSecOps improves security while supporting rapid software delivery.

---

# Next Section

## 11.1 CIA Triad

In the next section, we will learn:

- What is the CIA Triad?
- Confidentiality
- Integrity
- Availability
- Real-World Examples
- Enterprise Architecture
- Best Practices
- Interview Questions
---

# 11.1 CIA Triad

Before learning advanced security tools,

every security professional must understand the foundation of information security.

That foundation is known as the **CIA Triad**.

Almost every security technology,

security policy,

security framework,

and compliance standard is built around these three principles.

```
CIA

↓

Confidentiality

Integrity

Availability
```

The CIA Triad helps organizations answer three important questions:

- Who can access the data?
- Can the data be trusted?
- Is the data available when needed?

---

# What is the CIA Triad?

The CIA Triad is the core security model used to protect information.

It consists of three principles:

```
Confidentiality

↓

Integrity

↓

Availability
```

Every security control supports one or more of these principles.

---

# CIA Triad Diagram

```
              CIA TRIAD

                 ▲

        Confidentiality

          ▲           ▲

         ▲             ▲

Integrity  ◄────────► Availability
```

Removing any one of these principles weakens security.

---

# Why is the CIA Triad Important?

Imagine an online banking application.

Customers expect:

- Only authorized users can access accounts.
- Account balances are accurate.
- Banking services are available 24×7.

These expectations directly map to the CIA Triad.

---

# Confidentiality

Confidentiality ensures that information is accessible only to authorized users.

Unauthorized people should never view sensitive information.

---

# Examples of Confidential Data

- Passwords
- Credit Card Numbers
- Aadhaar Numbers
- Medical Records
- Bank Details
- Company Source Code
- API Keys
- Encryption Keys

---

# Confidentiality Example

```
Customer Data

↓

Encryption

↓

Authorized User

↓

Access Granted
```

Unauthorized user:

```
Customer Data

↓

Access Denied
```

---

# How Confidentiality is Achieved

Common security controls include:

- Authentication
- Authorization
- Encryption
- VPN
- Multi-Factor Authentication (MFA)
- Role-Based Access Control (RBAC)
- Network Firewalls

---

# Real World Example

Suppose an employee opens a payroll application.

```
Login

↓

Authentication

↓

HR Role

↓

Salary Records Visible
```

Another employee without permission:

```
Login

↓

Access Denied
```

Confidentiality is maintained.

---

# Integrity

Integrity ensures that data remains accurate,

complete,

and unmodified unless changed by an authorized user.

Users should trust that the information has not been tampered with.

---

# Integrity Example

Original Record

```
Account Balance

₹10,000
```

Unauthorized modification

```
₹50,000
```

This is an integrity violation.

---

# How Integrity is Protected

Organizations use:

- Hashing
- Checksums
- Digital Signatures
- Version Control
- Database Constraints
- File Permissions
- Audit Logs

---

# Real World Example

When downloading software,

many vendors publish:

```
SHA256 Hash
```

After downloading,

users calculate the file hash.

```
Hashes Match

↓

File Not Modified
```

If hashes differ,

the file may have been corrupted or altered.

---

# Availability

Availability ensures that systems,

applications,

and data are accessible whenever authorized users need them.

Even perfectly secure systems are not useful if they are unavailable.

---

# Availability Example

Customer opens:

```
www.bank.com
```

Expected result:

```
Website Available
```

If the website is down,

availability has been affected.

---

# How Availability is Achieved

Organizations improve availability using:

- High Availability (HA)
- Redundant Servers
- Load Balancers
- Backups
- Disaster Recovery
- Auto Scaling
- Monitoring
- UPS and Power Backup

---

# High Availability Example

```
Load Balancer

↓

Server 1

Server 2

Server 3
```

If one server fails,

traffic is redirected to healthy servers.

---

# CIA Triad in Cloud Computing

```
Cloud Users

↓

Authentication

↓

Encryption

↓

Load Balancer

↓

Cloud Servers

↓

Backups
```

Each layer contributes to one or more CIA principles.

---

# CIA Triad in Kubernetes

```
RBAC

↓

Confidentiality

----------------

Admission Controls

↓

Integrity

----------------

Multiple Pods

↓

Availability
```

Kubernetes security features support all three principles.

---

# CIA Triad in DevSecOps

```
Git

↓

Secure Code

↓

CI/CD

↓

Security Scans

↓

Production

↓

Monitoring
```

Every phase should protect:

- Confidentiality
- Integrity
- Availability

---

# Practical Examples

## Online Banking

Confidentiality

```
Only account owner can access account.
```

Integrity

```
Balance cannot be changed without authorization.
```

Availability

```
Banking portal should remain available.
```

---

## Hospital

Confidentiality

```
Patient records visible only to authorized staff.
```

Integrity

```
Medical records must not be altered incorrectly.
```

Availability

```
Doctors must access records during emergencies.
```

---

## E-commerce

Confidentiality

```
Customer payment information protected.
```

Integrity

```
Order details remain accurate.
```

Availability

```
Website remains available during sales events.
```

---

# Enterprise Architecture

```
Users

↓

Authentication

↓

Application

↓

Database

↓

Encrypted Storage

↓

Backup

↓

Monitoring
```

Every layer contributes to the CIA Triad.

---

# Threats Against CIA

| Principle | Example Threat |
|------------|----------------|
| Confidentiality | Data Leak |
| Integrity | Data Tampering |
| Availability | DDoS Attack |

---

# Mapping Security Controls

| Security Control | CIA Principle |
|------------------|--------------|
| Encryption | Confidentiality |
| RBAC | Confidentiality |
| Hashing | Integrity |
| Digital Signature | Integrity |
| Backup | Availability |
| Load Balancer | Availability |
| Auto Scaling | Availability |
| Disaster Recovery | Availability |

---

# Common Beginner Mistakes

### Mistake 1

Thinking encryption alone provides complete security.

Encryption primarily protects confidentiality.

---

### Mistake 2

Ignoring data integrity.

Unauthorized data modification can be as damaging as data theft.

---

### Mistake 3

Focusing only on availability.

A highly available but insecure application still poses significant risk.

---

### Mistake 4

Confusing authentication with confidentiality.

Authentication verifies identity, while confidentiality limits access to authorized users.

---

### Mistake 5

Not planning for disasters.

Availability requires backups, redundancy and recovery planning.

---

# Interview Questions

### Q1. What is the CIA Triad?

The CIA Triad is the foundational information security model consisting of Confidentiality, Integrity and Availability.

---

### Q2. What is Confidentiality?

Confidentiality ensures that information is accessible only to authorized users.

---

### Q3. What is Integrity?

Integrity ensures that data remains accurate, complete and unmodified without authorization.

---

### Q4. What is Availability?

Availability ensures that systems and data remain accessible when needed.

---

### Q5. Name three controls used to protect Confidentiality.

- Encryption
- Authentication
- Role-Based Access Control (RBAC)

---

### Q6. Name three controls used to improve Availability.

- Load Balancing
- High Availability
- Backups

---

# Production Best Practices

✔ Encrypt sensitive data.

✔ Apply least privilege access.

✔ Enable Multi-Factor Authentication (MFA).

✔ Verify file integrity using hashes.

✔ Implement backups and disaster recovery.

✔ Deploy redundant infrastructure.

✔ Continuously monitor systems.

✔ Test recovery procedures regularly.

---

# Key Takeaways

- The CIA Triad is the foundation of modern information security.
- Confidentiality protects sensitive information from unauthorized access.
- Integrity ensures that data remains accurate and trustworthy.
- Availability keeps systems and services accessible to authorized users.
- Every security technology supports one or more principles of the CIA Triad.

---

# Next Section

## 11.2 Authentication vs Authorization

In the next section, we will learn:

- What is Authentication?
- What is Authorization?
- Authentication Methods
- Authorization Models
- RBAC
- ABAC
- OAuth
- JWT
- Enterprise Examples
- Interview Questions
---

# 11.2 Authentication vs Authorization

One of the most common interview questions in DevOps, Cloud and Security interviews is:

> **What is the difference between Authentication and Authorization?**

Many beginners confuse these two concepts.

Although they are closely related,

they solve two completely different problems.

Understanding this topic is essential for:

- Linux Security
- Cloud Security
- Kubernetes RBAC
- IAM
- APIs
- DevSecOps
- Identity Management

---

# Authentication vs Authorization

The simplest way to remember:

```
Authentication

↓

Who are you?

------------------------

Authorization

↓

What are you allowed to do?
```

Authentication happens first.

Authorization happens after successful authentication.

---

# Real World Example

Suppose you visit your office.

### Step 1

You show your ID card.

Security verifies your identity.

```
Authentication
```

---

### Step 2

You enter the building.

Can you access:

- HR Department?
- Finance Department?
- Server Room?

Your permissions decide this.

```
Authorization
```

---

# Authentication

Authentication is the process of verifying the identity of a user or system.

It answers:

```
Who are you?
```

---

# Authentication Workflow

```
User

↓

Username

↓

Password

↓

Identity Verified

↓

Authenticated
```

---

# Authentication Factors

Authentication is generally based on one or more factors.

---

## Something You Know

Examples:

- Password
- PIN
- Security Questions

---

## Something You Have

Examples:

- Mobile Phone
- Smart Card
- OTP Token
- USB Security Key

---

## Something You Are

Examples:

- Fingerprint
- Face Recognition
- Retina Scan
- Voice Recognition

---

# Multi-Factor Authentication (MFA)

Using multiple authentication factors increases security.

Example

```
Password

+

OTP

↓

Access Granted
```

or

```
Password

+

Fingerprint

↓

Login Successful
```

---

# Common Authentication Methods

Organizations commonly use:

- Username & Password
- OTP
- MFA
- Biometrics
- SSH Keys
- Certificates
- OAuth Login
- SSO

---

# Password Authentication

```
Username

↓

Password

↓

Authentication Server

↓

Success
```

Still the most common authentication method.

---

# OTP Authentication

```
Password

↓

OTP Sent

↓

OTP Verified

↓

Login
```

Adds another security layer.

---

# Biometric Authentication

```
Fingerprint

↓

Scanner

↓

Verified
```

Common on smartphones and laptops.

---

# Certificate Authentication

Used in:

- HTTPS
- VPN
- Enterprise Systems

Example

```
Client Certificate

↓

Verification

↓

Authenticated
```

---

# SSH Key Authentication

Instead of passwords,

Linux servers often use SSH keys.

```
Private Key

↓

Public Key

↓

Authentication
```

This is generally more secure than password-based SSH login.

---

# Authorization

Authorization determines what an authenticated user is allowed to access.

It answers:

```
What are you allowed to do?
```

---

# Authorization Workflow

```
Authenticated User

↓

Permissions

↓

Allowed Resources

↓

Access Granted
```

---

# Authorization Example

Suppose three users log in.

```
Admin

↓

Read

Write

Delete

----------------

Developer

↓

Read

Write

----------------

Guest

↓

Read
```

Each user has different permissions.

---

# Authentication vs Authorization Workflow

```
User

↓

Authentication

↓

Identity Verified

↓

Authorization

↓

Access Control

↓

Application
```

Authentication always comes before authorization.

---

# Authentication Failure

```
Wrong Password

↓

Authentication Failed

↓

No Login
```

Since authentication failed,

authorization is never evaluated.

---

# Authorization Failure

```
Correct Password

↓

Login Successful

↓

Delete Database

↓

Permission Denied
```

The user is authenticated,

but not authorized.

---

# Comparison Table

| Authentication | Authorization |
|----------------|---------------|
| Verifies Identity | Verifies Permissions |
| Happens First | Happens Second |
| Login Process | Access Control |
| Username & Password | Roles & Permissions |
| Answers "Who are you?" | Answers "What can you do?" |

---

# Role-Based Access Control (RBAC)

One of the most common authorization models.

Permissions are assigned to roles.

Example

```
Admin

↓

All Permissions

----------------

Developer

↓

Deploy

Read Logs

----------------

Viewer

↓

Read Only
```

---

# RBAC Workflow

```
User

↓

Role

↓

Permissions

↓

Resources
```

---

# Attribute-Based Access Control (ABAC)

ABAC grants access based on attributes.

Examples:

- Department
- Location
- Time
- Device
- Project

Example

```
Department = HR

↓

Can Access Payroll
```

---

# Access Control List (ACL)

ACL defines permissions directly on resources.

Example

```
File

↓

Read

Write

Execute
```

ACLs are common in Linux file systems and networking devices.

---

# Authentication in Linux

Common methods include:

- Password Authentication
- SSH Keys
- LDAP
- Kerberos

Example

```bash
ssh user@server
```

---

# Authorization in Linux

Permissions are controlled using:

- Users
- Groups
- File Permissions
- sudo
- ACLs

Example

```bash
chmod

chown

sudo
```

---

# Authentication in Kubernetes

Authentication methods include:

- Client Certificates
- Service Accounts
- OpenID Connect (OIDC)
- Cloud IAM
- Bearer Tokens

---

# Authorization in Kubernetes

Authorization is commonly handled using:

- RBAC
- ABAC (legacy)
- Node Authorization
- Webhook Authorization

---

# Authentication in Cloud

Cloud providers support:

- IAM Users
- IAM Roles
- MFA
- Federation
- SSO

---

# Enterprise Example

An employee opens the company portal.

```
Username

↓

Password

↓

MFA

↓

Authentication

↓

RBAC

↓

Application Access
```

Authentication verifies identity.

RBAC determines permissions.

---

# Banking Example

Customer logs into online banking.

```
Username

↓

Password

↓

OTP

↓

Authenticated

↓

Authorization

↓

View Own Account
```

The customer cannot access another customer's account.

---

# API Example

```
Client

↓

JWT Token

↓

Authentication

↓

API Role

↓

Authorization

↓

Response
```

---

# Common Authentication Protocols

Examples:

- LDAP
- Kerberos
- OAuth 2.0
- OpenID Connect (OIDC)
- SAML

---

# Common Authorization Models

Examples:

- RBAC
- ABAC
- ACL
- Policy-Based Access Control (PBAC)

---

# Authentication vs Authorization in DevSecOps

```
Developer

↓

Git Login

↓

Authentication

↓

Repository Permissions

↓

Authorization

↓

Push Code
```

---

# Common Beginner Mistakes

### Mistake 1

Thinking Authentication and Authorization are the same.

They solve different problems.

---

### Mistake 2

Checking authorization before authentication.

Authorization only happens after identity is verified.

---

### Mistake 3

Giving every user administrative permissions.

Follow the Principle of Least Privilege (PoLP).

---

### Mistake 4

Using passwords without MFA.

Enable Multi-Factor Authentication whenever possible.

---

### Mistake 5

Sharing user accounts.

Every user should have an individual identity.

---

# Interview Questions

### Q1. What is Authentication?

Authentication verifies the identity of a user or system.

---

### Q2. What is Authorization?

Authorization determines what an authenticated user is allowed to access.

---

### Q3. Which happens first?

Authentication.

---

### Q4. What is RBAC?

Role-Based Access Control assigns permissions based on user roles.

---

### Q5. What is Multi-Factor Authentication (MFA)?

MFA requires two or more authentication factors before granting access.

---

### Q6. Give one real-world example.

ATM Example:

- Insert ATM Card + PIN → Authentication
- Withdraw Money → Authorization based on account permissions and balance.

---

# Production Best Practices

✔ Enable MFA for all privileged accounts.

✔ Apply the Principle of Least Privilege (PoLP).

✔ Use RBAC wherever possible.

✔ Regularly review user permissions.

✔ Disable inactive accounts.

✔ Avoid shared credentials.

✔ Log authentication and authorization events.

✔ Integrate identity management with SSO where appropriate.

---

# Key Takeaways

- Authentication answers **"Who are you?"**
- Authorization answers **"What are you allowed to do?"**
- Authentication always occurs before authorization.
- RBAC is the most common authorization model in DevOps and Kubernetes.
- MFA significantly strengthens authentication security.
- Proper identity and access management is a foundation of secure DevSecOps.

---

# Next Section

## 11.3 Encryption & Hashing

In the next section, we will learn:

- What is Encryption?
- Symmetric Encryption
- Asymmetric Encryption
- Public Key & Private Key
- What is Hashing?
- Hash Functions
- Digital Signatures
- Real-World Examples
- Production Best Practices
- Interview Questions
---

# 11.3 Encryption & Hashing

One of the biggest misconceptions among beginners is:

> **Encryption and Hashing are NOT the same thing.**

Although both deal with protecting data,

they solve completely different security problems.

Understanding this topic is essential for:

- DevSecOps
- Linux Security
- Cloud Security
- HTTPS
- Kubernetes
- Docker
- IAM
- Password Storage
- Digital Certificates

---

# Data Protection

Suppose a customer enters:

```
Password

↓

Internet

↓

Web Server
```

How do we protect the password while it travels?

How do we protect it while it is stored?

These are two different problems.

Encryption protects data during transmission and storage.

Hashing protects data integrity and password verification.

---

# Encryption

Encryption is the process of converting readable data into unreadable data.

```
Plain Text

↓

Encryption

↓

Cipher Text
```

Only authorized users with the correct key can convert it back.

---

# Simple Example

Original Message

```
Transfer ₹50,000
```

After Encryption

```
A7H#9D!Q@8L...
```

Without the key,

the message cannot be understood.

---

# Encryption Workflow

```
Plain Text

↓

Encryption Algorithm

↓

Encryption Key

↓

Cipher Text

↓

Decryption Key

↓

Original Data
```

---

# Why Encryption?

Encryption protects:

- Confidentiality
- Sensitive Information
- Customer Data
- API Traffic
- Database Data
- Secrets
- Backups

---

# Types of Encryption

Encryption is mainly divided into:

```
Encryption

│

├── Symmetric Encryption

└── Asymmetric Encryption
```

---

# Symmetric Encryption

Symmetric encryption uses **one key** for both encryption and decryption.

```
Plain Text

↓

Key

↓

Encrypted

↓

Same Key

↓

Original Data
```

---

# Example

Alice and Bob both know the same secret key.

```
Alice

↓

Encrypt

↓

Secret Key

↓

Bob

↓

Decrypt

↓

Same Secret Key
```

---

# Advantages

✔ Very Fast

✔ Less CPU Usage

✔ Suitable for Large Data

---

# Disadvantages

The secret key must be shared securely.

If the key is leaked,

all encrypted data is at risk.

---

# Common Symmetric Algorithms

Examples:

- AES
- DES (Legacy)
- 3DES (Legacy)
- ChaCha20

AES is the most widely used today.

---

# Real World Uses

Symmetric encryption is commonly used for:

- Disk Encryption
- File Encryption
- Database Encryption
- VPN Traffic
- Backup Encryption

---

# Asymmetric Encryption

Asymmetric encryption uses **two keys**.

```
Public Key

↓

Encrypt

↓

Private Key

↓

Decrypt
```

---

# Public Key

The public key can be shared with anyone.

It is used to encrypt data.

---

# Private Key

The private key must remain secret.

It is used to decrypt data.

---

# Example

```
Alice

↓

Bob's Public Key

↓

Encrypted Message

↓

Bob

↓

Private Key

↓

Original Message
```

Only Bob can decrypt the message.

---

# Advantages

✔ Secure Key Exchange

✔ Digital Signatures

✔ Identity Verification

✔ No Shared Secret Required

---

# Disadvantages

Asymmetric encryption is slower than symmetric encryption.

It is generally used to exchange keys rather than encrypt large amounts of data.

---

# Common Asymmetric Algorithms

Examples:

- RSA
- ECC (Elliptic Curve Cryptography)
- DSA

RSA and ECC are widely used.

---

# Real World Uses

Asymmetric encryption is used in:

- HTTPS
- SSL/TLS
- SSH
- Digital Certificates
- Email Encryption
- Cloud Authentication

---

# Symmetric vs Asymmetric

| Symmetric | Asymmetric |
|------------|------------|
| One Key | Two Keys |
| Faster | Slower |
| Bulk Data Encryption | Secure Key Exchange |
| AES | RSA / ECC |

---

# Hybrid Encryption

Modern systems use both encryption methods together.

Example:

```
Browser

↓

Public Key

↓

Exchange AES Key

↓

AES Encrypts Session
```

HTTPS works this way.

---

# What is Hashing?

Hashing converts data into a fixed-length value called a **Hash**.

Unlike encryption,

hashing is **one-way**.

```
Plain Text

↓

Hash Function

↓

Hash Value
```

The original data cannot normally be recovered from the hash.

---

# Hash Example

Password

```
Mayank@123
```

Hash

```
8e72d9a4e9d8...

```

The stored value is the hash, not the original password.

---

# Hash Characteristics

A good hash function should:

✔ Produce fixed-length output

✔ Be deterministic

✔ Be fast to compute

✔ Be difficult to reverse

✔ Produce different hashes for different inputs

---

# Common Hash Algorithms

Examples:

- SHA-256
- SHA-384
- SHA-512
- SHA-3

Legacy algorithms such as MD5 and SHA-1 are considered insecure for cryptographic integrity purposes.

---

# Password Storage

Correct method:

```
Password

↓

Hash

↓

Database
```

Wrong method:

```
Password

↓

Database
```

Never store plain-text passwords.

---

# Password Verification

During login:

```
User Password

↓

Hash

↓

Compare Stored Hash

↓

Match?

↓

Login Successful
```

---

# Salting

If two users have the same password,

their hashes should still be different.

This is achieved using a **Salt**.

```
Password

+

Random Salt

↓

Hash
```

Salting helps defend against rainbow table attacks.

---

# Encryption vs Hashing

| Encryption | Hashing |
|------------|----------|
| Reversible | One-Way |
| Protects Confidentiality | Protects Integrity & Password Verification |
| Uses Keys | No Decryption Key |
| Plain Text Can Be Recovered | Original Data Cannot Normally Be Recovered |

---

# Digital Signature

Digital signatures provide:

- Authentication
- Integrity
- Non-Repudiation

Workflow

```
Document

↓

Hash

↓

Private Key

↓

Digital Signature

↓

Receiver

↓

Public Key

↓

Verification
```

---

# File Integrity Example

Suppose you download Ubuntu ISO.

Website provides:

```
SHA256

↓

ABC123...
```

You calculate:

```
SHA256

↓

ABC123...
```

Hashes match.

The file has not been modified.

---

# HTTPS Example

```
Browser

↓

Server Public Key

↓

Encrypted Session Key

↓

AES Session

↓

Secure Communication
```

HTTPS combines asymmetric and symmetric encryption.

---

# SSH Example

```
Client

↓

Public Key

↓

Server

↓

Private Key Verification

↓

Secure Login
```

---

# Enterprise Example

An online banking application:

```
Customer

↓

HTTPS

↓

Encrypted Traffic

↓

Application

↓

Password Hash

↓

Database
```

Data remains protected both during transmission and storage.

---

# Common Beginner Mistakes

### Mistake 1

Thinking hashing is encryption.

Hashing cannot normally be reversed.

---

### Mistake 2

Storing passwords using encryption.

Passwords should be stored using secure password hashing algorithms, not reversible encryption.

---

### Mistake 3

Using MD5 for password security.

Modern password storage should use algorithms such as Argon2, bcrypt or scrypt. SHA-256 alone is not sufficient for password hashing because it is designed to be fast.

---

### Mistake 4

Sharing private keys.

Private keys must never be shared.

---

### Mistake 5

Assuming HTTPS uses only RSA.

Modern HTTPS typically uses asymmetric cryptography for key exchange and symmetric encryption (such as AES or ChaCha20) for the actual session.

---

# Interview Questions

### Q1. What is Encryption?

Encryption converts readable data into unreadable ciphertext that can be decrypted using the appropriate key.

---

### Q2. What is Hashing?

Hashing converts data into a fixed-length value for integrity verification or password verification.

---

### Q3. What is the difference between Symmetric and Asymmetric Encryption?

Symmetric encryption uses one shared key.

Asymmetric encryption uses a public/private key pair.

---

### Q4. Why are passwords hashed?

To avoid storing passwords in plain text and to enable secure verification.

---

### Q5. What is a Salt?

A random value added to a password before hashing to produce unique hashes and defend against precomputed attacks.

---

### Q6. Give one example of each.

Symmetric:

- AES

Asymmetric:

- RSA
- ECC

Hash:

- SHA-256 (general-purpose hash)
- Argon2 or bcrypt (password hashing)

---

# Production Best Practices

✔ Encrypt sensitive data in transit and at rest.

✔ Use TLS for all external communication.

✔ Use AES for bulk data encryption.

✔ Use RSA or ECC for secure key exchange and digital signatures.

✔ Store passwords with Argon2, bcrypt or scrypt plus unique salts.

✔ Protect private keys using secure key management.

✔ Rotate encryption keys periodically.

✔ Verify file integrity using SHA-256 or stronger hashes where appropriate.

---

# Key Takeaways

- Encryption protects confidentiality by making data unreadable without the correct key.
- Symmetric encryption is fast and ideal for encrypting large amounts of data.
- Asymmetric encryption enables secure key exchange and identity verification.
- Hashing is a one-way operation used for integrity checks and password verification.
- Modern applications use a combination of encryption, hashing and digital signatures to secure data.

---

# Next Section

## 11.4 SSL/TLS & HTTPS

In the next section, we will learn:

- What is SSL?
- What is TLS?
- SSL vs TLS
- HTTPS Handshake
- Digital Certificates
- Certificate Authorities (CA)
- TLS Handshake
- Real-World Examples
- Production Best Practices
- Interview Questions
---

# 11.4 SSL/TLS & HTTPS

Whenever you open a secure website like:

- Google
- Amazon
- GitHub
- Banking Websites
- UPI Applications

you usually see:

```
https://
```

instead of

```
http://
```

That small **"S"** represents one of the most important security technologies on the Internet.

It means your communication is protected using **TLS**.

---

# Why Do We Need HTTPS?

Imagine you log in to your bank using public Wi-Fi.

Without encryption,

an attacker on the same network could intercept your:

- Username
- Password
- Session Cookie
- Banking Details

This type of attack is commonly called:

```
Packet Sniffing
```

HTTPS prevents attackers from reading or modifying transmitted data.

---

# HTTP vs HTTPS

## HTTP

```
Browser

↓

Internet

↓

Server
```

Everything is transmitted in plain text.

Anyone intercepting the traffic can read it.

---

## HTTPS

```
Browser

↓

Encrypted TLS Connection

↓

Server
```

Even if traffic is intercepted,

the attacker cannot understand the encrypted data.

---

# What is SSL?

SSL stands for:

```
Secure Sockets Layer
```

SSL was one of the earliest protocols used to secure Internet communication.

However,

older SSL versions (SSL 2.0 and SSL 3.0) are obsolete and considered insecure.

Modern systems should **not** use SSL.

---

# What is TLS?

TLS stands for:

```
Transport Layer Security
```

TLS is the modern and secure successor to SSL.

When people say:

```
SSL Certificate
```

they usually mean:

```
TLS Certificate
```

---

# SSL vs TLS

| SSL | TLS |
|------|-----|
| Older Protocol | Modern Protocol |
| Deprecated | Recommended |
| Less Secure | More Secure |
| SSL 2.0 & SSL 3.0 Obsolete | TLS 1.2 & TLS 1.3 Widely Used |

---

# What is HTTPS?

HTTPS stands for:

```
HyperText Transfer Protocol Secure
```

HTTPS is simply:

```
HTTP

+

TLS
```

It protects communication between client and server.

---

# HTTPS Architecture

```
Browser

↓

HTTPS

↓

TLS

↓

Web Server
```

---

# Security Goals of HTTPS

HTTPS provides:

✔ Confidentiality

✔ Integrity

✔ Authentication

These align with the CIA Triad.

---

# HTTPS Workflow

```
Browser

↓

Connect

↓

TLS Handshake

↓

Secure Session

↓

Encrypted Communication
```

---

# TLS Handshake

Before secure communication begins,

the browser and server perform a handshake.

This process establishes:

- Identity Verification
- Encryption Algorithms
- Session Keys

---

# Simplified TLS Handshake

```
Client

↓

Hello

↓

Server Hello

↓

Certificate

↓

Key Exchange

↓

Session Key

↓

Encrypted Communication
```

---

# Step 1 – Client Hello

The browser sends:

- Supported TLS Versions
- Cipher Suites
- Random Number

```
Browser

↓

Client Hello
```

---

# Step 2 – Server Hello

The server replies with:

- Selected TLS Version
- Selected Cipher Suite
- Server Random Number

```
Server

↓

Server Hello
```

---

# Step 3 – Digital Certificate

The server sends its TLS certificate.

The certificate proves:

```
This server really owns this domain.
```

---

# Step 4 – Certificate Validation

The browser checks:

- Certificate Expiry
- Domain Name
- Certificate Authority
- Signature Chain

If validation fails,

the browser displays a security warning.

---

# Step 5 – Key Exchange

The browser and server securely establish a shared session key.

Modern TLS commonly uses **ECDHE (Elliptic Curve Diffie-Hellman Ephemeral)** for key exchange, providing **Forward Secrecy**.

---

# Step 6 – Secure Communication

Once the session key is established,

all application data is encrypted.

```
Browser

↓

Encrypted Data

↓

Server
```

---

# Digital Certificate

A certificate contains:

- Domain Name
- Public Key
- Certificate Authority
- Expiration Date
- Serial Number
- Digital Signature

---

# Certificate Authority (CA)

A Certificate Authority is a trusted organization that issues digital certificates.

Examples include:

- DigiCert
- GlobalSign
- Sectigo
- Let's Encrypt

Browsers trust certificates issued by recognized CAs.

---

# Certificate Chain

```
Root CA

↓

Intermediate CA

↓

Website Certificate
```

Browsers verify the entire chain.

---

# Public Key & Private Key

Every TLS certificate includes:

```
Public Key

↓

Shared Publicly

----------------

Private Key

↓

Kept Secret
```

The private key must never leave the server.

---

# Session Keys

Although TLS uses asymmetric cryptography during the handshake,

the actual communication usually uses symmetric encryption.

Example:

```
TLS Handshake

↓

Session Key

↓

AES

↓

Encrypted Communication
```

This provides both security and performance.

---

# Common Encryption Algorithms

Examples:

Symmetric:

- AES-GCM
- ChaCha20-Poly1305

Asymmetric / Key Exchange:

- ECDHE
- RSA (legacy key exchange)
- ECC

Hash / Integrity:

- SHA-256
- SHA-384

---

# Forward Secrecy

Modern TLS supports:

```
Forward Secrecy
```

This means:

Even if the server's long-term private key is compromised in the future,

previous encrypted sessions remain secure.

---

# TLS Versions

| Version | Status |
|----------|--------|
| SSL 2.0 | Obsolete |
| SSL 3.0 | Obsolete |
| TLS 1.0 | Deprecated |
| TLS 1.1 | Deprecated |
| TLS 1.2 | Widely Used |
| TLS 1.3 | Recommended |

---

# HTTPS Example

Suppose you visit:

```
https://bank.com
```

Workflow:

```
Browser

↓

TLS Handshake

↓

Certificate Validation

↓

Session Key

↓

Encrypted Banking Session
```

---

# SSH vs HTTPS

| SSH | HTTPS |
|------|--------|
| Remote Login | Secure Web Communication |
| Port 22 | Port 443 |
| SSH Keys | TLS Certificates |

---

# Kubernetes Example

```
kubectl

↓

TLS

↓

API Server

↓

Certificate Verification
```

Kubernetes secures API communication using TLS.

---

# Enterprise Architecture

```
Users

↓

Load Balancer

↓

TLS

↓

Application Servers

↓

Database
```

TLS is often terminated at the load balancer or ingress controller, depending on the architecture.

---

# Common Beginner Mistakes

### Mistake 1

Thinking SSL and TLS are different technologies in current production.

Modern deployments use TLS, although "SSL" is still commonly used informally.

---

### Mistake 2

Ignoring certificate expiration.

Expired certificates can make services unavailable.

---

### Mistake 3

Using old TLS versions.

Disable SSL, TLS 1.0 and TLS 1.1 unless there is a specific legacy requirement.

---

### Mistake 4

Sharing private keys.

Private keys must remain secret.

---

### Mistake 5

Using self-signed certificates in production without proper trust management.

Use certificates from trusted Certificate Authorities or an approved internal PKI.

---

# Interview Questions

### Q1. What is TLS?

TLS (Transport Layer Security) is the modern protocol used to secure network communication.

---

### Q2. What is HTTPS?

HTTPS is HTTP protected by TLS encryption.

---

### Q3. Why is TLS more secure than SSL?

TLS provides stronger cryptography, better protocol design and fixes known SSL vulnerabilities.

---

### Q4. What is a Digital Certificate?

A digital certificate binds a public key to an identity and is issued by a trusted Certificate Authority.

---

### Q5. What is a Certificate Authority (CA)?

A trusted organization that validates identities and issues digital certificates.

---

### Q6. Which TLS versions should be used today?

TLS 1.2 and TLS 1.3.

TLS 1.3 is recommended whenever supported.

---

# Production Best Practices

✔ Use HTTPS for every public-facing application.

✔ Prefer TLS 1.3, with TLS 1.2 as a compatibility option.

✔ Disable SSL and deprecated TLS versions.

✔ Protect private keys using secure key management.

✔ Monitor certificate expiration.

✔ Automate certificate renewal where possible.

✔ Use strong cipher suites.

✔ Enable HSTS for public web applications where appropriate.

---

# Key Takeaways

- HTTPS secures web communication using TLS.
- TLS provides confidentiality, integrity and authentication.
- Digital certificates verify server identity.
- Certificate Authorities establish trust on the Internet.
- Modern TLS combines asymmetric cryptography for key exchange with symmetric encryption for efficient communication.
- TLS 1.3 is the current best practice for secure web communications.

---

# Next Section

## 11.5 Secrets Management

In the next section, we will learn:

- What are Secrets?
- Why Secrets Management is Important
- Types of Secrets
- Secret Storage
- Secret Rotation
- Kubernetes Secrets
- HashiCorp Vault Introduction
- Production Best Practices
- Interview Questions
---

# 11.5 Secrets Management

Modern applications require many sensitive values to operate.

Examples include:

- Database Passwords
- API Keys
- Cloud Credentials
- SSH Private Keys
- TLS Certificates
- Kubernetes Tokens
- OAuth Client Secrets

These sensitive values are called **Secrets**.

Managing them securely is one of the most important responsibilities in DevSecOps.

---

# What is a Secret?

A Secret is any sensitive piece of information that provides access to a system, service or resource.

If a secret is exposed,

attackers may gain unauthorized access.

---

# Examples of Secrets

Common secrets include:

- Username & Password
- API Keys
- Access Tokens
- JWT Signing Keys
- OAuth Client Secrets
- SSH Keys
- TLS Private Keys
- Database Credentials
- AWS Access Keys
- Azure Service Principals
- GCP Service Account Keys

---

# Real World Example

Suppose an application connects to a database.

```
Application

↓

Database Password

↓

Database
```

Without the password,

the application cannot connect.

If the password is leaked,

an attacker may access the database.

---

# Why Secrets Management?

Without proper secrets management,

organizations often:

- Hardcode passwords
- Share credentials over email
- Store secrets in Git
- Reuse passwords
- Never rotate credentials

These practices create serious security risks.

---

# Secret Lifecycle

```
Create

↓

Store

↓

Access

↓

Rotate

↓

Revoke

↓

Delete
```

Every secret should follow a controlled lifecycle.

---

# Common Places Where Secrets Are Used

Examples:

- CI/CD Pipelines
- Docker Containers
- Kubernetes Pods
- Cloud Applications
- Databases
- APIs
- Microservices

---

# Bad Practice

Hardcoding a password.

```python
password = "Admin@123"
```

If this code is pushed to GitHub,

the secret becomes exposed.

---

# Better Practice

Read secrets from a secure secret manager.

```python
password = get_secret("database-password")
```

The application never stores the password directly.

---

# Where Should Secrets Be Stored?

Secrets should be stored in dedicated secret management systems.

Examples:

- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- Google Secret Manager
- Kubernetes Secrets (with additional protection such as encryption at rest)

---

# Environment Variables

Applications often receive secrets through environment variables.

Example

```bash
export DB_PASSWORD=*******
```

Advantages:

- Keeps secrets out of source code.

Limitations:

- Environment variables may still be exposed to privileged users or debugging tools if not handled carefully.

---

# Secret Management Workflow

```
Application

↓

Secret Request

↓

Secret Manager

↓

Authentication

↓

Authorized?

↓

Secret Returned
```

Only authenticated and authorized applications receive secrets.

---

# Secret Rotation

Secrets should not remain unchanged forever.

Example

```
Old Password

↓

Generate New Password

↓

Update Applications

↓

Delete Old Password
```

This process is called **Secret Rotation**.

---

# Why Rotate Secrets?

Rotation reduces risk if a secret is compromised.

Organizations commonly rotate:

- Database Passwords
- API Keys
- Cloud Credentials
- Certificates
- SSH Keys

---

# Automatic Rotation

Modern secret managers support automatic rotation.

Workflow

```
Secret Near Expiry

↓

Generate New Secret

↓

Update Applications

↓

Revoke Old Secret
```

Automation reduces operational effort and risk.

---

# Secret Versioning

Many secret managers keep multiple versions.

Example

```
Version 1

↓

Version 2

↓

Version 3
```

Applications can transition safely during rotation.

---

# Principle of Least Privilege

Applications should only access the secrets they actually need.

Example

```
Payment Service

↓

Payment Database Password

------------------------

Inventory Service

↓

Inventory Database Password
```

Avoid sharing secrets across unrelated services.

---

# Secrets in Kubernetes

Kubernetes provides a Secret resource.

Example

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: database-secret
type: Opaque
```

Pods can consume secrets as:

- Environment Variables
- Mounted Volumes

---

# Kubernetes Secret Workflow

```
Secret

↓

Kubernetes API

↓

Pod

↓

Application
```

Applications retrieve secrets without embedding them in container images.

---

# Important Note About Kubernetes Secrets

By default,

Kubernetes Secrets are **Base64 encoded**, **not encrypted**.

Production clusters should enable:

- Encryption at Rest
- RBAC
- Network Policies
- Secret Rotation
- External Secret Managers

---

# Docker Secrets

Docker Swarm supports Docker Secrets.

Workflow

```
Docker Secret

↓

Container

↓

Application
```

Only authorized containers receive the secret.

---

# Cloud Secrets Management

Cloud providers offer managed services.

Examples:

AWS

```
AWS Secrets Manager
```

Azure

```
Azure Key Vault
```

Google Cloud

```
Secret Manager
```

These services provide:

- Encryption
- Rotation
- Auditing
- Access Control

---

# Enterprise Example

An organization has:

```
Git Repository

↓

CI/CD Pipeline

↓

HashiCorp Vault

↓

Temporary Credentials

↓

Application
```

No passwords are stored in source code.

---

# Secret Scanning

Organizations automatically scan repositories for leaked secrets.

Examples of detectable items:

- AWS Keys
- GitHub Tokens
- API Keys
- Passwords
- Private Keys

Popular tools:

- GitHub Secret Scanning
- Gitleaks
- TruffleHog

---

# Secret Auditing

Every secret access should be logged.

Audit records typically include:

- Who accessed the secret
- When it was accessed
- Which application used it
- Whether access was successful

Auditing supports compliance and incident investigations.

---

# Common Beginner Mistakes

### Mistake 1

Hardcoding passwords inside source code.

Never store secrets in application code.

---

### Mistake 2

Committing secrets to Git repositories.

Secrets should never be version controlled.

---

### Mistake 3

Using one password for every service.

Use separate credentials for each application.

---

### Mistake 4

Never rotating secrets.

Regular rotation reduces the impact of credential compromise.

---

### Mistake 5

Giving every application access to every secret.

Follow the Principle of Least Privilege.

---

# Interview Questions

### Q1. What is a Secret?

A Secret is sensitive information such as a password, API key or token that grants access to a resource.

---

### Q2. Why is Secrets Management important?

It protects sensitive credentials from unauthorized access and reduces security risk.

---

### Q3. Should secrets be stored in Git?

No.

Secrets should never be committed to source control.

---

### Q4. What is Secret Rotation?

Secret Rotation is the process of periodically replacing credentials with new ones.

---

### Q5. Are Kubernetes Secrets encrypted by default?

No.

By default they are Base64 encoded. Encryption at rest must be configured separately.

---

### Q6. Name some popular Secret Management tools.

- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- Google Secret Manager

---

# Production Best Practices

✔ Never hardcode secrets.

✔ Use a centralized secret manager.

✔ Rotate secrets regularly.

✔ Enable encryption at rest.

✔ Audit secret access.

✔ Apply least privilege.

✔ Scan repositories for leaked credentials.

✔ Automate secret rotation whenever possible.

---

# Key Takeaways

- Secrets are sensitive credentials used by applications and infrastructure.
- Secrets must never be stored in source code.
- Dedicated secret managers provide secure storage and controlled access.
- Secret rotation reduces long-term risk.
- Proper secrets management is a core practice of modern DevSecOps.

---

# Next Section

## 11.6 HashiCorp Vault

In the next section, we will learn:

- What is HashiCorp Vault?
- Vault Architecture
- Authentication Methods
- Secret Engines
- Dynamic Secrets
- Secret Rotation
- Kubernetes Integration
- Production Best Practices
- Interview Questions
---

# 11.6 HashiCorp Vault

As organizations adopt cloud computing,

microservices,

containers,

and Kubernetes,

the number of secrets grows rapidly.

Examples include:

- Database Passwords
- API Keys
- Cloud Credentials
- TLS Certificates
- SSH Keys
- Kubernetes Tokens

Managing thousands of secrets manually becomes difficult and insecure.

To solve this problem,

many organizations use **HashiCorp Vault**.

Vault is considered one of the industry's leading secrets management platforms.

---

# What is HashiCorp Vault?

HashiCorp Vault is an open-source secrets management platform.

It securely stores,

protects,

controls,

and distributes secrets.

Vault also supports:

- Dynamic Secrets
- Encryption as a Service
- Key Management
- Secret Rotation
- Identity-Based Access

---

# Simple Definition

```
Applications

↓

Vault

↓

Secrets

↓

Secure Access
```

Vault becomes the central place for managing secrets.

---

# Why Vault?

Without Vault

```
Applications

↓

Passwords

↓

Config Files

↓

Git Repository
```

Security Risks:

- Password Leakage
- Secret Reuse
- No Rotation
- Difficult Auditing

---

With Vault

```
Applications

↓

Authentication

↓

Vault

↓

Temporary Secrets

↓

Secure Access
```

Secrets remain centrally managed.

---

# Why Companies Use Vault

Vault provides:

✔ Centralized Secrets

✔ Dynamic Credentials

✔ Automatic Rotation

✔ Encryption

✔ Identity-Based Access

✔ Audit Logs

✔ Cloud Integration

✔ Kubernetes Support

---

# Vault Architecture

```
Applications

↓

Authentication

↓

Vault Server

↓

Secret Engine

↓

Secret Storage
```

---

# Vault Components

```
Vault

│

├── Authentication

├── Policies

├── Secret Engines

├── Audit Logs

├── Storage Backend

└── Tokens
```

---

# Authentication

Before accessing secrets,

applications must authenticate.

Vault supports many authentication methods.

Examples:

- Username & Password
- Token
- AppRole
- Kubernetes
- AWS IAM
- Azure
- GCP
- LDAP
- GitHub
- OIDC

---

# Authentication Workflow

```
Application

↓

Authenticate

↓

Vault

↓

Token

↓

Access Granted
```

---

# Tokens

After successful authentication,

Vault issues a token.

```
Login

↓

Vault Token

↓

Secret Access
```

Tokens can expire automatically.

---

# Policies

Policies define what a user or application is allowed to access.

Example

```
Developer

↓

Read

----------------

Administrator

↓

Read

Write

Delete
```

Policies follow the Principle of Least Privilege.

---

# Secret Engines

Vault stores secrets using Secret Engines.

Examples:

- Key/Value (KV)
- Database
- PKI
- Transit
- AWS
- Azure
- GCP

Each engine serves a different purpose.

---

# KV Secret Engine

Stores static secrets.

Example

```
Database Password

↓

Vault

↓

Application
```

---

# Database Secret Engine

Instead of storing permanent passwords,

Vault generates temporary database credentials.

Workflow

```
Application

↓

Vault

↓

Temporary DB User

↓

Database
```

After expiration,

the credentials become invalid automatically.

---

# Dynamic Secrets

One of Vault's biggest advantages is **Dynamic Secrets**.

Instead of storing fixed passwords,

Vault creates new credentials on demand.

```
Application

↓

Vault

↓

New Credential

↓

Database
```

Every request can receive a different username and password.

---

# Why Dynamic Secrets?

Benefits:

✔ Reduced Credential Reuse

✔ Automatic Expiration

✔ Improved Security

✔ Easier Rotation

---

# Secret Rotation

Vault can rotate secrets automatically.

Example

```
Old Password

↓

Generate New Password

↓

Update Service

↓

Revoke Old Password
```

Applications continue using valid credentials without manual intervention.

---

# Encryption as a Service

Vault can encrypt application data without storing it.

Workflow

```
Application

↓

Vault

↓

Encrypt

↓

Encrypted Data
```

Applications do not need to implement encryption logic themselves.

---

# PKI Secret Engine

Vault can act as an internal Certificate Authority.

It can generate:

- TLS Certificates
- Client Certificates
- Server Certificates

This simplifies certificate management.

---

# Audit Logging

Every Vault operation can be recorded.

Example

```
User

↓

Read Secret

↓

Audit Log
```

Audit logs help with:

- Compliance
- Incident Investigation
- Security Monitoring

---

# Vault Storage

Vault supports multiple storage backends.

Examples:

- Integrated Storage (Raft)
- Consul
- Cloud Storage
- Filesystem (for development)

Integrated Storage using Raft is commonly recommended for production.

---

# High Availability

Production Vault deployments often use multiple servers.

```
Vault Cluster

│

├── Active Node

├── Standby Node

└── Standby Node
```

If the active node fails,

a standby node becomes active.

---

# Vault in Kubernetes

Vault integrates directly with Kubernetes.

Workflow

```
Pod

↓

Kubernetes Authentication

↓

Vault

↓

Secrets

↓

Application
```

Secrets are retrieved at runtime rather than embedded in container images.

---

# Vault Agent

Vault Agent can automatically retrieve and renew secrets.

```
Application

↓

Vault Agent

↓

Vault

↓

Secret
```

Applications no longer need to communicate with Vault directly.

---

# Enterprise Example

A banking application:

```
Microservice

↓

Vault

↓

Temporary Database Credential

↓

Database

↓

Credential Expires Automatically
```

Even if credentials are stolen,

they quickly become invalid.

---

# Vault vs Kubernetes Secrets

| Vault | Kubernetes Secrets |
|--------|--------------------|
| Dynamic Secrets | Static Secrets |
| Automatic Rotation | Manual Rotation |
| Encryption Services | Secret Storage Only |
| Rich Audit Logs | Limited Auditing |
| Multiple Authentication Methods | Kubernetes Native Authentication |

Many organizations use Vault together with Kubernetes.

---

# Vault vs AWS Secrets Manager

| Vault | AWS Secrets Manager |
|--------|---------------------|
| Multi-Cloud | AWS Only |
| Open Source | Managed Service |
| Dynamic Secrets | Limited Dynamic Secrets |
| Encryption Services | Secret Storage |
| Self-Hosted or Managed | Managed AWS Service |

---

# Common Use Cases

Vault is widely used for:

- Database Credentials
- Cloud Credentials
- API Keys
- SSH Certificates
- TLS Certificates
- Kubernetes Secrets
- CI/CD Pipelines
- Encryption

---

# Common Beginner Mistakes

### Mistake 1

Using Vault as a simple password storage tool.

Vault offers dynamic secrets, encryption, auditing and policy-based access.

---

### Mistake 2

Creating long-lived tokens.

Use short-lived tokens whenever possible.

---

### Mistake 3

Giving applications unrestricted access.

Apply least privilege policies.

---

### Mistake 4

Disabling audit logging.

Audit logs are critical for compliance and investigations.

---

### Mistake 5

Using static credentials everywhere.

Prefer dynamic secrets whenever supported.

---

# Interview Questions

### Q1. What is HashiCorp Vault?

HashiCorp Vault is a platform for securely storing, managing and distributing secrets.

---

### Q2. What are Dynamic Secrets?

Dynamic Secrets are temporary credentials generated on demand and automatically expired.

---

### Q3. What are Vault Policies?

Policies define which secrets users or applications can access.

---

### Q4. Why is Vault better than storing passwords in configuration files?

Vault centralizes secrets, supports auditing, rotation, encryption and access control.

---

### Q5. Can Vault integrate with Kubernetes?

Yes.

Vault supports Kubernetes authentication and secure secret delivery to Pods.

---

### Q6. What is the benefit of Secret Rotation?

Rotation reduces the risk associated with compromised credentials.

---

# Production Best Practices

✔ Enable audit logging.

✔ Use Integrated Storage (Raft) for production clusters.

✔ Apply least privilege policies.

✔ Prefer dynamic secrets over static credentials.

✔ Rotate secrets automatically.

✔ Use short-lived authentication tokens.

✔ Secure Vault communication with TLS.

✔ Back up Vault data securely.

---

# Key Takeaways

- HashiCorp Vault is a leading enterprise secrets management platform.
- Vault centralizes secret storage and access control.
- Dynamic secrets greatly reduce credential exposure.
- Vault integrates with Kubernetes, cloud platforms and CI/CD pipelines.
- Automatic rotation, auditing and policy enforcement make Vault a cornerstone of modern DevSecOps.

---

# Next Section

## 11.7 Identity & Access Management (IAM)

In the next section, we will learn:

- What is IAM?
- IAM Components
- Users, Groups & Roles
- Policies
- Least Privilege
- Cloud IAM (AWS, Azure, GCP)
- Kubernetes RBAC & IAM
- Enterprise Best Practices
- Interview Questions
---

# 11.8 Docker Security

Docker makes application deployment simple,

but containers are **not automatically secure**.

A Docker container shares the host operating system kernel.

If a container is misconfigured,

an attacker may escape the container,

gain elevated privileges,

or compromise the host.

For this reason,

Docker security is a fundamental part of DevSecOps.

---

# Why Docker Security Matters

Suppose an application runs inside a container.

```
Application

↓

Docker Container

↓

Host OS
```

If the container is compromised,

the attacker may attempt to reach:

- Host Files
- Docker Socket
- Other Containers
- Kubernetes Cluster
- Cloud Resources

Proper security controls reduce this risk.

---

# What is Docker Security?

Docker Security refers to the collection of practices and technologies used to protect:

- Docker Images
- Containers
- Docker Hosts
- Registries
- Networks
- Secrets
- Runtime Environment

---

# Docker Security Layers

```
Docker Security

│

├── Image Security

├── Container Security

├── Host Security

├── Network Security

├── Runtime Security

├── Secrets Management

└── Registry Security
```

Each layer should be secured independently.

---

# Docker Architecture

```
Application

↓

Docker Image

↓

Docker Container

↓

Docker Engine

↓

Linux Kernel

↓

Host
```

Security weaknesses at any layer may affect the entire system.

---

# Container Isolation

Containers isolate applications from one another.

Isolation is achieved using Linux kernel features.

Main technologies include:

- Namespaces
- cgroups
- Capabilities
- Seccomp
- AppArmor
- SELinux

---

# Linux Namespaces

Namespaces isolate resources.

Examples:

- Process IDs
- Network Interfaces
- Mount Points
- Hostname
- Users
- IPC

Each container gets its own isolated view.

---

# Namespace Example

```
Container A

↓

PID 1

----------------

Container B

↓

PID 1
```

Although both see PID 1,

they are isolated.

---

# cgroups (Control Groups)

cgroups limit resource usage.

Examples:

- CPU
- Memory
- Disk I/O
- Network Bandwidth

Example

```
Container

↓

Memory Limit

↓

512 MB
```

Without limits,

one container could consume all host resources.

---

# Running as Root

One of the biggest Docker security mistakes is:

```
Container

↓

Root User
```

If compromised,

the attacker has greater privileges inside the container.

---

# Non-Root Containers

Better approach:

```
Container

↓

Application User

↓

Limited Privileges
```

Applications should run as non-root whenever possible.

Example

```dockerfile
USER appuser
```

---

# Docker Capabilities

Linux divides root privileges into smaller units called capabilities.

Examples:

- CAP_NET_ADMIN
- CAP_SYS_ADMIN
- CAP_SYS_TIME

Instead of giving full root access,

grant only the required capabilities.

---

# Drop Unnecessary Capabilities

Example

```bash
docker run --cap-drop ALL
```

Then add back only required capabilities.

This follows the Principle of Least Privilege.

---

# Read-Only File System

Containers often do not need write access.

Example

```bash
docker run --read-only
```

This helps prevent attackers from modifying files inside the container.

---

# Seccomp

Seccomp filters Linux system calls.

Workflow

```
Application

↓

System Call

↓

Seccomp Policy

↓

Allowed?

↓

Kernel
```

Dangerous system calls can be blocked.

Docker provides a default Seccomp profile.

---

# AppArmor

AppArmor restricts application behavior.

Example

```
Container

↓

AppArmor Profile

↓

Allowed Actions
```

It limits file access and system operations.

---

# SELinux

On supported Linux distributions,

SELinux provides mandatory access control.

```
Container

↓

SELinux Policy

↓

Host Resources
```

SELinux further isolates containers from the host.

---

# Image Security

Images should come only from trusted sources.

Preferred sources:

- Official Images
- Internal Registry
- Verified Publishers

Avoid downloading random images from unknown publishers.

---

# Image Scanning

Images should be scanned before deployment.

Scanners detect:

- Known CVEs
- Outdated Packages
- Weak Configurations
- Malware (where supported)

Popular tools:

- Trivy
- Docker Scout
- Grype
- Snyk

---

# Image Signing

Image signing verifies image authenticity.

Example

```
Developer

↓

Sign Image

↓

Registry

↓

Verify Signature

↓

Deploy
```

Signing helps prevent supply-chain attacks.

---

# Docker Registry Security

Private registries should use:

- Authentication
- TLS
- Role-Based Access
- Image Signing
- Audit Logs

Example

```
Developer

↓

Login

↓

Private Registry

↓

Pull Image
```

---

# Docker Secrets

Instead of hardcoding passwords,

Docker Swarm supports Docker Secrets.

```
Secret

↓

Container

↓

Application
```

Secrets are provided securely at runtime.

---

# Docker Networking Security

Best practices include:

- Use private bridge networks.
- Avoid unnecessary exposed ports.
- Restrict inter-container communication.
- Encrypt external communication with TLS.

---

# Docker Socket

The Docker socket:

```
/var/run/docker.sock
```

provides powerful control over the Docker daemon.

Mounting it inside containers can effectively grant control over the host.

Avoid exposing the Docker socket unless absolutely necessary.

---

# Resource Limits

Example

```bash
docker run \
  --memory=512m \
  --cpus=1
```

Limits improve stability and reduce denial-of-service risk.

---

# Logging & Monitoring

Monitor:

- Container Restarts
- CPU Usage
- Memory Usage
- Security Events
- Failed Logins
- Runtime Anomalies

Docker should be integrated with centralized monitoring and logging.

---

# Enterprise Example

A production deployment:

```
Developer

↓

Signed Image

↓

Private Registry

↓

Image Scan

↓

Docker Host

↓

Non-Root Container

↓

Monitoring
```

Security checks occur before and during runtime.

---

# Docker Security Checklist

✔ Use trusted base images.

✔ Keep images updated.

✔ Run containers as non-root.

✔ Enable Seccomp.

✔ Use AppArmor or SELinux.

✔ Limit resources.

✔ Drop unnecessary capabilities.

✔ Scan images regularly.

✔ Use secrets management.

✔ Monitor runtime activity.

---

# Common Beginner Mistakes

### Mistake 1

Running every container as root.

Always prefer non-root users.

---

### Mistake 2

Using the `latest` image tag everywhere.

Pin images to specific, tested versions.

---

### Mistake 3

Embedding passwords inside Docker images.

Use secret management solutions instead.

---

### Mistake 4

Ignoring image vulnerabilities.

Scan images before deployment.

---

### Mistake 5

Mounting the Docker socket into application containers.

Only do this when absolutely necessary and understand the security implications.

---

# Interview Questions

### Q1. Why should containers avoid running as root?

Running as non-root reduces the impact of a container compromise.

---

### Q2. What are Linux Namespaces?

Namespaces isolate resources such as processes, networking and file systems.

---

### Q3. What are cgroups?

cgroups limit CPU, memory and other resource usage.

---

### Q4. What is Seccomp?

Seccomp restricts Linux system calls available to containerized applications.

---

### Q5. Why should Docker images be scanned?

To identify known vulnerabilities before deployment.

---

### Q6. Why is the Docker socket sensitive?

Because access to the Docker daemon can provide extensive control over containers and potentially the host.

---

# Production Best Practices

✔ Use minimal base images.

✔ Run containers as non-root.

✔ Enable Seccomp and AppArmor or SELinux.

✔ Scan every image before deployment.

✔ Keep images updated.

✔ Sign container images.

✔ Store secrets securely.

✔ Monitor container runtime activity.

---

# Key Takeaways

- Docker security involves protecting images, containers, hosts and registries.
- Containers should run with the least privileges possible.
- Linux namespaces and cgroups provide isolation and resource control.
- Image scanning and signing strengthen software supply-chain security.
- Runtime protections such as Seccomp, AppArmor and SELinux reduce attack surfaces.

---

# Next Section

## 11.9 Kubernetes Security

In the next section, we will learn:

- Kubernetes Security Fundamentals
- API Server Security
- RBAC
- Network Policies
- Pod Security
- Admission Controllers
- Secrets Security
- Runtime Protection
- Production Best Practices
- Interview Questions
---

# 11.9 Kubernetes Security

Kubernetes is one of the most powerful container orchestration platforms,

but it also introduces many security challenges.

A Kubernetes cluster contains:

- API Server
- Worker Nodes
- Pods
- Containers
- Secrets
- Service Accounts
- Networking

If any one of these components is compromised,

the entire cluster may be at risk.

Therefore,

Kubernetes security is one of the most important topics in modern DevSecOps.

---

# Why Kubernetes Security Matters

Suppose an attacker gains access to:

```
One Pod

↓

Service Account Token

↓

Kubernetes API

↓

Cluster Resources
```

If permissions are too broad,

the attacker could control the cluster.

Proper security controls prevent this.

---

# What is Kubernetes Security?

Kubernetes Security is the practice of protecting:

- Cluster Components
- Applications
- Containers
- Nodes
- Networking
- Secrets
- Workloads

through multiple layers of security.

---

# Kubernetes Security Layers

```
Kubernetes Security

│

├── Cluster Security

├── API Server Security

├── Authentication

├── Authorization

├── Pod Security

├── Network Security

├── Secrets Security

├── Runtime Security

└── Supply Chain Security
```

---

# Kubernetes Architecture

```
Users

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
```

Every layer requires proper security controls.

---

# Cluster Security

Protect the cluster by:

- Keeping Kubernetes updated
- Securing etcd
- Restricting API access
- Enabling Audit Logs
- Using TLS Everywhere

---

# API Server Security

The API Server is the control plane entry point.

```
kubectl

↓

API Server

↓

Cluster
```

Best Practices:

✔ Enable Authentication

✔ Enable Authorization

✔ Enable Audit Logging

✔ Use TLS

✔ Restrict Network Access

---

# Authentication

Kubernetes supports:

- Client Certificates
- Service Accounts
- OpenID Connect (OIDC)
- Cloud IAM
- Bearer Tokens

Authentication verifies identity before access.

---

# Authorization

Common authorization methods:

- RBAC
- Node Authorization
- Webhook Authorization

RBAC is the most widely used.

---

# Role-Based Access Control (RBAC)

RBAC controls permissions using:

```
Role

↓

RoleBinding

↓

User

↓

Resource
```

Example

```
Developer

↓

Deploy Pods

✔

Delete Nodes

✖
```

---

# ClusterRole

A ClusterRole applies across the entire cluster.

Example permissions:

- View Nodes
- Manage Namespaces
- Access Cluster Resources

Use ClusterRoles only when cluster-wide permissions are required.

---

# Service Accounts

Applications should use Service Accounts instead of user credentials.

```
Pod

↓

Service Account

↓

API Access
```

Assign only the permissions each workload needs.

---

# Principle of Least Privilege

Every Pod,

Service Account,

and User should receive only the minimum required permissions.

Never grant:

```
cluster-admin
```

unless absolutely necessary.

---

# Pod Security

Pods should follow secure configurations.

Recommendations:

✔ Run as Non-Root

✔ Read-Only Root Filesystem

✔ Drop Linux Capabilities

✔ Disable Privileged Mode

✔ Use Resource Limits

---

# Security Context

Example

```yaml
securityContext:
  runAsNonRoot: true
  readOnlyRootFilesystem: true
  allowPrivilegeEscalation: false
```

Security Context defines runtime security settings for Pods and containers.

---

# Privileged Containers

Avoid running:

```yaml
privileged: true
```

Privileged containers receive extensive access to the host and should be used only for specific infrastructure workloads.

---

# Pod Security Admission

Modern Kubernetes uses **Pod Security Admission** to enforce Pod Security Standards.

Profiles include:

- Privileged
- Baseline
- Restricted

The **Restricted** profile provides the strongest built-in security controls.

---

# Network Policies

By default,

many Kubernetes networking solutions allow Pods to communicate freely.

Network Policies restrict traffic.

Example

```
Frontend

↓

Backend

↓

Database
```

Unauthorized Pods cannot communicate.

---

# Example Network Policy

```
Frontend

↓

Backend

✔

----------------

Unknown Pod

↓

Database

✖
```

---

# Secrets Security

Kubernetes Secrets should be protected.

Recommendations:

✔ Enable Encryption at Rest

✔ Use RBAC

✔ Rotate Secrets

✔ Consider External Secret Managers

---

# etcd Security

etcd stores cluster state.

It contains:

- Secrets
- Configurations
- Cluster Metadata

Best Practices:

✔ Encrypt etcd

✔ Restrict Access

✔ Backup Regularly

✔ Use TLS

---

# Admission Controllers

Admission Controllers validate or modify requests before objects are stored.

Examples:

- Resource Validation
- Security Policy Enforcement
- Image Restrictions

They add another layer of protection.

---

# Image Security

Only deploy:

- Trusted Images
- Signed Images
- Scanned Images

Never deploy images from unknown sources.

---

# Image Pull Policy

Example

```yaml
imagePullPolicy: IfNotPresent
```

For production,

ensure image versions are controlled and trusted.

---

# Runtime Security

Monitor workloads for:

- Privilege Escalation
- Unexpected Processes
- Suspicious Network Connections
- Container Escapes
- File System Changes

Runtime security tools provide additional protection.

---

# Audit Logging

Enable Kubernetes Audit Logs.

Audit logs record:

- User Activity
- API Requests
- Resource Changes
- Authentication Events

Audit logs are essential for investigations.

---

# Kubernetes Security Workflow

```
Developer

↓

Secure Image

↓

Image Scan

↓

Admission Controller

↓

RBAC

↓

Pod Deployment

↓

Runtime Monitoring
```

---

# Enterprise Example

A production deployment:

```
Developer

↓

Git

↓

CI/CD

↓

Image Scan

↓

Signed Image

↓

Kubernetes

↓

RBAC

↓

Network Policies

↓

Monitoring
```

Every deployment passes multiple security checks.

---

# Common Kubernetes Security Risks

Examples:

- Privileged Pods
- Exposed Dashboard
- Over-Permissive RBAC
- Unencrypted Secrets
- Public API Server
- Outdated Kubernetes Version

---

# Kubernetes Security Checklist

✔ Enable RBAC

✔ Enable Audit Logs

✔ Encrypt Secrets

✔ Secure etcd

✔ Use Network Policies

✔ Use Pod Security Admission

✔ Scan Images

✔ Keep Kubernetes Updated

✔ Run Containers as Non-Root

✔ Apply Least Privilege

---

# Common Beginner Mistakes

### Mistake 1

Giving every user `cluster-admin`.

Grant only required permissions.

---

### Mistake 2

Running privileged containers.

Use privileged mode only when absolutely necessary.

---

### Mistake 3

Leaving the Kubernetes Dashboard publicly accessible.

Protect dashboards using authentication and network restrictions.

---

### Mistake 4

Ignoring Network Policies.

Without them,

workloads may communicate more broadly than intended.

---

### Mistake 5

Not encrypting Kubernetes Secrets.

Enable Encryption at Rest and protect etcd.

---

# Interview Questions

### Q1. What is RBAC?

Role-Based Access Control manages permissions using Roles and RoleBindings.

---

### Q2. Why should Pods run as non-root?

Running as non-root reduces the impact of container compromise.

---

### Q3. What is a Service Account?

A Kubernetes identity used by Pods to authenticate with the API Server.

---

### Q4. What are Network Policies?

Network Policies control which Pods can communicate with each other.

---

### Q5. Why should etcd be secured?

Because it stores sensitive cluster information including Secrets and configuration.

---

### Q6. What is Pod Security Admission?

A Kubernetes admission controller that enforces Pod Security Standards such as Privileged, Baseline and Restricted.

---

# Production Best Practices

✔ Enable RBAC.

✔ Enable Pod Security Admission.

✔ Encrypt Secrets and etcd.

✔ Apply Network Policies.

✔ Scan every container image.

✔ Run workloads as non-root.

✔ Enable audit logging.

✔ Keep Kubernetes updated with security patches.

---

# Key Takeaways

- Kubernetes security requires multiple layers of protection.
- RBAC, Service Accounts and Least Privilege are fundamental security controls.
- Pod Security Admission helps enforce secure workload configurations.
- Network Policies restrict Pod-to-Pod communication.
- Protecting etcd, Secrets and the API Server is essential for securing the cluster.
- Kubernetes security should be integrated into the CI/CD pipeline and runtime operations.

---

# Next Section

## 11.10 Container Image Scanning

In the next section, we will learn:

- What is Image Scanning?
- Why Image Scanning is Important
- CVEs
- Vulnerability Databases
- Trivy
- Docker Scout
- Grype
- CI/CD Integration
- Production Best Practices
- Interview Questions
---

# 11.10 Container Image Scanning

Building a Docker image is only the first step.

Before deploying that image into production,

organizations must verify that it does not contain:

- Known Vulnerabilities
- Malware
- Outdated Packages
- Weak Configurations
- Secrets
- Misconfigured Software

This process is called **Container Image Scanning**.

Image scanning is a critical part of modern DevSecOps.

---

# Why Image Scanning?

Suppose a developer builds a Docker image.

```
Application

↓

Docker Image

↓

Production
```

The image contains:

```
OpenSSL

↓

Known Critical CVE
```

If deployed,

the application becomes vulnerable.

Image scanning detects such issues before deployment.

---

# What is Container Image Scanning?

Container Image Scanning is the process of analyzing container images for security vulnerabilities and configuration issues before they are deployed.

---

# What Can Be Detected?

Modern scanners detect:

- Known CVEs
- Outdated Packages
- OS Vulnerabilities
- Language Package Vulnerabilities
- Secrets
- Misconfigurations
- Weak Base Images
- License Issues (tool-dependent)

---

# Image Scanning Workflow

```
Dockerfile

↓

Build Image

↓

Image Scanner

↓

Security Report

↓

Fix Vulnerabilities

↓

Deploy
```

---

# Why Companies Scan Images

Image scanning provides:

✔ Early Vulnerability Detection

✔ Secure CI/CD

✔ Compliance

✔ Risk Reduction

✔ Better Software Quality

✔ Supply Chain Security

---

# Common Vulnerability Sources

A container image may contain vulnerabilities from:

- Base Image
- Operating System Packages
- Application Dependencies
- Programming Libraries
- Runtime Components

Example

```
Ubuntu Image

↓

Old OpenSSL Package

↓

Critical Vulnerability
```

---

# CVE (Common Vulnerabilities and Exposures)

Security vulnerabilities are commonly identified using **CVE IDs**.

Example

```
CVE-2025-12345
```

Each CVE has:

- Identifier
- Severity
- Description
- Fix Information

---

# CVSS Score

Many vulnerabilities include a **CVSS (Common Vulnerability Scoring System)** score.

Typical ranges:

| Score | Severity |
|--------|----------|
| 0.0 | None |
| 0.1 – 3.9 | Low |
| 4.0 – 6.9 | Medium |
| 7.0 – 8.9 | High |
| 9.0 – 10.0 | Critical |

Organizations often block deployments with Critical vulnerabilities.

---

# Vulnerability Databases

Scanners compare packages against vulnerability databases.

Common sources include:

- NVD (National Vulnerability Database)
- GitHub Advisory Database
- Distribution Security Advisories
- Vendor Security Advisories

---

# Image Scanning Architecture

```
Developer

↓

Docker Image

↓

Scanner

↓

Vulnerability Database

↓

Security Report
```

---

# Popular Image Scanners

Widely used tools include:

- Trivy
- Docker Scout
- Grype
- Snyk
- Clair

Each tool has different strengths.

---

# Trivy

Trivy is one of the most popular open-source scanners.

It scans:

- Docker Images
- Kubernetes
- Filesystems
- Git Repositories
- IaC Configurations

Example

```bash
trivy image nginx:latest
```

---

# Docker Scout

Docker Scout integrates with Docker.

It analyzes:

- Base Images
- Vulnerabilities
- Image Recommendations
- Supply Chain Information

Example

```bash
docker scout quickview nginx:latest
```

---

# Grype

Grype is another open-source vulnerability scanner.

Example

```bash
grype nginx:latest
```

---

# Scan Report Example

Typical report:

```
Critical : 2

High : 5

Medium : 14

Low : 8
```

Organizations prioritize fixing Critical and High vulnerabilities first.

---

# CI/CD Integration

Image scanning should be automated.

Workflow

```
Git Commit

↓

Build Image

↓

Image Scan

↓

Pass?

↓

Deploy
```

If the scan fails,

deployment is blocked.

---

# Image Scanning in Jenkins

Typical pipeline:

```
Build

↓

Trivy Scan

↓

Unit Tests

↓

Push Image

↓

Deploy
```

---

# Kubernetes Workflow

```
Developer

↓

Container Image

↓

Scan

↓

Registry

↓

Kubernetes Deployment
```

Only approved images are deployed.

---

# Base Image Selection

Choose:

✔ Official Images

✔ Minimal Images

✔ Regularly Updated Images

Examples:

- Alpine Linux
- Ubuntu LTS
- Distroless Images
- Chainguard Images

Smaller images usually have fewer attack surfaces.

---

# Image Updates

Old images accumulate vulnerabilities.

Example

```
Ubuntu 20.04

↓

Old Packages

↓

Many CVEs
```

Updating packages reduces risk.

---

# False Positives

Sometimes scanners report vulnerabilities that:

- Are not exploitable
- Have no impact
- Already have compensating controls

Security teams should evaluate findings before remediation.

---

# Severity Prioritization

Typical priority:

```
Critical

↓

High

↓

Medium

↓

Low
```

Critical vulnerabilities should be addressed immediately.

---

# Enterprise Example

Company Workflow

```
Developer

↓

Docker Build

↓

Trivy

↓

Critical Vulnerability?

↓

YES

↓

Pipeline Failed

↓

Fix Image

↓

Rebuild
```

Only secure images reach production.

---

# Image Signing

After scanning,

many organizations sign images.

Workflow

```
Image

↓

Scan

↓

Sign

↓

Registry

↓

Deploy
```

Signed images help verify authenticity.

---

# Continuous Scanning

Scanning should not stop after deployment.

Reasons:

- New CVEs appear daily.
- Previously safe images may become vulnerable.

Organizations rescan stored images regularly.

---

# Common Beginner Mistakes

### Mistake 1

Scanning images only before production.

Images should be scanned continuously.

---

### Mistake 2

Ignoring High vulnerabilities.

High severity issues can also lead to compromise.

---

### Mistake 3

Using outdated base images.

Always update and rebuild images regularly.

---

### Mistake 4

Deploying images directly from public registries without validation.

Use trusted registries and scan every image.

---

### Mistake 5

Ignoring scan failures in CI/CD.

Pipelines should fail when critical security policies are violated.

---

# Interview Questions

### Q1. What is Container Image Scanning?

It is the process of detecting vulnerabilities and security issues in container images before deployment.

---

### Q2. What is a CVE?

A Common Vulnerabilities and Exposures (CVE) identifier uniquely identifies a publicly known security vulnerability.

---

### Q3. Name three popular image scanning tools.

- Trivy
- Docker Scout
- Grype

---

### Q4. Why should image scanning be integrated into CI/CD?

To prevent vulnerable images from reaching production.

---

### Q5. What is CVSS?

The Common Vulnerability Scoring System is used to measure vulnerability severity.

---

### Q6. Why should images be rescanned regularly?

Because new vulnerabilities may be discovered after the image was originally built.

---

# Production Best Practices

✔ Scan every image before deployment.

✔ Use minimal trusted base images.

✔ Update base images regularly.

✔ Block deployments containing critical vulnerabilities.

✔ Automate scanning in CI/CD.

✔ Rescan stored images periodically.

✔ Sign verified images.

✔ Keep vulnerability databases updated.

---

# Key Takeaways

- Image scanning identifies vulnerabilities before deployment.
- CVEs and CVSS scores help prioritize security fixes.
- Trivy, Docker Scout and Grype are popular scanning tools.
- Image scanning should be fully automated in CI/CD pipelines.
- Continuous scanning and image signing strengthen container supply-chain security.

---

# Next Section

## 11.11 Vulnerability Management

In the next section, we will learn:

- What is Vulnerability Management?
- Vulnerability Lifecycle
- Risk Assessment
- CVE & CVSS
- Patch Management
- Remediation
- Continuous Monitoring
- Enterprise Best Practices
- Interview Questions
---

# 11.11 Vulnerability Management

Modern software is built using:

- Operating Systems
- Programming Languages
- Open Source Libraries
- Docker Images
- Kubernetes
- Cloud Services

Every one of these components may contain security vulnerabilities.

Simply finding vulnerabilities is not enough.

Organizations must continuously identify,

assess,

prioritize,

fix,

and verify them.

This complete process is called **Vulnerability Management**.

---

# What is Vulnerability Management?

Vulnerability Management is a continuous security process used to identify, assess, prioritize, remediate and monitor security weaknesses.

It is not a one-time activity.

It is an ongoing cycle throughout the software and infrastructure lifecycle.

---

# Simple Definition

```
Find

↓

Analyze

↓

Prioritize

↓

Fix

↓

Verify

↓

Monitor
```

---

# Why Vulnerability Management?

Without Vulnerability Management

```
Known Vulnerability

↓

Ignored

↓

Attacker Exploits

↓

Data Breach
```

---

With Vulnerability Management

```
Scanner

↓

Find Vulnerability

↓

Patch

↓

Rescan

↓

Secure System
```

---

# Types of Vulnerabilities

Organizations commonly encounter vulnerabilities in:

- Operating Systems
- Docker Images
- Kubernetes
- Cloud Resources
- Applications
- Web Servers
- Databases
- Programming Libraries
- CI/CD Pipelines

---

# Vulnerability Lifecycle

```
Identify

↓

Assess

↓

Prioritize

↓

Remediate

↓

Verify

↓

Monitor
```

This lifecycle repeats continuously.

---

# Step 1 – Identify

Security teams identify vulnerabilities using:

- Vulnerability Scanners
- Security Audits
- Penetration Testing
- Bug Reports
- Threat Intelligence

---

# Step 2 – Assess

Each vulnerability is evaluated.

Questions include:

- Is it exploitable?
- Which systems are affected?
- What is the business impact?
- Is a patch available?

---

# Step 3 – Prioritize

Not every vulnerability has the same urgency.

Organizations prioritize using:

- CVSS Score
- Business Risk
- Internet Exposure
- Asset Criticality
- Active Exploitation

---

# CVE

Every publicly disclosed vulnerability usually receives a:

```
CVE Identifier
```

Example

```
CVE-2026-12345
```

This uniquely identifies the vulnerability.

---

# CVSS

CVSS measures vulnerability severity.

Typical ratings:

| Severity | Score |
|-----------|-------|
| Low | 0.1–3.9 |
| Medium | 4.0–6.9 |
| High | 7.0–8.9 |
| Critical | 9.0–10.0 |

Higher scores usually receive higher remediation priority.

---

# Risk Assessment

Security teams consider:

```
Severity

+

Likelihood

+

Business Impact

↓

Overall Risk
```

A Medium vulnerability on a public payment system may be more important than a High vulnerability on an isolated development server.

---

# Step 4 – Remediation

Common remediation methods include:

- Install Security Patches
- Upgrade Software
- Replace Vulnerable Libraries
- Update Container Images
- Change Configurations
- Disable Vulnerable Features

---

# Patch Management

Patch Management is a major part of vulnerability management.

Workflow

```
Vendor Releases Patch

↓

Testing

↓

Approval

↓

Production Deployment

↓

Verification
```

---

# Step 5 – Verification

After remediation,

security teams verify:

```
Rescan

↓

No Vulnerability Found

↓

Issue Closed
```

Verification ensures the fix was successful.

---

# Step 6 – Continuous Monitoring

Security does not end after patching.

Organizations continuously monitor:

- New CVEs
- Threat Intelligence
- Software Updates
- Infrastructure Changes

---

# Vulnerability Sources

Common information sources:

- National Vulnerability Database (NVD)
- Vendor Security Advisories
- GitHub Security Advisories
- Security Mailing Lists
- CERT Advisories

---

# Common Vulnerability Scanners

Popular tools include:

- Trivy
- Nessus
- Qualys
- OpenVAS
- Grype
- Snyk

Different tools specialize in different environments.

---

# Infrastructure Scanning

Infrastructure scanners examine:

- Linux Servers
- Windows Servers
- Virtual Machines
- Cloud Resources
- Network Devices

---

# Container Scanning

Container scanners check:

- Base Images
- Installed Packages
- Language Dependencies
- Configuration Issues

---

# Kubernetes Scanning

Kubernetes security tools check:

- RBAC
- Network Policies
- Pod Security
- Misconfigurations
- Exposed Services

---

# Dependency Scanning

Applications often depend on hundreds of third-party libraries.

Dependency scanners identify vulnerable packages.

Example

```
Application

↓

Log4j

↓

Critical CVE

↓

Upgrade Required
```

---

# Vulnerability Management Workflow

```
Developer

↓

CI/CD

↓

Security Scan

↓

Fix

↓

Deploy

↓

Continuous Monitoring
```

Security is integrated into the software delivery process.

---

# Enterprise Example

Suppose an organization has:

```
500 Servers

↓

Daily Scans

↓

Critical Vulnerability Found

↓

Emergency Patch

↓

Rescan

↓

Compliance Report
```

The issue is resolved before attackers can exploit it.

---

# Metrics

Organizations often track:

- Number of Open Vulnerabilities
- Mean Time to Remediate (MTTR)
- Critical Vulnerabilities
- Patch Compliance
- Scan Coverage
- Risk Trend

These metrics help measure security maturity.

---

# Vulnerability Prioritization Example

```
Critical

↓

Internet Facing

↓

Fix Immediately

----------------

High

↓

Production

↓

Fix Quickly

----------------

Medium

↓

Internal

↓

Planned Maintenance

----------------

Low

↓

Monitor
```

---

# Common Beginner Mistakes

### Mistake 1

Running scans only once.

Vulnerability management must be continuous.

---

### Mistake 2

Ignoring Medium vulnerabilities.

Multiple Medium vulnerabilities can combine into significant risk.

---

### Mistake 3

Applying patches directly to production.

Test patches before deployment.

---

### Mistake 4

Ignoring unsupported software.

End-of-life software often no longer receives security updates.

---

### Mistake 5

Closing vulnerabilities without verification.

Always rescan after remediation.

---

# Interview Questions

### Q1. What is Vulnerability Management?

Vulnerability Management is the continuous process of identifying, assessing, prioritizing, fixing and monitoring security vulnerabilities.

---

### Q2. What is the difference between a Vulnerability and a Risk?

A vulnerability is a weakness.

Risk is the likelihood and impact of that weakness being exploited.

---

### Q3. What is CVE?

A Common Vulnerabilities and Exposures (CVE) identifier uniquely identifies a publicly known vulnerability.

---

### Q4. What is CVSS?

CVSS measures the severity of security vulnerabilities.

---

### Q5. Why is patch management important?

Because patches remove known security vulnerabilities before attackers exploit them.

---

### Q6. Why should systems be rescanned?

To verify that vulnerabilities have been successfully remediated and that no new issues have appeared.

---

# Production Best Practices

✔ Perform regular vulnerability scans.

✔ Prioritize based on risk, not just severity.

✔ Patch systems promptly.

✔ Test updates before production.

✔ Automate scanning within CI/CD.

✔ Continuously monitor new CVEs.

✔ Track remediation metrics.

✔ Maintain a documented vulnerability management process.

---

# Key Takeaways

- Vulnerability Management is a continuous lifecycle, not a one-time activity.
- Risk assessment determines remediation priorities.
- Patch management and verification are critical steps.
- Continuous scanning helps detect newly disclosed vulnerabilities.
- Mature organizations automate vulnerability management across infrastructure, applications and containers.

---

# Next Section

## 11.12 SAST (Static Application Security Testing)

In the next section, we will learn:

- What is SAST?
- How SAST Works
- Advantages & Limitations
- Popular SAST Tools
- CI/CD Integration
- Production Best Practices
- Interview Questions