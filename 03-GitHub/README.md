# Chapter 3

# Git & GitHub for DevOps Engineers

---

# Chapter Objectives

After completing this chapter, you will understand:

- Why Version Control is important.
- Why every software company uses Git.
- Difference between Git and GitHub.
- How developers collaborate using Git.
- Git installation.
- Git workflow.
- Git commands.
- Branching Strategy.
- Merge & Rebase.
- Pull Requests.
- GitHub.
- GitHub Actions.
- Production Git Best Practices.

---

# 3.1 Introduction

Imagine you are working in a software company.

There are:

- 20 Developers
- 5 QA Engineers
- 4 DevOps Engineers

All of them are working on the same application.

Question:

**How can everyone modify the same project without overwriting each other's work?**

The answer is:

**Git**

Git is one of the most important tools in DevOps.

Without Git, modern software development is almost impossible.

---

# Real Company Example

Suppose ShopKart Pvt. Ltd. has started developing a new E-Commerce website.

The project contains:

```
Backend

↓

Java

----------------

Frontend

↓

React

----------------

Database

↓

MySQL

----------------

Infrastructure

↓

Terraform

----------------

CI/CD

↓

Jenkins
```

More than 30 engineers are working together.

Without Version Control,

their work would constantly overwrite each other.

Git solves this problem.

---

# What is Version Control?

Version Control is a system that records every change made to files.

Suppose you create:

```
login.java
```

Day 1

```
Version 1
```

Day 2

You add a Login Button.

```
Version 2
```

Day 3

You fix a bug.

```
Version 3
```

Instead of keeping multiple files like:

```
login-final.java

login-final2.java

login-final-latest.java

login-final-new.java
```

Git stores every version automatically.

---

# Life Without Git

Before Git,

developers often created folders like:

```
Project

Project_Final

Project_Final2

Project_Final_Last

Project_Final_Last_New

Project_Real_Final
```

This created confusion.

Nobody knew which version was correct.

---

# Life With Git

Git stores every version inside a repository.

```
Repository

↓

Version 1

↓

Version 2

↓

Version 3

↓

Version 4
```

At any time,

you can return to any previous version.

---

# Why Companies Use Git

Companies use Git because it provides:

- Version History
- Team Collaboration
- Backup
- Branching
- Merging
- Code Review
- Rollback
- Release Management

Git is the foundation of every CI/CD pipeline.

---

# Where Git is Used

Git is used by:

- Google
- Microsoft
- Amazon
- Netflix
- Flipkart
- Swiggy
- Zomato
- Paytm
- Startups
- Government Projects

Almost every software company uses Git.

---

# Git in DevOps

Git is not used only by Developers.

DevOps Engineers also store:

- Dockerfiles
- Kubernetes YAML
- Jenkinsfiles
- Terraform Code
- Ansible Playbooks
- Bash Scripts
- Helm Charts
- Monitoring Configurations

Everything is version controlled.

---

# Real Production Workflow

```
Developer

↓

Write Code

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

Production
```

Every deployment begins with Git.

---

# Example

Developer fixes a payment bug.

```
Developer

↓

Git Commit

↓

GitHub

↓

Jenkins

↓

Build

↓

Docker Image

↓

Deploy

↓

Production
```

Without Git,

this automated workflow cannot exist.

---

# Advantages of Git

- Distributed Version Control
- Fast
- Secure
- Offline Support
- Easy Collaboration
- Branching
- Merging
- Complete History
- Open Source

---

# Git vs Traditional Backup

Traditional Backup

```
Copy Folder

↓

Rename Folder

↓

Edit Files
```

Git

```
Commit

↓

History

↓

Rollback

↓

Branch

↓

Merge
```

Git is smarter, faster and more reliable.

---

# Interview Questions

### Q1. What is Git?

Git is a Distributed Version Control System used to track changes in source code.

---

### Q2. Why is Git important?

Git allows multiple developers to work on the same project while maintaining complete version history.

---

### Q3. Can Git be used without the Internet?

Yes.

Git works completely offline.

Internet is required only when communicating with remote repositories such as GitHub.

---

### Q4. Does DevOps use Git?

Yes.

Git is one of the most important tools used by DevOps Engineers.

---

# Key Takeaways

- Git is a Version Control System.
- Git stores every version of a project.
- Git enables collaboration.
- Git is used by Developers, DevOps Engineers and Cloud Engineers.
- Every CI/CD pipeline begins with Git.

---

# Next Section

## 3.2 Why Git Was Created

In the next section, we will understand:

- Problems before Git
- History of Git
- Why Linus Torvalds created Git
- Distributed Version Control
- Centralized vs Distributed Version Control
- Real Production Examples
---

# 3.2 Why Git Was Created

Before learning Git commands, every DevOps Engineer should understand **why Git was created.**

Knowing the history of Git helps you understand why it became the world's most popular Version Control System.

---

# Software Development Before Git

Imagine the year is **2000**.

A software company has 25 developers working on one application.

```
Developer A

↓

login.java

----------------

Developer B

↓

payment.java

----------------

Developer C

↓

database.sql
```

Every developer manually copies files between computers.

Soon problems begin.

---

# Common Problems Before Git

Developers faced problems like:

- File Overwritten
- Wrong Version
- Lost Code
- Duplicate Files
- No Backup
- Difficult Collaboration

Example

```
Project

↓

Project_New

↓

Project_Final

↓

Project_Final_New

↓

Project_Final_Latest

↓

Project_Final_Really_Final
```

Nobody knew which folder contained the latest code.

---

# Real Company Problem

Suppose Rahul and Priya are working on the same file.

```
login.java
```

Rahul adds:

```
Password Validation
```

Priya adds:

```
OTP Verification
```

Both save the file.

Now whose version should be kept?

One person's work is lost.

Large companies faced this issue every day.

---

# Earlier Version Control Systems

Before Git, companies used centralized systems like:

- CVS
- SVN (Subversion)
- Perforce

These systems worked,

but had several limitations.

---

# Centralized Version Control

```
Developer A

↓

Central Server

↑

Developer B

↑

Developer C
```

Everything depended on one server.

If the server failed,

development stopped.

---

# Problems with Centralized Systems

Suppose the central server crashes.

```
Central Server

↓

Failure

↓

No Commit

↓

No History

↓

No Collaboration
```

The entire development team becomes blocked.

This was a major business risk.

---

# Why Git Was Created

In **2005**, the Linux Kernel project needed a better Version Control System.

Linus Torvalds, the creator of Linux, designed Git to solve these problems.

His goals were:

- Speed
- Reliability
- Distributed Architecture
- Data Integrity
- Efficient Branching
- Offline Support

Today, Git is the most widely used Version Control System in the world.

---

# Distributed Version Control

Git introduced a new idea.

Instead of keeping only one copy,

every developer receives a complete copy of the repository.

```
Developer A

↓

Complete Repository

----------------

Developer B

↓

Complete Repository

----------------

Developer C

↓

Complete Repository
```

Every machine contains the complete history.

---

# Advantages of Distributed Git

Even if GitHub becomes unavailable,

developers can continue working.

Example

```
Laptop

↓

Commit

↓

Commit

↓

Commit

↓

Internet Restored

↓

Push to GitHub
```

Development never stops.

---

# Data Integrity

Git identifies every version using a unique SHA (Secure Hash).

Example

```
Commit

↓

a8f1c23

↓

Unique Identity
```

If even one character changes,

Git generates a completely different hash.

This ensures data integrity.

---

# Why Git is Fast

Git stores most operations locally.

Examples:

- Commit
- Branch
- Merge
- History
- Log

These operations do not require the Internet.

As a result,

Git is extremely fast.

---

# Git Solved Major Problems

Before Git

```
Lost Files

↓

Conflicts

↓

Manual Backup

↓

Slow Collaboration
```

After Git

```
Commit

↓

History

↓

Branch

↓

Merge

↓

Rollback

↓

Collaboration
```

Software development became much easier.

---

# Real Production Example

Suppose ShopKart has:

- 100 Developers
- 20 QA Engineers
- 10 DevOps Engineers

Every engineer clones the repository.

Each person works independently.

```
Git Repository

↓

Clone

↓

Developer Laptop

↓

Commit

↓

Push

↓

GitHub
```

No one's work is overwritten.

---

# Git in Modern DevOps

Every DevOps workflow starts with Git.

```
Developer

↓

Git Commit

↓

GitHub

↓

Pull Request

↓

Code Review

↓

Merge

↓

Jenkins

↓

Docker

↓

Kubernetes

↓

Production
```

Without Git,

modern CI/CD pipelines cannot function efficiently.

---

# Centralized vs Distributed Version Control

| Feature | Centralized | Git |
|----------|-------------|-----|
| Offline Work | No | Yes |
| Speed | Moderate | Very Fast |
| Complete History | Server Only | Every Developer |
| Backup | Server | Every Clone |
| Branching | Slow | Very Fast |
| Collaboration | Good | Excellent |

---

# Interview Questions

### Q1. Why was Git created?

Git was created to provide a fast, distributed and reliable Version Control System for software development.

---

### Q2. Who created Git?

**Linus Torvalds** created Git in 2005.

---

### Q3. What is the biggest advantage of Git over centralized systems?

Every developer has a complete copy of the repository and can work offline.

---

### Q4. Can Git work without GitHub?

Yes.

Git is a Version Control System.

GitHub is only a remote hosting platform.

---

### Q5. Why is Git considered a Distributed Version Control System?

Because every cloned repository contains the complete project history.

---

# Key Takeaways

- Git was created in 2005 by Linus Torvalds.
- Git solved the limitations of centralized version control systems.
- Every developer has a complete copy of the repository.
- Git supports offline development.
- Git forms the foundation of modern DevOps workflows.

---

# Next Section

## 3.3 Git vs GitHub

In the next section, we will clearly understand the difference between:

- Git
- GitHub
- GitLab
- Bitbucket

using real production examples, because this is one of the most commonly asked interview questions.
---

# 3.3 Git vs GitHub

One of the most common interview questions is:

> **What is the difference between Git and GitHub?**

Many beginners think Git and GitHub are the same.

They are not.

Git and GitHub solve different problems.

---

# What is Git?

Git is a **Version Control System (VCS).**

It helps developers:

- Track Code Changes
- Maintain Version History
- Create Branches
- Merge Code
- Roll Back Changes

Git works completely on your local computer.

Example

```
Laptop

↓

Git Repository

↓

Commit

↓

History
```

Internet is not required.

---

# What is GitHub?

GitHub is a **Cloud Repository Hosting Platform.**

It stores Git repositories online.

GitHub provides:

- Cloud Storage
- Collaboration
- Pull Requests
- Code Review
- Issue Tracking
- GitHub Actions
- Team Management

Example

```
Developer Laptop

↓

Git

↓

GitHub

↓

Cloud
```

---

# Simple Analogy

Imagine writing a book.

Git is like:

```
Microsoft Word

↓

Save Versions

↓

Undo

↓

History
```

GitHub is like:

```
Google Drive

↓

Store Book Online

↓

Share With Team

↓

Backup
```

Git manages versions.

GitHub stores and shares them.

---

# Git Without GitHub

You can use Git without GitHub.

Example

```
Laptop

↓

Git Init

↓

Commit

↓

Commit

↓

Commit
```

Everything works locally.

No Internet required.

---

# GitHub Without Git

GitHub cannot function without Git.

GitHub stores Git repositories.

It does not replace Git.

---

# Real Company Workflow

Suppose ShopKart has 50 developers.

Each developer works on their laptop.

```
Developer

↓

Git

↓

Local Repository
```

After completing work,

developers upload changes.

```
Git

↓

GitHub

↓

Central Repository
```

Other developers download the latest code.

---

# Git Workflow

```
Create Project

↓

git init

↓

Write Code

↓

git add

↓

git commit

↓

git push

↓

GitHub
```

Every project follows this workflow.

---

# GitHub Workflow

```
Developer

↓

Clone Repository

↓

Create Branch

↓

Write Code

↓

Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

Merge

↓

Production
```

This is the workflow followed by most software companies.

---

# Features of Git

Git provides:

- Version Control
- Branching
- Merging
- Commit History
- Offline Support
- Fast Performance

---

# Features of GitHub

GitHub provides:

- Remote Repository
- Collaboration
- Pull Requests
- Code Review
- GitHub Actions
- Security Scanning
- Team Permissions
- Issue Tracking

---

# Git Repository

A Git repository contains:

```
Source Code

↓

Commit History

↓

Branches

↓

Tags
```

Everything is stored locally.

---

# GitHub Repository

A GitHub repository contains:

```
Git Repository

↓

Cloud

↓

Available to Team
```

Developers anywhere in the world can collaborate.

---

# GitHub Collaboration Example

Suppose three developers work together.

```
Rahul

↓

GitHub Repository

↑

Priya

↑

Sandeep
```

Everyone pushes code to GitHub.

Everyone pulls the latest updates.

No files are exchanged using email.

---

# Real DevOps Workflow

```
Developer

↓

Git Commit

↓

GitHub Push

↓

GitHub Repository

↓

Jenkins Pipeline

↓

Docker Build

↓

Kubernetes Deployment

↓

Production
```

Every deployment starts from GitHub.

---

# GitHub Is Not a Backup Only

Many beginners think GitHub is only for backup.

Actually it is used for:

- Team Collaboration
- Code Review
- CI/CD
- Automation
- Documentation
- Releases
- Security

---

# Git Hosting Platforms

GitHub is not the only platform.

Other popular platforms include:

| Platform | Usage |
|-----------|-------|
| GitHub | Most Popular |
| GitLab | Enterprise DevOps |
| Bitbucket | Atlassian Ecosystem |
| Azure Repos | Microsoft Azure DevOps |

All of them use Git.

---

# Git vs GitHub

| Feature | Git | GitHub |
|----------|-----|---------|
| Type | Version Control System | Cloud Hosting Platform |
| Internet Required | No | Yes |
| Stores History | Yes | Yes |
| Collaboration | Limited (Local) | Excellent |
| Branching | Yes | Uses Git |
| Pull Requests | No | Yes |
| Code Review | No | Yes |
| CI/CD | No | GitHub Actions |

---

# Real Production Example

Suppose the Internet connection is lost.

Developer continues working.

```
Laptop

↓

Git Commit

↓

Git Commit

↓

Git Commit
```

When Internet returns,

```
git push

↓

GitHub Updated
```

No work is lost.

---

# Interview Questions

### Q1. What is Git?

Git is a Distributed Version Control System used to track changes in source code.

---

### Q2. What is GitHub?

GitHub is a cloud platform used to host Git repositories and enable collaboration.

---

### Q3. Can Git work without GitHub?

Yes.

Git works completely offline.

---

### Q4. Can GitHub work without Git?

No.

GitHub is built to host Git repositories.

---

### Q5. Name some alternatives to GitHub.

- GitLab
- Bitbucket
- Azure Repos

---

# Key Takeaways

- Git is a Version Control System.
- GitHub is a Cloud Hosting Platform.
- Git manages versions.
- GitHub enables collaboration.
- Every modern DevOps workflow uses both Git and GitHub.

---

# Next Section

## 3.4 Installing Git

In the next section, we will learn:

- Install Git on Windows
- Install Git on Ubuntu
- Install Git on Rocky Linux
- Verify Installation
- Configure Username
- Configure Email
- First Git Configuration

After that, we will create our first Git repository.
---

# 3.4 Installing Git

Before using Git, it must be installed and configured on your system.

Git is available for almost every operating system, including:

- Windows
- Linux
- macOS

Once installed, the same Git commands work almost everywhere.

---

# Verify Whether Git is Installed

The first step is to check whether Git is already installed.

Run:

```bash
git --version
```

Example Output

```text
git version 2.55.0.windows.1
```

If a version number is displayed,

Git is installed successfully.

---

# Install Git on Windows

Visit the official Git website.

```
https://git-scm.com
```

Download the latest Windows installer.

Installation Steps

```
Download Installer

↓

Run Setup

↓

Next

↓

Next

↓

Install

↓

Finish
```

After installation,

restart the terminal.

Verify

```bash
git --version
```

---

# Install Git on Ubuntu

Update package information.

```bash
sudo apt update
```

Install Git.

```bash
sudo apt install git -y
```

Verify.

```bash
git --version
```

---

# Install Git on Rocky Linux / RHEL

Install Git.

```bash
sudo dnf install git -y
```

Older systems may use:

```bash
sudo yum install git -y
```

Verify.

```bash
git --version
```

---

# Install Git on macOS

Using Homebrew.

```bash
brew install git
```

Verify.

```bash
git --version
```

---

# Why Verification is Important?

Always verify installation before proceeding.

Example

```
Install Git

↓

git --version

↓

Version Displayed

↓

Ready to Use
```

---

# Configure Git

Git needs two basic pieces of information.

- Username
- Email Address

These values are stored with every commit.

---

# Configure Username

```bash
git config --global user.name "Sandeep Pandey"
```

Example

```bash
git config --global user.name "Rahul Sharma"
```

---

# Configure Email

```bash
git config --global user.email "your@email.com"
```

Example

```bash
git config --global user.email "rahul@gmail.com"
```

---

# Why Username and Email?

Whenever you commit,

Git records:

```
Commit

↓

Username

↓

Email

↓

Date

↓

Time

↓

Commit ID
```

Every commit has an owner.

---

# Verify Configuration

Display all configured values.

```bash
git config --list
```

Example

```text
user.name=Sandeep Pandey

user.email=sandeep@example.com
```

---

# View Individual Configuration

Display username.

```bash
git config user.name
```

Display email.

```bash
git config user.email
```

---

# Global vs Local Configuration

Git supports two configuration levels.

### Global

Applies to every repository.

```bash
git config --global
```

### Local

Applies only to the current repository.

```bash
git config
```

without `--global`.

---

# Configuration Files

Global configuration

```
~/.gitconfig
```

Repository configuration

```
.git/config
```

Git reads these files automatically.

---

# Change Username

```bash
git config --global user.name "New Name"
```

---

# Change Email

```bash
git config --global user.email "new@email.com"
```

---

# Remove Configuration

Remove username.

```bash
git config --global --unset user.name
```

Remove email.

```bash
git config --global --unset user.email
```

---

# Real Production Example

A company has multiple developers.

Every commit must identify the author.

Example

```
Developer

↓

Git Commit

↓

Username

↓

Email

↓

Git History
```

This helps during:

- Code Review
- Auditing
- Debugging
- Rollback

---

# Production Best Practices

✔ Use your official company email.

✔ Configure Git immediately after installation.

✔ Verify configuration before committing code.

✔ Never use another developer's identity.

✔ Keep the same identity across all company projects.

---

# Common Installation Problems

### Problem

```
git is not recognized as an internal or external command
```

Reason

Git is either:

- Not Installed
- PATH Variable Not Configured

Solution

- Install Git.
- Restart the terminal.
- Verify using:

```bash
git --version
```

---

### Problem

Wrong Username

Solution

```bash
git config --global user.name "Correct Name"
```

---

### Problem

Wrong Email

Solution

```bash
git config --global user.email "correct@email.com"
```

---

# Interview Questions

### Q1. Which command verifies Git installation?

```bash
git --version
```

---

### Q2. Which command configures the Git username?

```bash
git config --global user.name "Your Name"
```

---

### Q3. Which command configures the Git email?

```bash
git config --global user.email "your@email.com"
```

---

### Q4. Which command displays Git configuration?

```bash
git config --list
```

---

### Q5. Where is the global Git configuration stored?

```
~/.gitconfig
```

---

# Key Takeaways

- Install Git before creating repositories.
- Always verify installation using `git --version`.
- Configure your username and email before making commits.
- Use `git config --list` to verify settings.
- Proper configuration ensures accurate commit history.

---

# Next Section

## 3.5 Git Architecture

In the next section, we will learn one of the most important Git concepts:

- Working Directory
- Staging Area
- Local Repository
- Remote Repository
- Complete Git Workflow

Understanding Git Architecture makes all Git commands easy to understand.
---

# 3.5 Git Architecture

Before learning Git commands, every DevOps Engineer must understand **how Git works internally**.

Many beginners memorize commands like:

- git add
- git commit
- git push

But they don't understand **where the data actually goes**.

Once you understand Git Architecture,

all Git commands become easy.

---

# Git Architecture Overview

Git has four important areas.

```
Working Directory

↓

Staging Area

↓

Local Repository

↓

Remote Repository (GitHub)
```

Every Git operation moves changes between these four areas.

---

# Step 1 — Working Directory

The Working Directory is the folder where you write and modify your project files.

Example

```
ShoppingApp

│

├── index.html

├── app.js

├── style.css

└── README.md
```

This is where developers spend most of their time.

---

# Real Example

Suppose you open

```
app.js
```

and add

```javascript
console.log("Welcome");
```

The file changes.

At this stage,

Git knows the file has changed,

but it is **not yet saved into Git history.**

---

# Step 2 — Staging Area

The Staging Area is a temporary place where you prepare changes before creating a commit.

Think of it as a **waiting room**.

```
Modified File

↓

git add

↓

Staging Area
```

Nothing is permanently saved yet.

---

# Why Staging Area Exists?

Imagine you modified three files.

```
login.java

payment.java

profile.java
```

You only want to commit

```
payment.java
```

Git allows you to stage only that file.

Without the staging area,

every modified file would be committed automatically.

---

# Step 3 — Local Repository

Once the staged files are ready,

you create a commit.

```
git commit
```

Git stores the snapshot inside the Local Repository.

```
Working Directory

↓

Staging Area

↓

Commit

↓

Local Repository
```

Now your changes are permanently recorded.

---

# What is a Commit?

A Commit is a snapshot of your project at a particular point in time.

Example

```
Commit 1

↓

Login Page

----------------

Commit 2

↓

Payment Module

----------------

Commit 3

↓

Bug Fixed
```

Each commit has its own unique ID.

---

# Step 4 — Remote Repository

The Local Repository exists only on your computer.

To share your work,

you push it to GitHub.

```
Local Repository

↓

git push

↓

GitHub Repository
```

Now the entire team can access your changes.

---

# Complete Git Flow

```
Write Code

↓

Working Directory

↓

git add

↓

Staging Area

↓

git commit

↓

Local Repository

↓

git push

↓

GitHub
```

This is the workflow followed by almost every software company.

---

# Downloading Code

When another developer wants the latest code,

they run

```bash
git pull
```

Flow

```
GitHub

↓

git pull

↓

Local Repository

↓

Working Directory
```

Everyone receives the latest version.

---

# Real Company Workflow

Suppose four developers work on the same project.

```
Rahul

↓

GitHub

↑

Priya

↑

Sandeep

↑

Amit
```

Every developer

- Writes code
- Commits locally
- Pushes to GitHub

Git keeps everyone's work synchronized.

---

# Visual Representation

```
                GitHub
          (Remote Repository)
                   ▲
                   │
             git push / pull
                   │
                   ▼
          Local Repository
              (Commits)
                   ▲
              git commit
                   │
                   ▼
            Staging Area
             (git add)
                   ▲
                   │
            Working Directory
            (Write Code)
```

This diagram is the foundation of Git.

---

# Example Workflow

Create a file.

```
notes.txt
```

Add some text.

```
Learning Git
```

Now execute:

```bash
git add notes.txt
```

The file moves to the Staging Area.

Next

```bash
git commit -m "Added notes file"
```

The file moves to the Local Repository.

Finally

```bash
git push
```

The file reaches GitHub.

---

# Why Git Uses Multiple Areas

Each layer has a purpose.

| Area | Purpose |
|------|----------|
| Working Directory | Create and Modify Files |
| Staging Area | Select Files for Commit |
| Local Repository | Store Commit History |
| Remote Repository | Share Code with Team |

---

# Production Example

Developer fixes a payment bug.

```
Modify Code

↓

git add

↓

git commit

↓

git push

↓

GitHub

↓

Jenkins Pipeline

↓

Docker Image

↓

Deploy

↓

Production
```

Every deployment begins with this architecture.

---

# Common Beginner Mistakes

### Mistake 1

Modify file and expect GitHub to update automatically.

❌ Wrong

Git requires

```
git add

↓

git commit

↓

git push
```

---

### Mistake 2

Run

```bash
git commit
```

without

```bash
git add
```

Nothing gets committed because Git only commits staged changes.

---

### Mistake 3

Commit locally but forget to push.

Result

Only your computer has the latest changes.

Your teammates cannot see them.

---

# Interview Questions

### Q1. What are the four areas of Git Architecture?

- Working Directory
- Staging Area
- Local Repository
- Remote Repository

---

### Q2. What is the purpose of the Staging Area?

It allows developers to select which changes should be included in the next commit.

---

### Q3. Where does `git commit` save changes?

Inside the Local Repository.

---

### Q4. Which command uploads commits to GitHub?

```bash
git push
```

---

### Q5. Which command downloads the latest changes from GitHub?

```bash
git pull
```

---

# Key Takeaways

- Git has four working areas.
- Files move through Git in a fixed sequence.
- The Staging Area acts as a preparation zone before committing.
- Commits are stored locally until pushed to GitHub.
- Understanding Git Architecture makes all future Git commands easier.

---

# Next Section

## 3.6 Creating Your First Git Repository

In the next section, we will learn:

- `git init`
- Create a Repository
- Understand the `.git` Folder
- First Commit
- Repository Structure
- Real Production Examples

This is where your hands-on Git journey begins.
---

# 3.6 Creating Your First Git Repository

Now that you understand Git Architecture, it is time to create your first Git repository.

This is the first practical step every developer and DevOps Engineer performs.

By the end of this section, you will know how to:

- Create a Repository
- Initialize Git
- Understand the `.git` directory
- Make your first commit
- View repository status

---

# What is a Git Repository?

A Git Repository is a project directory managed by Git.

It contains:

- Source Code
- Commit History
- Branches
- Configuration
- Git Metadata

Example

```
ShoppingApp

│

├── app.js

├── index.html

├── style.css

└── .git
```

The `.git` folder makes an ordinary directory into a Git repository.

---

# Step 1 – Create a Project Folder

Create a new directory.

```bash
mkdir MyProject
```

Move inside it.

```bash
cd MyProject
```

Current directory

```
MyProject
```

At this point,

Git is **not** managing this folder.

---

# Step 2 – Initialize Git

Run

```bash
git init
```

Output

```text
Initialized empty Git repository in ...

```

Git creates a hidden directory named

```
.git
```

Now Git starts tracking this project.

---

# What is the .git Folder?

The `.git` directory stores everything required by Git.

It contains:

- Commit History
- Branch Information
- Configuration
- References
- Objects
- Logs

Never delete the `.git` folder unless you intentionally want to remove Git from the project.

---

# View Hidden Files

Linux

```bash
ls -la
```

Windows PowerShell

```powershell
dir -Force
```

Example

```
MyProject

│

├── .git

├── README.md

└── app.py
```

---

# Step 3 – Create a File

Create a README file.

```bash
touch README.md
```

Windows

```powershell
New-Item README.md
```

Open the file and write:

```text
My First Git Project
```

Save the file.

---

# Step 4 – Check Repository Status

Run

```bash
git status
```

Output

```text
Untracked files:

README.md
```

Git knows the file exists,

but it is not yet tracked.

---

# Understanding Git Status

`git status` tells you:

- Current Branch
- Modified Files
- Untracked Files
- Staged Files
- Pending Commits

This is one of the most frequently used Git commands.

---

# Git File States

A file moves through several states.

```
Create File

↓

Untracked

↓

git add

↓

Staged

↓

git commit

↓

Tracked
```

Understanding these states is very important.

---

# Step 5 – Add File to Staging Area

Run

```bash
git add README.md
```

Or add every file.

```bash
git add .
```

Now check status.

```bash
git status
```

Output

```text
Changes to be committed:

README.md
```

The file is now staged.

---

# Step 6 – Create First Commit

Run

```bash
git commit -m "Initial Commit"
```

Example Output

```text
1 file changed

create mode 100644 README.md
```

Congratulations!

Your first commit has been created.

---

# Check Status Again

```bash
git status
```

Output

```text
nothing to commit,

working tree clean
```

Everything is saved.

---

# Repository Workflow

```
Create File

↓

git status

↓

git add

↓

git commit

↓

Repository Updated
```

---

# Real Example

Suppose you create

```
app.py
```

Contents

```python
print("Hello Git")
```

Now execute

```bash
git status

git add app.py

git commit -m "Added app.py"
```

The file becomes part of Git history.

---

# Common Beginner Mistakes

### Mistake 1

Forget to initialize Git.

```
git add

↓

Error

↓

Not a Git Repository
```

Solution

```bash
git init
```

---

### Mistake 2

Forget to stage files.

Running

```bash
git commit
```

without

```bash
git add
```

will not commit new changes.

---

### Mistake 3

Ignoring `git status`.

Professional developers check

```bash
git status
```

before almost every commit.

---

# Production Example

Developer starts a new microservice.

```
Create Project

↓

git init

↓

Write Code

↓

git add .

↓

git commit

↓

Push to GitHub

↓

CI/CD Starts
```

Every new project follows this pattern.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| mkdir | Create Project Folder |
| cd | Enter Folder |
| git init | Initialize Repository |
| git status | Check Repository Status |
| git add | Stage Files |
| git add . | Stage All Files |
| git commit -m | Save Changes |

---

# Interview Questions

### Q1. Which command creates a Git repository?

```bash
git init
```

---

### Q2. What is the purpose of the `.git` folder?

It stores all Git metadata, commit history, branches and configuration.

---

### Q3. Which command checks the repository status?

```bash
git status
```

---

### Q4. Which command stages all files?

```bash
git add .
```

---

### Q5. Which command creates a commit?

```bash
git commit -m "Commit Message"
```

---

# Key Takeaways

- Every Git project starts with `git init`.
- The `.git` folder stores the repository's internal data.
- `git status` should be checked frequently.
- Files must be staged before committing.
- Commits create permanent snapshots of your project.

---

# Next Section

## 3.7 Understanding Git Status & File Lifecycle

In the next section, we will learn:

- Untracked Files
- Tracked Files
- Modified Files
- Staged Files
- Committed Files
- Git Status in Detail
- Complete File Lifecycle with Real Examples

This is one of the most important Git concepts for beginners.
---

# 3.7 Understanding Git Status & File Lifecycle

One of the most confusing topics for beginners is understanding the output of:

```bash
git status
```

Every DevOps Engineer uses this command dozens of times every day.

If you understand the Git File Lifecycle, you will never be confused by Git again.

---

# Why is Git Status Important?

Imagine you modify ten files.

Questions arise:

- Which files changed?
- Which files are staged?
- Which files are committed?
- Which files are ignored?
- Which files will be pushed?

The answer is:

```bash
git status
```

---

# Git File Lifecycle

Every file passes through several stages.

```
Create File

↓

Untracked

↓

git add

↓

Staged

↓

git commit

↓

Tracked

↓

Modify

↓

Modified

↓

git add

↓

Staged

↓

git commit

↓

Tracked
```

This is called the **Git File Lifecycle**.

---

# Stage 1 – Untracked File

Suppose you create:

```
login.html
```

Run

```bash
git status
```

Output

```text
Untracked files:

login.html
```

Git knows the file exists,

but it is not managing it yet.

---

# Stage 2 – Staged File

Run

```bash
git add login.html
```

Check again.

```bash
git status
```

Output

```text
Changes to be committed:

login.html
```

Now the file is inside the Staging Area.

---

# Stage 3 – Committed File

Run

```bash
git commit -m "Added login page"
```

Now

```bash
git status
```

shows

```text
nothing to commit

working tree clean
```

Git is now tracking the file.

---

# Stage 4 – Modified File

Open

```
login.html
```

Add

```html
<button>Login</button>
```

Save.

Now

```bash
git status
```

Output

```text
Modified:

login.html
```

The file changed,

but Git has not staged the modification.

---

# Stage 5 – Restaged File

Run

```bash
git add login.html
```

Now

```bash
git status
```

shows

```text
Changes to be committed
```

The updated version is ready for commit.

---

# Stage 6 – New Commit

```bash
git commit -m "Added Login Button"
```

Git saves another snapshot.

---

# Complete File Lifecycle

```
Create File

↓

Untracked

↓

git add

↓

Staged

↓

git commit

↓

Tracked

↓

Modify

↓

Modified

↓

git add

↓

Staged

↓

git commit

↓

Tracked
```

Every file always follows this lifecycle.

---

# Working Tree Clean

Suppose

```bash
git status
```

returns

```text
nothing to commit,
working tree clean
```

Meaning:

✔ No modified files

✔ No staged files

✔ Repository is completely synchronized

This is the ideal state before switching branches.

---

# Example Project

```
ShoppingApp

│

├── login.html

├── payment.html

├── style.css

└── app.js
```

Suppose only

```
payment.html
```

changes.

Git Status

```text
Modified:

payment.html
```

Only that file requires staging.

---

# Multiple File Example

Project

```
login.html

payment.html

profile.html
```

Modify all three.

Run

```bash
git status
```

Output

```text
Modified:

login.html

payment.html

profile.html
```

Stage only

```bash
git add payment.html
```

Now

```text
Changes to be committed

payment.html

---------------------

Changes not staged

login.html

profile.html
```

This demonstrates the importance of the Staging Area.

---

# Git Status Colors

Most terminals display:

```
Red

↓

Modified / Untracked

---------------------

Green

↓

Staged
```

These colors make repository status easy to understand.

---

# Production Example

Developer fixes three bugs.

```
Login Bug

Payment Bug

Dashboard Bug
```

Manager requests:

"Deploy only the Payment Bug."

Developer stages only:

```bash
git add payment.java
```

Commit

```bash
git commit -m "Fixed Payment Bug"
```

The remaining changes stay uncommitted.

This is why the Staging Area exists.

---

# Common Beginner Mistakes

### Mistake 1

Editing a file and expecting GitHub to update automatically.

Wrong.

Modified files remain local until committed and pushed.

---

### Mistake 2

Running

```bash
git push
```

without creating a commit.

Nothing new is uploaded.

---

### Mistake 3

Ignoring

```bash
git status
```

Professional developers check repository status before almost every commit.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git status | Repository Status |
| git add | Stage File |
| git add . | Stage All Files |
| git commit | Save Snapshot |
| git push | Upload to GitHub |

---

# Interview Questions

### Q1. What are the stages of a Git file?

Untracked → Staged → Committed → Modified → Staged → Committed.

---

### Q2. What does "Working Tree Clean" mean?

There are no pending changes and the repository is fully committed.

---

### Q3. Which command stages a modified file?

```bash
git add filename
```

---

### Q4. Which command displays the current file state?

```bash
git status
```

---

### Q5. Can Git commit an untracked file directly?

No.

It must first be added to the Staging Area using `git add`.

---

# Key Takeaways

- Every Git file follows a fixed lifecycle.
- `git status` is one of the most important Git commands.
- Files must be staged before they can be committed.
- A clean working tree indicates there are no pending changes.
- Understanding file states prevents most beginner mistakes.

---

# Next Section

## 3.8 Git Add & Staging Area (Deep Dive)

In the next section, we will learn:

- `git add`
- `git add .`
- `git add -A`
- `git add <filename>`
- Why the Staging Area Exists
- Partial Staging
- Interactive Staging
- Real Production Examples

This section will explain one of Git's most powerful and unique features in detail.
---

# 3.8 Git Add & Staging Area (Deep Dive)

One of Git's most unique and powerful features is the **Staging Area**.

Many Version Control Systems directly save every modified file.

Git does something smarter.

It allows you to decide **exactly which changes should become part of the next commit.**

Understanding the Staging Area separates beginners from professional developers.

---

# What is the Staging Area?

The Staging Area is a temporary storage location between your Working Directory and Local Repository.

```
Working Directory

↓

git add

↓

Staging Area

↓

git commit

↓

Local Repository
```

Nothing reaches Git history until it is committed.

---

# Why Does Git Have a Staging Area?

Suppose today you worked on three different tasks.

```
Login Bug

↓

Payment Bug

↓

Dashboard UI
```

Your manager says:

> "Deploy only the Payment Bug."

Without a Staging Area,

all three changes would be committed together.

Git allows you to stage only the required files.

---

# Example Project

```
ShoppingApp

│

├── login.html

├── payment.html

├── dashboard.html

└── style.css
```

You modified every file.

But today you only want to commit

```
payment.html
```

Run

```bash
git add payment.html
```

Only that file enters the Staging Area.

---

# git add

Syntax

```bash
git add filename
```

Example

```bash
git add app.py
```

Only

```
app.py
```

moves to the Staging Area.

---

# git add .

One of the most commonly used commands.

```bash
git add .
```

Stages every new and modified file in the current directory.

Example

```
Project

↓

login.html

payment.html

style.css

↓

git add .
```

All files become staged.

---

# git add -A

Stages:

- New Files
- Modified Files
- Deleted Files

Command

```bash
git add -A
```

This is commonly used before large commits.

---

# git add *

Another variation

```bash
git add *
```

It stages matching files,

but behaves differently from `git add .` in some cases.

Most companies prefer

```bash
git add .
```

or

```bash
git add -A
```

---

# Stage Multiple Files

Example

```bash
git add login.html payment.html
```

Only these files are staged.

---

# Stage an Entire Folder

```bash
git add src/
```

Everything inside

```
src
```

is staged.

---

# Verify Staged Files

Run

```bash
git status
```

Example

```text
Changes to be committed:

login.html

payment.html
```

These files are ready for commit.

---

# Remove File from Staging Area

Suppose you staged the wrong file.

Command

```bash
git restore --staged login.html
```

The file returns to the Modified state.

Its content is not deleted.

---

# Stage Everything Except One File

Stage all files.

```bash
git add .
```

Remove one file.

```bash
git restore --staged config.yml
```

Now

```
config.yml
```

will not be committed.

---

# Interactive Staging

Git also supports interactive staging.

```bash
git add -p
```

This allows developers to stage only specific portions of a file.

Useful when a single file contains multiple unrelated changes.

---

# Production Example

Developer modifies

```
payment.java

login.java

README.md
```

Only the payment fix is approved.

Commands

```bash
git add payment.java

git commit -m "Fixed payment issue"
```

Other files remain uncommitted.

---

# Another Production Example

A DevOps Engineer updates:

- Jenkinsfile
- Dockerfile
- Kubernetes YAML

The Dockerfile still requires testing.

Stage only

```bash
git add Jenkinsfile deployment.yaml
```

Commit

```bash
git commit -m "Updated Jenkins pipeline and Kubernetes deployment"
```

The unfinished Dockerfile is excluded.

---

# Common Mistakes

### Mistake 1

Using

```bash
git add .
```

without checking changes.

You may accidentally stage:

- Password Files
- Temporary Files
- Debug Scripts

Always review with

```bash
git status
```

---

### Mistake 2

Forgetting to stage a modified file.

Result

The commit is created,

but the latest modification is missing.

---

### Mistake 3

Assuming `git add` creates a backup.

It does not.

Only

```bash
git commit
```

creates a permanent snapshot.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git add filename | Stage One File |
| git add . | Stage Current Directory |
| git add -A | Stage All Changes |
| git add folder | Stage Folder |
| git add -p | Interactive Staging |
| git restore --staged | Unstage File |
| git status | Verify Staging |

---

# Interview Questions

### Q1. What is the purpose of the Staging Area?

It allows developers to choose exactly which changes will be included in the next commit.

---

### Q2. What is the difference between `git add` and `git commit`?

`git add` moves changes to the Staging Area.

`git commit` permanently records those staged changes in the Local Repository.

---

### Q3. Which command stages every modified file?

```bash
git add .
```

---

### Q4. Which command removes a file from the Staging Area?

```bash
git restore --staged filename
```

---

### Q5. Why do companies use the Staging Area?

It allows selective commits, cleaner history and better collaboration.

---

# Key Takeaways

- The Staging Area is one of Git's most powerful features.
- `git add` prepares changes for commit.
- `git commit` permanently saves staged changes.
- Always verify staged files using `git status`.
- Selective staging creates cleaner and more meaningful commit history.

---

# Next Section

## 3.9 Git Commit

In the next section, we will learn:

- What is a Commit?
- Commit IDs
- Commit Messages
- `git commit`
- `git commit -m`
- Best Practices
- Atomic Commits
- Professional Commit Standards
- Real Production Examples
---

# 3.9 Git Commit

Now that you understand the Staging Area, the next step is to create a **Commit**.

A Commit is the heart of Git.

Everything in Git revolves around commits.

Every bug fix, new feature, documentation update and deployment starts with a commit.

---

# What is a Commit?

A Commit is a snapshot of your project at a specific point in time.

Think of it as taking a photograph of your project.

```
Project

↓

Snapshot

↓

Commit
```

Git stores the entire project state, not just individual files.

---

# Real Life Example

Suppose you are developing an E-Commerce application.

Day 1

```
Login Page Created
```

Commit

```
Commit A
```

Day 2

```
Payment Module Added
```

Commit

```
Commit B
```

Day 3

```
Order Tracking Added
```

Commit

```
Commit C
```

At any time, Git allows you to return to any previous commit.

---

# Why Commits are Important

Commits provide:

- Project History
- Backup
- Rollback
- Collaboration
- Audit Trail
- Bug Tracking

Every change becomes traceable.

---

# Creating a Commit

Syntax

```bash
git commit -m "Commit Message"
```

Example

```bash
git commit -m "Added Login Page"
```

Git creates a new snapshot.

---

# Understanding the Commit Message

A commit message explains:

- What changed?
- Why was it changed?

Good Example

```
Fixed Payment Gateway Timeout
```

Bad Example

```
Update
```

Always write meaningful commit messages.

---

# Commit Structure

Each commit contains:

```
Commit ID

↓

Author

↓

Email

↓

Date

↓

Time

↓

Message

↓

Project Snapshot
```

---

# Commit ID (SHA)

Every commit receives a unique SHA hash.

Example

```
8d7a2e4f91b63...

```

No two commits have the same ID.

Git uses SHA hashes to uniquely identify every commit.

---

# View Commit History

Command

```bash
git log
```

Example

```text
commit 8d7a2e4f91b63...

Author: Rahul Sharma

Date:

Added Login Page
```

Every commit appears in reverse chronological order.

---

# Compact Commit History

```bash
git log --oneline
```

Example

```text
a83c12f Added Login Page

e92a34f Fixed Payment Bug

b12d54a Initial Commit
```

This is the most commonly used format.

---

# Commit Workflow

```
Modify File

↓

git add

↓

git commit

↓

Commit Created
```

Nothing is saved permanently until a commit is created.

---

# Atomic Commits

Professional developers create **Atomic Commits**.

One commit should represent **one logical change**.

Good Example

```
Fixed Login Validation
```

Bad Example

```
Login Fix

Payment Fix

Database Update

Docker Changes

README Changes

All in One Commit
```

Small commits are easier to review and rollback.

---

# Commit Frequently

Do not wait until the end of the week.

Instead

```
Small Change

↓

Commit

↓

Small Change

↓

Commit

↓

Small Change

↓

Commit
```

Frequent commits create a clean project history.

---

# Amend the Last Commit

Suppose you forgot to add one file.

Instead of creating another commit,

use

```bash
git commit --amend
```

Git updates the previous commit.

⚠️

Avoid amending commits that have already been pushed to shared repositories.

---

# Production Example

Developer fixes a login issue.

Commands

```bash
git add login.java

git commit -m "Fixed login validation issue"
```

Now the fix is permanently stored.

---

# Another Production Example

DevOps Engineer updates:

- Dockerfile
- Jenkinsfile

Commands

```bash
git add Dockerfile Jenkinsfile

git commit -m "Updated Docker image and Jenkins pipeline"
```

The deployment pipeline now uses the new configuration.

---

# Viewing Detailed History

```bash
git log
```

Displays:

- Commit ID
- Author
- Email
- Date
- Commit Message

Useful during audits and debugging.

---

# Searching Commit History

Example

```bash
git log --author="Rahul"
```

Displays commits created by Rahul.

Search by message.

```bash
git log --grep="payment"
```

Displays commits related to payments.

---

# Common Beginner Mistakes

### Mistake 1

Creating huge commits.

Example

```
100 Files

↓

One Commit
```

This makes debugging difficult.

---

### Mistake 2

Using meaningless commit messages.

Bad

```
Updated

Changes

Test

abc

Final
```

Good

```
Added User Authentication

Fixed Payment API Timeout

Updated Docker Configuration
```

---

### Mistake 3

Forgetting to commit.

Many beginners run

```bash
git add
```

and assume everything is saved.

It is not.

Only

```bash
git commit
```

creates a permanent snapshot.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git commit | Create Commit |
| git commit -m | Commit with Message |
| git commit --amend | Modify Last Commit |
| git log | Detailed History |
| git log --oneline | Compact History |
| git log --author | Search by Author |
| git log --grep | Search by Message |

---

# Interview Questions

### Q1. What is a Git Commit?

A Git Commit is a snapshot of the project at a specific point in time.

---

### Q2. Which command creates a commit?

```bash
git commit -m "Commit Message"
```

---

### Q3. Why are commit messages important?

They explain what changes were made and why, making project history easier to understand.

---

### Q4. Which command displays commit history?

```bash
git log
```

---

### Q5. What is an Atomic Commit?

An Atomic Commit contains one logical change, making it easier to review, test and rollback.

---

# Production Best Practices

✔ Write meaningful commit messages.

✔ Create small, focused commits.

✔ Commit frequently.

✔ Review changes before committing.

✔ Never commit passwords, API keys or secrets.

✔ Follow your team's commit message conventions.

---

# Key Takeaways

- A Commit is a permanent snapshot of your project.
- Every commit has a unique SHA identifier.
- Meaningful commit messages improve collaboration.
- Small, atomic commits simplify debugging and code reviews.
- Commits are the foundation of Git history.

---

# Next Section

## 3.10 Git Log & Commit History

In the next section, we will learn:

- `git log`
- `git log --oneline`
- `git show`
- `git diff`
- Viewing Commit History
- Comparing Commits
- Inspecting Changes
- Real Production Examples

Understanding commit history is one of the most valuable Git skills for debugging and troubleshooting.
---

# 3.10 Git Log & Commit History

One of Git's greatest strengths is its ability to maintain a complete history of every change made to a project.

Whenever someone asks:

- Who changed this file?
- When was it changed?
- Why was it changed?
- Which commit introduced the bug?

The answer is usually found in the **Git Commit History**.

Every DevOps Engineer must know how to inspect Git history.

---

# Why Commit History Matters

Imagine a production application suddenly stops working after deployment.

Developers ask:

```
Who changed the code?

↓

Which file changed?

↓

Which commit caused the issue?
```

Instead of guessing,

Git provides the complete history.

---

# View Complete Commit History

Command

```bash
git log
```

Example

```text
commit 7f2a1b9...

Author: Sandeep Pandey

Date: Tue Jul 1

Added Payment Module

----------------------------

commit 5a1d29f...

Author: Rahul Sharma

Initial Commit
```

Git displays commits from newest to oldest.

---

# Understanding git log Output

Each commit contains:

```
Commit SHA

↓

Author

↓

Email

↓

Date

↓

Commit Message
```

This information is useful during debugging and audits.

---

# View Compact History

Most developers prefer

```bash
git log --oneline
```

Example

```text
7f2a1b9 Added Payment Module

5a1d29f Initial Commit
```

This format is cleaner and easier to read.

---

# View Limited History

Display the latest three commits.

```bash
git log -3
```

Example

```text
Commit A

Commit B

Commit C
```

Useful for quickly reviewing recent work.

---

# Display Commit Details

Command

```bash
git show
```

Git displays:

- Commit Information
- Author
- Date
- Files Changed
- Actual Code Differences

---

# Show Specific Commit

```bash
git show 7f2a1b9
```

Displays all details for that commit.

---

# Compare Changes

Command

```bash
git diff
```

Shows differences between:

- Current Working Directory
- Staging Area
- Last Commit

Example

```text
- Old Line

+ New Line
```

Red lines indicate removed code.

Green lines indicate added code.

---

# Compare Staged Changes

```bash
git diff --staged
```

Displays changes that have already been staged but not yet committed.

---

# Compare Two Commits

```bash
git diff commit1 commit2
```

Example

```bash
git diff a82bc12 b91df33
```

Useful for understanding what changed between two versions.

---

# Show File History

Suppose you want to know every change made to

```
app.py
```

Run

```bash
git log app.py
```

Git displays every commit affecting that file.

---

# View One Commit Per Line

```bash
git log --pretty=oneline
```

Output

```text
7f2a1b9 Added Payment Module

5a1d29f Initial Commit
```

Useful in scripts and automation.

---

# Graphical History

```bash
git log --graph --oneline
```

Example

```text
* Added Payment Module

*

* Initial Commit
```

Later, when branches are introduced, this graph becomes extremely useful.

---

# Production Example 1

Developer reports:

```
Login stopped working after deployment.
```

DevOps Engineer checks

```bash
git log
```

Finds

```
Yesterday

↓

Login Module Updated
```

The responsible commit is identified immediately.

---

# Production Example 2

A production bug appears.

Compare the last two commits.

```bash
git diff HEAD~1 HEAD
```

Git displays exactly what changed.

Root cause is found much faster.

---

# Production Example 3

Manager asks:

> "Who modified the Dockerfile last week?"

Run

```bash
git log Dockerfile
```

Git displays:

- Author
- Date
- Commit Message

No manual investigation is required.

---

# Common Beginner Mistakes

### Mistake 1

Ignoring commit history.

Many beginners modify code without reviewing previous commits.

Professional developers always check history before making major changes.

---

### Mistake 2

Using only

```bash
git log
```

For large projects,

prefer

```bash
git log --oneline
```

It is much easier to read.

---

### Mistake 3

Comparing files manually.

Instead of opening two files,

use

```bash
git diff
```

Git highlights the exact differences.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git log | Full Commit History |
| git log --oneline | Compact History |
| git log -3 | Last Three Commits |
| git show | Commit Details |
| git show commitID | Specific Commit |
| git diff | Compare Working Directory |
| git diff --staged | Compare Staged Changes |
| git diff commit1 commit2 | Compare Two Commits |
| git log filename | File History |
| git log --graph --oneline | Graph View |

---

# Interview Questions

### Q1. Which command displays commit history?

```bash
git log
```

---

### Q2. Which command shows a compact commit history?

```bash
git log --oneline
```

---

### Q3. Which command displays detailed information about a commit?

```bash
git show
```

---

### Q4. Which command compares file changes?

```bash
git diff
```

---

### Q5. How do you view the history of a specific file?

```bash
git log filename
```

---

# Production Best Practices

✔ Review commit history before debugging.

✔ Use meaningful commit messages for easier tracking.

✔ Use `git diff` before committing changes.

✔ Keep commits small and focused.

✔ Learn to identify changes using commit history instead of manually comparing files.

---

# Key Takeaways

- Git stores the complete history of every project.
- `git log` helps identify who changed what and when.
- `git show` displays complete commit details.
- `git diff` compares code changes accurately.
- Understanding Git history is essential for debugging production issues.

---

# Next Section

## 3.11 Git Ignore (.gitignore)

In the next section, we will learn:

- What is `.gitignore`
- Why it is important
- Ignoring temporary files
- Ignoring logs
- Ignoring build artifacts
- Ignoring secrets and environment files
- Best Practices
- Real Production Examples

`.gitignore` is one of the most important files in every professional Git repository.
---

# 3.10 Git Log & Commit History

One of Git's greatest strengths is its ability to maintain a complete history of every change made to a project.

Whenever someone asks:

- Who changed this file?
- When was it changed?
- Why was it changed?
- Which commit introduced the bug?

The answer is usually found in the **Git Commit History**.

Every DevOps Engineer must know how to inspect Git history.

---

# Why Commit History Matters

Imagine a production application suddenly stops working after deployment.

Developers ask:

```
Who changed the code?

↓

Which file changed?

↓

Which commit caused the issue?
```

Instead of guessing,

Git provides the complete history.

---

# View Complete Commit History

Command

```bash
git log
```

Example

```text
commit 7f2a1b9...

Author: Sandeep Pandey

Date: Tue Jul 1

Added Payment Module

----------------------------

commit 5a1d29f...

Author: Rahul Sharma

Initial Commit
```

Git displays commits from newest to oldest.

---

# Understanding git log Output

Each commit contains:

```
Commit SHA

↓

Author

↓

Email

↓

Date

↓

Commit Message
```

This information is useful during debugging and audits.

---

# View Compact History

Most developers prefer

```bash
git log --oneline
```

Example

```text
7f2a1b9 Added Payment Module

5a1d29f Initial Commit
```

This format is cleaner and easier to read.

---

# View Limited History

Display the latest three commits.

```bash
git log -3
```

Example

```text
Commit A

Commit B

Commit C
```

Useful for quickly reviewing recent work.

---

# Display Commit Details

Command

```bash
git show
```

Git displays:

- Commit Information
- Author
- Date
- Files Changed
- Actual Code Differences

---

# Show Specific Commit

```bash
git show 7f2a1b9
```

Displays all details for that commit.

---

# Compare Changes

Command

```bash
git diff
```

Shows differences between:

- Current Working Directory
- Staging Area
- Last Commit

Example

```text
- Old Line

+ New Line
```

Red lines indicate removed code.

Green lines indicate added code.

---

# Compare Staged Changes

```bash
git diff --staged
```

Displays changes that have already been staged but not yet committed.

---

# Compare Two Commits

```bash
git diff commit1 commit2
```

Example

```bash
git diff a82bc12 b91df33
```

Useful for understanding what changed between two versions.

---

# Show File History

Suppose you want to know every change made to

```
app.py
```

Run

```bash
git log app.py
```

Git displays every commit affecting that file.

---

# View One Commit Per Line

```bash
git log --pretty=oneline
```

Output

```text
7f2a1b9 Added Payment Module

5a1d29f Initial Commit
```

Useful in scripts and automation.

---

# Graphical History

```bash
git log --graph --oneline
```

Example

```text
* Added Payment Module

*

* Initial Commit
```

Later, when branches are introduced, this graph becomes extremely useful.

---

# Production Example 1

Developer reports:

```
Login stopped working after deployment.
```

DevOps Engineer checks

```bash
git log
```

Finds

```
Yesterday

↓

Login Module Updated
```

The responsible commit is identified immediately.

---

# Production Example 2

A production bug appears.

Compare the last two commits.

```bash
git diff HEAD~1 HEAD
```

Git displays exactly what changed.

Root cause is found much faster.

---

# Production Example 3

Manager asks:

> "Who modified the Dockerfile last week?"

Run

```bash
git log Dockerfile
```

Git displays:

- Author
- Date
- Commit Message

No manual investigation is required.

---

# Common Beginner Mistakes

### Mistake 1

Ignoring commit history.

Many beginners modify code without reviewing previous commits.

Professional developers always check history before making major changes.

---

### Mistake 2

Using only

```bash
git log
```

For large projects,

prefer

```bash
git log --oneline
```

It is much easier to read.

---

### Mistake 3

Comparing files manually.

Instead of opening two files,

use

```bash
git diff
```

Git highlights the exact differences.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git log | Full Commit History |
| git log --oneline | Compact History |
| git log -3 | Last Three Commits |
| git show | Commit Details |
| git show commitID | Specific Commit |
| git diff | Compare Working Directory |
| git diff --staged | Compare Staged Changes |
| git diff commit1 commit2 | Compare Two Commits |
| git log filename | File History |
| git log --graph --oneline | Graph View |

---

# Interview Questions

### Q1. Which command displays commit history?

```bash
git log
```

---

### Q2. Which command shows a compact commit history?

```bash
git log --oneline
```

---

### Q3. Which command displays detailed information about a commit?

```bash
git show
```

---

### Q4. Which command compares file changes?

```bash
git diff
```

---

### Q5. How do you view the history of a specific file?

```bash
git log filename
```

---

# Production Best Practices

✔ Review commit history before debugging.

✔ Use meaningful commit messages for easier tracking.

✔ Use `git diff` before committing changes.

✔ Keep commits small and focused.

✔ Learn to identify changes using commit history instead of manually comparing files.

---

# Key Takeaways

- Git stores the complete history of every project.
- `git log` helps identify who changed what and when.
- `git show` displays complete commit details.
- `git diff` compares code changes accurately.
- Understanding Git history is essential for debugging production issues.

---

# Next Section

## 3.11 Git Ignore (.gitignore)

In the next section, we will learn:

- What is `.gitignore`
- Why it is important
- Ignoring temporary files
- Ignoring logs
- Ignoring build artifacts
- Ignoring secrets and environment files
- Best Practices
- Real Production Examples

`.gitignore` is one of the most important files in every professional Git repository.
---

# 3.11 Git Ignore (.gitignore)

Imagine you have created a Git repository for a Java project.

Your project contains:

```
ShoppingApp

│

├── src/

├── target/

├── logs/

├── .env

├── application.properties

└── README.md
```

Question:

Should every file be stored inside Git?

**No.**

Some files should **never** be committed.

Git provides a special file called:

```
.gitignore
```

---

# What is .gitignore?

`.gitignore` is a text file that tells Git:

> "Ignore these files and folders."

Git will not track them.

---

# Why Do We Need .gitignore?

Every project generates temporary files.

Examples:

- Log Files
- Cache Files
- Build Files
- Temporary Files
- IDE Settings
- Secrets

These files should not be stored in Git.

---

# Real Production Example

A Java application creates

```
logs/

↓

application.log
```

Every second,

the log file changes.

Imagine committing this file every minute.

Git history would become huge.

Instead,

Git ignores

```
logs/
```

using

```
.gitignore
```

---

# Creating .gitignore

Create a file named

```
.gitignore
```

Example

```
ShoppingApp

│

├── .gitignore

├── app.py

└── README.md
```

---

# Ignore Log Files

```
*.log
```

Git ignores

```
application.log

server.log

error.log
```

---

# Ignore Temporary Files

```
*.tmp

*.temp
```

---

# Ignore Backup Files

```
*.bak
```

---

# Ignore Object Files

```
*.o

*.obj
```

---

# Ignore Python Cache

```
__pycache__/

*.pyc
```

---

# Ignore Java Build Files

```
target/

*.class
```

---

# Ignore Maven Repository

```
.mvn/
```

---

# Ignore Gradle Files

```
.gradle/

build/
```

---

# Ignore Node Modules

```
node_modules/
```

This folder may contain thousands of files.

It should never be committed.

---

# Ignore Environment Files

One of the most important rules.

```
.env
```

Environment files often contain

- Passwords
- API Keys
- Database URLs
- Tokens

Never push them to GitHub.

---

# Ignore IDE Files

Visual Studio Code

```
.vscode/
```

IntelliJ IDEA

```
.idea/
```

Eclipse

```
.project

.classpath
```

These files are user-specific.

---

# Ignore Operating System Files

Windows

```
Thumbs.db
```

macOS

```
.DS_Store
```

---

# Ignore Terraform Files

```
.terraform/

terraform.tfstate

terraform.tfstate.backup
```

Terraform state files often contain sensitive information.

---

# Ignore Docker Files

Normally,

Dockerfiles should be committed.

But generated Docker cache should not.

Example

```
docker-cache/
```

---

# Sample .gitignore

```
# Logs

*.log

# Python

__pycache__/

*.pyc

# Environment

.env

# Node

node_modules/

# Java

target/

*.class

# IDE

.idea/

.vscode/

# Terraform

.terraform/

terraform.tfstate

# OS

.DS_Store

Thumbs.db
```

---

# Check Ignored Files

Command

```bash
git status
```

Ignored files do not appear.

---

# Important Rule

Git ignores files **only if they are not already being tracked.**

Suppose

```
.env
```

was already committed.

Adding

```
.env
```

to

```
.gitignore
```

will **not** stop Git from tracking it.

---

# Stop Tracking a File

Example

```bash
git rm --cached .env
```

Now Git stops tracking it.

Then add

```
.env
```

to

```
.gitignore
```

---

# Production Example 1

A developer accidentally commits

```
.env
```

containing:

```
Database Password

AWS Secret Key

API Token
```

Repository becomes vulnerable.

Correct procedure:

```
Remove File

↓

git rm --cached .env

↓

Update .gitignore

↓

Commit

↓

Rotate Secrets
```

---

# Production Example 2

Node.js project

```
node_modules/

↓

1,50,000 Files
```

Instead of committing,

developers ignore it.

Every developer runs

```bash
npm install
```

to regenerate dependencies.

---

# Production Example 3

Java project

```
target/

↓

500 MB
```

Generated during every build.

Ignored using

```
target/
```

---

# Common Beginner Mistakes

### Mistake 1

Committing

```
.env
```

Never commit secrets.

---

### Mistake 2

Committing

```
node_modules/
```

This unnecessarily increases repository size.

---

### Mistake 3

Adding `.gitignore` after files are already tracked.

Git will continue tracking them until removed using

```bash
git rm --cached
```

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git status | Verify Ignored Files |
| git rm --cached file | Stop Tracking File |
| git add .gitignore | Stage Ignore File |
| git commit | Save Ignore Rules |

---

# Interview Questions

### Q1. What is `.gitignore`?

A file that tells Git which files and directories should not be tracked.

---

### Q2. Why should `.env` be ignored?

Because it usually contains sensitive information such as passwords, API keys and tokens.

---

### Q3. Does `.gitignore` remove already tracked files?

No.

Tracked files must first be removed using

```bash
git rm --cached
```

---

### Q4. Should `node_modules` be committed?

No.

It should be ignored.

---

### Q5. Should `Dockerfile` be ignored?

No.

`Dockerfile` is source code and should normally be committed.

---

# Production Best Practices

✔ Commit `.gitignore` as one of the first files.

✔ Never commit passwords or API keys.

✔ Ignore build artifacts.

✔ Ignore IDE-specific files.

✔ Review `git status` before every commit.

✔ Regularly audit repositories for accidentally committed secrets.

---

# Key Takeaways

- `.gitignore` prevents unnecessary and sensitive files from being tracked.
- Secrets should never be committed.
- Generated files should usually be ignored.
- `.gitignore` is present in almost every professional repository.
- A well-maintained `.gitignore` keeps repositories clean and secure.

---

# Next Section

## 3.12 Git Branching

In the next section, we will learn:

- What is a Branch?
- Why Branches are Important
- `git branch`
- `git switch`
- `git checkout`
- Feature Branches
- Branch Strategy
- Git Flow
- Real Production Examples

Branching is one of Git's most powerful features and is used in every professional software company.
---

# 3.12 Git Branching

One of the biggest reasons Git became popular is its **Branching System**.

Branching allows multiple developers to work on different features simultaneously without affecting the main project.

Almost every software company uses Git Branches.

Without branching, modern software development would become extremely difficult.

---

# What is a Branch?

A Branch is an independent line of development.

Instead of modifying the main code directly,

developers create a separate branch.

```
Main Branch

↓

Feature Branch

↓

Develop Feature

↓

Merge Back
```

This keeps the main project stable.

---

# Real Company Example

Suppose an E-Commerce application is under development.

Three developers are assigned different tasks.

Developer A

```
Login Feature
```

Developer B

```
Payment Gateway
```

Developer C

```
User Dashboard
```

Instead of editing the same branch,

each developer creates a separate branch.

---

# Branch Structure

```
main

│

├── login-feature

│

├── payment-feature

│

└── dashboard-feature
```

Each developer works independently.

---

# Default Branch

When a repository is created,

Git creates the default branch.

Modern Git uses:

```
main
```

Older repositories may use:

```
master
```

---

# View Branches

Command

```bash
git branch
```

Example

```text
* main
```

The asterisk (*) indicates the current branch.

---

# Create a New Branch

Syntax

```bash
git branch branch-name
```

Example

```bash
git branch login-feature
```

The branch is created,

but you are still on the current branch.

---

# Switch Branch

Modern Git command

```bash
git switch login-feature
```

Older Git command

```bash
git checkout login-feature
```

You are now working inside

```
login-feature
```

---

# Create and Switch Together

Instead of two commands,

use

```bash
git switch -c payment-feature
```

Older syntax

```bash
git checkout -b payment-feature
```

This creates and switches to the branch immediately.

---

# Verify Current Branch

```bash
git branch
```

Output

```text
main

* payment-feature
```

The asterisk indicates the active branch.

---

# Branch Workflow

```
main

↓

Create Branch

↓

Develop Feature

↓

Commit Changes

↓

Merge into main

↓

Delete Branch
```

This is the workflow followed by most software companies.

---

# Why Use Branches?

Without branches,

every developer edits the same code.

Result

```
Conflicts

↓

Broken Builds

↓

Production Issues
```

Branches isolate changes until they are ready.

---

# Production Example

Developer Rahul works on Login.

Developer Priya works on Payment.

Developer Amit works on Notifications.

```
main

├── login-feature

├── payment-feature

└── notification-feature
```

Each developer commits independently.

Later,

their branches are merged after code review.

---

# Branch Naming Best Practices

Use meaningful names.

Good Examples

```
feature/login

feature/payment

bugfix/cart-error

hotfix/server-crash

release/v1.2.0
```

Avoid names like

```
test

new

abc

temp
```

---

# List All Branches

Local branches

```bash
git branch
```

Remote branches

```bash
git branch -r
```

All branches

```bash
git branch -a
```

---

# Rename Branch

Rename the current branch.

```bash
git branch -m new-branch-name
```

Example

```bash
git branch -m login-feature
```

---

# Delete Branch

Delete a merged branch.

```bash
git branch -d login-feature
```

Force delete

```bash
git branch -D login-feature
```

Use `-D` carefully.

---

# Branch History

View commit history for the current branch.

```bash
git log --oneline
```

Each branch maintains its own commit history until merged.

---

# Common Beginner Mistakes

### Mistake 1

Working directly on `main`.

Professional teams rarely develop directly on the main branch.

---

### Mistake 2

Creating one branch for every project.

A branch should represent one feature, bug fix or release.

---

### Mistake 3

Forgetting to switch branches.

Always verify using

```bash
git branch
```

before starting work.

---

# Real DevOps Workflow

```
Developer

↓

Create Feature Branch

↓

Write Code

↓

Commit

↓

Push Branch

↓

Pull Request

↓

Code Review

↓

Merge to main

↓

Jenkins Pipeline

↓

Docker Build

↓

Kubernetes Deployment
```

Almost every CI/CD pipeline follows this workflow.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git branch | List Local Branches |
| git branch branch-name | Create Branch |
| git switch branch-name | Switch Branch |
| git switch -c branch-name | Create & Switch |
| git checkout branch-name | Older Switch Command |
| git checkout -b branch-name | Older Create & Switch |
| git branch -m | Rename Branch |
| git branch -d | Delete Branch |
| git branch -D | Force Delete |
| git branch -a | List All Branches |

---

# Interview Questions

### Q1. What is a Git Branch?

A Git Branch is an independent line of development that allows developers to work without affecting the main branch.

---

### Q2. Which command creates a branch?

```bash
git branch branch-name
```

---

### Q3. Which command switches branches?

Modern Git

```bash
git switch branch-name
```

Older Git

```bash
git checkout branch-name
```

---

### Q4. Which branch is usually the default branch?

```
main
```

---

### Q5. Why do software companies use branches?

To develop features independently, reduce conflicts and maintain a stable main branch.

---

# Production Best Practices

✔ Never develop directly on the `main` branch.

✔ Create one branch per feature or bug fix.

✔ Use meaningful branch names.

✔ Delete merged branches to keep the repository clean.

✔ Always pull the latest changes before creating a new branch.

---

# Key Takeaways

- Branches allow parallel development.
- Every feature should have its own branch.
- `git switch` is the modern way to change branches.
- Branching keeps the main branch stable.
- Git Branching is a core concept used in every professional development team.

---

# Next Section

## 3.13 Git Merge

In the next section, we will learn:

- What is Git Merge?
- Fast-Forward Merge
- Three-Way Merge
- Merge Commit
- Merge Conflicts
- Conflict Resolution
- Production Examples

Merging is the process of combining changes from one branch into another and is one of the most frequently used operations in Git.
---

# 3.13 Git Merge

So far, we have learned how to create branches.

But after completing a feature,

how do we bring those changes back into the main branch?

The answer is:

**Git Merge**

Git Merge combines the work from one branch into another.

It is one of the most frequently used Git operations in every software company.

---

# What is Git Merge?

Git Merge combines two branches into one.

Example

```
main

↓

Create Feature Branch

↓

Develop Feature

↓

Merge

↓

main Updated
```

After merging,

the feature becomes part of the main project.

---

# Real Company Example

Suppose three developers are working.

```
main

│

├── login-feature

├── payment-feature

└── notification-feature
```

Developer Rahul finishes

```
login-feature
```

Now the Login feature must become part of

```
main
```

Git Merge performs this task.

---

# Merge Workflow

```
main

↓

Create Branch

↓

Develop

↓

Commit

↓

Switch to main

↓

Merge

↓

Updated main
```

---

# Step 1 — Switch to Main Branch

Before merging,

move to the destination branch.

```bash
git switch main
```

---

# Step 2 — Merge Feature Branch

Command

```bash
git merge login-feature
```

Git combines the changes.

---

# Result

```
main

↓

Login Feature Added

↓

History Updated
```

The feature is now available on the main branch.

---

# Fast-Forward Merge

Suppose no one modified

```
main
```

while the feature branch was being developed.

Git simply moves the branch pointer.

```
main

↓

Commit A

↓

Commit B

↓

Commit C
```

No merge commit is created.

This is called a

**Fast-Forward Merge.**

---

# Three-Way Merge

Suppose both branches changed.

```
main

↓

Commit A

↓

Commit B

--------------------

feature

↓

Commit A

↓

Commit X

↓

Commit Y
```

Git creates a new Merge Commit.

```
Commit M
```

This is called a

**Three-Way Merge.**

---

# Merge Commit

A Merge Commit has two parent commits.

```
main

↓

Merge Commit

↙      ↘

main   feature
```

It records that two development histories have been combined.

---

# Check Commit History

```bash
git log --oneline --graph
```

Example

```text
* Merge login-feature

|\
| * Added Login Page

| * Added Login API

* Initial Commit
```

The graph shows branch history visually.

---

# Merge Conflict

Sometimes two developers modify the same line.

Example

Developer Rahul

```text
Welcome User
```

Developer Priya

```text
Welcome Customer
```

Git cannot decide which version is correct.

A Merge Conflict occurs.

---

# Conflict Example

Git marks the conflict.

```text
<<<<<<< HEAD

Welcome User

=======

Welcome Customer

>>>>>>> login-feature
```

You must edit the file manually.

Choose the correct version,

save the file,

then continue.

---

# Resolve Merge Conflict

After fixing the file,

stage it.

```bash
git add filename
```

Complete the merge.

```bash
git commit
```

Conflict resolved.

---

# Abort Merge

If something goes wrong,

cancel the merge.

```bash
git merge --abort
```

Git returns to the previous state.

---

# Production Example 1

Developer completes Login Module.

Commands

```bash
git switch main

git merge login-feature
```

Main branch now contains the Login feature.

---

# Production Example 2

Two developers modify

```
application.properties
```

Both change the database URL.

Merge fails.

Git asks for manual conflict resolution.

After reviewing,

the DevOps Engineer keeps the correct configuration,

stages the file,

and commits the merge.

---

# Production Example 3

A company releases version 2.0.

```
feature/payment

↓

Merge

↓

main

↓

Jenkins

↓

Docker

↓

Kubernetes

↓

Production
```

The deployment pipeline starts only after the merge is completed.

---

# Common Beginner Mistakes

### Mistake 1

Merging while on the wrong branch.

Always verify using

```bash
git branch
```

before merging.

---

### Mistake 2

Ignoring merge conflicts.

Never delete conflict markers without understanding the changes.

---

### Mistake 3

Deleting a feature branch before confirming the merge succeeded.

Always verify the merge first.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git merge branch-name | Merge Branch |
| git merge --abort | Cancel Merge |
| git log --graph | Visual History |
| git log --oneline --graph | Compact Graph |
| git branch | Verify Current Branch |

---

# Interview Questions

### Q1. What is Git Merge?

Git Merge combines changes from one branch into another.

---

### Q2. What is a Fast-Forward Merge?

A merge where the target branch has not changed and Git simply moves the branch pointer.

---

### Q3. What is a Merge Conflict?

A Merge Conflict occurs when Git cannot automatically combine changes because the same part of a file was modified differently.

---

### Q4. Which command merges a branch?

```bash
git merge branch-name
```

---

### Q5. Which command cancels an ongoing merge?

```bash
git merge --abort
```

---

# Production Best Practices

✔ Pull the latest changes before merging.

✔ Merge only reviewed code.

✔ Resolve conflicts carefully.

✔ Test the application after every merge.

✔ Delete feature branches only after successful verification.

✔ Use Pull Requests for production repositories.

---

# Key Takeaways

- Git Merge combines development from multiple branches.
- Fast-Forward Merge is the simplest type of merge.
- Three-Way Merge creates a Merge Commit.
- Merge Conflicts require manual resolution.
- Every professional software team uses Git Merge daily.

---

# Next Section

## 3.14 Git Rebase

In the next section, we will learn:

- What is Git Rebase?
- Merge vs Rebase
- Interactive Rebase
- Squash Commits
- Rebase Conflicts
- Best Practices
- Real Production Examples

Git Rebase helps maintain a clean and linear commit history and is widely used in professional DevOps teams.
---

# 3.14 Git Rebase

Git Merge is not the only way to combine branches.

Git provides another powerful command called **Git Rebase**.

Many professional software companies prefer Rebase because it creates a **clean and linear commit history**.

However, Rebase must be used carefully.

---

# What is Git Rebase?

Git Rebase moves the commits of one branch and places them on top of another branch.

Instead of creating a Merge Commit,

Git rewrites the commit history.

Example

```
Before

main

A --- B

         \

feature

          C --- D

```

After Rebase

```
main

A --- B --- C' --- D'
```

Notice that commits **C** and **D** are recreated as **C'** and **D'**.

---

# Why Use Rebase?

Rebase creates a cleaner history.

Instead of

```
Merge Commit

↓

Messy History
```

you get

```
Linear History

↓

Easy to Read
```

Large organizations often prefer this approach.

---

# Merge vs Rebase

Merge

```
A

↓

B

↘

 C

↓

Merge Commit
```

History contains an additional merge commit.

---

Rebase

```
A

↓

B

↓

C

↓

D
```

History appears as if development happened sequentially.

---

# When Should You Use Rebase?

Use Rebase when:

- Updating a Feature Branch
- Cleaning Commit History
- Preparing Pull Requests
- Working on Personal Branches

Avoid rebasing shared branches.

---

# Basic Rebase Workflow

Suppose

```
main

↓

A

↓

B
```

Feature Branch

```
feature

↓

A

↓

C

↓

D
```

Meanwhile,

main receives another commit.

```
main

↓

A

↓

B

↓

E
```

Update your feature branch.

```
git switch feature

git rebase main
```

Result

```
main

↓

A

↓

B

↓

E

↓

C'

↓

D'
```

Feature branch now starts from the latest main branch.

---

# Rebase Command

Syntax

```bash
git rebase branch-name
```

Example

```bash
git rebase main
```

Git applies your commits one by one on top of the latest main branch.

---

# Real Production Example

Developer starts work on Monday.

```
Feature Branch

↓

Login Module
```

During the week,

other developers merge 25 commits into main.

Instead of merging,

the developer rebases.

```
Feature

↓

Latest Main

↓

Apply Login Commits
```

Now the feature branch contains the latest code.

---

# Interactive Rebase

Git allows developers to edit commit history.

Command

```bash
git rebase -i HEAD~5
```

Git opens the last five commits.

Example

```
pick

pick

pick

pick

pick
```

You can:

- Reorder commits
- Rename commits
- Delete commits
- Squash commits

---

# Squash Commits

Suppose you have

```
Fixed Login

↓

Fixed Login Again

↓

Another Login Fix

↓

Final Login Fix
```

Instead of four commits,

combine them into one.

```
Added Complete Login Feature
```

This process is called **Squashing**.

Interactive Rebase makes this easy.

---

# Rebase Conflict

Like Merge,

Rebase may also produce conflicts.

Example

Developer Rahul

```
Payment URL A
```

Developer Priya

```
Payment URL B
```

Git cannot decide.

Conflict occurs.

---

# Resolve Rebase Conflict

After fixing the file,

run

```bash
git add filename
```

Continue the rebase.

```bash
git rebase --continue
```

Git proceeds with the next commit.

---

# Skip Current Commit

If a commit is no longer needed,

skip it.

```bash
git rebase --skip
```

Git ignores the conflicting commit.

---

# Cancel Rebase

Abort the operation.

```bash
git rebase --abort
```

Git restores the repository to its previous state.

---

# Merge vs Rebase Comparison

| Feature | Merge | Rebase |
|----------|-------|---------|
| Creates Merge Commit | Yes | No |
| Linear History | No | Yes |
| Rewrites History | No | Yes |
| Easy to Understand | Yes | Moderate |
| Best for Shared Branches | Yes | No |
| Clean Commit History | Moderate | Excellent |

---

# Production Example 2

Developer creates

```
feature/payment
```

Main branch receives 50 commits.

Before opening a Pull Request,

run

```bash
git fetch origin

git rebase origin/main
```

Now the Pull Request contains only the payment feature commits.

Review becomes much easier.

---

# Common Beginner Mistakes

### Mistake 1

Rebasing the main branch.

Normally,

only feature branches should be rebased.

---

### Mistake 2

Rebasing a branch already shared with teammates.

This rewrites commit history and may create confusion.

---

### Mistake 3

Ignoring conflicts during rebase.

Always resolve conflicts carefully before continuing.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git rebase main | Rebase Current Branch |
| git rebase -i HEAD~5 | Interactive Rebase |
| git rebase --continue | Continue Rebase |
| git rebase --abort | Cancel Rebase |
| git rebase --skip | Skip Current Commit |

---

# Interview Questions

### Q1. What is Git Rebase?

Git Rebase moves commits from one branch and reapplies them on top of another branch to create a linear history.

---

### Q2. What is the difference between Merge and Rebase?

Merge preserves branch history and creates a Merge Commit.

Rebase rewrites commit history to produce a clean, linear sequence.

---

### Q3. Which command starts an Interactive Rebase?

```bash
git rebase -i HEAD~5
```

---

### Q4. Which command continues a paused rebase?

```bash
git rebase --continue
```

---

### Q5. Which command cancels an ongoing rebase?

```bash
git rebase --abort
```

---

# Production Best Practices

✔ Rebase feature branches before creating Pull Requests.

✔ Never rebase shared branches unless everyone agrees.

✔ Resolve conflicts carefully.

✔ Use Interactive Rebase to clean commit history.

✔ Test the application after completing a rebase.

---

# Key Takeaways

- Git Rebase creates a clean, linear commit history.
- Rebase rewrites commit history.
- Interactive Rebase allows editing and squashing commits.
- Avoid rebasing branches already shared with others.
- Rebase is widely used before Pull Requests in professional DevOps teams.

---

# Next Section

## 3.15 Merge vs Rebase (Complete Comparison)

In the next section, we will compare Merge and Rebase in depth, understand when to use each approach, examine real production workflows, and learn the interview questions most commonly asked on this topic.
---

# 3.15 Merge vs Rebase (Complete Comparison)

One of the most frequently asked Git interview questions is:

> **Should I use Merge or Rebase?**

The answer depends on the situation.

Both commands combine changes from different branches, but they do it in different ways.

Every professional DevOps Engineer should understand both approaches.

---

# Common Goal

Both Merge and Rebase are used to bring changes from one branch into another.

Example

```
Feature Branch

↓

Completed

↓

Integrate into Main
```

The goal is the same.

The process is different.

---

# Git Merge

Git Merge preserves branch history.

```
main

A ---- B

       \

feature

        C ---- D

             \

              Merge Commit
```

History clearly shows when branches were merged.

---

# Git Rebase

Git Rebase rewrites history.

```
Before

main

A ---- B

       \

feature

        C ---- D

```

After Rebase

```
A ---- B ---- C ---- D
```

History becomes linear.

---

# Merge Workflow

```
Feature Completed

↓

Switch to Main

↓

git merge feature

↓

Merge Commit

↓

Push
```

---

# Rebase Workflow

```
Update Feature Branch

↓

git rebase main

↓

Resolve Conflicts

↓

Push

↓

Merge Fast Forward
```

---

# Visual Comparison

### Merge

```
A

↓

B

↘

 C

↓

Merge Commit
```

History branches and rejoins.

---

### Rebase

```
A

↓

B

↓

C

↓

D
```

Straight history.

---

# Advantages of Merge

- Original history preserved.
- Safe for shared branches.
- Easy to understand.
- No commit rewriting.
- Suitable for beginners.

---

# Advantages of Rebase

- Clean history.
- No unnecessary merge commits.
- Easier code review.
- Better for Pull Requests.
- Professional commit history.

---

# Disadvantages of Merge

```
Large History

↓

Many Merge Commits

↓

Harder to Read
```

Projects with hundreds of developers may create thousands of merge commits.

---

# Disadvantages of Rebase

Rebase rewrites commit history.

If used incorrectly,

it may confuse teammates.

Never rebase commits already shared publicly unless your team follows that workflow.

---

# Real Company Example

Suppose 50 developers work on an application.

Every developer creates:

```
Feature Branch

↓

Coding

↓

Testing

↓

Pull Request
```

Before opening the Pull Request,

developers usually run

```bash
git fetch origin

git rebase origin/main
```

This keeps the branch updated with the latest code.

---

# Production Example

GitHub Repository

```
main

↓

Feature Branch

↓

Rebase

↓

Pull Request

↓

Code Review

↓

Merge

↓

Jenkins

↓

Docker

↓

Kubernetes
```

This workflow is followed in many DevOps teams.

---

# Merge Conflict vs Rebase Conflict

Both commands may produce conflicts.

Merge

```
Conflict

↓

Resolve

↓

Commit
```

Rebase

```
Conflict

↓

Resolve

↓

git rebase --continue
```

The resolution process is similar.

---

# Which One Should You Use?

### Use Merge When

- Working on shared branches
- Preserving history is important
- Team prefers merge commits
- Simplicity is preferred

---

### Use Rebase When

- Updating feature branches
- Cleaning commit history
- Preparing Pull Requests
- Working on personal branches

---

# Decision Flow

```
Need Original History?

↓

Yes

↓

Merge

----------------------

Need Clean History?

↓

Yes

↓

Rebase
```

---

# GitHub Pull Request Workflow

Developer

```
Create Branch

↓

Commit

↓

Push

↓

Rebase

↓

Pull Request

↓

Code Review

↓

Merge
```

This is one of the most common workflows in modern software companies.

---

# Merge vs Rebase Comparison

| Feature | Merge | Rebase |
|----------|-------|---------|
| Preserves History | ✔ | ✘ |
| Linear History | ✘ | ✔ |
| Merge Commit | ✔ | ✘ |
| Rewrites History | ✘ | ✔ |
| Safe for Shared Branches | ✔ | ✘ |
| Clean Git Log | Moderate | Excellent |
| Beginner Friendly | ✔ | Moderate |
| Preferred Before PR | Sometimes | Frequently |

---

# Common Beginner Mistakes

### Mistake 1

Using Rebase on a branch already pushed and shared with teammates.

This may rewrite history and cause confusion.

---

### Mistake 2

Using Merge for every small update.

Too many merge commits make history difficult to read.

---

### Mistake 3

Not understanding the team's Git workflow.

Always follow your organization's branching strategy.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git merge branch | Merge Branch |
| git rebase main | Rebase Current Branch |
| git rebase --continue | Continue Rebase |
| git rebase --abort | Abort Rebase |
| git log --graph | View Branch History |

---

# Interview Questions

### Q1. What is the main difference between Merge and Rebase?

Merge preserves branch history by creating a merge commit.

Rebase rewrites history to create a clean, linear sequence.

---

### Q2. Does Merge rewrite history?

No.

---

### Q3. Does Rebase rewrite history?

Yes.

---

### Q4. Which command creates a Merge Commit?

```bash
git merge
```

---

### Q5. Which approach is preferred for cleaning commit history?

Git Rebase.

---

# Production Best Practices

✔ Use Merge for shared branches.

✔ Use Rebase to update feature branches.

✔ Always resolve conflicts carefully.

✔ Follow your organization's Git workflow.

✔ Test the application after Merge or Rebase.

---

# Key Takeaways

- Merge and Rebase solve similar problems in different ways.
- Merge preserves history.
- Rebase creates a cleaner history.
- Choose the method based on your team's workflow.
- Understanding both approaches is essential for DevOps Engineers.

---

# Next Section

## 3.16 Git Remote Repositories

In the next section, we will learn:

- What is a Remote Repository?
- GitHub Remote
- `git remote`
- `git remote -v`
- `git remote add origin`
- `git push`
- `git fetch`
- `git pull`
- `git clone`
- Real Production Workflows

This is where local Git repositories connect with GitHub and team collaboration begins.
---

# 3.16 Git Remote Repositories

Until now, all our work has been stored on the local computer.

But in a real software company, developers work together from different locations.

To collaborate, Git uses **Remote Repositories**.

A Remote Repository is usually hosted on platforms like:

- GitHub
- GitLab
- Bitbucket
- Azure Repos

---

# What is a Remote Repository?

A Remote Repository is a copy of your Git repository stored on a remote server.

Example

```
Developer Laptop

↓

Local Repository

↓

Internet

↓

GitHub Repository
```

This allows multiple developers to work on the same project.

---

# Why Do We Need Remote Repositories?

Imagine three developers.

```
Rahul

↓

Laptop

---------------

Priya

↓

Laptop

---------------

Sandeep

↓

Laptop
```

Without a remote repository,

they cannot easily share code.

A Remote Repository becomes the common meeting point.

```
Rahul

↓

GitHub

↑

Priya

↑

Sandeep
```

---

# What is Origin?

When we connect our local repository to GitHub,

Git usually names the remote repository

```
origin
```

Example

```
Local Repository

↓

origin

↓

GitHub Repository
```

"origin" is only a default name.

It can be changed.

---

# View Remote Repositories

Command

```bash
git remote
```

Example Output

```text
origin
```

---

# View Remote URLs

Command

```bash
git remote -v
```

Example

```text
origin

https://github.com/company/project.git

(fetch)

origin

https://github.com/company/project.git

(push)
```

This displays both fetch and push URLs.

---

# Add a Remote Repository

Syntax

```bash
git remote add origin <repository-url>
```

Example

```bash
git remote add origin https://github.com/linuxwithsandeep-lab/DevOps-Engineer-Handbook1.git
```

Now the local repository is connected to GitHub.

---

# Verify Remote

```bash
git remote -v
```

Output

```text
origin

https://github.com/linuxwithsandeep-lab/DevOps-Engineer-Handbook1.git
```

Connection verified.

---

# Rename a Remote

Suppose

```
origin
```

should become

```
github
```

Run

```bash
git remote rename origin github
```

---

# Remove a Remote

Command

```bash
git remote remove origin
```

Only the connection is removed.

Your local repository remains safe.

---

# Clone a Remote Repository

Instead of creating a project manually,

download an existing repository.

```bash
git clone https://github.com/linuxwithsandeep-lab/DevOps-Engineer-Handbook1.git
```

Git automatically downloads:

- Source Code
- Commit History
- Branches
- Remote Configuration

---

# Push Local Changes

Upload commits to GitHub.

```bash
git push origin main
```

Flow

```
Local Commit

↓

git push

↓

GitHub Updated
```

---

# Fetch Remote Changes

Download remote changes,

but do not merge them.

```bash
git fetch origin
```

Flow

```
GitHub

↓

Download Updates

↓

Local Repository

(No Merge)
```

---

# Pull Remote Changes

Download and merge changes.

```bash
git pull origin main
```

Flow

```
GitHub

↓

Download

↓

Merge

↓

Working Directory Updated
```

---

# Fetch vs Pull

| Command | Action |
|----------|--------|
| git fetch | Download Only |
| git pull | Download + Merge |

---

# Real Production Workflow

Developer writes code.

```
Write Code

↓

git add

↓

git commit

↓

git push origin feature/login

↓

GitHub

↓

Pull Request

↓

Merge

↓

Deployment
```

---

# Clone Workflow

New employee joins the company.

Instead of creating the project,

they execute:

```bash
git clone https://github.com/company/project.git
```

Within minutes,

they have the complete project.

---

# Production Example

Suppose you fixed a payment bug.

Commands

```bash
git add .

git commit -m "Fixed Payment Gateway"

git push origin payment-feature
```

The feature branch appears on GitHub.

Now the team can review your code.

---

# Common Beginner Mistakes

### Mistake 1

Running

```bash
git push
```

before creating a remote.

Git displays an error.

Always verify

```bash
git remote -v
```

---

### Mistake 2

Using the wrong repository URL.

Verify the URL before pushing.

---

### Mistake 3

Using

```bash
git pull
```

without committing local work.

This may create merge conflicts.

Commit your work first.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git remote | List Remote Names |
| git remote -v | Show Remote URLs |
| git remote add origin URL | Add Remote |
| git remote remove origin | Remove Remote |
| git remote rename | Rename Remote |
| git clone URL | Download Repository |
| git fetch | Download Changes |
| git pull | Download & Merge |
| git push origin main | Upload Commits |

---

# Interview Questions

### Q1. What is a Remote Repository?

A Remote Repository is a Git repository hosted on a remote server such as GitHub that enables team collaboration.

---

### Q2. What is the default name of a Git remote?

```
origin
```

---

### Q3. What is the difference between `git fetch` and `git pull`?

`git fetch` downloads changes without merging.

`git pull` downloads and automatically merges changes into the current branch.

---

### Q4. Which command clones a repository?

```bash
git clone <repository-url>
```

---

### Q5. Which command uploads commits to GitHub?

```bash
git push origin main
```

---

# Production Best Practices

✔ Verify the remote URL before pushing.

✔ Use `git fetch` before merging.

✔ Commit local changes before running `git pull`.

✔ Push feature branches instead of directly pushing to `main`.

✔ Regularly synchronize your local repository with the remote repository.

---

# Key Takeaways

- Remote repositories enable collaboration between developers.
- GitHub is the most commonly used remote repository platform.
- `git clone` downloads a complete repository.
- `git push` uploads commits.
- `git fetch` downloads changes without merging.
- `git pull` downloads and merges changes.

---

# Next Section

## 3.17 Git Push, Pull & Fetch (Deep Dive)

In the next section, we will explore these three commands in detail with production scenarios, diagrams, troubleshooting examples, and interview questions. This is one of the most frequently used topics in day-to-day DevOps work.
---

# 3.17 Git Push, Pull & Fetch (Deep Dive)

Among all Git commands,

these three are used the most in professional software companies:

- git push
- git pull
- git fetch

Every developer and DevOps Engineer uses them daily.

Understanding the difference between these commands is essential.

---

# Overview

```
Local Repository

↓

git push

↓

GitHub Repository

------------------------

GitHub Repository

↓

git fetch

↓

Local Repository

(No Merge)

------------------------

GitHub Repository

↓

git pull

↓

Download

↓

Merge

↓

Working Directory
```

---

# What is git push?

`git push` uploads your local commits to the remote repository.

Command

```bash
git push origin main
```

Flow

```
Local Commit

↓

git push

↓

GitHub Updated
```

Other developers can now see your changes.

---

# Real Example

Suppose you fixed a login issue.

Commands

```bash
git add .

git commit -m "Fixed Login Validation"

git push origin login-feature
```

The feature branch is now available on GitHub.

---

# What Happens During Push?

```
Working Directory

↓

Commit

↓

Local Repository

↓

git push

↓

GitHub Repository
```

Only committed changes are uploaded.

---

# What is git fetch?

`git fetch` downloads new commits from the remote repository.

It does **not** merge them.

Command

```bash
git fetch origin
```

Result

```
GitHub

↓

Download

↓

Local Repository

(No Merge)
```

Your working files remain unchanged.

---

# Why Use Fetch?

Suppose another developer has pushed new commits.

You want to inspect them before merging.

Use

```bash
git fetch
```

Now review the changes.

Only merge when you are ready.

---

# What is git pull?

`git pull` combines two operations.

```
git fetch

+

git merge
```

Command

```bash
git pull origin main
```

Flow

```
GitHub

↓

Download

↓

Merge

↓

Working Directory Updated
```

---

# Fetch vs Pull

Imagine GitHub contains new commits.

Using

```bash
git fetch
```

```
GitHub

↓

Download

↓

Local Repository

(No Merge)
```

Using

```bash
git pull
```

```
GitHub

↓

Download

↓

Merge

↓

Current Branch Updated
```

---

# Push Workflow

Developer completes a feature.

```
Write Code

↓

git add

↓

git commit

↓

git push

↓

GitHub
```

Simple and straightforward.

---

# Pull Workflow

Developer starts work every morning.

First command

```bash
git pull origin main
```

Reason

```
Latest Code

↓

Merge

↓

Start Development
```

Always begin with the latest code.

---

# Fetch Workflow

Production Engineer wants to inspect incoming changes.

Commands

```bash
git fetch

git log origin/main

git diff origin/main
```

No merge occurs.

Safe inspection.

---

# Real Production Example 1

Rahul pushes

```
Payment Feature
```

Priya wants the latest code.

She runs

```bash
git pull origin main
```

Her repository becomes up to date.

---

# Real Production Example 2

DevOps Engineer wants to inspect new commits before deployment.

Commands

```bash
git fetch origin

git log origin/main
```

Only after verification,

the changes are merged.

---

# Real Production Example 3

Developer forgets to push.

```
Commit Exists

↓

Laptop Only

↓

GitHub Not Updated
```

Teammates cannot see the work.

Solution

```bash
git push
```

---

# Common Push Errors

### Error

```
rejected (non-fast-forward)
```

Reason

Someone pushed changes before you.

Solution

```bash
git pull origin main

↓

Resolve Conflicts

↓

git push
```

---

### Error

```
Permission denied
```

Reason

- Authentication Failed
- No Repository Access

Verify:

- GitHub Login
- Personal Access Token
- Repository Permissions

---

### Error

```
Everything up-to-date
```

Meaning

There are no new commits to push.

---

# Common Pull Errors

### Merge Conflict

Another developer modified the same file.

Git cannot merge automatically.

Resolve conflict manually.

Then

```bash
git add .

git commit
```

---

# Best Practice Workflow

Every morning

```
git pull

↓

Start Coding

↓

git add

↓

git commit

↓

git push
```

This is followed by most software companies.

---

# Git Push vs Pull vs Fetch

| Command | Upload | Download | Merge |
|----------|---------|----------|-------|
| git push | ✔ | ✘ | ✘ |
| git fetch | ✘ | ✔ | ✘ |
| git pull | ✘ | ✔ | ✔ |

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git push origin main | Upload Commits |
| git push origin branch | Upload Branch |
| git pull origin main | Download & Merge |
| git fetch origin | Download Only |
| git log origin/main | View Remote History |
| git diff origin/main | Compare Remote Changes |

---

# Interview Questions

### Q1. What does `git push` do?

It uploads local commits to the remote repository.

---

### Q2. What is the difference between `git fetch` and `git pull`?

`git fetch` downloads changes without merging.

`git pull` downloads and merges changes into the current branch.

---

### Q3. Why do companies sometimes prefer `git fetch`?

Because it allows developers to review incoming changes before merging them.

---

### Q4. Which command uploads a feature branch?

```bash
git push origin feature/login
```

---

### Q5. Which command should you usually run before starting work?

```bash
git pull origin main
```

---

# Production Best Practices

✔ Pull the latest code before starting work.

✔ Commit before pushing.

✔ Use `git fetch` when reviewing incoming changes.

✔ Resolve merge conflicts carefully.

✔ Push feature branches instead of directly pushing to `main`.

✔ Verify successful push on GitHub.

---

# Key Takeaways

- `git push` uploads commits.
- `git fetch` downloads changes without merging.
- `git pull` downloads and merges changes.
- Always synchronize your repository before starting development.
- These three commands form the backbone of daily Git collaboration.

---

# Next Section

## 3.18 Git Clone

In the next section, we will learn:

- What is `git clone`?
- Clone vs Download ZIP
- Cloning Public Repositories
- Cloning Private Repositories
- HTTPS vs SSH Clone
- Real Production Examples
- Interview Questions

`git clone` is the first command every new developer executes when joining a software project.
---

# 3.18 Git Clone

Suppose you join a new software company today.

The Team Lead says:

> "Clone the project from GitHub and start working."

The first Git command you will execute is:

```bash
git clone
```

Every developer and DevOps Engineer uses this command on the very first day of a project.

---

# What is Git Clone?

`git clone` creates a complete copy of a remote Git repository on your local computer.

It downloads:

- Source Code
- Commit History
- Branches
- Tags
- Git Configuration

Everything required to start development.

---

# Clone Workflow

```
GitHub Repository

↓

git clone

↓

Local Computer

↓

Ready to Work
```

After cloning,

you can immediately start coding.

---

# Syntax

```bash
git clone <repository-url>
```

Example

```bash
git clone https://github.com/linuxwithsandeep-lab/DevOps-Engineer-Handbook1.git
```

Git automatically creates a folder with the repository name.

---

# Example

Suppose GitHub contains

```
ShoppingApp
```

Execute

```bash
git clone https://github.com/company/ShoppingApp.git
```

Result

```
ShoppingApp/

├── src/

├── README.md

├── .git/

└── pom.xml
```

The project is ready.

---

# What Does Git Clone Download?

Git downloads:

```
Repository

↓

Branches

↓

Commits

↓

Tags

↓

Remote Configuration

↓

Working Files
```

Everything required to work offline.

---

# Clone Public Repository

Public repositories require no authentication.

Example

```bash
git clone https://github.com/git/git.git
```

Anyone can clone public repositories.

---

# Clone Private Repository

Private repositories require authentication.

Example

```bash
git clone https://github.com/company/private-project.git
```

Git may ask for:

- Username
- Password (older systems)
- Personal Access Token (PAT)
- Browser Authentication

---

# HTTPS Clone

Example

```bash
git clone https://github.com/company/project.git
```

Advantages

- Easy to use
- Works almost everywhere
- Good for beginners

Disadvantages

May require authentication for push operations.

---

# SSH Clone

Example

```bash
git clone git@github.com:company/project.git
```

Advantages

- Faster authentication
- No repeated password prompts
- Preferred in production environments

Requires SSH Key setup.

---

# HTTPS vs SSH

| Feature | HTTPS | SSH |
|----------|--------|------|
| Easy Setup | ✔ | Moderate |
| Password Required | Sometimes | No |
| SSH Key Required | No | Yes |
| Enterprise Usage | Good | Excellent |

---

# Clone into a Specific Folder

By default,

Git creates a folder with the repository name.

You can specify your own folder.

```bash
git clone https://github.com/company/project.git MyProject
```

Result

```
MyProject/
```

instead of

```
project/
```

---

# Check Remote After Clone

Run

```bash
git remote -v
```

Example

```text
origin

https://github.com/company/project.git
```

Git automatically configures the remote named

```
origin
```

---

# Verify Repository Status

After cloning,

run

```bash
git status
```

Output

```text
On branch main

nothing to commit,

working tree clean
```

The repository is ready.

---

# Clone vs Download ZIP

Many beginners download ZIP files.

This is not the same as cloning.

### Download ZIP

```
Files Only

❌ No History

❌ No Branches

❌ No Git
```

---

### Git Clone

```
Files

↓

History

↓

Branches

↓

Commits

↓

Git Repository
```

Git Clone is the correct method for development.

---

# Real Production Example

A new DevOps Engineer joins the company.

The Team Lead shares:

```
https://github.com/company/devops-project.git
```

The engineer runs:

```bash
git clone https://github.com/company/devops-project.git
```

Within a few minutes,

the complete infrastructure code is available locally.

---

# Clone in Enterprise Projects

Large organizations store:

- Dockerfiles
- Jenkinsfiles
- Kubernetes YAML
- Terraform
- Helm Charts
- Bash Scripts

inside Git repositories.

A single clone provides access to the entire infrastructure.

---

# Common Beginner Mistakes

### Mistake 1

Downloading ZIP instead of cloning.

The downloaded project cannot use Git commands until Git is initialized again.

---

### Mistake 2

Cloning into an existing project folder.

Always clone into a new directory unless you know exactly what you are doing.

---

### Mistake 3

Editing files before checking the current branch.

Always verify using:

```bash
git branch
```

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git clone URL | Clone Repository |
| git clone URL Folder | Clone into Specific Folder |
| git remote -v | Verify Remote |
| git status | Verify Repository |
| git branch | Show Current Branch |

---

# Interview Questions

### Q1. What does `git clone` do?

It creates a complete local copy of a remote Git repository.

---

### Q2. Does `git clone` download commit history?

Yes.

It downloads the complete Git history.

---

### Q3. What is the difference between Download ZIP and Git Clone?

ZIP downloads only project files.

Git Clone downloads files, commit history, branches and Git metadata.

---

### Q4. Which remote name is automatically created after cloning?

```
origin
```

---

### Q5. Which cloning method is preferred in enterprise environments?

SSH cloning, because it provides secure authentication using SSH keys.

---

# Production Best Practices

✔ Prefer SSH for company repositories.

✔ Verify the remote using `git remote -v`.

✔ Pull the latest changes before starting development.

✔ Never edit code before confirming the correct branch.

✔ Clone repositories instead of downloading ZIP files.

---

# Key Takeaways

- `git clone` creates a complete local copy of a repository.
- It downloads source code, commit history, branches and Git configuration.
- SSH is commonly used in enterprise environments.
- Cloning is the standard way to start working on any Git project.
- Every developer begins by cloning the repository.

---

# Next Section

## 3.19 Git Branching Strategy (Feature, Develop, Release, Hotfix)

In the next section, we will learn:

- Feature Branches
- Develop Branch
- Release Branch
- Hotfix Branch
- Main Branch
- Git Flow Strategy
- GitHub Flow
- Trunk-Based Development
- Real Enterprise Workflows

This is one of the most important topics for DevOps interviews and real production environments.
---

# 3.19 Git Branching Strategy (Feature, Develop, Release, Hotfix)

Creating branches is easy.

Managing branches for hundreds of developers is difficult.

Large software companies follow a **Branching Strategy** to ensure that everyone works in an organized manner.

A Branching Strategy defines:

- Which branches should exist?
- Who works on which branch?
- When should code be merged?
- How are releases prepared?
- How are production bugs fixed?

Without a proper strategy, software development quickly becomes chaotic.

---

# Why is a Branching Strategy Important?

Imagine a company with:

- 120 Developers
- 20 QA Engineers
- 10 DevOps Engineers

All developers push code directly to the **main** branch.

Result:

```
Broken Builds

↓

Merge Conflicts

↓

Deployment Failures

↓

Production Downtime
```

A branching strategy prevents these problems.

---

# Common Branch Types

Most enterprise projects use these branches.

```
main

↓

develop

↓

feature/*

↓

release/*

↓

hotfix/*
```

Each branch has a specific purpose.

---

# Main Branch

The **main** branch contains production-ready code.

Rules:

- Stable
- Tested
- Deployable
- Protected

Never develop new features directly on the main branch.

---

# Develop Branch

The **develop** branch is the integration branch.

All completed features are merged here first.

```
feature/login

↓

develop

↓

Testing

↓

Release
```

This branch represents the next software version.

---

# Feature Branch

Every new feature gets its own branch.

Examples

```
feature/login

feature/payment

feature/dashboard

feature/profile
```

Developers work independently.

---

# Feature Branch Workflow

```
develop

↓

Create Feature Branch

↓

Coding

↓

Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

Merge into develop
```

---

# Release Branch

When all planned features are completed,

a Release Branch is created.

Example

```
release/v2.0
```

Only:

- Bug Fixes
- Documentation
- Version Updates

are allowed here.

No new features.

---

# Release Workflow

```
develop

↓

release/v2.0

↓

QA Testing

↓

Bug Fixes

↓

main

↓

Production
```

---

# Hotfix Branch

Suppose production crashes.

A fix cannot wait for the next release.

Create

```
hotfix/payment-crash
```

Workflow

```
main

↓

hotfix

↓

Fix

↓

Testing

↓

main

↓

Production
```

Hotfixes bypass the normal release cycle.

---

# Complete Git Flow

```
                   main

                     ▲

                     │

               release/v2.0

                     ▲

                     │

                 develop

          ▲      ▲      ▲

          │      │      │

feature/login

feature/cart

feature/payment
```

This is the classic **Git Flow** model.

---

# GitHub Flow

Many startups use a simpler workflow.

```
main

↓

Feature Branch

↓

Pull Request

↓

Review

↓

Merge

↓

Deploy
```

No develop branch.

Continuous Deployment becomes easier.

---

# Trunk-Based Development

Companies like Google often use

**Trunk-Based Development.**

```
main

↓

Small Feature Branch

↓

Merge Quickly

↓

Delete Branch
```

Branches are short-lived.

Developers merge code frequently.

---

# Which Strategy Should You Choose?

| Team Size | Recommended Strategy |
|------------|----------------------|
| 1–5 Developers | GitHub Flow |
| 5–30 Developers | Git Flow |
| Large Enterprises | Git Flow / Trunk-Based |
| Continuous Deployment | GitHub Flow |
| High Release Frequency | Trunk-Based |

---

# Real Production Example

Suppose ShopKart is developing Version 3.0.

Developers create:

```
feature/login

feature/payment

feature/orders

feature/reports
```

After completion,

all branches merge into

```
develop
```

QA performs testing.

Once approved,

```
release/v3.0
```

is created.

Finally,

the release is merged into

```
main

↓

Production
```

---

# Branch Protection

Production branches are usually protected.

Restrictions include:

✔ Direct Push Disabled

✔ Pull Request Required

✔ Code Review Required

✔ CI/CD Must Pass

✔ Approval Required

These rules prevent accidental changes.

---

# Branch Naming Convention

Professional naming examples:

```
feature/login-page

feature/payment-api

bugfix/cart-issue

hotfix/security-patch

release/v2.1.0

experiment/new-ui
```

Avoid names like:

```
test

new

temp

abc

demo
```

---

# Branch Lifecycle

```
Create Branch

↓

Develop

↓

Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

Merge

↓

Delete Branch
```

Branches should not remain open forever.

---

# Common Beginner Mistakes

### Mistake 1

Working directly on **main**.

Professional teams rarely allow this.

---

### Mistake 2

Using one branch for multiple unrelated features.

Each feature deserves its own branch.

---

### Mistake 3

Keeping feature branches open for months.

Long-lived branches increase merge conflicts.

Merge frequently.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git branch | List Branches |
| git switch -c feature/login | Create Feature Branch |
| git switch develop | Switch Branch |
| git merge feature/login | Merge Branch |
| git branch -d feature/login | Delete Branch |
| git push origin feature/login | Push Feature Branch |

---

# Interview Questions

### Q1. Why do software companies use branching strategies?

To organize development, reduce conflicts and maintain stable production code.

---

### Q2. Which branch usually contains production-ready code?

```
main
```

---

### Q3. What is a Feature Branch?

A branch created for developing a single feature independently.

---

### Q4. What is a Hotfix Branch?

A branch used to quickly fix critical production issues.

---

### Q5. What is Git Flow?

Git Flow is a branching strategy that uses **main**, **develop**, **feature**, **release** and **hotfix** branches.

---

# Production Best Practices

✔ Protect the main branch.

✔ Create one branch per feature.

✔ Keep branches short-lived.

✔ Merge frequently.

✔ Use Pull Requests for every merge.

✔ Delete merged branches.

✔ Follow a consistent branch naming convention.

---

# Key Takeaways

- A branching strategy organizes team collaboration.
- Main should always remain stable.
- Feature branches isolate development.
- Release branches prepare production releases.
- Hotfix branches quickly resolve production issues.
- Every professional software company follows a branching strategy.

---

# Next Section

## 3.20 Pull Requests (PR)

In the next section, we will learn:

- What is a Pull Request?
- Why Pull Requests are Important
- Code Review Process
- PR Approval Workflow
- Merge Checks
- CI/CD Integration
- GitHub Pull Requests
- Real Production Examples

Pull Requests are one of the most important collaboration features in GitHub and are used by every professional development team.
---

# 3.20 Pull Requests (PR)

Writing code is only one part of software development.

Before code reaches production, it should be reviewed by other developers.

GitHub provides a feature called the **Pull Request (PR)** for this purpose.

Almost every professional software company uses Pull Requests.

---

# What is a Pull Request?

A Pull Request is a request to merge changes from one branch into another.

Example

```
feature/login

↓

Pull Request

↓

Code Review

↓

Merge

↓

main
```

The developer requests the team to review the changes.

---

# Why Do We Need Pull Requests?

Imagine a developer accidentally writes a bug.

Without code review,

the bug reaches production.

Using a Pull Request,

another developer reviews the code before merging.

Benefits include:

- Better Code Quality
- Fewer Bugs
- Knowledge Sharing
- Team Collaboration
- Secure Deployments

---

# Real Company Example

Rahul develops a Login Feature.

He pushes the branch.

```
feature/login

↓

GitHub

↓

Create Pull Request
```

Senior Developer reviews the code.

Only after approval,

the code is merged into **main**.

---

# Pull Request Workflow

```
Create Feature Branch

↓

Write Code

↓

Commit

↓

Push

↓

Create Pull Request

↓

Code Review

↓

Approval

↓

Merge

↓

Delete Branch
```

This workflow is used by most software companies.

---

# Creating a Pull Request

Step 1

Push your feature branch.

```bash
git push origin feature/login
```

Step 2

Open GitHub.

Click

```
Compare & Pull Request
```

Step 3

Provide:

- Title
- Description
- Reviewer
- Labels (Optional)

Step 4

Click

```
Create Pull Request
```

---

# Pull Request Components

A Pull Request usually contains:

- Title
- Description
- Commits
- Files Changed
- Comments
- Reviewers
- CI/CD Status

Everything is visible before merging.

---

# Writing a Good PR Title

Good Examples

```
Add Login Authentication

Fix Payment Gateway Timeout

Update Kubernetes Deployment
```

Bad Examples

```
Update

Fix

Changes

Test
```

---

# Writing a Good PR Description

Example

```
## Summary

Added Login Authentication

## Changes

- Added JWT Authentication

- Added Login API

- Updated Database Schema

## Testing

- Unit Tested

- Manual Testing Completed
```

A clear description helps reviewers understand the purpose of the changes.

---

# Code Review

During review,

reviewers check:

✔ Code Quality

✔ Security

✔ Performance

✔ Readability

✔ Naming Conventions

✔ Best Practices

They may request changes before approval.

---

# Review Outcomes

A Pull Request may receive:

```
Approve

↓

Merge

-------------------

Request Changes

↓

Developer Updates Code

↓

Push Again

↓

Review Again
```

---

# CI/CD Integration

Many companies connect Pull Requests with Jenkins or GitHub Actions.

Workflow

```
Pull Request

↓

Automatic Build

↓

Unit Tests

↓

Security Scan

↓

Code Quality

↓

Approval

↓

Merge
```

If tests fail,

the PR cannot be merged.

---

# Merge Pull Request

Once approved,

click

```
Merge Pull Request
```

GitHub merges the feature branch into the target branch.

---

# Close Pull Request

Sometimes the feature is cancelled.

Instead of merging,

click

```
Close Pull Request
```

The branch remains unchanged.

---

# Draft Pull Request

Developers can create a

```
Draft Pull Request
```

Purpose

- Work in Progress
- Feedback
- Early Review

Draft PRs cannot be merged until marked ready.

---

# Real Production Example

Developer creates

```
feature/payment
```

Pushes changes.

GitHub automatically starts:

```
GitHub Actions

↓

Run Unit Tests

↓

Run Security Scan

↓

Run Code Quality Check
```

All checks pass.

Senior Developer approves.

Merge completed.

Jenkins deploys the application.

---

# Branch Protection with Pull Requests

Many companies configure:

✔ Direct Push Disabled

✔ Pull Request Mandatory

✔ Two Reviewers Required

✔ CI/CD Must Pass

✔ Security Scan Must Pass

Only then can the branch be merged.

---

# Common Beginner Mistakes

### Mistake 1

Creating very large Pull Requests.

Smaller PRs are easier to review.

---

### Mistake 2

Not writing a description.

Always explain:

- What changed?
- Why?
- How was it tested?

---

### Mistake 3

Ignoring reviewer comments.

Review feedback improves code quality.

---

### Mistake 4

Merging without running tests.

Always verify:

- Build Success
- Tests Passed
- Code Review Completed

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| git push origin feature/login | Push Feature Branch |
| git status | Check Repository |
| git log | View Commits |
| git diff | Review Changes Before PR |

Most Pull Request operations are performed through the GitHub web interface.

---

# Interview Questions

### Q1. What is a Pull Request?

A Pull Request is a request to merge changes from one branch into another after review.

---

### Q2. Why are Pull Requests important?

They improve code quality through code reviews and automated validation.

---

### Q3. Can a Pull Request trigger CI/CD?

Yes.

Many companies automatically run builds, tests and security scans when a Pull Request is created.

---

### Q4. What should a good Pull Request contain?

- Clear Title
- Description
- Related Changes
- Testing Information

---

### Q5. Can reviewers request changes before merging?

Yes.

Reviewers can approve, reject or request modifications before the Pull Request is merged.

---

# Production Best Practices

✔ Keep Pull Requests small.

✔ Write meaningful titles.

✔ Add a detailed description.

✔ Review your own code before requesting review.

✔ Ensure all CI/CD checks pass.

✔ Respond to reviewer comments promptly.

✔ Delete the feature branch after a successful merge.

---

# Key Takeaways

- Pull Requests enable safe collaboration.
- Every code change should be reviewed.
- CI/CD pipelines often validate Pull Requests automatically.
- Branch protection rules improve software quality.
- Pull Requests are a core part of modern DevOps workflows.

---

# Next Section

## 3.21 GitHub Actions (CI/CD Basics)

In the next section, we will learn:

- What is GitHub Actions?
- Workflows
- Events
- Jobs
- Runners
- YAML Workflow Files
- Automatic Build & Test
- Deployment Pipelines
- Real Production Examples

GitHub Actions is one of the most widely used CI/CD platforms and an essential skill for modern DevOps Engineers.
---

# 3.21 GitHub Actions (CI/CD Basics)

Modern software companies do not manually build, test and deploy applications after every code change.

Instead, they use **CI/CD Pipelines**.

One of the most popular CI/CD platforms today is **GitHub Actions**.

Whenever code is pushed to GitHub, GitHub Actions can automatically:

- Build the Application
- Run Unit Tests
- Perform Security Scans
- Create Docker Images
- Deploy Applications
- Send Notifications

Everything happens automatically.

---

# What is GitHub Actions?

GitHub Actions is GitHub's built-in CI/CD automation platform.

It allows developers to automate workflows directly from a GitHub repository.

Example

```
Developer

↓

Git Push

↓

GitHub Actions

↓

Build

↓

Test

↓

Deploy
```

---

# Why Do We Need GitHub Actions?

Imagine 100 developers are pushing code every day.

Without automation,

someone would manually:

- Compile Code
- Run Tests
- Build Docker Image
- Deploy Server

This would be slow and error-prone.

GitHub Actions automates the entire process.

---

# Real Production Example

Developer fixes a bug.

```
Git Commit

↓

Git Push

↓

GitHub Actions

↓

Run Build

↓

Run Tests

↓

Deploy

↓

Production
```

No manual intervention is required.

---

# GitHub Actions Workflow

Everything starts with a **Workflow**.

A Workflow is a YAML file.

Location

```
.github/

└── workflows/

      └── build.yml
```

Git automatically detects workflow files stored in this folder.

---

# What is YAML?

GitHub Actions uses YAML configuration files.

Example

```yaml
name: Build Project
```

YAML is easy to read and uses indentation.

---

# Basic Workflow Structure

```yaml
name:

on:

jobs:
```

Every workflow contains these three sections.

---

# Workflow Components

```
Workflow

↓

Event

↓

Job

↓

Steps

↓

Runner
```

---

# Workflow

A Workflow is the complete automation process.

Example

```
Build

↓

Test

↓

Deploy
```

---

# Event

Events determine **when** the workflow starts.

Examples

- Push
- Pull Request
- Schedule
- Release
- Manual Trigger

---

# Push Event

Automatically start after every push.

```yaml
on:
  push:
```

---

# Pull Request Event

Run after a Pull Request is created.

```yaml
on:
  pull_request:
```

Useful for automatic testing before merging.

---

# Manual Workflow

Developers can manually start workflows.

```yaml
on:
  workflow_dispatch:
```

Useful for production deployments.

---

# Scheduled Workflow

Automatically execute at fixed times.

Example

```yaml
on:
  schedule:
```

Useful for:

- Nightly Builds
- Backups
- Security Scans

---

# Jobs

A Workflow contains one or more Jobs.

Example

```
Workflow

↓

Build Job

↓

Test Job

↓

Deploy Job
```

Jobs can run sequentially or in parallel.

---

# Steps

Every Job contains multiple Steps.

Example

```
Checkout Code

↓

Install Java

↓

Run Maven Build

↓

Execute Tests

↓

Create Artifact
```

---

# Runner

A Runner is the machine that executes your workflow.

GitHub provides hosted runners such as:

- Ubuntu
- Windows
- macOS

You can also configure Self-Hosted Runners.

---

# GitHub Hosted Runner

Example

```yaml
runs-on: ubuntu-latest
```

GitHub automatically creates a temporary Ubuntu virtual machine.

---

# Basic GitHub Actions Workflow

```yaml
name: Build Project

on:
  push:

jobs:

  build:

    runs-on: ubuntu-latest

    steps:

      - uses: actions/checkout@v4

      - name: Display Message

        run: echo "Build Started"
```

Whenever code is pushed,

this workflow executes automatically.

---

# Real Production Workflow

```
Git Push

↓

Checkout Code

↓

Install Dependencies

↓

Run Tests

↓

Build

↓

Docker Build

↓

Push Docker Image

↓

Deploy Kubernetes

↓

Success Notification
```

Everything is automated.

---

# Production Example

A Java project.

Developer pushes code.

GitHub Actions performs:

```
Checkout

↓

Java Setup

↓

Maven Build

↓

JUnit Tests

↓

Docker Image

↓

Push to Docker Hub

↓

Deploy to Kubernetes
```

The entire deployment pipeline runs automatically.

---

# Advantages of GitHub Actions

- Integrated with GitHub
- Easy YAML Configuration
- Free for Public Repositories
- Marketplace Support
- Cross Platform
- Supports Docker
- Supports Kubernetes
- Supports Cloud Providers

---

# Common Beginner Mistakes

### Mistake 1

Saving workflow outside

```
.github/workflows/
```

GitHub will not detect it.

---

### Mistake 2

Incorrect YAML indentation.

YAML is indentation-sensitive.

---

### Mistake 3

Forgetting to commit the workflow file.

GitHub only executes committed workflows.

---

# Frequently Used Terms

| Term | Meaning |
|-------|----------|
| Workflow | Complete Automation |
| Event | Trigger |
| Job | Group of Steps |
| Step | Individual Task |
| Runner | Machine Executing Workflow |
| YAML | Workflow Configuration |

---

# Interview Questions

### Q1. What is GitHub Actions?

GitHub Actions is GitHub's built-in CI/CD automation platform used to build, test and deploy applications.

---

### Q2. Where are GitHub Actions workflow files stored?

```
.github/workflows/
```

---

### Q3. Which file format is used for GitHub Actions?

YAML (`.yml` or `.yaml`)

---

### Q4. What is a Runner?

A Runner is the machine that executes a GitHub Actions workflow.

---

### Q5. Can GitHub Actions automatically trigger after a Git Push?

Yes.

Using the `push` event.

---

# Production Best Practices

✔ Store workflow files inside `.github/workflows/`.

✔ Keep workflows modular.

✔ Test workflows in feature branches.

✔ Never hardcode secrets inside workflow files.

✔ Use GitHub Secrets for passwords and API keys.

✔ Review workflow logs after every execution.

---

# Key Takeaways

- GitHub Actions automates CI/CD workflows.
- Workflows are written in YAML.
- Events trigger workflows.
- Jobs contain multiple steps.
- Runners execute the workflow.
- GitHub Actions is widely used in modern DevOps environments.

---

# Next Section

## 3.22 GitHub Actions Workflow (Hands-on)

In the next section, we will build our **first real GitHub Actions workflow** step-by-step.

We will learn:

- Create `.github/workflows`
- Build `build.yml`
- Run a Workflow
- View Logs
- Debug Failed Workflows
- Build a Java Project
- Build a Python Project
- Build a Docker Image
- Real Production CI/CD Pipeline

This will be your **first practical GitHub Actions project**.
---

# 3.22 GitHub Actions Workflow (Hands-on)

In the previous section, we learned the theory of GitHub Actions.

Now it's time to build our **first CI/CD pipeline**.

This section follows a real-world approach used in software companies.

By the end of this section, you will be able to create your own GitHub Actions workflow from scratch.

---

# Project Scenario

Suppose your project structure looks like this.

```
ShoppingApp

│

├── app.py

├── requirements.txt

├── Dockerfile

└── README.md
```

Every time code is pushed,

we want GitHub Actions to automatically:

```
Pull Code

↓

Install Dependencies

↓

Run Tests

↓

Build

↓

Success
```

---

# Step 1 – Create Workflow Directory

Inside your repository create

```
.github

└── workflows
```

Structure

```
ShoppingApp

│

├── .github

│      └── workflows

│              └── build.yml

├── app.py

└── Dockerfile
```

GitHub automatically scans this folder.

---

# Step 2 – Create Workflow File

Create

```
build.yml
```

inside

```
.github/workflows/
```

Example

```yaml
name: Python Build
```

---

# Step 3 – Define Trigger

Suppose we want the workflow to start after every push.

```yaml
on:

  push:
```

Now every push triggers the pipeline.

---

# Step 4 – Create Job

Every workflow contains one or more jobs.

```yaml
jobs:

  build:
```

Job name

```
build
```

---

# Step 5 – Select Runner

GitHub creates a virtual machine.

```yaml
runs-on: ubuntu-latest
```

The workflow now runs on Ubuntu.

---

# Step 6 – Checkout Repository

The runner initially contains no project files.

Download the repository.

```yaml
- uses: actions/checkout@v4
```

Now the workflow has access to your code.

---

# Step 7 – Install Python

```yaml
- name: Setup Python

  uses: actions/setup-python@v5

  with:

    python-version: "3.12"
```

Python is now available.

---

# Step 8 – Install Dependencies

```yaml
- name: Install Dependencies

  run: |

    pip install -r requirements.txt
```

Packages are installed automatically.

---

# Step 9 – Execute Tests

Example

```yaml
- name: Run Tests

  run: |

    python -m unittest
```

If tests fail,

the workflow stops.

---

# Step 10 – Success Message

```yaml
- name: Build Completed

  run: echo "Build Successful"
```

---

# Complete Workflow

```yaml
name: Python Build

on:

  push:

jobs:

  build:

    runs-on: ubuntu-latest

    steps:

      - uses: actions/checkout@v4

      - uses: actions/setup-python@v5

        with:

          python-version: "3.12"

      - run: pip install -r requirements.txt

      - run: python -m unittest

      - run: echo "Build Successful"
```

This is your first CI workflow.

---

# Execution Flow

```
Git Push

↓

GitHub

↓

Workflow Trigger

↓

Ubuntu Runner

↓

Checkout Code

↓

Install Python

↓

Install Packages

↓

Run Tests

↓

Build Successful
```

---

# Viewing Workflow Execution

Open GitHub.

Click

```
Actions
```

Select the workflow.

GitHub displays:

- Start Time
- End Time
- Build Logs
- Failed Steps
- Successful Steps

---

# Understanding Workflow Logs

Every step generates logs.

Example

```
Checkout Repository

✔ Success

-------------------

Install Python

✔ Success

-------------------

Install Packages

✔ Success

-------------------

Run Tests

✔ Success
```

Logs help during debugging.

---

# Workflow Failure Example

Suppose

```
requirements.txt
```

contains an invalid package.

Workflow

```
Install Dependencies

↓

Error

↓

Workflow Failed
```

Remaining steps will not execute.

---

# Java Project Example

Workflow

```
Checkout

↓

Setup Java

↓

Maven Build

↓

JUnit Tests

↓

Build Artifact
```

Example

```yaml
- uses: actions/setup-java@v4

- run: mvn clean package
```

---

# Node.js Example

Workflow

```
Checkout

↓

Setup Node.js

↓

npm install

↓

npm test

↓

npm build
```

---

# Docker Example

Workflow

```
Checkout

↓

Docker Build

↓

Docker Push
```

Example

```yaml
- run: docker build -t shoppingapp .
```

---

# Multi-Job Workflow

GitHub Actions supports multiple jobs.

```
Workflow

├── Build

├── Test

└── Deploy
```

Each job can run independently.

---

# Sequential Jobs

```
Build

↓

Test

↓

Deploy
```

Deployment starts only if Build and Test succeed.

---

# Parallel Jobs

```
Build

↙      ↘

Test     Security Scan
```

GitHub executes both simultaneously.

---

# Production CI/CD Pipeline

```
Developer

↓

Git Push

↓

GitHub Actions

↓

Build

↓

Unit Test

↓

Code Quality

↓

Security Scan

↓

Docker Build

↓

Push Docker Image

↓

Deploy Kubernetes

↓

Slack Notification
```

This workflow is commonly used in enterprise environments.

---

# Common Beginner Mistakes

### Mistake 1

Incorrect YAML indentation.

GitHub cannot parse the workflow.

---

### Mistake 2

Wrong workflow location.

Always use

```
.github/workflows/
```

---

### Mistake 3

Forgetting to commit

```
build.yml
```

GitHub only executes committed workflows.

---

### Mistake 4

Ignoring failed logs.

Always read the failing step before fixing the issue.

---

# Frequently Used GitHub Actions

| Action | Purpose |
|----------|----------|
| actions/checkout | Download Repository |
| actions/setup-python | Install Python |
| actions/setup-java | Install Java |
| actions/setup-node | Install Node.js |
| docker/build-push-action | Build Docker Images |

---

# Interview Questions

### Q1. Where should GitHub Actions workflow files be stored?

```
.github/workflows/
```

---

### Q2. Which Action downloads the repository?

```yaml
actions/checkout
```

---

### Q3. Which Action installs Python?

```yaml
actions/setup-python
```

---

### Q4. What happens if one workflow step fails?

The workflow stops unless configured otherwise.

---

### Q5. Where can you view workflow execution logs?

Inside the **Actions** tab of the GitHub repository.

---

# Production Best Practices

✔ Keep workflows small and modular.

✔ Use reusable actions whenever possible.

✔ Never store secrets directly in YAML.

✔ Review workflow logs after every execution.

✔ Test workflows in feature branches before merging.

✔ Use descriptive workflow names.

---

# Key Takeaways

- GitHub Actions workflows are stored in `.github/workflows/`.
- Workflows are written in YAML.
- Actions automate build, test and deployment.
- Workflow logs are essential for troubleshooting.
- GitHub Actions forms the foundation of modern CI/CD pipelines.

---

# Next Section

## 3.23 GitHub Secrets & Environment Variables

In the next section, we will learn:

- What are GitHub Secrets?
- Why Secrets are Important
- Storing API Keys
- Storing AWS Credentials
- Environment Variables
- Secret Management Best Practices
- Production Examples
- Interview Questions

This is a critical security topic used in every enterprise CI/CD pipeline.
---

# 3.23 GitHub Secrets & Environment Variables

Security is one of the most important responsibilities of a DevOps Engineer.

Imagine your project needs to connect to:

- AWS
- Azure
- Docker Hub
- Kubernetes
- Database
- SMTP Server
- API Gateway

All of these services require credentials.

A common beginner mistake is writing credentials directly inside the source code.

Example

```python
AWS_ACCESS_KEY="AKIAxxxxxxxxxxxx"

AWS_SECRET_KEY="abcd123456789"

DB_PASSWORD="admin123"
```

This is extremely dangerous.

GitHub provides a secure solution called **GitHub Secrets**.

---

# What are GitHub Secrets?

GitHub Secrets are encrypted values stored securely inside a GitHub repository or organization.

Secrets are used by GitHub Actions during workflow execution.

Developers cannot directly read their values.

---

# Why Do We Need GitHub Secrets?

Suppose your workflow pushes a Docker image.

Docker Hub requires:

```
Username

↓

Password

↓

Authentication
```

Instead of storing credentials inside the workflow,

store them as GitHub Secrets.

---

# Real Production Example

A workflow deploys an application to AWS.

Required credentials:

```
AWS Access Key

↓

AWS Secret Key

↓

AWS Region
```

These values are stored as GitHub Secrets.

The workflow reads them securely.

---

# Repository Secrets

Secrets can be stored for a single repository.

Example

```
Repository

↓

Settings

↓

Secrets and Variables

↓

Actions

↓

Repository Secrets
```

These secrets are available only to that repository.

---

# Organization Secrets

Large companies often manage hundreds of repositories.

Instead of creating the same secret repeatedly,

they create Organization Secrets.

```
Organization

↓

Secrets

↓

Available to Multiple Repositories
```

---

# Creating a GitHub Secret

Open

```
Repository

↓

Settings

↓

Secrets and Variables

↓

Actions

↓

New Repository Secret
```

Example

```
Name

AWS_ACCESS_KEY_ID

-----------------------

Value

AKIAxxxxxxxxxxxx
```

Save.

GitHub encrypts it automatically.

---

# Common Secret Names

```
AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

DOCKER_USERNAME

DOCKER_PASSWORD

AZURE_CLIENT_ID

KUBE_CONFIG

SSH_PRIVATE_KEY

DATABASE_PASSWORD

API_KEY
```

---

# Using Secrets in GitHub Actions

Example

```yaml
env:

  AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}

  AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
```

GitHub automatically injects the values during workflow execution.

---

# Environment Variables

Environment Variables store values used by applications.

Example

```yaml
env:

  APP_NAME: ShoppingApp

  ENVIRONMENT: Production

  PORT: 8080
```

These values are not necessarily secret.

---

# Secrets vs Environment Variables

| Feature | Secret | Environment Variable |
|----------|---------|----------------------|
| Encrypted | ✔ | ✘ |
| Hidden in Logs | ✔ | ✘ |
| Used for Passwords | ✔ | ✘ |
| Used for Configuration | Sometimes | ✔ |
| Visible in Workflow | No | Yes |

---

# Accessing Secrets

Inside GitHub Actions

```yaml
${{ secrets.SECRET_NAME }}
```

Example

```yaml
${{ secrets.DOCKER_PASSWORD }}
```

---

# Accessing Environment Variables

```yaml
${{ env.APP_NAME }}
```

Example

```yaml
run: echo $APP_NAME
```

---

# Production Example

Workflow

```
Git Push

↓

GitHub Actions

↓

Read Secrets

↓

Login Docker Hub

↓

Build Image

↓

Push Image
```

Credentials are never exposed.

---

# Docker Login Example

```yaml
- name: Login Docker Hub

  run: |

    docker login \
    -u ${{ secrets.DOCKER_USERNAME }} \
    -p ${{ secrets.DOCKER_PASSWORD }}
```

Password never appears in the repository.

---

# AWS Example

```yaml
env:

  AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}

  AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}

  AWS_REGION: ap-south-1
```

Now AWS CLI can authenticate securely.

---

# Kubernetes Example

Store

```
KUBECONFIG
```

as a secret.

Workflow

```
Read Secret

↓

kubectl Apply

↓

Deployment
```

---

# SSH Key Example

Instead of storing SSH keys in the repository,

save them as

```
SSH_PRIVATE_KEY
```

GitHub injects the key only during workflow execution.

---

# Real Enterprise Workflow

```
Developer

↓

Git Push

↓

GitHub Actions

↓

Read Secrets

↓

Build Docker Image

↓

Push Docker Hub

↓

Deploy AWS EKS

↓

Slack Notification
```

No passwords appear in the workflow.

---

# Common Beginner Mistakes

### Mistake 1

Hardcoding passwords inside source code.

Never do this.

---

### Mistake 2

Committing

```
.env
```

containing credentials.

Always ignore it using

```
.gitignore
```

---

### Mistake 3

Printing secrets inside workflow logs.

Example

```yaml
echo $AWS_SECRET_ACCESS_KEY
```

Avoid printing sensitive values.

---

### Mistake 4

Using one secret for every environment.

Production,

Testing

and

Development

should use separate credentials.

---

# Frequently Used Secret Names

| Secret | Purpose |
|----------|----------|
| AWS_ACCESS_KEY_ID | AWS Authentication |
| AWS_SECRET_ACCESS_KEY | AWS Authentication |
| DOCKER_USERNAME | Docker Login |
| DOCKER_PASSWORD | Docker Login |
| KUBE_CONFIG | Kubernetes Access |
| SSH_PRIVATE_KEY | SSH Authentication |
| API_KEY | External APIs |
| DATABASE_PASSWORD | Database Login |

---

# Interview Questions

### Q1. What are GitHub Secrets?

Encrypted values used to securely store passwords, API keys and credentials for GitHub Actions.

---

### Q2. How do you access a GitHub Secret?

```yaml
${{ secrets.SECRET_NAME }}
```

---

### Q3. Should passwords be stored inside workflow YAML files?

No.

Store them as GitHub Secrets.

---

### Q4. What is the difference between Secrets and Environment Variables?

Secrets are encrypted and hidden.

Environment Variables are mainly used for configuration values.

---

### Q5. Why are GitHub Secrets important?

They protect sensitive credentials from being exposed in repositories and workflow files.

---

# Production Best Practices

✔ Never hardcode credentials.

✔ Store all passwords in GitHub Secrets.

✔ Rotate secrets regularly.

✔ Use different secrets for Development, Testing and Production.

✔ Restrict access to repository secrets.

✔ Audit secrets periodically.

✔ Never print secrets in logs.

---

# Key Takeaways

- GitHub Secrets securely store sensitive information.
- Secrets are encrypted and protected.
- Environment Variables are mainly for application configuration.
- GitHub Actions can safely use secrets during execution.
- Proper secret management is essential for secure CI/CD pipelines.

---

# Next Section

## 3.24 Git Best Practices

In the next section, we will learn:

- Professional Git Standards
- Commit Best Practices
- Branch Best Practices
- Repository Structure
- Security Guidelines
- Team Collaboration
- Git Workflow Standards
- Enterprise Recommendations
- Interview Tips

This chapter will summarize the professional Git practices followed by top software companies like Google, Microsoft, Amazon, Netflix and Meta.
---

# 3.24 Git Best Practices

Learning Git commands is not enough.

Professional DevOps Engineers also follow **Git Best Practices**.

These practices make projects:

- Easy to Maintain
- Easy to Review
- Secure
- Scalable
- Reliable

Companies like Google, Microsoft, Amazon, Netflix and Meta have Git standards that every engineer follows.

---

# Why Git Best Practices Matter?

Imagine a company with:

- 300 Developers
- 50 QA Engineers
- 20 DevOps Engineers

Without standards,

developers may:

- Use random branch names
- Write poor commit messages
- Commit passwords
- Push directly to production
- Ignore code reviews

This leads to confusion and production issues.

---

# Best Practice 1 — Write Meaningful Commit Messages

Good

```
Added User Authentication

Fixed Payment Gateway Timeout

Updated Kubernetes Deployment
```

Bad

```
Update

Final

abc

Changes

Test
```

A commit message should explain:

- What changed?
- Why it changed?

---

# Best Practice 2 — Commit Frequently

Instead of:

```
100 Changes

↓

One Commit
```

Prefer:

```
Feature A

↓

Commit

↓

Feature B

↓

Commit

↓

Bug Fix

↓

Commit
```

Small commits make debugging easier.

---

# Best Practice 3 — Create Atomic Commits

One commit should contain one logical change.

Good

```
Added Login API
```

Bad

```
Login

Docker

Terraform

README

Database

All Together
```

Atomic commits simplify rollbacks.

---

# Best Practice 4 — Never Work Directly on Main

Wrong

```
Developer

↓

main

↓

Commit
```

Correct

```
Developer

↓

feature/login

↓

Pull Request

↓

Review

↓

Merge main
```

---

# Best Practice 5 — Use Pull Requests

Every code change should go through:

```
Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

Merge
```

This improves software quality.

---

# Best Practice 6 — Protect Main Branch

Production branches should have:

✔ Direct Push Disabled

✔ Pull Request Required

✔ CI/CD Checks

✔ Code Review

✔ Approval Required

---

# Best Practice 7 — Never Commit Secrets

Never commit

```
Passwords

API Keys

AWS Keys

SSH Keys

Certificates

Database Passwords
```

Store them in:

- GitHub Secrets
- Vault
- Secret Manager

---

# Best Practice 8 — Use .gitignore

Always ignore:

```
node_modules/

.env

logs/

target/

.idea/

.vscode/

terraform.tfstate
```

This keeps repositories clean.

---

# Best Practice 9 — Pull Before Push

Start your day with:

```bash
git pull origin main
```

Reason

```
Latest Code

↓

Start Development
```

This reduces merge conflicts.

---

# Best Practice 10 — Push Feature Branches

Instead of

```bash
git push origin main
```

Use

```bash
git push origin feature/login
```

Production code should be merged through Pull Requests.

---

# Best Practice 11 — Delete Merged Branches

After a successful merge,

delete the feature branch.

```bash
git branch -d feature/login
```

This keeps the repository organized.

---

# Best Practice 12 — Review Before Commit

Always check:

```bash
git status

git diff
```

before committing.

Never commit files accidentally.

---

# Best Practice 13 — Keep Repository Organized

Example

```
ShoppingApp

│

├── src/

├── docs/

├── tests/

├── Dockerfile

├── README.md

└── .gitignore
```

A clean repository is easier to maintain.

---

# Best Practice 14 — Tag Releases

Production releases should be tagged.

Example

```bash
git tag v1.0.0

git tag v2.0.0
```

Tags make it easy to identify release versions.

---

# Best Practice 15 — Keep Commit History Clean

Instead of:

```
Fix

Fix Again

Again

Again

Final

Really Final
```

Use Interactive Rebase to squash related commits into one meaningful commit.

---

# Best Practice 16 — Follow Branch Naming Standards

Good

```
feature/login

feature/payment

bugfix/cart

hotfix/security

release/v2.0
```

Bad

```
abc

new

demo

temp

xyz
```

---

# Best Practice 17 — Review CI/CD Before Merge

Before merging,

verify:

✔ Build Passed

✔ Unit Tests Passed

✔ Security Scan Passed

✔ Code Review Completed

Never ignore failing pipelines.

---

# Best Practice 18 — Document Important Changes

Update:

- README
- CHANGELOG
- Documentation

whenever major functionality changes.

Documentation should evolve with the code.

---

# Best Practice 19 — Resolve Conflicts Carefully

Never rush conflict resolution.

Understand:

```
Your Changes

↓

Incoming Changes

↓

Correct Solution
```

Incorrect conflict resolution may introduce bugs.

---

# Best Practice 20 — Learn Git Internals

Professional engineers understand:

- Commit Objects
- Blob Objects
- Trees
- References
- HEAD
- Reflog

Understanding Git internals helps solve complex problems.

---

# Real Enterprise Workflow

```
Create Feature Branch

↓

Write Code

↓

git status

↓

git add

↓

git commit

↓

git push

↓

Pull Request

↓

Code Review

↓

CI/CD

↓

Merge

↓

Delete Branch
```

This workflow is used in most enterprise projects.

---

# Common Beginner Mistakes

### Mistake 1

Large commits.

Always create smaller logical commits.

---

### Mistake 2

Ignoring `.gitignore`.

Temporary files should never be committed.

---

### Mistake 3

Working directly on `main`.

Always use feature branches.

---

### Mistake 4

Using meaningless commit messages.

Write clear and descriptive messages.

---

### Mistake 5

Ignoring CI/CD failures.

Never merge broken builds.

---

# Git Checklist Before Every Push

✔ Repository Updated

✔ Correct Branch

✔ `git status` Clean

✔ No Secrets

✔ Tests Passed

✔ Build Passed

✔ Commit Message Correct

✔ Pull Request Ready

---

# Interview Questions

### Q1. Why are Git Best Practices important?

They improve collaboration, security, maintainability and software quality.

---

### Q2. Should developers commit directly to the main branch?

No.

Feature branches and Pull Requests should be used.

---

### Q3. Why should commits be small?

Small commits are easier to review, debug and rollback.

---

### Q4. Why should secrets never be committed?

Because they expose sensitive credentials and create security risks.

---

### Q5. Why should feature branches be deleted after merging?

To keep the repository clean and reduce maintenance.

---

# Production Best Practices Summary

✔ Write meaningful commits.

✔ Create feature branches.

✔ Use Pull Requests.

✔ Protect production branches.

✔ Keep repositories clean.

✔ Review code before merging.

✔ Never commit secrets.

✔ Keep documentation updated.

✔ Test before every merge.

✔ Follow your team's Git workflow.

---

# Key Takeaways

- Professional Git usage is about discipline, not just commands.
- Small, meaningful commits improve project history.
- Feature branches and Pull Requests enable safe collaboration.
- Security and code quality should always come before speed.
- Following Git best practices helps teams scale efficiently.

---

# Next Section

## 3.25 Git Interview Questions & Real Production Scenarios

In the final section of this chapter, we will cover:

- Top 100 Git Interview Questions
- Real Production Scenarios
- Troubleshooting Examples
- Frequently Encountered Git Errors
- Enterprise Workflow Questions
- Practical Tips for DevOps Interviews

This section will prepare you for real-world Git usage and technical interviews.
---

# 3.25 Git Interview Questions & Real Production Scenarios

Congratulations!

You have completed the Git chapter.

Now it's time to prepare for **real DevOps jobs and interviews**.

This section contains:

- Frequently Asked Interview Questions
- Real Production Scenarios
- Troubleshooting Examples
- Common Git Errors
- Practical Decision Making
- Enterprise Best Practices

This is one of the most valuable sections of this chapter.

---

# Real Production Scenario 1

## Two Developers Modified the Same File

Rahul changes

```
payment.java
```

Priya also changes

```
payment.java
```

Both push their work.

Result

```
Merge Conflict
```

Solution

```
git pull

↓

Resolve Conflict

↓

git add

↓

git commit

↓

git push
```

---

# Real Production Scenario 2

## Wrong File Committed

Developer accidentally commits

```
application.properties
```

containing passwords.

Solution

```
git rm --cached application.properties

↓

Update .gitignore

↓

Commit

↓

Rotate Passwords

↓

Push
```

Never leave exposed credentials active.

---

# Real Production Scenario 3

## Wrong Branch

Developer writes code on

```
main
```

instead of

```
feature/login
```

Solution

```
Create Feature Branch

↓

Move Commit

↓

Reset Main

↓

Push Feature Branch
```

---

# Real Production Scenario 4

## Production Bug After Deployment

Deployment completed.

Users report login failures.

DevOps Engineer investigates.

Commands

```bash
git log

git show

git diff
```

The faulty commit is identified.

Rollback begins.

---

# Real Production Scenario 5

## New Developer Joins

The Team Lead shares:

```
Repository URL
```

Developer executes

```bash
git clone

↓

git branch

↓

git pull

↓

Start Development
```

Standard onboarding process.

---

# Real Production Scenario 6

## Build Failed After Merge

Developer merges a Pull Request.

CI/CD Pipeline fails.

Workflow

```
GitHub Actions

↓

Build Failed

↓

Review Logs

↓

Fix

↓

Commit

↓

Push

↓

Pipeline Success
```

Never ignore failed pipelines.

---

# Real Production Scenario 7

## Feature Not Ready

Developer has unfinished work.

Instead of merging,

keep working inside

```
feature/payment
```

Only merge after:

✔ Testing

✔ Review

✔ Approval

---

# Real Production Scenario 8

## Production Hotfix

Critical payment failure.

Workflow

```
main

↓

hotfix/payment

↓

Fix

↓

Testing

↓

Merge

↓

Deploy

↓

Delete Branch
```

Hotfixes should be small and focused.

---

# Real Production Scenario 9

## Repository Accidentally Deleted

GitHub repository removed.

Because every developer has a local clone,

the repository can be restored.

One developer pushes the local repository back to GitHub.

---

# Real Production Scenario 10

## CI/CD Deployment

```
Developer

↓

Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

Merge

↓

GitHub Actions

↓

Docker Build

↓

Image Push

↓

Kubernetes

↓

Production
```

This is a common enterprise deployment pipeline.

---

# Common Git Errors

## Error

```
fatal: not a git repository
```

Reason

Git has not been initialized.

Solution

```bash
git init
```

---

## Error

```
Permission denied
```

Reason

Authentication problem.

Check:

- SSH Keys
- GitHub Token
- Repository Access

---

## Error

```
Merge Conflict
```

Reason

Two branches modified the same code.

Solution

Resolve manually.

---

## Error

```
Everything up-to-date
```

Meaning

There are no new commits to push.

---

## Error

```
non-fast-forward
```

Reason

Remote repository contains newer commits.

Solution

```bash
git pull

↓

Resolve

↓

git push
```

---

# Git Command Cheat Sheet

| Task | Command |
|------|----------|
| Initialize Repository | `git init` |
| Clone Repository | `git clone URL` |
| Repository Status | `git status` |
| Stage File | `git add filename` |
| Stage All Files | `git add .` |
| Commit Changes | `git commit -m "message"` |
| View History | `git log --oneline` |
| Create Branch | `git switch -c branch` |
| Switch Branch | `git switch branch` |
| Merge Branch | `git merge branch` |
| Push Changes | `git push origin main` |
| Pull Changes | `git pull origin main` |
| Fetch Changes | `git fetch origin` |
| Clone Repository | `git clone URL` |
| View Remote | `git remote -v` |

---

# Top Interview Questions

### Q1. What is Git?

Git is a Distributed Version Control System used to track source code changes.

---

### Q2. Difference between Git and GitHub?

Git manages version history.

GitHub hosts Git repositories online.

---

### Q3. What is a Commit?

A snapshot of the project at a specific point in time.

---

### Q4. What is a Branch?

An independent line of development.

---

### Q5. What is Merge?

Combining one branch into another.

---

### Q6. What is Rebase?

Rewriting commit history to create a clean, linear history.

---

### Q7. Difference between Merge and Rebase?

Merge preserves history.

Rebase rewrites history.

---

### Q8. What is a Pull Request?

A request to review and merge changes.

---

### Q9. What is Git Fetch?

Downloads remote changes without merging.

---

### Q10. What is Git Pull?

Downloads and merges remote changes.

---

### Q11. Difference between Fetch and Pull?

Fetch downloads only.

Pull downloads and merges.

---

### Q12. Why is `.gitignore` important?

It prevents temporary and sensitive files from being committed.

---

### Q13. What is HEAD?

HEAD is a pointer to the currently checked-out commit or branch.

---

### Q14. What is Origin?

The default name for a remote repository.

---

### Q15. Why are small commits recommended?

They simplify code reviews, debugging and rollbacks.

---

# Practical Interview Scenario

**Interviewer**

Your teammate accidentally pushed a password to GitHub.

What will you do?

**Expected Answer**

- Remove the sensitive file from Git tracking.
- Rotate the exposed credentials immediately.
- Update `.gitignore`.
- Remove the secret from repository history if required.
- Verify no active systems still use the exposed credential.

---

# Enterprise Git Workflow

```
Requirement

↓

Feature Branch

↓

Development

↓

Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

CI/CD Pipeline

↓

QA Approval

↓

Merge

↓

Deployment

↓

Monitoring

↓

Production
```

This workflow is followed by most enterprise software teams.

---

# Chapter 3 Summary

In this chapter, you learned:

✔ Git Fundamentals

✔ Git Installation

✔ Git Configuration

✔ Git Architecture

✔ Git Repository

✔ Git Status

✔ Git Add

✔ Git Commit

✔ Git Log

✔ Git Ignore

✔ Git Branching

✔ Git Merge

✔ Git Rebase

✔ Merge vs Rebase

✔ Remote Repositories

✔ Push, Pull & Fetch

✔ Git Clone

✔ Branching Strategy

✔ Pull Requests

✔ GitHub Actions

✔ GitHub Secrets

✔ Git Best Practices

✔ Real Production Scenarios

✔ Interview Questions

---

# Chapter Completion Checklist

Before moving to the next chapter, make sure you can confidently:

- Create and initialize a Git repository.
- Stage and commit changes.
- Read commit history.
- Create, switch and merge branches.
- Resolve basic merge conflicts.
- Use remote repositories.
- Push and pull code from GitHub.
- Create Pull Requests.
- Understand GitHub Actions basics.
- Manage GitHub Secrets securely.
- Follow professional Git workflows.

---

# Final Key Takeaways

- Git is the foundation of modern DevOps.
- Every CI/CD pipeline starts with Git.
- Good Git practices improve collaboration and software quality.
- Understanding Git deeply makes learning Jenkins, Docker and Kubernetes much easier.
- Mastering Git is essential for every DevOps Engineer.

---

# End of Chapter 3

## Next Chapter

# Chapter 4 — AWS Cloud Basics ☁️

In the next chapter, we will learn:

- Introduction to Cloud Computing
- Why Cloud is Important
- AWS Global Infrastructure
- Regions & Availability Zones
- IAM
- EC2
- EBS
- Security Groups
- VPC
- Load Balancer
- Auto Scaling
- S3
- RDS
- CloudWatch
- CloudFormation
- Hands-on Labs
- Real Production Architecture

By the end of Chapter 4, you will be able to deploy real-world applications on AWS like a professional DevOps Engineer.