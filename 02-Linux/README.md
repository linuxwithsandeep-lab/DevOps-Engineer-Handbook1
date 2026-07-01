# Chapter 2

# Linux for DevOps Engineers

---

# Chapter Objectives

After completing this chapter, you will be able to understand:

- Why Linux is the first operating system for DevOps Engineers.
- Why almost every production server runs Linux.
- The difference between Desktop Linux and Server Linux.
- The Linux boot process.
- The Linux file system.
- Why DevOps Engineers spend most of their time on Linux servers.

---

# 2.1 Introduction

Congratulations.

In Chapter 1, you learned how a software company builds its infrastructure.

You understood:

- Data Centers
- Physical Servers
- Virtual Machines
- Containers
- Kubernetes
- DevOps Workflow

Now the next question is:

> **Which Operating System runs on those servers?**

The answer is:

**Linux.**

Almost every modern cloud platform and Kubernetes cluster runs on Linux.

If you become a DevOps Engineer, Linux will become your daily working environment.

---

# Real Company Example

Suppose ShopKart has launched its production infrastructure.

The Infrastructure Team has created ten Virtual Machines.

```
VM-1

↓

Ubuntu Server

-----------------------

VM-2

↓

Ubuntu Server

-----------------------

VM-3

↓

Red Hat Enterprise Linux

-----------------------

VM-4

↓

Rocky Linux

-----------------------

VM-5

↓

Amazon Linux
```

The company now asks the DevOps Team:

> Prepare these servers for application deployment.

The first skill required is Linux Administration.

---

# Why Linux?

Most beginners ask:

> Why don't companies use Windows Server everywhere?

The answer is simple.

Linux provides:

- Stability
- Security
- Performance
- Flexibility
- Automation
- Lower Licensing Cost

Linux is also the native operating system for Docker and Kubernetes.

---

# Where Linux is Used

Linux is used in:

- Amazon
- Google
- Microsoft Azure
- Netflix
- Flipkart
- Banking Applications
- Kubernetes Clusters
- Docker Hosts
- Web Servers
- Database Servers
- Monitoring Servers

Even Android is based on the Linux Kernel.

---

# Linux in a Production Environment

A production server normally runs without a graphical interface.

Example:

```
SSH

↓

Linux Terminal

↓

Command Line

↓

Application
```

Most production servers do not have a desktop environment.

Everything is managed using commands.

---

# Common Linux Distributions

Some popular Linux distributions used in production include:

| Distribution | Common Usage |
|--------------|--------------|
| Ubuntu Server | Cloud & DevOps |
| Red Hat Enterprise Linux (RHEL) | Enterprise |
| Rocky Linux | Enterprise |
| AlmaLinux | Enterprise |
| Debian | Stable Servers |
| Amazon Linux | AWS |
| SUSE Linux | Enterprise |

Although commands are mostly similar, package managers and support models may differ.

---

# Linux Learning Roadmap

In this chapter we will learn Linux exactly as a DevOps Engineer uses it.

```
Linux Architecture

↓

File System

↓

Files & Directories

↓

Users & Groups

↓

Permissions

↓

Processes

↓

Services

↓

Package Management

↓

Networking

↓

Storage

↓

Logs

↓

Shell Scripting
```

Each topic will be explained using real production examples.

---

# Key Takeaways

- Linux is the most widely used operating system in DevOps.
- Almost every production Kubernetes cluster runs on Linux.
- Cloud providers primarily use Linux-based servers.
- Every DevOps Engineer must be comfortable working from the Linux terminal.

---

# Next Section

## 2.2 Why Companies Choose Linux

In the next section, we will understand **why enterprises prefer Linux over other operating systems**, using technical comparisons and real production scenarios.
---

# 2.2 Why Companies Choose Linux

Before learning Linux commands, every DevOps Engineer must understand one important question.

> **Why do companies use Linux instead of Windows Server for most production workloads?**

The answer is not because Linux is free.

The real answer is reliability, performance, security and automation.

---

# Real Company Example

Suppose ShopKart Pvt. Ltd. launches a new E-Commerce platform.

The company needs the following servers.

```
Application Server

Database Server

Jenkins Server

Docker Server

Kubernetes Master

Worker Node

Monitoring Server

Log Server

Backup Server
```

Now imagine buying Windows Server licenses for every server.

The infrastructure cost increases significantly.

Instead, the company installs Linux.

---

# Why Linux Became the Industry Standard

Linux became popular because it solves several business problems.

Major advantages include:

- Stability
- Performance
- Security
- Automation
- Flexibility
- Low Cost
- Open Source
- Strong Community Support

---

# Stability

Production servers are expected to run continuously.

Many Linux servers run for months or even years without rebooting.

Example:

```
Linux Server

↓

Running

↓

180 Days

↓

No Reboot
```

This level of stability is essential for banking systems, cloud platforms and e-commerce applications.

---

# Performance

Linux consumes fewer system resources.

Example.

Server Configuration

```
CPU : 8 Core

RAM : 32 GB
```

Windows may consume a significant portion of memory for GUI services.

Linux Server (CLI only) leaves more resources available for applications.

Result:

- Faster Applications
- Better Response Time
- Higher User Capacity

---

# Security

Linux provides strong security mechanisms.

Examples:

- User Permissions
- File Permissions
- SELinux
- AppArmor
- Firewall
- SSH Authentication
- Audit Logs

These features help protect production servers.

---

# Automation

DevOps depends heavily on automation.

Linux allows administrators to automate tasks using:

- Bash
- Cron Jobs
- Shell Scripts
- Python
- Ansible

Example.

```
Backup Script

↓

Runs Every Night

↓

Automatic Backup

↓

Email Notification
```

No manual work is required.

---

# Open Source

Linux source code is publicly available.

Companies can:

- Customize Linux
- Improve Linux
- Fix Bugs
- Build Their Own Distributions

This flexibility is one of the reasons why cloud providers use Linux extensively.

---

# Cost Advantage

Linux distributions such as Ubuntu, Debian, Rocky Linux and AlmaLinux can be used without purchasing expensive operating system licenses.

Large organizations with thousands of servers save significant costs.

---

# Linux in Modern Technologies

Today almost every major DevOps technology runs on Linux.

| Technology | Linux Support |
|------------|---------------|
| Docker | Native |
| Kubernetes | Native |
| Jenkins | Excellent |
| Terraform | Excellent |
| Ansible | Native |
| Nginx | Native |
| Apache | Native |
| MySQL | Native |
| PostgreSQL | Native |
| Redis | Native |

Learning Linux automatically prepares you for these technologies.

---

# Production Example

Suppose ShopKart uses Kubernetes.

The Kubernetes Cluster contains:

```
Master Node

↓

Ubuntu Server

--------------------

Worker Node 1

↓

Ubuntu Server

--------------------

Worker Node 2

↓

Ubuntu Server

--------------------

Worker Node 3

↓

Ubuntu Server
```

Every Kubernetes node runs Linux.

Without Linux, Kubernetes cannot function in its standard production architecture.

---

# Interview Questions

### Q1. Why do companies prefer Linux?

Because Linux provides stability, security, performance, automation, flexibility and lower operating costs.

---

### Q2. Is Linux mandatory for DevOps?

Yes.

Almost every production DevOps environment uses Linux servers.

---

### Q3. Which Linux distributions are commonly used?

- Ubuntu Server
- Red Hat Enterprise Linux
- Rocky Linux
- AlmaLinux
- Debian
- Amazon Linux

---

# Key Takeaways

- Linux is the industry standard for DevOps.
- Most cloud servers run Linux.
- Docker and Kubernetes are designed primarily for Linux.
- Learning Linux is the foundation of every DevOps career.

---

# Next Section

## 2.3 Linux Architecture

In the next section, we will open a Linux system and understand its internal architecture:

- User Space
- Shell
- Kernel
- System Calls
- Hardware

This knowledge will help you understand how every Linux command actually works.
---

# 2.3 Linux Architecture

Before learning Linux commands, every DevOps Engineer should understand how Linux works internally.

When you type a command such as:

```bash
ls
```

or

```bash
mkdir project
```

the command does not directly communicate with the hardware.

Several software layers work together before the command is executed.

Understanding these layers helps you troubleshoot Linux systems more effectively.

---

# Linux Architecture

```
+---------------------------------------+
|              User                     |
+---------------------------------------+
                │
                ▼
+---------------------------------------+
|         Shell (Bash, Zsh)             |
+---------------------------------------+
                │
                ▼
+---------------------------------------+
|         Linux Kernel                  |
+---------------------------------------+
                │
                ▼
+---------------------------------------+
| Hardware (CPU, RAM, Disk, Network)    |
+---------------------------------------+
```

Every Linux command follows this architecture.

---

# Layer 1 - User

The User is the person interacting with the Linux system.

Examples:

- DevOps Engineer
- Linux Administrator
- Application Developer
- Database Administrator

The user provides commands through the terminal.

Example:

```bash
pwd
```

or

```bash
cd /var/log
```

The user never communicates directly with the hardware.

---

# Layer 2 - Shell

The Shell acts as an interpreter.

Its responsibilities include:

- Reading commands
- Checking syntax
- Executing commands
- Displaying output

Popular Linux shells include:

- Bash
- Zsh
- Ksh
- Fish

Most production servers use **Bash**.

Example:

```
User

↓

mkdir project

↓

Bash Shell

↓

Kernel
```

---

# Layer 3 - Linux Kernel

The Kernel is the heart of Linux.

Every hardware component communicates through the Kernel.

The Kernel manages:

- CPU Scheduling
- Memory Management
- Process Management
- Device Drivers
- Network Stack
- File System
- Security

Without the Kernel, Linux cannot function.

---

# Example

Suppose you execute:

```bash
touch report.txt
```

Internally, Linux performs the following steps.

```
User

↓

Shell

↓

Kernel

↓

Disk Controller

↓

SSD

↓

File Created
```

Although only one command was typed, several components worked together.

---

# Memory Management

The Kernel controls memory allocation.

Example:

```
Application A

↓

2 GB RAM

-----------------

Application B

↓

4 GB RAM

-----------------

Application C

↓

1 GB RAM
```

The Kernel ensures that one application cannot overwrite another application's memory.

---

# Process Management

Whenever a program starts, Linux creates a **Process**.

Example:

```
nginx

↓

PID 1050

-----------------

mysql

↓

PID 2088

-----------------

docker

↓

PID 3021
```

Every running program has a unique Process ID (PID).

The Kernel manages these processes.

---

# File System Management

The Kernel controls:

- File Creation
- File Deletion
- Permissions
- Storage Allocation
- Disk Access

Whenever you run:

```bash
rm file.txt
```

the Kernel performs the actual deletion.

---

# Device Drivers

Linux communicates with hardware using Device Drivers.

Examples:

- Keyboard Driver
- Mouse Driver
- Network Driver
- USB Driver
- Storage Driver

Without drivers, Linux cannot communicate with hardware devices.

---

# Networking

The Linux Kernel also manages networking.

Examples:

- IP Address
- TCP/IP
- Routing
- Firewall
- Network Interfaces

This is why Linux is widely used for servers and cloud infrastructure.

---

# Why DevOps Engineers Should Understand Linux Architecture

Many production issues occur because engineers understand commands but not the internal working of Linux.

Example:

A developer reports:

```
Application is slow.
```

A DevOps Engineer investigates:

- CPU Usage
- Memory Usage
- Disk I/O
- Network Latency
- Process State

All of these are managed by the Linux Kernel.

Understanding Linux Architecture makes troubleshooting much easier.

---

# Interview Questions

### Q1. What is the Kernel?

The Kernel is the core component of the Linux operating system responsible for managing hardware resources and providing services to applications.

---

### Q2. What is the Shell?

The Shell is a command interpreter that accepts user commands and passes them to the Linux Kernel.

---

### Q3. Does the user communicate directly with hardware?

No.

The user communicates with the Shell, which communicates with the Kernel, and the Kernel interacts with the hardware.

---

# Key Takeaways

- Linux follows a layered architecture.
- The Kernel is the core of the operating system.
- The Shell interprets user commands.
- Hardware is controlled through the Kernel.
- Understanding Linux Architecture is essential for troubleshooting production servers.

---

# Next Section

## 2.4 Linux File System

In the next section, we will explore the Linux File System and understand every important directory such as:

- /
- /home
- /etc
- /var
- /usr
- /opt
- /tmp
- /boot
- /dev
- /proc

These directories are used daily by every DevOps Engineer.
---

# 2.4 Linux File System

One of the biggest differences between Windows and Linux is the File System.

In Windows, files are organized using drives.

Examples:

```
C:\

D:\

E:\
```

In Linux, there are **no drive letters**.

Everything starts from a single root directory.

```
/
```

This is called the **Root Directory**.

Every file, folder, hard disk, USB drive and network storage is attached somewhere under this directory.

---

# Linux File System Hierarchy

```
                    /
                    │
 ├── bin
 ├── boot
 ├── dev
 ├── etc
 ├── home
 ├── lib
 ├── media
 ├── mnt
 ├── opt
 ├── proc
 ├── root
 ├── run
 ├── sbin
 ├── srv
 ├── sys
 ├── tmp
 ├── usr
 └── var
```

Every directory has a specific purpose.

A DevOps Engineer should know what each directory stores.

---

# Root Directory (/)

The root directory is the starting point of the Linux file system.

Everything exists under this directory.

```
/

↓

Everything
```

Without the root directory, Linux cannot boot.

---

# /home

This directory stores the home directories of normal users.

Example

```
/home

↓

sandeep

↓

Documents

Downloads

Projects
```

Suppose user **rahul** logs in.

His files are stored here.

```
/home/rahul
```

---

# /root

This directory belongs to the **root user**.

It is different from `/home`.

Example

```
/root
```

Only the root administrator normally uses this directory.

---

# /etc

One of the most important directories in Linux.

It contains configuration files.

Examples:

```
/etc/passwd

/etc/group

/etc/hosts

/etc/fstab

/etc/ssh

/etc/systemd
```

Whenever a DevOps Engineer changes server configuration,

most changes happen inside `/etc`.

---

# /var

Stores data that changes frequently.

Examples:

```
Logs

Mail

Cache

Database Files

Web Server Logs
```

Important directory:

```
/var/log
```

Production logs are usually stored here.

Example:

```
/var/log/messages

/var/log/syslog

/var/log/nginx

/var/log/httpd
```

---

# /usr

Contains installed software.

Examples:

```
Applications

Libraries

Commands

Documentation
```

Whenever software is installed,

many files are stored under `/usr`.

---

# /opt

Optional software is generally installed here.

Examples:

```
/opt/jenkins

/opt/tomcat

/opt/application
```

Many companies install custom enterprise applications inside `/opt`.

---

# /tmp

Temporary files are stored here.

Example:

```
Downloads

Installer Files

Temporary Data
```

The operating system may automatically delete these files after reboot.

---

# /boot

Contains files required to boot Linux.

Examples:

```
Kernel

GRUB

Boot Loader
```

If this directory becomes corrupted,

Linux may fail to start.

---

# /dev

Everything in Linux is treated as a file.

Even hardware devices.

Examples:

```
Hard Disk

USB

Keyboard

Mouse

DVD
```

These devices appear inside `/dev`.

Example:

```
/dev/sda

/dev/sdb

/dev/null
```

---

# /proc

This is a virtual file system.

It provides information about:

- CPU
- Memory
- Running Processes
- Kernel

Example:

```
/proc/cpuinfo

/proc/meminfo
```

These files are generated dynamically.

They are not stored on disk.

---

# /bin

Contains essential user commands.

Examples:

```
ls

cp

mv

cat

mkdir

pwd
```

Without these commands,

basic Linux operations become impossible.

---

# /sbin

Contains system administration commands.

Examples:

```
reboot

shutdown

fdisk

mkfs
```

These commands are mainly used by administrators.

---

# /media

External storage devices are usually mounted here.

Example:

```
USB Drive

DVD

External HDD
```

---

# /mnt

Used for manually mounting storage.

Example:

```
Network Storage

Additional Hard Disk

Cloud Storage
```

System administrators often use this directory during maintenance.

---

# Linux File System Summary

| Directory | Purpose |
|------------|----------|
| / | Root Directory |
| /home | User Home Directories |
| /root | Root User Home |
| /etc | Configuration Files |
| /var | Logs and Variable Data |
| /usr | Installed Applications |
| /opt | Optional Software |
| /tmp | Temporary Files |
| /boot | Boot Files |
| /dev | Device Files |
| /proc | Process Information |
| /bin | Essential Commands |
| /sbin | System Commands |
| /media | Removable Devices |
| /mnt | Manual Mount Points |

---

# Production Example

Suppose your company's website is down.

A DevOps Engineer immediately checks:

```
Application Logs

↓

/var/log
```

If SSH is not working,

configuration is checked inside:

```
/etc/ssh
```

If disk space is full,

temporary files may be cleaned from:

```
/tmp
```

If a custom application is installed,

it may exist inside:

```
/opt/application
```

This is why understanding the Linux File System is one of the first skills expected from every DevOps Engineer.

---

# Interview Questions

### Q1. What is the top-most directory in Linux?

The root directory (`/`) is the top-most directory.

---

### Q2. Where are Linux configuration files stored?

Configuration files are generally stored inside `/etc`.

---

### Q3. Where are log files stored?

Most production log files are stored inside `/var/log`.

---

### Q4. Where are normal user home directories stored?

Normal user home directories are stored inside `/home`.

---

# Key Takeaways

- Linux has a single hierarchical file system.
- Everything starts from the root directory (`/`).
- Every directory has a specific purpose.
- Understanding the file system is essential for server administration and troubleshooting.

---

# Next Section

## 2.5 Navigating the Linux File System

In the next section, we will learn the first production Linux commands used by every DevOps Engineer:

- `pwd`
- `ls`
- `cd`
- `tree`
- `clear`
- `history`

These commands are used hundreds of times every day in production environments.
---

# 2.5 Navigating the Linux File System

A DevOps Engineer spends most of the day working inside the Linux terminal.

Before managing servers, deploying applications or troubleshooting issues, you must know how to move around the Linux file system.

This section introduces the first Linux commands that every engineer uses daily.

---

# Present Working Directory (pwd)

The `pwd` command displays the current directory.

### Syntax

```bash
pwd
```

### Example

```bash
$ pwd

/home/sandeep
```

### Explanation

```
/

↓

home

↓

sandeep
```

This tells us that the current location is the **sandeep** user's home directory.

---

# Listing Files (ls)

The `ls` command lists files and directories.

### Syntax

```bash
ls
```

### Example

```bash
$ ls

Documents
Downloads
Projects
Pictures
Videos
```

---

# Long Listing Format

```bash
ls -l
```

Example

```bash
$ ls -l

drwxr-xr-x 2 root root 4096 Jun 25 Projects
-rw-r--r-- 1 root root 1250 Jun 25 notes.txt
```

### Explanation

| Field | Meaning |
|--------|----------|
| d | Directory |
| rwx | Owner Permission |
| r-x | Group Permission |
| r-x | Others Permission |
| root | Owner |
| root | Group |
| 4096 | Size |
| Jun 25 | Last Modified |
| Projects | Name |

---

# Show Hidden Files

Linux hides files beginning with a dot (`.`).

To display them:

```bash
ls -a
```

Example

```bash
$ ls -a

.
..
.bashrc
.profile
.ssh
Projects
```

Hidden files usually store configuration settings.

---

# Human Readable Size

```bash
ls -lh
```

Example

```bash
-rw-r--r-- 1 root root 2.5M report.pdf
```

Instead of bytes,

Linux displays KB, MB or GB.

---

# Changing Directory (cd)

The `cd` command changes the current directory.

### Syntax

```bash
cd directory_name
```

Example

```bash
cd Projects
```

Current location changes to

```
/home/sandeep/Projects
```

---

# Move Back One Directory

```bash
cd ..
```

Example

```
Current

/home/sandeep/Projects

↓

cd ..

↓

/home/sandeep
```

---

# Go to Home Directory

```bash
cd
```

or

```bash
cd ~
```

Both commands return to the user's home directory.

---

# Go to Root Directory

```bash
cd /
```

Example

```
/

↓

bin

etc

home

var
```

---

# Absolute Path

Example

```bash
cd /var/log
```

Linux moves directly to

```
/var/log
```

regardless of the current location.

---

# Relative Path

Suppose current directory is

```
/home/sandeep
```

Then

```bash
cd Projects
```

moves to

```
/home/sandeep/Projects
```

Relative paths start from the current directory.

---

# Clear Screen

```bash
clear
```

This clears the terminal screen.

Shortcut

```
Ctrl + L
```

---

# Command History

Linux remembers previously executed commands.

```bash
history
```

Example

```bash
1 pwd
2 ls
3 cd Projects
4 mkdir DevOps
5 vim notes.txt
```

This is extremely useful during troubleshooting.

---

# Auto Completion

Linux supports command completion using the **TAB** key.

Example

Instead of typing

```bash
cd /home/sandeep/Documents
```

Type

```bash
cd /ho
```

Press **TAB**

Linux automatically completes the path.

This saves time and reduces typing mistakes.

---

# Production Example

Suppose a developer reports:

> "Application logs are located in `/var/log/nginx`."

The DevOps Engineer executes:

```bash
cd /var/log/nginx

ls -lh

pwd
```

Output

```
/var/log/nginx
```

The engineer has now reached the correct log directory.

---

# Most Frequently Used Navigation Commands

| Command | Purpose |
|----------|----------|
| pwd | Show Current Directory |
| ls | List Files |
| ls -l | Detailed Listing |
| ls -a | Show Hidden Files |
| ls -lh | Human Readable Sizes |
| cd | Change Directory |
| cd .. | Move One Level Up |
| cd / | Go to Root Directory |
| cd ~ | Go to Home Directory |
| clear | Clear Screen |
| history | Show Command History |

---

# Interview Questions

### Q1. Which command shows the current directory?

```bash
pwd
```

---

### Q2. Which command displays hidden files?

```bash
ls -a
```

---

### Q3. What is the difference between an Absolute Path and a Relative Path?

**Absolute Path** starts from the root directory (`/`).

Example:

```bash
/var/log
```

**Relative Path** starts from the current working directory.

Example:

```bash
cd Projects
```

---

### Q4. Which command returns to the user's home directory?

```bash
cd
```

or

```bash
cd ~
```

---

# Key Takeaways

- `pwd` shows the current directory.
- `ls` lists files and folders.
- `cd` changes directories.
- Absolute and Relative paths are different.
- Navigation commands are the most frequently used Linux commands in production.

---

# Next Section

## 2.6 Creating, Copying, Moving and Deleting Files & Directories

In the next section, we will learn the commands used daily by DevOps Engineers:

- `mkdir`
- `touch`
- `cp`
- `mv`
- `rm`
- `rmdir`
- `find`
- `locate`

These commands form the foundation of Linux file management.
---

# 2.6 Creating, Copying, Moving and Deleting Files & Directories

Managing files is one of the most common daily activities performed by a DevOps Engineer.

Whether you are deploying applications, collecting logs, creating backup directories or editing configuration files, you constantly create, copy, move and remove files.

In this section, we will learn the most frequently used Linux file management commands.

---

# mkdir - Create Directory

The `mkdir` command creates a new directory.

### Syntax

```bash
mkdir directory_name
```

### Example

```bash
mkdir DevOps
```

Output

```
DevOps/
```

A new directory named **DevOps** is created.

---

# Create Multiple Directories

```bash
mkdir project logs backup scripts
```

Output

```
project/

logs/

backup/

scripts/
```

All directories are created together.

---

# Create Nested Directories

```bash
mkdir -p Project/app/config
```

Output

```
Project/

└── app

    └── config
```

The `-p` option automatically creates missing parent directories.

---

# touch - Create Empty File

The `touch` command creates an empty file.

### Syntax

```bash
touch filename
```

### Example

```bash
touch notes.txt
```

Output

```
notes.txt
```

---

# Create Multiple Files

```bash
touch app.py config.yml Dockerfile README.md
```

All files are created simultaneously.

---

# cp - Copy Files

The `cp` command copies files.

### Syntax

```bash
cp source destination
```

### Example

```bash
cp notes.txt backup.txt
```

Output

```
notes.txt

backup.txt
```

The original file remains unchanged.

---

# Copy Directory

```bash
cp -r Project Backup
```

The `-r` option copies the entire directory recursively.

---

# mv - Move or Rename

The `mv` command is used to move or rename files.

### Rename Example

```bash
mv notes.txt linux_notes.txt
```

Old Name

```
notes.txt
```

New Name

```
linux_notes.txt
```

---

### Move Example

```bash
mv linux_notes.txt Documents/
```

The file moves into the **Documents** directory.

---

# rm - Remove File

The `rm` command deletes files.

### Example

```bash
rm linux_notes.txt
```

The file is permanently deleted.

⚠️ Linux does not move deleted files to a Recycle Bin.

Deletion is immediate.

---

# Remove Multiple Files

```bash
rm file1.txt file2.txt file3.txt
```

---

# Remove Directory

To remove an empty directory.

```bash
rmdir Test
```

---

# Remove Directory with Contents

```bash
rm -r Project
```

The directory and all files inside it are deleted.

---

# Force Delete

```bash
rm -rf Project
```

Explanation

```
-r

Recursive

-f

Force
```

⚠️ This command is one of the most dangerous Linux commands.

A wrong path can permanently delete important data.

Always verify the path before executing.

---

# find - Search Files

The `find` command searches files.

### Example

```bash
find /home -name notes.txt
```

Output

```
/home/sandeep/Documents/notes.txt
```

---

# Search All Log Files

```bash
find /var/log -name "*.log"
```

Useful during troubleshooting.

---

# locate Command

`locate` searches files much faster than `find`.

Example

```bash
locate nginx.conf
```

Output

```
/etc/nginx/nginx.conf
```

Unlike `find`, `locate` uses a database.

---

# Production Example

Suppose your manager asks:

> Create a backup folder before deployment.

Commands

```bash
mkdir backup

cp app.jar backup/

ls
```

Output

```
backup/

app.jar
```

Deployment can now proceed safely.

---

# Another Production Example

A developer accidentally deletes a configuration file.

You restore it from backup.

```bash
cp backup/application.yml /opt/application/
```

The application configuration is restored within seconds.

---

# Most Frequently Used Commands

| Command | Purpose |
|----------|----------|
| mkdir | Create Directory |
| mkdir -p | Create Nested Directories |
| touch | Create File |
| cp | Copy File |
| cp -r | Copy Directory |
| mv | Move / Rename |
| rm | Delete File |
| rm -r | Delete Directory |
| rm -rf | Force Delete |
| rmdir | Remove Empty Directory |
| find | Search Files |
| locate | Fast File Search |

---

# Interview Questions

### Q1. Which command creates a new directory?

```bash
mkdir
```

---

### Q2. Which command creates an empty file?

```bash
touch
```

---

### Q3. Which command copies an entire directory?

```bash
cp -r
```

---

### Q4. Which command is considered dangerous?

```bash
rm -rf
```

Because it recursively and forcefully deletes files and directories.

---

# Key Takeaways

- `mkdir` creates directories.
- `touch` creates files.
- `cp` copies files and directories.
- `mv` moves or renames files.
- `rm` permanently deletes files.
- `find` and `locate` help search files.
- These commands are used daily in production Linux environments.

---

# Next Section

## 2.7 Viewing and Editing Files

In the next section, we will learn:

- `cat`
- `less`
- `more`
- `head`
- `tail`
- `tail -f`
- `nano`
- `vi`
- `vim`

These commands are among the most frequently used tools for reading logs and editing configuration files in production servers.
---

# 2.7 Viewing and Editing Files

In Linux, applications store configuration files, log files and scripts as plain text.

A DevOps Engineer spends a significant amount of time reading logs, checking configuration files and editing application settings.

This section introduces the most commonly used commands for viewing and editing files.

---

# cat - Display File Contents

The `cat` command displays the complete contents of a file.

### Syntax

```bash
cat filename
```

### Example

```bash
cat server.conf
```

Output

```text
server_name=shopkart
port=8080
environment=production
```

Use `cat` when the file is small.

---

# Display Multiple Files

```bash
cat file1.txt file2.txt
```

Linux displays the contents of both files sequentially.

---

# Number Every Line

```bash
cat -n server.conf
```

Example

```text
1 server_name=shopkart
2 port=8080
3 environment=production
```

Useful while debugging configuration files.

---

# less - Read Large Files

Production log files can contain millions of lines.

Using `cat` is not practical.

Use:

```bash
less logfile.log
```

Navigation

| Key | Action |
|------|--------|
| Space | Next Page |
| b | Previous Page |
| / | Search |
| q | Quit |

---

# more

`more` also displays large files page by page.

```bash
more logfile.log
```

Today, `less` is preferred because it offers better navigation.

---

# head

Displays the beginning of a file.

Example

```bash
head server.log
```

Default output

```
First 10 Lines
```

Specify the number of lines.

```bash
head -20 server.log
```

Displays the first 20 lines.

---

# tail

Displays the end of a file.

Example

```bash
tail server.log
```

Output

```
Last 10 Lines
```

Display more lines.

```bash
tail -50 server.log
```

---

# tail -f

One of the most frequently used DevOps commands.

```bash
tail -f application.log
```

Linux continuously displays newly added log entries.

Example

```
Application Started...

Database Connected...

User Login Success...

Payment Completed...
```

As new log entries are generated,

they appear automatically.

Press

```
Ctrl + C
```

to stop monitoring.

---

# Real Production Example

Suppose your application is not starting.

You immediately monitor the log.

```bash
tail -f /var/log/application.log
```

Output

```text
Database Connection Failed

Application Shutdown
```

Within seconds,

you identify the root cause.

---

# nano Editor

Nano is a beginner-friendly text editor.

Open a file.

```bash
nano application.yml
```

Save

```
Ctrl + O
```

Exit

```
Ctrl + X
```

Nano is easy to learn.

---

# vi Editor

The original Linux editor.

Open a file.

```bash
vi application.yml
```

Modes

```
Command Mode

↓

Insert Mode

↓

Save

↓

Exit
```

Press

```
i
```

to enter Insert Mode.

---

# Save File

Press

```
Esc
```

Then type

```text
:w
```

Press

```
Enter
```

---

# Save and Exit

```
Esc
```

Then

```text
:wq
```

---

# Exit Without Saving

```
Esc
```

Then

```text
:q!
```

---

# vim Editor

Vim is an improved version of vi.

Open

```bash
vim application.yml
```

Advantages

- Syntax Highlighting
- Better Navigation
- Search
- Plugins
- Faster Editing

Most DevOps Engineers prefer Vim.

---

# Search Inside a File

Inside Vim

```
/database
```

Press

```
Enter
```

Linux jumps to the matching word.

---

# Production Example

Suppose Nginx is not starting.

You check its configuration.

```bash
vim /etc/nginx/nginx.conf
```

You correct the configuration.

Save

```text
:wq
```

Restart Nginx.

```bash
systemctl restart nginx
```

Problem solved.

---

# Common Commands Summary

| Command | Purpose |
|----------|----------|
| cat | Display Entire File |
| cat -n | Show Line Numbers |
| less | Read Large Files |
| more | Read File Page by Page |
| head | Show First Lines |
| tail | Show Last Lines |
| tail -f | Live Log Monitoring |
| nano | Beginner Text Editor |
| vi | Standard Linux Editor |
| vim | Advanced Linux Editor |

---

# Interview Questions

### Q1. Which command continuously monitors a log file?

```bash
tail -f
```

---

### Q2. Which editor is beginner-friendly?

```text
nano
```

---

### Q3. Which editor is most commonly used by Linux Administrators and DevOps Engineers?

```text
vim
```

---

### Q4. How do you exit Vim without saving?

```text
:q!
```

---

# Key Takeaways

- `cat` is useful for small files.
- `less` is preferred for large files.
- `tail -f` is one of the most important commands for production troubleshooting.
- `vim` is the industry-standard editor for Linux servers.
- Reading logs is one of the daily responsibilities of every DevOps Engineer.

---

# Next Section

## 2.8 Linux Users and Groups

In the next section, we will learn:

- User Management
- Group Management
- root User
- sudo
- useradd
- usermod
- userdel
- passwd
- groups
- id

These concepts are essential for managing secure production Linux servers.
---

# 2.8 Linux Users and Groups

One of the primary responsibilities of a Linux Administrator or DevOps Engineer is managing users and controlling access to the server.

A production server is never shared using a single account.

Instead, every engineer receives an individual Linux account with specific permissions.

This approach improves:

- Security
- Accountability
- Auditing
- Access Control

---

# Real Production Example

Suppose five engineers work in the DevOps team.

```
Rahul

Sandeep

Priya

Amit

Neha
```

Should everyone log in using the same account?

```
root
```

No.

Every engineer receives an individual user account.

Example:

```
rahul

sandeep

priya

amit

neha
```

This allows the company to track who performed each activity.

---

# Types of Users

Linux generally contains three categories of users.

### Root User

The root user is the super administrator.

Capabilities:

- Install Software
- Delete Files
- Create Users
- Stop Services
- Modify Configuration
- Change Permissions

Username:

```text
root
```

User ID:

```text
0
```

---

### Normal User

A normal user has limited permissions.

Example:

```text
sandeep
```

A normal user cannot perform administrative tasks without permission.

---

### System Users

Linux automatically creates several users for services.

Examples:

```
nginx

mysql

postgres

docker

www-data
```

These users run background services securely.

---

# View Current User

Command

```bash
whoami
```

Example

```bash
$ whoami

sandeep
```

---

# Display User ID

Command

```bash
id
```

Example

```bash
$ id

uid=1000(sandeep)

gid=1000(sandeep)

groups=1000(sandeep),27(sudo)
```

Explanation

| Field | Meaning |
|--------|---------|
| uid | User ID |
| gid | Primary Group ID |
| groups | Groups the user belongs to |

---

# Display Logged-In User

Command

```bash
who
```

Example

```bash
$ who

sandeep pts/0
```

Useful for checking who is currently logged into the server.

---

# Create User

Command

```bash
sudo useradd rahul
```

This creates a new Linux user.

---

# Create User with Home Directory

```bash
sudo useradd -m rahul
```

Linux creates:

```
/home/rahul
```

automatically.

---

# Set Password

Command

```bash
sudo passwd rahul
```

Example

```
New Password

Retype Password

Password Updated Successfully
```

---

# Switch User

Command

```bash
su rahul
```

Linux switches to the **rahul** account.

Return to the previous user.

```bash
exit
```

---

# Delete User

Command

```bash
sudo userdel rahul
```

Delete the user and home directory.

```bash
sudo userdel -r rahul
```

---

# Groups

A group allows multiple users to share the same permissions.

Example

```
Developers

↓

Rahul

Sandeep

Priya
```

Instead of assigning permissions individually,

permissions are assigned to the group.

---

# Create Group

Command

```bash
sudo groupadd developers
```

---

# Add User to Group

Command

```bash
sudo usermod -aG developers rahul
```

Explanation

```
-a

Append

-G

Group
```

---

# Display User Groups

Command

```bash
groups rahul
```

Example

```text
rahul developers docker sudo
```

---

# sudo

The **sudo** command allows a normal user to execute administrative commands.

Example

Without sudo

```bash
apt update
```

Output

```
Permission Denied
```

With sudo

```bash
sudo apt update
```

The command executes successfully.

---

# Why sudo is Preferred

Companies avoid logging in directly as **root**.

Instead,

users log in using personal accounts and execute privileged commands using `sudo`.

Benefits:

- Better Security
- Audit Trail
- Reduced Risk
- User Accountability

---

# Production Example

A developer needs Docker access.

Instead of giving root access,

the DevOps Engineer executes:

```bash
sudo usermod -aG docker rahul
```

The developer can now use Docker without becoming the root user.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| whoami | Current User |
| who | Logged-In Users |
| id | User Information |
| useradd | Create User |
| passwd | Set Password |
| userdel | Delete User |
| groupadd | Create Group |
| usermod | Modify User |
| groups | Display User Groups |
| su | Switch User |
| sudo | Execute Administrative Commands |

---

# Interview Questions

### Q1. Who is the superuser in Linux?

```
root
```

---

### Q2. What is the User ID of root?

```
0
```

---

### Q3. Which command creates a new Linux user?

```bash
useradd
```

---

### Q4. Which command changes a user's password?

```bash
passwd
```

---

### Q5. Why is `sudo` preferred over logging in directly as root?

Because it provides better security, accountability and auditing while reducing the risk of accidental system changes.

---

# Key Takeaways

- Every production engineer should have an individual Linux account.
- The `root` account has unrestricted access.
- Groups simplify permission management.
- `sudo` is the recommended way to perform administrative tasks.
- Proper user management is essential for securing production servers.

---

# Next Section

## 2.9 Linux File Permissions

In the next section, we will learn one of the most important Linux topics for every DevOps Engineer:

- Ownership
- Read, Write and Execute Permissions
- chmod
- chown
- Numeric Permissions
- Symbolic Permissions
- Real Production Permission Scenarios
---

# 2.9 Linux File Permissions

Linux is a multi-user operating system.

Multiple users can access the same server simultaneously.

To protect files from unauthorized access, Linux uses a powerful permission system.

Every DevOps Engineer must understand Linux permissions because incorrect permissions are one of the most common production issues.

---

# Real Production Example

Suppose your company has deployed an application.

```
Application

↓

/opt/shopkart
```

Inside this directory there is an important configuration file.

```
application.yml
```

If every user can modify this file,

anyone can accidentally stop the production application.

Linux permissions prevent this.

---

# File Ownership

Every file in Linux has two owners.

```
Owner (User)

↓

Group
```

Example

```bash
ls -l
```

Output

```text
-rw-r----- 1 root developers 2540 Jun 30 application.yml
```

Explanation

| Field | Meaning |
|---------|---------|
| root | Owner |
| developers | Group |

---

# Three Types of Permissions

Linux permissions are divided into three categories.

```
Owner

↓

Group

↓

Others
```

Each category has three permissions.

```
Read

Write

Execute
```

---

# Permission Structure

Example

```text
-rwxr-xr--
```

Breakdown

```
-

File

------------

rwx

Owner

------------

r-x

Group

------------

r--

Others
```

---

# Read Permission (r)

Read permission allows a user to read a file.

Example

```
notes.txt

↓

Open

↓

Read
```

Numeric Value

```
4
```

---

# Write Permission (w)

Write permission allows modification.

Example

```
application.yml

↓

Edit

↓

Save
```

Numeric Value

```
2
```

---

# Execute Permission (x)

Execute permission allows execution.

Example

```
backup.sh

↓

Run Script
```

Numeric Value

```
1
```

---

# Permission Values

| Permission | Value |
|------------|-------|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

---

# Numeric Permissions

Linux combines these values.

| Number | Permission |
|---------|------------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 3 | -wx |
| 2 | -w- |
| 1 | --x |
| 0 | --- |

---

# Example

```
755

↓

Owner

7

↓

rwx

-------------------

Group

5

↓

r-x

-------------------

Others

5

↓

r-x
```

This is one of the most common permission settings.

---

# Another Example

```
644

↓

Owner

rw-

Group

r--

Others

r--
```

Configuration files usually use this permission.

---

# View Permissions

Command

```bash
ls -l
```

Example

```text
-rwxr-xr-x 1 root root backup.sh
```

---

# chmod Command

`chmod` changes permissions.

Example

```bash
chmod 755 backup.sh
```

Permissions become

```
rwxr-xr-x
```

---

# Another Example

```bash
chmod 644 application.yml
```

Result

```
rw-r--r--
```

---

# Symbolic Mode

Permissions can also be changed symbolically.

Add Execute permission.

```bash
chmod +x backup.sh
```

Remove Write permission.

```bash
chmod -w report.txt
```

Add Read permission.

```bash
chmod +r notes.txt
```

---

# chown Command

Changes file ownership.

Example

```bash
sudo chown sandeep application.yml
```

Owner changes to

```
sandeep
```

---

# Change Owner and Group

```bash
sudo chown sandeep:developers application.yml
```

Owner

```
sandeep
```

Group

```
developers
```

---

# chgrp Command

Changes only the group.

Example

```bash
sudo chgrp developers application.yml
```

---

# Real Production Example

Suppose Nginx cannot read a configuration file.

```
Application Failed
```

Investigation

```bash
ls -l
```

Output

```text
---------- 1 root root nginx.conf
```

No permissions.

Solution

```bash
chmod 644 nginx.conf
```

Restart service.

```bash
systemctl restart nginx
```

Problem solved.

---

# Dangerous Permission

Many beginners execute:

```bash
chmod 777 file.txt
```

Meaning

```
Owner

↓

Read

Write

Execute

----------------

Group

↓

Read

Write

Execute

----------------

Others

↓

Read

Write

Execute
```

Everyone can modify the file.

This creates a serious security risk.

Avoid `777` in production unless absolutely necessary.

---

# Frequently Used Permission Values

| Permission | Usage |
|------------|-------|
| 755 | Executable Programs |
| 750 | Secure Applications |
| 700 | Private Scripts |
| 644 | Configuration Files |
| 600 | Password Files |
| 777 | Testing Only (Avoid in Production) |

---

# Production Best Practices

✔ Never use **777** unless required.

✔ Give users the minimum permissions necessary.

✔ Use groups instead of assigning permissions individually.

✔ Keep configuration files owned by **root** whenever possible.

✔ Regularly audit file permissions.

---

# Interview Questions

### Q1. What does 755 mean?

Owner has Read, Write and Execute permissions.

Group and Others have Read and Execute permissions.

---

### Q2. Which command changes file permissions?

```bash
chmod
```

---

### Q3. Which command changes file ownership?

```bash
chown
```

---

### Q4. Why should `chmod 777` be avoided?

Because every user can read, modify and execute the file, creating a major security risk.

---

# Key Takeaways

- Every Linux file has an Owner and a Group.
- Linux permissions are based on Read, Write and Execute.
- `chmod` changes permissions.
- `chown` changes ownership.
- Correct permissions are critical for production security.
- Misconfigured permissions are one of the most common causes of production issues.

---

# Next Section

## 2.10 Linux Processes

In the next section, we will learn how Linux runs applications internally and how DevOps Engineers monitor, stop and troubleshoot running processes using commands such as:

- `ps`
- `top`
- `htop`
- `kill`
- `killall`
- `nice`
- `renice`
- `jobs`
- `bg`
- `fg`
---

# 2.10 Linux Processes

Whenever you start an application in Linux, the operating system creates a **Process**.

A process is simply a running instance of a program.

Examples:

- Nginx
- Apache
- MySQL
- Docker
- Jenkins
- Kubernetes
- Python Script

All of these run as Linux processes.

Understanding processes is one of the most important skills for every DevOps Engineer because production issues often involve stuck, crashed or high CPU processes.

---

# What is a Process?

Suppose you execute:

```bash
python app.py
```

Linux creates a process.

```
Python Program

↓

Linux Process

↓

PID 2451
```

Every process receives a unique **PID (Process ID).**

---

# Process Life Cycle

```
Program

↓

Start

↓

Running

↓

Waiting

↓

Completed

↓

Terminated
```

Every process follows this life cycle.

---

# View Running Processes

Command

```bash
ps
```

Example

```bash
$ ps

PID TTY TIME CMD

1050 pts/0 00:00 bash

2080 pts/0 00:00 ps
```

---

# View All Processes

```bash
ps -ef
```

Example

```text
UID PID PPID CMD

root 1 systemd

root 820 sshd

mysql 1042 mysqld

nginx 2045 nginx

jenkins 3045 java
```

This command is heavily used in production.

---

# Process Tree

```bash
pstree
```

Example

```text
systemd

├── sshd

├── nginx

├── docker

├── mysqld

└── java
```

This shows the parent-child relationship.

---

# top Command

One of the most important Linux monitoring commands.

```bash
top
```

Displays:

- CPU Usage
- Memory Usage
- Running Processes
- Load Average
- Uptime

Example

```text
PID USER CPU MEM COMMAND

3021 root 35 nginx

4205 mysql 22 mysqld

5502 root 15 java
```

Refreshes automatically.

Press

```
q
```

to quit.

---

# htop

Improved version of `top`.

```bash
htop
```

Advantages:

- Colorful Interface
- Easier Navigation
- Search
- Kill Process
- Sort Processes

Many DevOps Engineers prefer `htop`.

---

# Find Process

Suppose you want to check whether Nginx is running.

```bash
ps -ef | grep nginx
```

Example

```text
root 2045 nginx
```

This confirms that Nginx is running.

---

# Kill Process

Sometimes an application hangs.

Terminate it using:

```bash
kill PID
```

Example

```bash
kill 3021
```

---

# Force Kill

```bash
kill -9 3021
```

Signal 9 immediately terminates the process.

⚠️ Use only when a normal kill does not work.

---

# Kill by Name

Instead of PID.

```bash
killall nginx
```

Linux stops every nginx process.

---

# Background Process

Suppose you execute

```bash
python app.py
```

The terminal becomes occupied.

Run it in the background.

```bash
python app.py &
```

Linux immediately returns the prompt.

---

# View Background Jobs

```bash
jobs
```

Example

```text
[1]+ Running python app.py &
```

---

# Bring Background Job to Foreground

```bash
fg
```

---

# Send Process to Background

```
Ctrl + Z
```

Then

```bash
bg
```

---

# nice Command

Adjusts process priority.

Example

```bash
nice -n 10 python backup.py
```

Lower priority.

---

# renice

Changes priority of an already running process.

```bash
renice 5 3021
```

---

# Production Example 1

Developer reports:

```
Application is slow.
```

DevOps Engineer checks:

```bash
top
```

Output

```text
java

CPU 98%
```

Root cause identified.

Java process is consuming excessive CPU.

---

# Production Example 2

Nginx refuses to restart.

Check process.

```bash
ps -ef | grep nginx
```

Kill old process.

```bash
kill -9 PID
```

Restart service.

```bash
systemctl restart nginx
```

Problem resolved.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| ps | Current Processes |
| ps -ef | All Processes |
| pstree | Process Tree |
| top | Real-Time Monitoring |
| htop | Advanced Monitoring |
| grep | Search Process |
| kill | Stop Process |
| kill -9 | Force Kill |
| killall | Kill by Name |
| jobs | Background Jobs |
| bg | Run in Background |
| fg | Bring to Foreground |
| nice | Start with Priority |
| renice | Change Priority |

---

# Interview Questions

### Q1. What is a Process?

A process is a running instance of a program.

---

### Q2. What is PID?

PID stands for Process ID, a unique number assigned to every running process.

---

### Q3. Which command displays running processes?

```bash
ps
```

---

### Q4. Which command shows real-time CPU and Memory usage?

```bash
top
```

or

```bash
htop
```

---

### Q5. What is the difference between `kill` and `kill -9`?

- `kill` sends a normal termination signal.
- `kill -9` forcefully terminates the process immediately.

---

# Key Takeaways

- Every running application is a Linux process.
- Every process has a unique PID.
- `ps`, `top` and `htop` are essential monitoring tools.
- `kill` and `kill -9` terminate processes.
- Process management is one of the most common production troubleshooting tasks.

---

# Next Section

## 2.11 Linux Services (systemd & systemctl)

In the next section, we will learn how Linux manages long-running services such as:

- Nginx
- Apache
- Docker
- Jenkins
- MySQL
- SSH

using the `systemctl` command. We will also cover enabling services at boot, checking service status, restarting failed services, and troubleshooting production service failures.
---

# 2.11 Linux Services (systemd & systemctl)

Most applications running on Linux are not started manually every time the server boots.

Instead, Linux uses **Services**.

Examples:

- Nginx
- Apache
- MySQL
- Docker
- Jenkins
- SSH
- Kubernetes
- Prometheus
- Grafana

These applications run continuously in the background and automatically start when the server boots.

---

# What is a Service?

A Service is a background program that starts automatically and waits for requests.

Example:

```
Linux Server

↓

SSH Service

↓

Waiting for SSH Login

-------------------

Nginx Service

↓

Waiting for HTTP Requests

-------------------

MySQL Service

↓

Waiting for Database Requests
```

Without services, servers would require manual startup after every reboot.

---

# What is systemd?

Modern Linux distributions use **systemd** as the system and service manager.

Responsibilities of systemd:

- Boot Linux
- Start Services
- Stop Services
- Restart Services
- Monitor Services
- Manage Logs
- Handle Dependencies

When Linux boots, **systemd** is usually the first process started.

Example

```bash
ps -p 1
```

Output

```text
PID TTY TIME CMD

1 ? 00:00:04 systemd
```

PID **1** is almost always systemd.

---

# systemctl Command

The primary command used to manage services is:

```bash
systemctl
```

Every DevOps Engineer uses this command daily.

---

# Check Service Status

Example

```bash
systemctl status nginx
```

Output

```text
Active: active (running)
```

If the service is running, Linux displays **active (running)**.

---

# Start a Service

Example

```bash
sudo systemctl start nginx
```

Linux starts the Nginx service immediately.

---

# Stop a Service

```bash
sudo systemctl stop nginx
```

The service stops.

No new requests will be accepted.

---

# Restart a Service

One of the most frequently used commands.

```bash
sudo systemctl restart nginx
```

Linux performs:

```
Stop

↓

Start
```

This is commonly used after changing configuration files.

---

# Reload a Service

Some applications support reloading configuration without restarting.

Example

```bash
sudo systemctl reload nginx
```

Benefits:

- No downtime
- Existing connections remain active

---

# Enable Service at Boot

To start a service automatically whenever Linux boots:

```bash
sudo systemctl enable nginx
```

Example

```
Server Reboot

↓

Nginx Starts Automatically
```

---

# Disable Auto Start

```bash
sudo systemctl disable nginx
```

Now Linux will not start Nginx automatically after reboot.

---

# Check Whether Service is Enabled

```bash
systemctl is-enabled nginx
```

Possible outputs:

```
enabled
```

or

```
disabled
```

---

# View All Running Services

```bash
systemctl list-units --type=service
```

Linux displays every active service.

---

# Failed Services

To view failed services:

```bash
systemctl --failed
```

Example

```text
mysql.service

failed

docker.service

failed
```

This is extremely useful during troubleshooting.

---

# Service Log

Suppose Jenkins fails to start.

First check the status.

```bash
systemctl status jenkins
```

If necessary,

view detailed logs.

```bash
journalctl -u jenkins
```

The logs usually reveal the exact problem.

---

# Common Production Workflow

Developer reports:

```
Website is Down
```

DevOps Engineer checks:

```bash
systemctl status nginx
```

Output

```
inactive
```

Restart

```bash
sudo systemctl restart nginx
```

Verify

```bash
systemctl status nginx
```

Output

```
active (running)
```

Website becomes available again.

---

# Another Production Example

Docker service stopped unexpectedly.

Check

```bash
systemctl status docker
```

Restart

```bash
sudo systemctl restart docker
```

Verify

```bash
docker ps
```

Containers start working again.

---

# Frequently Used systemctl Commands

| Command | Purpose |
|----------|----------|
| systemctl status service | Service Status |
| systemctl start service | Start Service |
| systemctl stop service | Stop Service |
| systemctl restart service | Restart Service |
| systemctl reload service | Reload Configuration |
| systemctl enable service | Enable at Boot |
| systemctl disable service | Disable at Boot |
| systemctl is-enabled service | Check Auto Start |
| systemctl --failed | Failed Services |
| systemctl list-units --type=service | Running Services |

---

# Real Services Used by DevOps Engineers

| Service | Purpose |
|----------|----------|
| sshd | SSH Login |
| nginx | Web Server |
| httpd | Apache Web Server |
| docker | Container Engine |
| kubelet | Kubernetes Worker |
| mysql | Database |
| postgresql | Database |
| jenkins | CI/CD |
| prometheus | Monitoring |
| grafana-server | Dashboard |

---

# Interview Questions

### Q1. What is systemd?

systemd is the default system and service manager used by modern Linux distributions.

---

### Q2. Which command checks the status of a service?

```bash
systemctl status service_name
```

Example

```bash
systemctl status nginx
```

---

### Q3. Which command starts a service?

```bash
systemctl start service_name
```

---

### Q4. Which command enables a service after reboot?

```bash
systemctl enable service_name
```

---

### Q5. Which command shows failed services?

```bash
systemctl --failed
```

---

# Production Best Practices

✔ Always verify service status before restarting.

✔ Check logs using `journalctl` before troubleshooting.

✔ Restart only after identifying the root cause.

✔ Enable critical production services to start automatically after reboot.

✔ Avoid unnecessary restarts during business hours.

---

# Key Takeaways

- Services run continuously in the background.
- systemd manages the Linux boot process and services.
- `systemctl` is one of the most important commands for DevOps Engineers.
- Service failures are among the most common production incidents.
- Understanding service management is essential for maintaining production systems.

---

# Next Section

## 2.12 Package Management (APT, DNF, YUM)

In the next section, we will learn how software is installed, updated and removed in Linux using package managers such as:

- apt
- apt-get
- dpkg
- yum
- dnf
- rpm

We will also learn how companies maintain secure and updated production servers.
---

# 2.12 Linux Package Management (APT, DNF, YUM & RPM)

A Linux server is useful only when the required software is installed.

For example:

- Docker
- Git
- Jenkins
- Java
- Python
- Nginx
- Apache
- MySQL

Instead of downloading software manually from websites, Linux uses **Package Managers**.

A Package Manager downloads, installs, updates and removes software automatically.

This is one of the most important skills for every DevOps Engineer.

---

# What is a Package?

A Package is a compressed software bundle.

It usually contains:

- Application Files
- Libraries
- Configuration Files
- Documentation
- Dependencies

Example

```
Docker Package

↓

Docker Engine

Configuration

Libraries

Documentation
```

---

# Why Package Managers?

Imagine installing Docker manually.

You would have to:

- Download Files
- Extract Files
- Install Dependencies
- Configure Paths
- Verify Installation

Instead,

one command does everything.

Example

```bash
sudo apt install docker.io
```

---

# Package Managers by Distribution

| Distribution | Package Manager |
|--------------|----------------|
| Ubuntu | apt |
| Debian | apt |
| Rocky Linux | dnf |
| RHEL | dnf / yum |
| CentOS | yum |
| Fedora | dnf |
| SUSE | zypper |

Although commands differ slightly,

the concept remains the same.

---

# APT (Advanced Package Tool)

Ubuntu and Debian use **APT**.

---

## Update Package Information

```bash
sudo apt update
```

This command **does not update software.**

It downloads the latest package information.

Example

```
Internet

↓

Ubuntu Repository

↓

Latest Package List

↓

Local Cache
```

---

## Upgrade Installed Packages

```bash
sudo apt upgrade
```

Linux upgrades all installed packages.

---

## Install Software

Example

```bash
sudo apt install nginx
```

APT automatically:

- Downloads Nginx
- Downloads Dependencies
- Installs Software
- Configures Packages

---

## Install Multiple Packages

```bash
sudo apt install git docker.io curl wget
```

---

## Remove Package

```bash
sudo apt remove nginx
```

Application is removed.

Configuration files remain.

---

## Remove Completely

```bash
sudo apt purge nginx
```

Everything is removed including configuration.

---

## Remove Unused Packages

```bash
sudo apt autoremove
```

Linux removes unnecessary dependencies.

---

## Search Package

```bash
apt search docker
```

---

## Display Package Information

```bash
apt show nginx
```

Example Output

```
Version

Description

Dependencies

Repository
```

---

# DNF Package Manager

Modern Red Hat based distributions use **DNF**.

Install package

```bash
sudo dnf install nginx
```

Update package

```bash
sudo dnf update
```

Remove package

```bash
sudo dnf remove nginx
```

Search package

```bash
dnf search docker
```

---

# YUM Package Manager

Older CentOS and RHEL versions use YUM.

Install

```bash
sudo yum install nginx
```

Update

```bash
sudo yum update
```

Remove

```bash
sudo yum remove nginx
```

Although DNF replaced YUM,

many companies still use YUM on older servers.

---

# RPM Package

RPM stands for

```
Red Hat Package Manager
```

Suppose a company provides software as

```
application.rpm
```

Install

```bash
sudo rpm -ivh application.rpm
```

Explanation

```
-i

Install

-v

Verbose

-h

Progress Bar
```

---

# View Installed Packages

Ubuntu

```bash
dpkg -l
```

Rocky Linux

```bash
rpm -qa
```

These commands list installed software.

---

# Check Package Version

Ubuntu

```bash
apt list --installed nginx
```

RHEL

```bash
rpm -q nginx
```

---

# Production Example

Suppose the developer requests Docker installation.

Ubuntu

```bash
sudo apt update

sudo apt install docker.io
```

Verify

```bash
docker --version
```

Output

```
Docker version 29.x.x
```

Docker is ready.

---

# Another Production Example

The Security Team announces:

```
Critical OpenSSL Vulnerability
```

The DevOps Engineer updates the server.

Ubuntu

```bash
sudo apt update

sudo apt upgrade
```

Latest security patches are installed.

---

# Package Installation Flow

```
User

↓

apt install nginx

↓

Ubuntu Repository

↓

Download Package

↓

Download Dependencies

↓

Install

↓

Configure

↓

Ready
```

Everything happens automatically.

---

# Frequently Used Commands

| Ubuntu | Purpose |
|---------|----------|
| apt update | Update Repository Information |
| apt upgrade | Upgrade Installed Packages |
| apt install | Install Package |
| apt remove | Remove Package |
| apt purge | Remove Completely |
| apt autoremove | Remove Unused Packages |
| apt search | Search Package |
| apt show | Package Information |

---

| RHEL / Rocky | Purpose |
|--------------|----------|
| dnf install | Install Package |
| dnf update | Update Packages |
| dnf remove | Remove Package |
| dnf search | Search Package |
| rpm -qa | List Installed Packages |

---

# Production Best Practices

✔ Always run `apt update` before installing software.

✔ Update production servers during maintenance windows.

✔ Remove unused packages regularly.

✔ Verify package versions before deployment.

✔ Avoid installing software from untrusted repositories.

---

# Interview Questions

### Q1. What is a Package Manager?

A Package Manager is software used to install, update, remove and manage applications automatically.

---

### Q2. Which package manager does Ubuntu use?

```
APT
```

---

### Q3. Which package manager does Rocky Linux use?

```
DNF
```

---

### Q4. What is the difference between `apt update` and `apt upgrade`?

- `apt update` downloads the latest package information.
- `apt upgrade` installs newer versions of installed packages.

---

### Q5. Why should production servers be updated regularly?

To receive security patches, bug fixes, performance improvements and software updates.

---

# Key Takeaways

- Package Managers simplify software installation.
- Ubuntu uses APT.
- RHEL and Rocky Linux use DNF.
- Older CentOS servers use YUM.
- RPM packages are common in Red Hat-based systems.
- Keeping packages updated is essential for production security.

---

# Next Section

## 2.13 Linux Networking

In the next section, we will learn the networking commands that every DevOps Engineer uses daily:

- ip
- ifconfig
- ping
- traceroute
- netstat
- ss
- nslookup
- dig
- curl
- wget
- ssh
- scp

We will troubleshoot real production network issues using these commands.
---

# 2.13 Linux Networking

A DevOps Engineer cannot manage production servers without understanding Linux Networking.

Almost every production issue involves networking in some form.

Examples:

- Website not opening
- SSH connection failed
- Database unreachable
- Kubernetes Pods cannot communicate
- Jenkins cannot access GitHub
- Docker cannot pull images

To troubleshoot these issues, every DevOps Engineer must know Linux networking commands.

---

# What is Networking?

Networking is the communication between two or more devices.

Example

```
Laptop

↓

Switch

↓

Router

↓

Internet

↓

AWS Server

↓

Application
```

Without networking,

applications cannot communicate.

---

# Real Production Example

Suppose a developer says:

> "The application cannot connect to the database."

Possible reasons:

- Wrong IP Address
- Firewall Blocking
- DNS Failure
- Port Closed
- Network Cable Issue
- Database Service Down

The DevOps Engineer uses Linux networking commands to identify the problem.

---

# Display Network Interfaces

Modern Linux distributions use:

```bash
ip addr
```

Example

```text
2: ens33

inet 192.168.1.50/24
```

This command displays:

- IP Address
- MAC Address
- Network Interface
- Status

---

# Older Command

```bash
ifconfig
```

Although still available,

`ip` is now recommended.

---

# Display Routing Table

```bash
ip route
```

Example

```text
default via 192.168.1.1
```

This shows where Linux sends network traffic.

---

# Check Connectivity

One of the first troubleshooting commands.

```bash
ping google.com
```

Output

```text
64 bytes from...

time=18ms
```

Successful replies indicate network connectivity.

Stop ping

```
Ctrl + C
```

---

# Ping Specific Number

```bash
ping -c 4 google.com
```

Linux sends only four packets.

---

# Trace Network Path

```bash
traceroute google.com
```

Displays every router between your server and the destination.

Useful when diagnosing latency.

---

# Check DNS

```bash
nslookup google.com
```

Output

```text
Address:

142.x.x.x
```

Verifies DNS resolution.

---

# Advanced DNS Query

```bash
dig google.com
```

Shows:

- IP Address
- DNS Server
- TTL
- Query Time

`dig` is preferred by many Linux administrators.

---

# Display Listening Ports

Older command

```bash
netstat -tulnp
```

Shows:

- TCP Ports
- UDP Ports
- Listening Services
- Process IDs

---

# Modern Alternative

```bash
ss -tulnp
```

Much faster than `netstat`.

Frequently used in production.

---

# Check Open Port

Suppose Jenkins should listen on port **8080**.

Run

```bash
ss -tulnp | grep 8080
```

Output

```text
LISTEN
```

If nothing appears,

Jenkins may not be running.

---

# Download Web Page

```bash
curl https://google.com
```

Downloads webpage content.

---

# Display HTTP Headers

```bash
curl -I https://google.com
```

Useful during troubleshooting.

Example

```text
HTTP/1.1 200 OK
```

---

# Download File

```bash
wget https://example.com/file.zip
```

Linux downloads the file.

Useful for:

- Software Installation
- Backup Files
- Scripts

---

# SSH

The most important Linux networking command.

Connect to another Linux server.

```bash
ssh user@192.168.1.100
```

Example

```bash
ssh ubuntu@10.0.0.20
```

The DevOps Engineer logs into the remote server securely.

---

# Copy File Between Servers

```bash
scp backup.sql user@192.168.1.100:/backup
```

Copies files securely using SSH.

---

# Production Example 1

Developer reports:

```
Website Not Opening
```

Troubleshooting

```bash
ping website.com

↓

curl -I website.com

↓

ss -tulnp

↓

systemctl status nginx
```

Problem identified quickly.

---

# Production Example 2

Database Connection Failed.

Check

```bash
ping database-server

↓

telnet database-server 3306

↓

ss -tulnp

↓

systemctl status mysql
```

Root cause determined.

---

# Frequently Used Networking Commands

| Command | Purpose |
|----------|----------|
| ip addr | Display IP Address |
| ip route | Routing Table |
| ifconfig | Old Network Command |
| ping | Connectivity Test |
| traceroute | Path Analysis |
| nslookup | DNS Lookup |
| dig | Advanced DNS Lookup |
| netstat | Network Statistics |
| ss | Modern Network Statistics |
| curl | Test HTTP/HTTPS |
| wget | Download Files |
| ssh | Remote Login |
| scp | Secure File Copy |

---

# Interview Questions

### Q1. Which command displays the IP address?

```bash
ip addr
```

---

### Q2. Which command tests network connectivity?

```bash
ping
```

---

### Q3. Which command checks DNS resolution?

```bash
nslookup
```

or

```bash
dig
```

---

### Q4. Which command securely connects to another Linux server?

```bash
ssh
```

---

### Q5. Which command is replacing `netstat`?

```bash
ss
```

---

# Production Best Practices

✔ Always verify network connectivity before troubleshooting applications.

✔ Use `ss` instead of `netstat` on modern Linux systems.

✔ Verify DNS before assuming application issues.

✔ Never expose SSH directly to the public Internet without proper security controls.

✔ Use SSH keys instead of passwords whenever possible.

---

# Key Takeaways

- Networking knowledge is essential for DevOps Engineers.
- `ip`, `ping`, `curl` and `ssh` are used daily.
- `ss` is the modern replacement for `netstat`.
- DNS troubleshooting begins with `nslookup` or `dig`.
- Most production issues can be diagnosed using a small set of networking commands.

---

# Next Section

## 2.14 SSH (Secure Shell) – Remote Server Administration

In the next section, we will learn SSH in depth, including:

- Password Authentication
- SSH Key Authentication
- `ssh-keygen`
- `authorized_keys`
- `known_hosts`
- SSH Configuration
- Port Forwarding
- Best Security Practices
- Real Production Examples

SSH is one of the most frequently used technologies by every DevOps Engineer.
---

# 2.14 SSH (Secure Shell)

Imagine your company has 500 Linux servers running across AWS.

Question:

How will you manage all of them?

Will you physically visit every server?

Obviously not.

Instead, Linux administrators and DevOps Engineers connect remotely using **SSH (Secure Shell).**

SSH is one of the most frequently used technologies in DevOps.

Most DevOps Engineers use SSH hundreds of times every day.

---

# What is SSH?

SSH stands for

**Secure Shell**

It is a secure protocol used to connect to another Linux server over a network.

Example

```
Your Laptop

↓

Internet

↓

AWS EC2 Server

↓

SSH

↓

Linux Terminal
```

After authentication,

you get complete command-line access to the remote server.

---

# Why SSH?

Suppose your production server is located in

```
Mumbai Data Center
```

You are currently sitting in

```
Delhi Office
```

SSH allows you to manage the Mumbai server from Delhi within seconds.

No physical access is required.

---

# Default SSH Port

SSH listens on

```
TCP Port 22
```

Verify

```bash
ss -tulnp | grep 22
```

Example

```text
LISTEN

0.0.0.0:22
```

---

# Basic SSH Connection

Syntax

```bash
ssh username@server_ip
```

Example

```bash
ssh ubuntu@192.168.1.100
```

Linux requests the password.

```
Password:

********
```

After successful authentication,

you are logged into the remote server.

---

# SSH Using Hostname

Instead of IP Address

```bash
ssh ubuntu@app.shopkart.com
```

DNS resolves the hostname automatically.

---

# First Connection

During the first login,

Linux displays

```text
The authenticity of host cannot be established.

Are you sure you want to continue connecting?
```

Type

```
yes
```

Linux stores the server fingerprint.

---

# known_hosts

Linux stores trusted server fingerprints inside

```
~/.ssh/known_hosts
```

Example

```
Laptop

↓

known_hosts

↓

Server Fingerprints
```

This helps prevent Man-in-the-Middle attacks.

---

# SSH Password Authentication

Traditional authentication

```
Laptop

↓

Username

↓

Password

↓

Server
```

Simple,

but not recommended for production.

---

# SSH Key Authentication

Production companies rarely use passwords.

Instead they use

**SSH Keys.**

Authentication becomes

```
Private Key

↓

Public Key

↓

Authentication
```

No password is required.

---

# Generate SSH Key

```bash
ssh-keygen
```

Example

```text
Generating public/private rsa key pair.
```

Linux creates

```
~/.ssh/id_rsa

Private Key

------------------

~/.ssh/id_rsa.pub

Public Key
```

---

# Important Rule

```
Private Key

Never Share
```

```
Public Key

Can Be Shared
```

---

# Copy Public Key

Command

```bash
ssh-copy-id ubuntu@192.168.1.100
```

Linux automatically copies the public key.

After that,

password authentication is no longer required.

---

# Manual Method

Copy

```
id_rsa.pub
```

Paste into

```
~/.ssh/authorized_keys
```

on the remote server.

---

# authorized_keys

Location

```
~/.ssh/authorized_keys
```

Contains all trusted public keys.

Example

```
Laptop A

↓

Public Key

↓

authorized_keys

↓

Server Access Granted
```

---

# SSH Configuration File

Client configuration

```
~/.ssh/config
```

Example

```text
Host production

HostName 10.0.0.15

User ubuntu

IdentityFile ~/.ssh/id_rsa
```

Now connect simply using

```bash
ssh production
```

---

# Copy Files Using SCP

Upload

```bash
scp backup.sql ubuntu@10.0.0.15:/backup
```

Download

```bash
scp ubuntu@10.0.0.15:/backup/backup.sql .
```

---

# Secure File Transfer

Large directories

```bash
scp -r project ubuntu@10.0.0.15:/opt
```

Recursive copy.

---

# Execute Remote Command

Instead of logging in

```bash
ssh ubuntu@10.0.0.15 uptime
```

Output

```text
10:45:31 up 45 days
```

Useful in automation.

---

# Check SSH Service

Ubuntu

```bash
systemctl status ssh
```

RHEL

```bash
systemctl status sshd
```

---

# Restart SSH

Ubuntu

```bash
sudo systemctl restart ssh
```

RHEL

```bash
sudo systemctl restart sshd
```

---

# Production Example 1

Developer reports

```
Cannot Login
```

DevOps Engineer checks

```bash
systemctl status ssh

↓

ss -tulnp | grep 22

↓

journalctl -u ssh
```

Root cause identified.

---

# Production Example 2

Company launches

```
100 EC2 Instances
```

DevOps Engineer generates one SSH key.

The public key is copied to every server.

Now one engineer can securely manage all servers without remembering passwords.

---

# SSH Best Practices

✔ Disable direct root login.

✔ Use SSH Keys.

✔ Disable password authentication whenever possible.

✔ Change default SSH port if company policy requires.

✔ Allow only required users.

✔ Restrict SSH using Security Groups and Firewalls.

✔ Rotate SSH keys periodically.

✔ Never share private keys.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| ssh | Remote Login |
| ssh-keygen | Generate SSH Keys |
| ssh-copy-id | Copy Public Key |
| scp | Secure File Copy |
| ssh hostname command | Remote Command Execution |
| systemctl status ssh | Check SSH Service |
| systemctl restart ssh | Restart SSH |

---

# Interview Questions

### Q1. What is SSH?

SSH (Secure Shell) is a secure protocol used for remote administration of Linux systems.

---

### Q2. What is the default SSH port?

```
22
```

---

### Q3. Which file stores trusted public keys?

```
~/.ssh/authorized_keys
```

---

### Q4. Which file stores trusted server fingerprints?

```
~/.ssh/known_hosts
```

---

### Q5. Which key should never be shared?

```
Private Key
```

---

# Key Takeaways

- SSH is the standard method for remote Linux administration.
- Production environments use SSH Keys instead of passwords.
- `authorized_keys` controls who can log in.
- `known_hosts` stores trusted servers.
- SSH security is one of the most important responsibilities of a DevOps Engineer.

---

# Next Section

## 2.15 Linux Logs & Troubleshooting

In the next section, we will learn how production engineers investigate failures using:

- `/var/log`
- `journalctl`
- `dmesg`
- `tail -f`
- `grep`
- `awk`
- `sed`
- `less`

You will learn exactly how experienced DevOps Engineers find the root cause of production issues within minutes.
---

# 2.15 Linux Logs & Troubleshooting

One of the primary responsibilities of a DevOps Engineer is troubleshooting production issues.

When an application fails, Linux records useful information inside log files.

Experienced engineers rarely guess the problem.

Instead, they analyze logs and identify the exact root cause.

Learning log analysis is one of the most valuable Linux skills.

---

# What are Logs?

Logs are records generated by the operating system and applications.

They contain information such as:

- Startup Events
- Shutdown Events
- Errors
- Warnings
- User Login
- Application Requests
- Security Events

Logs help engineers understand **what happened, when it happened and why it happened.**

---

# Real Production Example

Suppose customers report:

```
Payment Failed
```

The DevOps Engineer immediately checks:

```
Application Logs

↓

Database Logs

↓

System Logs

↓

Network Logs
```

Within a few minutes,

the engineer identifies the issue.

---

# Linux Log Directory

Most Linux log files are stored inside

```text
/var/log
```

Display files

```bash
cd /var/log

ls
```

Typical output

```text
messages

syslog

auth.log

kern.log

boot.log

nginx

apache2

journal
```

---

# Common Log Files

| File | Purpose |
|------|----------|
| /var/log/syslog | General System Logs |
| /var/log/messages | System Messages |
| /var/log/auth.log | Login Attempts |
| /var/log/boot.log | Boot Information |
| /var/log/dmesg | Kernel Messages |
| /var/log/nginx | Nginx Logs |
| /var/log/apache2 | Apache Logs |

---

# View Log File

Example

```bash
cat /var/log/syslog
```

Small files can be viewed using `cat`.

Large files should be viewed using

```bash
less /var/log/syslog
```

---

# Live Monitoring

One of the most useful production commands.

```bash
tail -f /var/log/syslog
```

Output

```text
Application Started

Database Connected

New User Login

Payment Success
```

As new events occur,

Linux displays them immediately.

---

# journalctl

Modern Linux distributions using **systemd** store logs in the system journal.

View all logs.

```bash
journalctl
```

---

# View Service Logs

Example

```bash
journalctl -u nginx
```

Displays logs only for Nginx.

Another example

```bash
journalctl -u docker
```

---

# View Recent Logs

```bash
journalctl -n 50
```

Displays the latest 50 log entries.

---

# Follow Logs

Similar to

```bash
tail -f
```

Use

```bash
journalctl -f
```

Logs are displayed in real time.

---

# Kernel Logs

Display kernel messages.

```bash
dmesg
```

Useful for troubleshooting:

- Hardware Detection
- USB Devices
- Disk Errors
- Memory Errors
- Boot Issues

---

# Search Logs

Use `grep`.

Example

```bash
grep ERROR application.log
```

Output

```text
Database Connection Error
```

---

# Ignore Case

```bash
grep -i error application.log
```

Matches

```
ERROR

error

Error
```

---

# Count Matching Lines

```bash
grep -c ERROR application.log
```

Example

```
15
```

There are fifteen matching lines.

---

# Search Multiple Files

```bash
grep -r "database" /var/log
```

Linux searches recursively.

---

# awk Command

`awk` extracts columns from files.

Example

```bash
awk '{print $1,$2}' access.log
```

Useful for:

- Reports
- Log Analysis
- Data Extraction

---

# sed Command

Used for searching and replacing text.

Example

```bash
sed 's/ERROR/WARNING/g' application.log
```

Every occurrence of

```
ERROR
```

becomes

```
WARNING
```

---

# Real Production Example 1

Developer reports:

```
Website Returning 500 Error
```

Troubleshooting

```bash
systemctl status nginx

↓

journalctl -u nginx

↓

tail -f /var/log/nginx/error.log
```

Output

```text
Permission Denied
```

Root cause identified.

---

# Real Production Example 2

Server fails to boot.

Commands

```bash
journalctl -b

↓

dmesg

↓

less /var/log/boot.log
```

Problem

```
Filesystem Corrupted
```

Corrective action begins.

---

# Real Production Example 3

Users cannot log in.

Check

```bash
cat /var/log/auth.log
```

Output

```text
Failed Password

User Locked
```

The engineer immediately identifies authentication failures.

---

# Log Rotation

Production logs grow rapidly.

Suppose Nginx generates

```
5 GB Logs

Every Day
```

Without cleanup,

the disk becomes full.

Linux automatically rotates logs using

```
logrotate
```

Old logs become

```
application.log.1

application.log.2.gz

application.log.3.gz
```

This prevents storage issues.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| cat | Display Log |
| less | Read Large Log |
| tail -f | Live Monitoring |
| journalctl | System Logs |
| journalctl -u | Service Logs |
| journalctl -f | Live Journal |
| journalctl -n | Recent Logs |
| dmesg | Kernel Logs |
| grep | Search Text |
| awk | Extract Columns |
| sed | Replace Text |

---

# Production Troubleshooting Flow

```
Problem Reported

↓

Check Service Status

↓

Check Logs

↓

Identify Error

↓

Fix Root Cause

↓

Restart Service

↓

Verify

↓

Close Incident
```

---

# Interview Questions

### Q1. Where are Linux logs stored?

Most logs are stored inside

```text
/var/log
```

---

### Q2. Which command displays systemd logs?

```bash
journalctl
```

---

### Q3. Which command continuously monitors a log file?

```bash
tail -f
```

or

```bash
journalctl -f
```

---

### Q4. Which command searches text inside a log file?

```bash
grep
```

---

### Q5. Which command displays kernel logs?

```bash
dmesg
```

---

# Production Best Practices

✔ Always identify the root cause before restarting services.

✔ Never delete log files without verifying retention policies.

✔ Monitor log growth to avoid disk space issues.

✔ Archive important logs for audits.

✔ Use centralized logging solutions such as ELK or Loki in production.

---

# Key Takeaways

- Logs are the primary source of troubleshooting information.
- `/var/log` contains most Linux log files.
- `journalctl` is essential for modern Linux systems.
- `tail -f` is one of the most frequently used production commands.
- Reading logs efficiently is a core skill for every DevOps Engineer.

---

# Next Section

## 2.16 Linux Disk Management & Storage

In the next section, we will learn how Linux manages storage using:

- `df`
- `du`
- `lsblk`
- `fdisk`
- `mount`
- `umount`
- `blkid`
- `mkfs`
- LVM (Logical Volume Manager)

We will also troubleshoot **"Disk Full"**, **"No Space Left on Device"**, and storage-related production issues.
---

# 2.16 Linux Disk Management & Storage

One of the most common production issues faced by DevOps Engineers is:

> **"No Space Left on Device."**

A full disk can stop:

- Jenkins Builds
- Docker Containers
- Kubernetes Pods
- MySQL Database
- Nginx Logs
- Linux Boot Process

Therefore, every DevOps Engineer must understand Linux storage management.

---

# Understanding Linux Storage

Every Linux server stores data on storage devices.

Examples:

- SSD
- HDD
- NVMe
- SAN Storage
- NAS Storage
- Cloud Storage (AWS EBS)

Linux identifies storage devices as block devices.

Example

```
/dev/sda

/dev/sdb

/dev/nvme0n1
```

---

# Storage Architecture

```
Physical Disk

↓

Partition

↓

Filesystem

↓

Mount Point

↓

Application
```

Every file written by an application follows this path.

---

# Display Disk Usage

The most common command is

```bash
df -h
```

Example

```text
Filesystem      Size Used Avail Use%

/dev/sda1       100G 65G 35G 65%
```

Explanation

| Column | Meaning |
|---------|---------|
| Size | Total Disk Size |
| Used | Used Space |
| Avail | Free Space |
| Use% | Percentage Used |
| Mounted On | Mount Point |

The `-h` option displays sizes in KB, MB and GB.

---

# Display Directory Size

```bash
du -sh /var/log
```

Example

```text
4.5G /var/log
```

Useful for identifying large directories.

---

# Display Subdirectory Sizes

```bash
du -sh *
```

Example

```text
2G docker

800M nginx

5G backup

10M scripts
```

---

# Find Large Files

```bash
find / -type f -size +500M
```

This displays files larger than **500 MB**.

Useful when cleaning disks.

---

# Display Block Devices

```bash
lsblk
```

Example

```text
NAME SIZE TYPE

sda 100G disk

├── sda1 1G

├── sda2 99G

sdb 500G disk
```

This command displays disks and partitions.

---

# Display UUID

```bash
blkid
```

Example

```text
UUID="7d34a5..."
```

Useful while editing

```
/etc/fstab
```

---

# Partition Disk

```bash
sudo fdisk /dev/sdb
```

Using `fdisk`, administrators can:

- Create Partition
- Delete Partition
- Modify Partition

---

# Create File System

Suppose a new partition is created.

Format it.

```bash
sudo mkfs.ext4 /dev/sdb1
```

Now Linux can store files.

---

# Mount File System

```bash
sudo mount /dev/sdb1 /data
```

Application data is now stored inside

```
/data
```

---

# Verify Mount

```bash
df -h
```

Output

```text
/dev/sdb1

↓

Mounted on

↓

/data
```

---

# Unmount File System

```bash
sudo umount /data
```

The storage is safely detached.

---

# Automatic Mount After Reboot

Linux stores permanent mount information inside

```
/etc/fstab
```

Example

```text
UUID=7d34...

↓

/data

↓

ext4

↓

defaults
```

Linux automatically mounts the disk after reboot.

---

# Swap Space

Swap acts as virtual memory.

Suppose

```
RAM

↓

100% Full
```

Linux temporarily moves inactive memory pages to Swap.

Display Swap

```bash
swapon --show
```

---

# LVM (Logical Volume Manager)

Large enterprises use **LVM**.

Instead of fixed partitions,

storage becomes flexible.

Example

```
Disk 1

↓

Volume Group

↓

Logical Volumes

↓

Application

Database

Backup
```

Benefits

- Resize Storage
- Easy Expansion
- Snapshots
- Flexible Management

---

# LVM Components

```
Physical Volume (PV)

↓

Volume Group (VG)

↓

Logical Volume (LV)

↓

Filesystem

↓

Mount Point
```

---

# Production Example

Suppose Jenkins build fails.

Error

```text
No Space Left on Device
```

Investigation

```bash
df -h
```

Output

```text
/

100%
```

Check directories

```bash
du -sh /var/*
```

Result

```text
Docker

↓

40 GB
```

Remove unused Docker images.

```bash
docker system prune
```

Disk usage returns to normal.

---

# Another Production Example

Application logs consume

```
80 GB
```

Commands

```bash
du -sh /var/log

↓

find /var/log -size +500M
```

Large logs identified.

Log rotation configured.

Problem solved.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| df -h | Disk Usage |
| du -sh | Directory Size |
| lsblk | Block Devices |
| blkid | UUID Information |
| fdisk | Partition Management |
| mkfs | Create Filesystem |
| mount | Mount Disk |
| umount | Unmount Disk |
| swapon --show | Display Swap |
| find -size | Find Large Files |

---

# Production Troubleshooting Flow

```
Disk Full

↓

df -h

↓

du -sh

↓

Find Large Files

↓

Delete / Archive

↓

Verify Free Space

↓

Application Running
```

---

# Interview Questions

### Q1. Which command displays disk usage?

```bash
df -h
```

---

### Q2. Which command displays directory size?

```bash
du -sh
```

---

### Q3. Which file stores automatic mount information?

```text
/etc/fstab
```

---

### Q4. What is LVM?

Logical Volume Manager allows flexible storage management by separating physical storage from logical volumes.

---

### Q5. Which command displays block devices?

```bash
lsblk
```

---

# Production Best Practices

✔ Keep root filesystem below **80% utilization**.

✔ Monitor `/var` because logs grow rapidly.

✔ Configure `logrotate`.

✔ Avoid storing application backups on the root partition.

✔ Monitor Docker images and volumes regularly.

✔ Expand storage before reaching critical utilization.

---

# Key Takeaways

- Storage management is a daily DevOps responsibility.
- `df` and `du` are among the most frequently used Linux commands.
- LVM provides flexible storage management.
- `/etc/fstab` controls automatic mounting.
- Storage monitoring prevents production outages.

---

# Next Section

## 2.17 Bash Shell Scripting

In the next section, we will begin one of the most important topics for every DevOps Engineer:

- Bash Basics
- Variables
- Loops
- Conditions
- Functions
- User Input
- Command-Line Arguments
- Automation Scripts
- Real Production Automation Examples

By the end of the Bash section, you will be able to automate repetitive Linux administration tasks like a professional DevOps Engineer.
---

# 2.17 Bash Shell Scripting

One of the biggest responsibilities of a DevOps Engineer is **Automation**.

Imagine your company has:

- 500 Linux Servers
- 300 Docker Containers
- 50 Jenkins Pipelines
- 20 Kubernetes Clusters

Can you perform every task manually?

No.

Instead, DevOps Engineers write **Shell Scripts** to automate repetitive tasks.

---

# What is Bash?

Bash stands for

**Bourne Again Shell**

It is the default shell in most Linux distributions.

Bash allows users to:

- Execute Commands
- Write Scripts
- Automate Tasks
- Schedule Jobs
- Manage Servers

---

# Why Learn Bash?

Suppose every morning you need to:

- Check Disk Usage
- Check CPU Usage
- Verify Services
- Backup Logs
- Send Email Report

Doing this manually on 200 servers would take hours.

Instead,

one Bash script performs everything automatically.

---

# What is a Shell Script?

A Shell Script is a text file containing Linux commands.

Example

```
backup.sh

↓

Linux Commands

↓

Execute

↓

Automation
```

---

# Your First Script

Create a file

```bash
touch hello.sh
```

Open it

```bash
vim hello.sh
```

Write

```bash
#!/bin/bash

echo "Hello DevOps"
```

Save the file.

---

# Make Script Executable

```bash
chmod +x hello.sh
```

Run it

```bash
./hello.sh
```

Output

```
Hello DevOps
```

---

# Understanding the Shebang

The first line

```bash
#!/bin/bash
```

is called the **Shebang**.

It tells Linux which interpreter should execute the script.

Examples

```
#!/bin/bash

↓

Bash

----------------

#!/usr/bin/python3

↓

Python

----------------

#!/usr/bin/env node

↓

Node.js
```

---

# Comments

Single-line comments begin with

```bash
#
```

Example

```bash
# Backup Script

echo "Starting Backup..."
```

Comments improve readability.

---

# Variables

Variables store values.

Example

```bash
name="Sandeep"

echo $name
```

Output

```
Sandeep
```

---

# Numeric Variables

```bash
a=10

b=20

echo $((a+b))
```

Output

```
30
```

---

# Read User Input

```bash
echo "Enter Your Name"

read name

echo "Welcome $name"
```

Example

```
Enter Your Name

Rahul

↓

Welcome Rahul
```

---

# Command Substitution

Store command output inside a variable.

```bash
today=$(date)

echo $today
```

Example Output

```
Tue Jul 01
```

---

# Environment Variables

Display current user

```bash
echo $USER
```

Home directory

```bash
echo $HOME
```

Current shell

```bash
echo $SHELL
```

Display PATH

```bash
echo $PATH
```

These variables are heavily used in automation.

---

# Conditional Statements

Example

```bash
if [ 5 -gt 3 ]
then
    echo "True"
fi
```

Output

```
True
```

---

# if...else

```bash
age=20

if [ $age -ge 18 ]
then
    echo "Eligible"
else
    echo "Not Eligible"
fi
```

---

# Comparison Operators

| Operator | Meaning |
|----------|----------|
| -eq | Equal |
| -ne | Not Equal |
| -gt | Greater Than |
| -lt | Less Than |
| -ge | Greater Than or Equal |
| -le | Less Than or Equal |

---

# For Loop

```bash
for i in 1 2 3 4 5
do
    echo $i
done
```

Output

```
1

2

3

4

5
```

---

# While Loop

```bash
count=1

while [ $count -le 5 ]
do
    echo $count
    count=$((count+1))
done
```

---

# Functions

```bash
greet(){

echo "Welcome DevOps"

}

greet
```

Functions reduce duplicate code.

---

# Command-Line Arguments

Create

```bash
script.sh
```

Execute

```bash
./script.sh Rahul Linux
```

Script

```bash
echo $1

echo $2
```

Output

```
Rahul

Linux
```

---

# Exit Status

Every Linux command returns an exit code.

Display it.

```bash
echo $?
```

Example

```
0

↓

Success
```

Non-zero

↓

Failure

---

# Production Example 1

Backup Script

```bash
#!/bin/bash

cp /opt/app/config.yml /backup/

echo "Backup Completed"
```

Run

```bash
./backup.sh
```

---

# Production Example 2

Check Disk Usage

```bash
#!/bin/bash

df -h

echo "Disk Report Generated"
```

---

# Production Example 3

Restart Nginx Automatically

```bash
#!/bin/bash

systemctl restart nginx

systemctl status nginx
```

This script is commonly used after deployment.

---

# Production Example 4

Check Server Uptime

```bash
#!/bin/bash

hostname

uptime
```

Useful while checking multiple servers.

---

# Frequently Used Bash Features

| Feature | Purpose |
|----------|----------|
| Variables | Store Values |
| read | User Input |
| echo | Display Output |
| if | Decision Making |
| for | Repeat Tasks |
| while | Repeat Until Condition |
| Function | Reusable Code |
| $1 $2 | Command-Line Arguments |
| $? | Exit Status |

---

# Interview Questions

### Q1. What is Bash?

Bash is the default command-line shell used by most Linux distributions for executing commands and writing automation scripts.

---

### Q2. What is a Shell Script?

A Shell Script is a text file containing Linux commands executed sequentially by the shell.

---

### Q3. What does `#!/bin/bash` mean?

It specifies that the Bash interpreter should execute the script.

---

### Q4. What does `$?` represent?

The exit status of the previously executed command.

---

### Q5. Why is Bash important in DevOps?

Because it automates repetitive Linux administration tasks such as deployments, backups, monitoring and health checks.

---

# Production Best Practices

✔ Always use meaningful variable names.

✔ Add comments for complex logic.

✔ Check command exit status.

✔ Use functions to avoid duplicate code.

✔ Test scripts on a non-production server before deployment.

✔ Store scripts in Git repositories.

✔ Handle errors gracefully.

---

# Key Takeaways

- Bash is the foundation of Linux automation.
- Shell scripts reduce manual work.
- Variables, loops and conditions make scripts powerful.
- Production DevOps Engineers automate repetitive tasks using Bash.
- Bash scripting is an essential interview skill.

---

# Next Section

## 2.18 Cron Jobs (Task Scheduling)

In the next section, we will learn how Linux automatically executes scripts at scheduled times using **Cron**, including:

- `crontab`
- Cron Syntax
- Scheduling Backups
- Log Cleanup
- Health Check Automation
- Production Scheduling Examples
---

# 2.18 Cron Jobs (Task Scheduling)

Imagine a company has 500 Linux servers.

Every day the following tasks must happen automatically.

- Backup Database at 2:00 AM
- Clean Old Logs
- Generate Disk Usage Report
- Restart Monitoring Agent
- Check SSL Expiry
- Send Health Report by Email

Should a DevOps Engineer wake up every night to execute these commands?

No.

Linux provides **Cron**, a built-in task scheduler.

Cron automatically executes commands at specified times.

---

# What is Cron?

Cron is a background service that schedules tasks.

Example

```
Current Time

↓

2:00 AM

↓

Cron Starts Backup Script

↓

Backup Completed
```

No human intervention is required.

---

# What is crontab?

Every user has a personal schedule file called

```
crontab
```

Linux checks this schedule every minute.

If the current time matches,

the command executes automatically.

---

# View Cron Jobs

```bash
crontab -l
```

Example

```text
0 2 * * * /home/sandeep/backup.sh
```

This displays all scheduled jobs.

---

# Edit Cron Jobs

```bash
crontab -e
```

Linux opens the cron editor.

---

# Remove All Cron Jobs

```bash
crontab -r
```

⚠️

Deletes every scheduled job.

Use carefully.

---

# Cron Format

Every cron entry contains five timing fields.

```
* * * * *

│ │ │ │ │

│ │ │ │ └── Day of Week

│ │ │ └──── Month

│ │ └────── Day of Month

│ └──────── Hour

└────────── Minute
```

Then comes the command.

```
Minute Hour Day Month Weekday Command
```

---

# Example 1

Run every day at

```
2:30 AM
```

```text
30 2 * * * /home/sandeep/backup.sh
```

---

# Example 2

Run every hour

```text
0 * * * * script.sh
```

---

# Example 3

Run every minute

```text
* * * * * script.sh
```

---

# Example 4

Run every Sunday

```text
0 3 * * 0 cleanup.sh
```

---

# Example 5

Run every Monday at 8 AM

```text
0 8 * * 1 report.sh
```

---

# Common Cron Examples

| Schedule | Cron Expression |
|-----------|----------------|
| Every Minute | `* * * * *` |
| Every Hour | `0 * * * *` |
| Every Day 2 AM | `0 2 * * *` |
| Every Sunday | `0 0 * * 0` |
| Every Month | `0 0 1 * *` |
| Every Monday | `0 0 * * 1` |

---

# Production Example 1

Daily Backup

```bash
0 2 * * * /opt/scripts/backup.sh
```

Every day at

```
2:00 AM
```

Database backup starts automatically.

---

# Production Example 2

Disk Usage Report

```bash
0 8 * * * df -h > /tmp/disk_report.txt
```

Every morning

```
8:00 AM
```

Disk usage report is generated.

---

# Production Example 3

Delete Old Logs

```bash
0 1 * * * find /var/log -type f -mtime +30 -delete
```

Deletes logs older than 30 days.

---

# Production Example 4

Restart Application

```bash
30 3 * * * systemctl restart nginx
```

Automatically restarts Nginx every day at 3:30 AM.

---

# Production Example 5

Health Check

```bash
*/5 * * * * /opt/scripts/health_check.sh
```

Runs every five minutes.

---

# Redirect Output

Store output in a log file.

```bash
0 2 * * * backup.sh >> backup.log 2>&1
```

Explanation

```
>>

Append Output

------------

2>&1

Store Errors
```

Useful for troubleshooting Cron jobs.

---

# Cron Service

Check Cron status.

Ubuntu

```bash
systemctl status cron
```

RHEL

```bash
systemctl status crond
```

Restart

Ubuntu

```bash
sudo systemctl restart cron
```

RHEL

```bash
sudo systemctl restart crond
```

---

# Production Troubleshooting

Problem

```
Backup Didn't Run
```

Check

```bash
systemctl status cron

↓

crontab -l

↓

tail /var/log/syslog

↓

journalctl -u cron
```

Root cause identified.

---

# Real Company Example

ShopKart generates

```
2 TB Database
```

Every night

Cron executes

```
Backup Script

↓

Compress Backup

↓

Upload to AWS S3

↓

Send Email Report
```

Entire process is fully automated.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| crontab -l | List Jobs |
| crontab -e | Edit Jobs |
| crontab -r | Remove Jobs |
| systemctl status cron | Check Cron |
| journalctl -u cron | Cron Logs |

---

# Interview Questions

### Q1. What is Cron?

Cron is a Linux task scheduler used to execute commands automatically at scheduled times.

---

### Q2. Which command edits Cron jobs?

```bash
crontab -e
```

---

### Q3. Which command lists scheduled Cron jobs?

```bash
crontab -l
```

---

### Q4. How do you run a script every day at 2 AM?

```text
0 2 * * * script.sh
```

---

### Q5. Why is Cron important in DevOps?

Cron automates repetitive administrative tasks such as backups, log cleanup, health checks and report generation.

---

# Production Best Practices

✔ Always use absolute file paths.

✔ Redirect output to log files.

✔ Test scripts manually before scheduling.

✔ Monitor Cron execution logs.

✔ Avoid overlapping Cron jobs.

✔ Document every scheduled task.

---

# Key Takeaways

- Cron automates repetitive Linux tasks.
- `crontab` manages scheduled jobs.
- Cron is heavily used for backups, monitoring and maintenance.
- Proper logging makes Cron troubleshooting easier.
- Automation is a core DevOps principle.

---

# Next Section

## 2.19 Linux Environment Variables

In the next section, we will learn:

- PATH
- HOME
- USER
- HOSTNAME
- SHELL
- export
- env
- printenv
- ~/.bashrc
- ~/.profile

These variables are essential for scripting, application deployment and CI/CD pipelines.
---

# 2.19 Linux Environment Variables

Almost every application running on Linux depends on **Environment Variables**.

Whether you are running:

- Docker
- Jenkins
- Kubernetes
- Java
- Python
- Node.js
- Terraform
- Ansible

you will use Environment Variables.

Understanding them is essential for every DevOps Engineer.

---

# What is an Environment Variable?

An Environment Variable is a named value stored by the operating system.

Applications read these values while running.

Example

```
Variable

↓

HOME

↓

/home/sandeep
```

Instead of hardcoding paths,

applications read values dynamically.

---

# Real Production Example

Suppose your application connects to a database.

Instead of writing:

```text
Password = MySecretPassword
```

inside the source code,

the application reads:

```text
DB_PASSWORD
```

from an Environment Variable.

This improves security.

---

# Display All Environment Variables

Command

```bash
printenv
```

or

```bash
env
```

Example Output

```text
HOME=/home/sandeep

USER=sandeep

PATH=/usr/bin:/usr/local/bin

SHELL=/bin/bash
```

---

# Display a Specific Variable

Example

```bash
echo $HOME
```

Output

```text
/home/sandeep
```

---

# HOME Variable

Displays the current user's home directory.

Command

```bash
echo $HOME
```

Example

```text
/home/sandeep
```

---

# USER Variable

Displays the logged-in user.

```bash
echo $USER
```

Output

```text
sandeep
```

---

# HOSTNAME Variable

Displays the server hostname.

```bash
echo $HOSTNAME
```

Example

```text
prod-web-01
```

---

# SHELL Variable

Displays the default shell.

```bash
echo $SHELL
```

Example

```text
/bin/bash
```

---

# PATH Variable

One of the most important Linux variables.

Display it.

```bash
echo $PATH
```

Example

```text
/usr/local/bin

/usr/bin

/bin

/snap/bin
```

Linux searches these directories whenever you execute a command.

---

# Example

Suppose you type

```bash
docker
```

Linux searches:

```
PATH

↓

/usr/local/bin

↓

Not Found

↓

/usr/bin

↓

Found

↓

Execute Docker
```

---

# Create Environment Variable

Example

```bash
export PROJECT=ShopKart
```

Display

```bash
echo $PROJECT
```

Output

```text
ShopKart
```

---

# Temporary Variable

Variables created using

```bash
export
```

exist only in the current shell session.

After logout,

they disappear.

---

# Permanent Variables

To make variables permanent,

edit

```text
~/.bashrc
```

Example

```bash
export JAVA_HOME=/usr/lib/jvm/java-21
```

Save

Reload

```bash
source ~/.bashrc
```

Now the variable remains available after every login.

---

# System-Wide Variables

For all users,

variables can be stored inside

```text
/etc/environment
```

or

```text
/etc/profile
```

These are loaded during user login.

---

# Check Variable

Determine whether a variable exists.

```bash
echo $JAVA_HOME
```

If nothing appears,

the variable is not configured.

---

# Remove Variable

```bash
unset PROJECT
```

Now

```bash
echo $PROJECT
```

returns nothing.

---

# Production Example 1

A Java application requires

```text
JAVA_HOME
```

Configure

```bash
export JAVA_HOME=/usr/lib/jvm/java-21
```

Application starts successfully.

---

# Production Example 2

A Python application needs

```text
DATABASE_URL
```

Instead of storing the password inside the code,

configure

```bash
export DATABASE_URL=mysql://user:password@dbserver
```

The application reads the value securely.

---

# Production Example 3

Jenkins Pipeline

```groovy
environment {

APP_ENV="Production"

}
```

The pipeline automatically uses the environment variable during deployment.

---

# Frequently Used Variables

| Variable | Purpose |
|----------|----------|
| HOME | User Home Directory |
| USER | Logged-In User |
| HOSTNAME | Server Name |
| SHELL | Default Shell |
| PATH | Command Search Path |
| PWD | Present Working Directory |
| JAVA_HOME | Java Installation |
| PATH | Executable Search Path |

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| env | Display Variables |
| printenv | Display Variables |
| echo $VAR | Display Variable |
| export | Create Variable |
| unset | Remove Variable |
| source ~/.bashrc | Reload Configuration |

---

# Interview Questions

### Q1. What is an Environment Variable?

An Environment Variable is a named value used by the operating system and applications to store configuration information.

---

### Q2. Which command displays all Environment Variables?

```bash
printenv
```

or

```bash
env
```

---

### Q3. Which variable stores executable search paths?

```text
PATH
```

---

### Q4. Which command creates a temporary Environment Variable?

```bash
export
```

---

### Q5. Which file is commonly used to store user Environment Variables permanently?

```text
~/.bashrc
```

---

# Production Best Practices

✔ Never store passwords directly inside scripts.

✔ Use Environment Variables for secrets.

✔ Keep PATH clean.

✔ Store permanent variables inside configuration files.

✔ Document custom Environment Variables.

---

# Key Takeaways

- Environment Variables store configuration values.
- PATH is one of the most important Linux variables.
- `export` creates variables.
- `~/.bashrc` stores user-specific permanent variables.
- Environment Variables are widely used in Docker, Kubernetes, Jenkins and CI/CD.

---

# Next Section

## 2.20 Linux Boot Process

In the next section, we will understand how Linux starts from the moment the power button is pressed until the login prompt appears.

We will cover:

- BIOS
- UEFI
- GRUB
- Linux Kernel
- initramfs
- systemd
- Boot Targets
- Troubleshooting Boot Failures

This is one of the favorite interview topics for Linux and DevOps Engineers.
---

# 2.20 Linux Boot Process

Have you ever wondered what happens after pressing the **Power Button** on a Linux server?

Does Linux start immediately?

No.

A Linux server goes through several stages before the login screen appears.

Understanding the Linux Boot Process helps DevOps Engineers troubleshoot servers that fail to boot.

It is also one of the most frequently asked interview topics.

---

# Why Should DevOps Engineers Learn the Boot Process?

Suppose your production server suddenly stops booting after a kernel update.

Customers cannot access the application.

The DevOps Engineer must determine:

- Is the hardware working?
- Is the Boot Loader damaged?
- Is the Kernel corrupted?
- Did systemd fail?
- Is the filesystem damaged?

Without understanding the boot process, troubleshooting becomes difficult.

---

# Linux Boot Sequence

```
Power On

↓

BIOS / UEFI

↓

Boot Loader (GRUB)

↓

Linux Kernel

↓

initramfs

↓

systemd

↓

Services

↓

Login Prompt
```

Every Linux system follows this sequence.

---

# Step 1 – Power On

The process begins when the server receives power.

```
Power Button

↓

CPU Starts

↓

Motherboard Activated
```

Hardware initialization begins immediately.

---

# Step 2 – BIOS / UEFI

The firmware performs a **Power-On Self Test (POST).**

It checks:

- CPU
- RAM
- Keyboard
- Storage Devices
- Network Cards

If a hardware problem exists, the boot process stops.

Modern systems usually use **UEFI** instead of BIOS.

---

# Step 3 – Boot Loader (GRUB)

After hardware initialization, Linux loads the Boot Loader.

The most common Boot Loader is:

```
GRUB

(Grand Unified Bootloader)
```

Responsibilities:

- Display Boot Menu
- Select Kernel
- Pass Boot Parameters
- Load Linux Kernel

---

# GRUB Configuration

Configuration file

```text
/etc/default/grub
```

After making changes,

update GRUB.

Ubuntu

```bash
sudo update-grub
```

RHEL

```bash
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```

---

# Step 4 – Linux Kernel

GRUB loads the Linux Kernel into memory.

The Kernel initializes:

- CPU
- Memory
- Device Drivers
- Filesystems
- Networking

The Kernel becomes the heart of the operating system.

---

# Step 5 – initramfs

Before the real filesystem is available,

Linux loads a temporary filesystem called

```
initramfs
```

Responsibilities:

- Load Drivers
- Detect Storage Devices
- Mount Root Filesystem

After this stage,

the temporary filesystem is removed.

---

# Step 6 – systemd

Once the Kernel finishes initialization,

Linux starts

```
systemd
```

systemd always runs with

```
PID = 1
```

Verify

```bash
ps -p 1
```

Output

```text
systemd
```

---

# Step 7 – Service Startup

systemd starts required services.

Example

```
SSH

↓

Docker

↓

MySQL

↓

Nginx

↓

Jenkins
```

Each service starts according to dependencies.

---

# Step 8 – Login Prompt

After all required services start,

Linux displays

```
login:
```

or

SSH becomes available.

The system is now ready for users.

---

# Boot Targets

Modern Linux uses **Targets** instead of Runlevels.

Display current target.

```bash
systemctl get-default
```

Example

```text
multi-user.target
```

---

# Common Targets

| Target | Purpose |
|---------|----------|
| poweroff.target | Shutdown |
| rescue.target | Rescue Mode |
| multi-user.target | CLI Mode |
| graphical.target | GUI Mode |
| reboot.target | Restart |

---

# Change Default Target

Example

```bash
sudo systemctl set-default graphical.target
```

or

```bash
sudo systemctl set-default multi-user.target
```

---

# Boot Time

Display boot duration.

```bash
systemd-analyze
```

Example

```text
Startup finished in

8.5 seconds
```

---

# Analyze Slow Boot

```bash
systemd-analyze blame
```

Example

```text
4.3s docker.service

3.1s mysql.service

2.5s nginx.service
```

Useful for identifying slow services.

---

# Production Example 1

Server does not boot after a Kernel update.

Investigation:

```
GRUB

↓

Kernel

↓

Recovery Mode

↓

Previous Kernel

↓

Boot Successful
```

The engineer boots using the previous kernel version.

---

# Production Example 2

SSH is unavailable after reboot.

Check

```bash
systemctl status ssh
```

Result

```
Service Disabled
```

Enable

```bash
sudo systemctl enable ssh
```

Reboot

Problem solved.

---

# Boot Troubleshooting Checklist

```
Server Doesn't Boot

↓

Hardware Check

↓

BIOS / UEFI

↓

GRUB

↓

Kernel

↓

Filesystem

↓

systemd

↓

Services

↓

Application
```

Always troubleshoot in sequence.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| ps -p 1 | Verify systemd |
| systemctl get-default | Current Boot Target |
| systemctl set-default | Change Target |
| systemd-analyze | Boot Time |
| systemd-analyze blame | Slow Boot Analysis |
| update-grub | Update GRUB (Ubuntu) |
| grub2-mkconfig | Update GRUB (RHEL) |

---

# Interview Questions

### Q1. What is the first software loaded after BIOS/UEFI?

**GRUB (Boot Loader).**

---

### Q2. Which process always has PID 1?

**systemd**

---

### Q3. What is the purpose of GRUB?

GRUB loads the Linux Kernel and provides boot options.

---

### Q4. What does `systemd-analyze` display?

The Linux boot time.

---

### Q5. Which command identifies slow boot services?

```bash
systemd-analyze blame
```

---

# Production Best Practices

✔ Keep multiple kernel versions available.

✔ Regularly update GRUB after configuration changes.

✔ Monitor boot times.

✔ Keep rescue media available.

✔ Test kernel updates on non-production servers first.

---

# Key Takeaways

- Linux follows a fixed boot sequence.
- GRUB loads the Linux Kernel.
- systemd initializes userspace and services.
- Understanding the boot process is essential for troubleshooting production servers.
- Boot failures should always be analyzed step by step.

---

# Next Section

## 2.21 Linux Security Fundamentals

In the next section, we will learn:

- Linux Security Principles
- Firewall (UFW & Firewalld)
- SELinux
- AppArmor
- Fail2Ban
- Password Policies
- SSH Hardening
- File Security
- Security Best Practices

Security is one of the most critical responsibilities of every DevOps Engineer.
---

# 2.21 Linux Security Fundamentals

Security is one of the highest priorities in every production environment.

A DevOps Engineer is not only responsible for deploying applications but also for protecting servers, applications, user data and infrastructure.

A single security mistake can lead to:

- Data Theft
- Server Compromise
- Financial Loss
- Service Downtime
- Legal Issues
- Reputation Damage

Understanding Linux Security is therefore essential.

---

# What is Linux Security?

Linux Security refers to protecting the operating system from:

- Unauthorized Access
- Malware
- Data Leakage
- Network Attacks
- Insider Threats
- Misconfigured Permissions

Security is not a single feature.

It is a combination of multiple layers.

---

# Defense in Depth

Modern companies use multiple security layers.

```
Internet

↓

Firewall

↓

Load Balancer

↓

Web Server

↓

Application

↓

Database

↓

Encrypted Storage
```

If one layer fails,

another layer still protects the system.

This approach is called

**Defense in Depth.**

---

# Principle of Least Privilege

One of the most important security principles.

Every user should receive only the permissions required to perform their work.

Example

```
Developer

↓

Deploy Application

❌

Cannot Shutdown Server

❌

Cannot Delete Database
```

Less access means lower risk.

---

# Keep Linux Updated

Old software often contains security vulnerabilities.

Regularly update packages.

Ubuntu

```bash
sudo apt update

sudo apt upgrade
```

Rocky Linux

```bash
sudo dnf update
```

Security patches should be applied during maintenance windows.

---

# Password Security

Weak passwords are a major security risk.

Bad Password

```
admin123
```

Strong Password

```
D3v0ps@2026#Linux
```

Use:

- Uppercase Letters
- Lowercase Letters
- Numbers
- Symbols
- Long Passwords

---

# Disable Root Login

Never allow direct SSH login as **root**.

Instead:

```
User Login

↓

sudo

↓

Administrative Task
```

Edit

```text
/etc/ssh/sshd_config
```

Set

```text
PermitRootLogin no
```

Restart SSH

```bash
sudo systemctl restart ssh
```

---

# SSH Key Authentication

Use SSH Keys instead of passwords.

```
Private Key

↓

Public Key

↓

Secure Login
```

This significantly improves security.

---

# Firewall

A firewall controls incoming and outgoing network traffic.

Example

```
Internet

↓

Firewall

↓

Allow Port 22

Allow Port 80

Allow Port 443

↓

Block Everything Else
```

---

# UFW (Ubuntu Firewall)

Check Status

```bash
sudo ufw status
```

Enable Firewall

```bash
sudo ufw enable
```

Allow SSH

```bash
sudo ufw allow 22
```

Allow HTTP

```bash
sudo ufw allow 80
```

Allow HTTPS

```bash
sudo ufw allow 443
```

---

# firewalld (RHEL/Rocky Linux)

Check Status

```bash
systemctl status firewalld
```

Allow HTTP

```bash
sudo firewall-cmd --permanent --add-service=http
```

Reload Firewall

```bash
sudo firewall-cmd --reload
```

---

# SELinux

SELinux stands for

**Security-Enhanced Linux**

It provides an additional security layer.

Check Status

```bash
getenforce
```

Possible Output

```
Enforcing

Permissive

Disabled
```

Production systems should generally use

```
Enforcing
```

---

# AppArmor

Ubuntu commonly uses

```
AppArmor
```

instead of SELinux.

Check Status

```bash
sudo aa-status
```

AppArmor limits what applications are allowed to do.

---

# Fail2Ban

Fail2Ban protects servers against brute-force attacks.

Example

```
Attacker

↓

100 Wrong Passwords

↓

Fail2Ban

↓

IP Blocked
```

This is commonly used to protect SSH servers.

---

# Secure File Permissions

Never make sensitive files publicly writable.

Bad

```bash
chmod 777 application.yml
```

Better

```bash
chmod 640 application.yml
```

Sensitive files should always have minimal permissions.

---

# Secure Backups

Backups should always be:

- Encrypted
- Access Controlled
- Tested Regularly
- Stored Offsite

A backup that cannot be restored is useless.

---

# Production Example 1

Developer cannot access Jenkins.

Firewall Investigation

```bash
sudo ufw status
```

Result

```
Port 8080

Blocked
```

Solution

```bash
sudo ufw allow 8080
```

Jenkins becomes accessible.

---

# Production Example 2

Thousands of failed SSH login attempts.

Check

```bash
journalctl -u ssh
```

Repeated failures detected.

Install

```
Fail2Ban
```

Attack automatically blocked.

---

# Production Example 3

A configuration file contains database passwords.

Instead of

```
database_password=admin123
```

Use

```
Environment Variables

↓

Secret Manager

↓

Vault

↓

Kubernetes Secrets
```

Sensitive information should never be stored directly in source code.

---

# Linux Security Checklist

Before deploying a production server, verify:

✔ Latest Security Updates Installed

✔ Firewall Enabled

✔ SSH Keys Configured

✔ Root Login Disabled

✔ Strong Password Policy

✔ SELinux/AppArmor Enabled

✔ File Permissions Verified

✔ Logs Monitored

✔ Backups Tested

✔ Unused Services Disabled

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| ufw status | Firewall Status |
| ufw enable | Enable Firewall |
| firewall-cmd | Manage firewalld |
| getenforce | Check SELinux |
| aa-status | Check AppArmor |
| chmod | Change Permissions |
| chown | Change Ownership |
| journalctl | View Logs |

---

# Interview Questions

### Q1. What is the Principle of Least Privilege?

Users should receive only the permissions necessary to perform their work.

---

### Q2. Why should root login be disabled?

It reduces the risk of unauthorized administrative access.

---

### Q3. Which Ubuntu firewall is commonly used?

```
UFW
```

---

### Q4. What is SELinux?

SELinux is a Linux security module that enforces mandatory access control policies.

---

### Q5. What is Fail2Ban?

Fail2Ban monitors logs and automatically blocks IP addresses that perform repeated failed login attempts.

---

# Production Best Practices

✔ Always enable a firewall.

✔ Disable unused services.

✔ Use SSH Keys instead of passwords.

✔ Keep Linux updated.

✔ Never expose sensitive information in source code.

✔ Regularly review user accounts and permissions.

✔ Monitor security logs daily.

---

# Key Takeaways

- Security is a shared responsibility across infrastructure, applications and users.
- Multiple security layers provide stronger protection.
- Firewalls, SELinux, SSH Keys and proper permissions are essential.
- Following security best practices significantly reduces production risks.

---

# Next Section

## 2.22 Linux Performance Monitoring

In the next section, we will learn how to monitor CPU, Memory, Disk and Network performance using:

- top
- htop
- vmstat
- iostat
- sar
- free
- uptime
- lscpu
- mpstat
- pidstat

These tools help DevOps Engineers diagnose slow production servers and performance bottlenecks.
---

# 2.22 Linux Performance Monitoring

In a production environment, applications must be fast and responsive.

Suppose users complain:

- Website is slow.
- API takes 30 seconds to respond.
- Jenkins build is hanging.
- Kubernetes Pods are restarting.
- Database queries are slow.

The first responsibility of a DevOps Engineer is to determine **which resource is causing the problem.**

Performance monitoring helps answer questions such as:

- Is CPU overloaded?
- Is RAM exhausted?
- Is Disk full?
- Is Disk I/O slow?
- Is Network congested?

---

# Four Major Resources

Every Linux server depends on four primary resources.

```
CPU

↓

Memory

↓

Disk

↓

Network
```

Whenever performance degrades, one or more of these resources is usually responsible.

---

# Performance Troubleshooting Flow

```
User Complaint

↓

CPU

↓

Memory

↓

Disk

↓

Network

↓

Application Logs

↓

Root Cause
```

Never restart a server without identifying the actual problem.

---

# uptime

Display system uptime and load average.

```bash
uptime
```

Example

```text
10:42:15 up 42 days, 3 users, load average: 0.50, 0.75, 0.82
```

Explanation

```
Load Average

↓

1 Minute

↓

5 Minutes

↓

15 Minutes
```

A high load average may indicate CPU or I/O bottlenecks.

---

# free

Display memory usage.

```bash
free -h
```

Example

```text
              total   used   free

Mem            16G    10G     6G

Swap            4G     0G      4G
```

The `-h` option displays values in a human-readable format.

---

# top

Monitor the system in real time.

```bash
top
```

Shows:

- CPU Usage
- Memory Usage
- Running Processes
- Load Average
- Uptime

This command refreshes automatically.

---

# htop

Enhanced version of `top`.

```bash
htop
```

Advantages

- Interactive Interface
- Color Display
- Process Search
- Easy Sorting
- Mouse Support

---

# vmstat

Displays virtual memory statistics.

```bash
vmstat 2
```

Updates every two seconds.

Important fields include:

- CPU
- Memory
- Swap
- I/O
- Context Switches

---

# iostat

Displays disk performance.

```bash
iostat -x 2
```

Useful for identifying:

- Slow Disks
- High Disk Utilization
- I/O Wait

---

# sar

Collects historical performance statistics.

```bash
sar -u
```

Displays CPU utilization.

Memory

```bash
sar -r
```

Network

```bash
sar -n DEV
```

Unlike `top`, SAR can display historical data.

---

# lscpu

Displays CPU information.

```bash
lscpu
```

Example

```text
Architecture: x86_64

CPU(s): 8

Core(s): 4

Thread(s): 2
```

Useful when verifying server hardware.

---

# mpstat

Displays CPU usage for every processor.

```bash
mpstat -P ALL
```

Useful on multi-core servers.

---

# pidstat

Displays CPU and memory usage by process.

```bash
pidstat
```

Useful for identifying applications consuming excessive resources.

---

# Check Memory Usage

```bash
free -h

↓

top

↓

ps -aux --sort=-%mem
```

These commands quickly identify memory-heavy applications.

---

# Check CPU Usage

```bash
top

↓

htop

↓

mpstat
```

---

# Check Disk Usage

```bash
df -h

↓

du -sh

↓

iostat
```

---

# Check Network Usage

```bash
ss

↓

sar -n DEV

↓

iftop
```

---

# Production Example 1

Problem

```
Website is Slow
```

Investigation

```bash
top
```

Output

```text
CPU

98%
```

The Java process is consuming almost all CPU resources.

---

# Production Example 2

Problem

```
Docker Containers Restarting
```

Investigation

```bash
free -h
```

Output

```text
Memory

100%
```

Linux begins using Swap.

Containers are killed due to memory pressure.

Solution:

- Increase RAM
- Optimize Application
- Limit Container Memory

---

# Production Example 3

Problem

```
Database Slow
```

Investigation

```bash
iostat -x
```

Output

```text
Disk Utilization

100%
```

Root Cause

```
Storage Bottleneck
```

---

# Production Example 4

Problem

```
Server Responding Slowly
```

Commands

```bash
uptime

↓

top

↓

free -h

↓

iostat

↓

journalctl
```

After checking every resource,

the DevOps Engineer identifies the bottleneck before taking corrective action.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| uptime | System Uptime & Load |
| free -h | Memory Usage |
| top | Real-Time Monitoring |
| htop | Advanced Monitoring |
| vmstat | Virtual Memory Statistics |
| iostat | Disk Performance |
| sar | Historical Statistics |
| lscpu | CPU Information |
| mpstat | Per-CPU Usage |
| pidstat | Per-Process Statistics |

---

# Performance Troubleshooting Checklist

```
Application Slow

↓

CPU

↓

Memory

↓

Disk

↓

Network

↓

Logs

↓

Database

↓

Application
```

Follow the same sequence every time.

---

# Interview Questions

### Q1. Which command displays memory usage?

```bash
free -h
```

---

### Q2. Which command displays load average?

```bash
uptime
```

---

### Q3. Which command shows real-time CPU usage?

```bash
top
```

or

```bash
htop
```

---

### Q4. Which command displays disk I/O statistics?

```bash
iostat
```

---

### Q5. Which command provides historical performance statistics?

```bash
sar
```

---

# Production Best Practices

✔ Monitor CPU continuously.

✔ Keep memory utilization below critical levels.

✔ Watch disk growth regularly.

✔ Monitor load average.

✔ Configure Prometheus and Grafana for continuous monitoring.

✔ Never assume the root cause without collecting performance data.

---

# Key Takeaways

- Performance monitoring is one of the most important daily DevOps tasks.
- CPU, Memory, Disk and Network should always be checked before troubleshooting applications.
- Linux provides many built-in monitoring tools.
- Proper monitoring helps prevent production outages.

---

# Next Section

## 2.23 Linux System Monitoring & Health Checks

In the next section, we will learn how DevOps Engineers perform complete server health checks using:

- hostname
- uname
- hostnamectl
- date
- timedatectl
- who
- w
- last
- uptime
- df
- free
- top
- systemctl

We will also build a complete **Linux Health Check Checklist** used in real production environments.
---

# 2.23 Linux System Monitoring & Health Checks

Imagine it is Monday morning.

You receive a message:

> **Production Server is Slow**

As a DevOps Engineer, what should you check first?

Should you immediately restart the server?

**No.**

Professional engineers always perform a complete **Server Health Check** before taking any action.

This chapter explains the exact health check procedure followed in production environments.

---

# What is a Health Check?

A Health Check is the process of verifying that every important component of the server is working correctly.

It includes checking:

- Server Information
- CPU
- Memory
- Disk
- Network
- Services
- Users
- Time
- Logs

Only after collecting this information should troubleshooting begin.

---

# Production Health Check Flow

```
Problem Reported

↓

Server Information

↓

CPU

↓

Memory

↓

Disk

↓

Network

↓

Services

↓

Logs

↓

Application

↓

Root Cause
```

Never skip steps.

---

# Check Server Hostname

Display the server name.

```bash
hostname
```

Example

```text
prod-web-01
```

---

# Display System Information

```bash
uname -a
```

Example

```text
Linux prod-web-01

6.8.0

x86_64

GNU/Linux
```

Displays:

- Kernel Version
- Architecture
- Hostname

---

# hostnamectl

```bash
hostnamectl
```

Output

```text
Static hostname

Operating System

Kernel

Architecture
```

Useful while documenting production servers.

---

# Check Date & Time

```bash
date
```

Example

```text
Tue Jul 1 12:30:20 IST 2026
```

---

# Verify Time Synchronization

```bash
timedatectl
```

Displays:

- Local Time
- Universal Time
- Time Zone
- NTP Status

Incorrect time causes:

- SSL Errors
- Authentication Problems
- Incorrect Logs

---

# Logged-In Users

```bash
who
```

Example

```text
sandeep

pts/0
```

---

# Active Users

```bash
w
```

Displays:

- Logged-in Users
- Login Time
- Idle Time
- Running Commands

---

# Login History

```bash
last
```

Example

```text
sandeep

Jul 1

09:20
```

Useful during security investigations.

---

# System Uptime

```bash
uptime
```

Example

```text
up 48 days
```

Long uptime generally indicates system stability.

---

# Memory Check

```bash
free -h
```

Review:

- Total Memory
- Used Memory
- Free Memory
- Swap

---

# CPU Check

```bash
top
```

or

```bash
htop
```

Look for:

- High CPU Usage
- Load Average
- Zombie Processes

---

# Disk Usage

```bash
df -h
```

Review:

- Root Partition
- /var
- /home
- Data Partition

Avoid disks reaching 100%.

---

# Large Directories

```bash
du -sh /*
```

Identify directories consuming excessive storage.

---

# Running Services

```bash
systemctl --failed
```

Displays failed services.

Verify important services.

```bash
systemctl status nginx

systemctl status docker

systemctl status ssh

systemctl status mysql
```

---

# Check Listening Ports

```bash
ss -tulnp
```

Verify:

- SSH
- HTTP
- HTTPS
- Database
- Application Ports

---

# Network Connectivity

```bash
ping google.com
```

Internal server

```bash
ping database-server
```

Verify DNS

```bash
nslookup google.com
```

---

# Check Open Files

```bash
lsof
```

Useful for:

- Locked Files
- Busy Filesystems
- Port Usage

---

# Kernel Messages

```bash
dmesg
```

Look for:

- Disk Errors
- Hardware Errors
- Memory Problems

---

# Recent Logs

```bash
journalctl -n 50
```

Displays the latest system events.

---

# Running Processes

```bash
ps -ef
```

Review:

- High CPU Processes
- Zombie Processes
- Duplicate Services

---

# Production Health Check Checklist

```
✔ Hostname

✔ Date & Time

✔ Uptime

✔ CPU

✔ Memory

✔ Disk

✔ Swap

✔ Network

✔ DNS

✔ Services

✔ Logs

✔ Running Processes

✔ Failed Services

✔ Listening Ports

✔ Recent Login Activity
```

This checklist should become a daily habit.

---

# Real Production Example 1

Complaint

```
Website Down
```

Health Check

```bash
hostname

↓

uptime

↓

df -h

↓

free -h

↓

systemctl status nginx

↓

ss -tulnp

↓

journalctl -u nginx
```

Within minutes, the root cause is identified.

---

# Real Production Example 2

Complaint

```
Jenkins Pipeline Failed
```

Commands

```bash
systemctl status jenkins

↓

df -h

↓

free -h

↓

journalctl -u jenkins

↓

top
```

Problem

```
Disk Full
```

Free space is created.

Pipeline succeeds.

---

# Real Production Example 3

Complaint

```
SSH Not Working
```

Commands

```bash
systemctl status ssh

↓

ss -tulnp | grep 22

↓

journalctl -u ssh

↓

ufw status
```

Problem

```
Firewall Blocking Port 22
```

Firewall rule updated.

SSH restored.

---

# Frequently Used Commands

| Command | Purpose |
|----------|----------|
| hostname | Server Name |
| hostnamectl | System Information |
| uname -a | Kernel Information |
| date | Current Date |
| timedatectl | Time Synchronization |
| who | Logged-In Users |
| w | Active Users |
| last | Login History |
| uptime | Uptime |
| free -h | Memory |
| df -h | Disk |
| du -sh | Directory Size |
| top | CPU Monitoring |
| systemctl | Service Status |
| ss | Network Ports |
| journalctl | Logs |
| ps -ef | Running Processes |
| dmesg | Kernel Logs |
| lsof | Open Files |

---

# Interview Questions

### Q1. Which command displays the Linux kernel version?

```bash
uname -a
```

---

### Q2. Which command shows logged-in users?

```bash
who
```

---

### Q3. Which command displays login history?

```bash
last
```

---

### Q4. Which command verifies time synchronization?

```bash
timedatectl
```

---

### Q5. Why is a Health Check important?

Because it helps identify the real root cause of production issues before taking corrective action.

---

# Production Best Practices

✔ Perform health checks before restarting services.

✔ Monitor CPU, Memory and Disk every day.

✔ Review failed services regularly.

✔ Verify system time using NTP.

✔ Document server configuration.

✔ Automate health checks using Bash scripts.

✔ Integrate health checks with monitoring tools such as Prometheus and Grafana.

---

# Key Takeaways

- A systematic health check prevents unnecessary troubleshooting.
- Never restart servers without collecting diagnostic information.
- Daily health checks improve server reliability.
- Health check automation is a core DevOps responsibility.

---

# Next Section

## 2.24 Linux Interview Questions & Real Production Scenarios

In the next section, we will cover **100+ Linux interview questions**, scenario-based troubleshooting, production incidents, and practical exercises that prepare you for real DevOps interviews and day-to-day operations.
---

# 2.24 Linux Interview Questions & Real Production Scenarios

Congratulations!

You have completed almost the entire Linux chapter.

Now it is time to apply everything you have learned.

In real interviews, companies rarely ask only command-based questions.

Instead, they ask:

- Production Scenarios
- Troubleshooting Questions
- Incident Handling
- Real-Time Problems

This section prepares you for those situations.

---

# Interview Round Structure

A Linux interview generally consists of four rounds.

```
Basic Linux

↓

Linux Administration

↓

Production Scenarios

↓

Troubleshooting
```

The final round usually focuses on real production incidents.

---

# Basic Linux Questions

### Q1. What is Linux?

Linux is an open-source operating system based on the Linux Kernel.

---

### Q2. What is the Linux Kernel?

The Kernel is the core component of Linux responsible for managing hardware resources, memory, processes and devices.

---

### Q3. What is the difference between Linux and Unix?

Unix is a family of proprietary operating systems.

Linux is an open-source Unix-like operating system.

---

### Q4. What is a Shell?

A Shell is a command interpreter that accepts user commands and communicates with the Linux Kernel.

---

### Q5. What is Bash?

Bash (Bourne Again Shell) is the default shell used in most Linux distributions.

---

# File System Questions

### Q6. What is the root directory?

```
/
```

The top-most directory in Linux.

---

### Q7. Where are configuration files stored?

```
/etc
```

---

### Q8. Where are log files stored?

```
/var/log
```

---

### Q9. Which directory stores user home directories?

```
/home
```

---

### Q10. What is stored in `/tmp`?

Temporary files.

---

# User Management Questions

### Q11. Who is the root user?

The super administrator with unrestricted access.

---

### Q12. What is the UID of root?

```
0
```

---

### Q13. Which command creates a user?

```bash
useradd
```

---

### Q14. Which command changes a password?

```bash
passwd
```

---

### Q15. What does sudo do?

Allows a normal user to execute administrative commands.

---

# Permission Questions

### Q16. What does 755 mean?

```
Owner

↓

rwx

Group

↓

r-x

Others

↓

r-x
```

---

### Q17. What does chmod do?

Changes file permissions.

---

### Q18. What does chown do?

Changes file ownership.

---

### Q19. Why is chmod 777 dangerous?

Because every user receives full permissions.

---

### Q20. What are Read, Write and Execute permissions?

```
Read

↓

4

Write

↓

2

Execute

↓

1
```

---

# Process Questions

### Q21. What is a Process?

A running instance of a program.

---

### Q22. Which command displays running processes?

```bash
ps
```

---

### Q23. Which command monitors CPU usage?

```bash
top
```

---

### Q24. Which command forcefully kills a process?

```bash
kill -9
```

---

### Q25. What is PID?

Process ID.

Every process has a unique PID.

---

# Service Questions

### Q26. Which command starts a service?

```bash
systemctl start
```

---

### Q27. Which command checks service status?

```bash
systemctl status
```

---

### Q28. Which process has PID 1?

```
systemd
```

---

### Q29. Which command enables a service after reboot?

```bash
systemctl enable
```

---

### Q30. Which command displays failed services?

```bash
systemctl --failed
```

---

# Networking Questions

### Q31. Which command displays the IP address?

```bash
ip addr
```

---

### Q32. Which command tests connectivity?

```bash
ping
```

---

### Q33. Which command performs DNS lookup?

```bash
nslookup
```

or

```bash
dig
```

---

### Q34. Which command securely connects to another Linux server?

```bash
ssh
```

---

### Q35. Which command copies files securely?

```bash
scp
```

---

# Storage Questions

### Q36. Which command displays disk usage?

```bash
df -h
```

---

### Q37. Which command displays directory size?

```bash
du -sh
```

---

### Q38. Which file controls automatic mounting?

```
/etc/fstab
```

---

### Q39. What is LVM?

Logical Volume Manager.

---

### Q40. Which command displays block devices?

```bash
lsblk
```

---

# Bash Questions

### Q41. What is a Shell Script?

A file containing Linux commands executed by the shell.

---

### Q42. What does `#!/bin/bash` represent?

The Bash interpreter.

---

### Q43. Which variable stores the previous command's exit code?

```bash
$?
```

---

### Q44. Which command creates an Environment Variable?

```bash
export
```

---

### Q45. Which file stores permanent Bash variables?

```
~/.bashrc
```

---

# Real Production Scenario 1

### Interviewer

Production website is down.

What will you do?

---

### Candidate Answer

```
Check Network

↓

Ping Server

↓

SSH Login

↓

systemctl status nginx

↓

journalctl -u nginx

↓

Check Disk

↓

Check Memory

↓

Restart Service (Only if required)

↓

Verify Website
```

---

# Real Production Scenario 2

### Interviewer

The application is running but users report it is very slow.

---

### Candidate Answer

```
top

↓

free -h

↓

uptime

↓

iostat

↓

Check Logs

↓

Database

↓

Application
```

Never restart without identifying the root cause.

---

# Real Production Scenario 3

### Interviewer

Docker containers are restarting automatically.

---

### Candidate Answer

```
docker ps

↓

docker logs

↓

free -h

↓

df -h

↓

journalctl

↓

docker inspect
```

---

# Real Production Scenario 4

### Interviewer

SSH login is failing.

---

### Candidate Answer

```
systemctl status ssh

↓

ss -tulnp

↓

journalctl -u ssh

↓

Firewall

↓

authorized_keys

↓

Disk Space
```

---

# Real Production Scenario 5

### Interviewer

The server shows "No Space Left on Device."

---

### Candidate Answer

```
df -h

↓

du -sh

↓

Find Large Files

↓

Archive

↓

Delete

↓

Verify Free Space

↓

Restart Application
```

---

# Golden Rule for Production

Never perform these actions immediately:

❌ Reboot Server

❌ Restart Database

❌ Delete Files

❌ Kill Processes

Instead,

Always follow this sequence.

```
Collect Information

↓

Analyze

↓

Identify Root Cause

↓

Take Corrective Action

↓

Verify

↓

Document
```

---

# Linux Chapter Summary

By completing this chapter, you have learned:

✔ Linux Architecture

✔ Linux File System

✔ Navigation Commands

✔ File Management

✔ Users & Groups

✔ Permissions

✔ Processes

✔ Services

✔ Package Management

✔ Networking

✔ SSH

✔ Logs

✔ Storage

✔ Bash

✔ Cron

✔ Environment Variables

✔ Boot Process

✔ Security

✔ Performance Monitoring

✔ Health Checks

✔ Production Troubleshooting

---

# What's Next?

## Chapter 3 – Git & GitHub

In the next chapter, you will learn:

- Version Control
- Git Architecture
- Git Workflow
- Git Commands
- Branching
- Merging
- Rebasing
- Conflict Resolution
- GitHub
- Pull Requests
- GitHub Actions
- Production Git Strategy

By the end of Chapter 3, you will be able to work confidently in a real DevOps team using Git and GitHub.

---

# End of Chapter 2