# Chapter 10 – Monitoring & Logging

Monitoring and Logging are among the most important skills for every DevOps Engineer.

No matter how well an application is developed,

failures will eventually happen.

Examples include:

- Server Crash
- High CPU Usage
- Memory Leak
- Disk Full
- Database Failure
- Network Latency
- Application Errors
- Kubernetes Pod Failure

If you don't have monitoring,

you won't know about the problem until users start complaining.

Logging tells you **what happened**.

Monitoring tells you **what is happening**.

Together,

they help engineers detect, troubleshoot and resolve issues quickly.

---

# What You Will Learn

In this chapter, you will learn:

- Introduction to Monitoring
- Why Monitoring is Important
- Monitoring Architecture
- Metrics vs Logs vs Traces
- Prometheus
- Grafana
- Alertmanager
- Node Exporter
- kube-state-metrics
- Application Monitoring
- Centralized Logging
- Fluent Bit
- Fluentd
- Loki
- Elasticsearch
- Kibana
- EFK & PLG Stacks
- Alerting
- Dashboards
- Production Best Practices
- Troubleshooting
- Interview Questions

---

# Chapter Roadmap

```
10.1 Introduction to Monitoring

10.2 Why Monitoring?

10.3 Monitoring Architecture

10.4 Metrics vs Logs vs Traces

10.5 Prometheus

10.6 Prometheus Architecture

10.7 PromQL Basics

10.8 Node Exporter

10.9 kube-state-metrics

10.10 Alertmanager

10.11 Grafana

10.12 Grafana Dashboards

10.13 Logging Fundamentals

10.14 Fluent Bit

10.15 Fluentd

10.16 Loki

10.17 Elasticsearch

10.18 Kibana

10.19 EFK Stack

10.20 PLG Stack

10.21 Application Monitoring

10.22 Monitoring Kubernetes

10.23 Production Best Practices

10.24 Interview Questions
```

---

# Prerequisites

Before starting this chapter,

you should already understand:

- Linux
- Networking
- Docker
- Kubernetes
- Services
- Pods
- Deployments
- Helm

These concepts will help you understand monitoring tools much more easily.

---

# Learning Goal

By the end of this chapter,

you will be able to:

✔ Monitor Linux Servers

✔ Monitor Kubernetes Clusters

✔ Monitor Containers

✔ Build Dashboards

✔ Configure Alerts

✔ Collect Logs

✔ Troubleshoot Production Issues

✔ Explain Monitoring Architecture in Interviews

---

# Next Section

## 10.1 Introduction to Monitoring

In the next section, we will learn:

- What is Monitoring?
- What is Observability?
- Why Monitoring is Important
- Monitoring Workflow
- Enterprise Examples
- Best Practices
- Interview Questions
---

# 10.1 Introduction to Monitoring

Imagine your company has deployed an application.

```
Users

↓

Application

↓

Server
```

Everything works perfectly.

Then suddenly,

users begin reporting:

- Website is slow
- Login is failing
- Payments are timing out
- API is returning errors

Without monitoring,

the DevOps team doesn't know:

- What failed?
- When did it fail?
- Why did it fail?
- Which server is affected?
- Which application is causing the problem?

This is why Monitoring is one of the most critical parts of DevOps.

---

# What is Monitoring?

Monitoring is the process of continuously collecting, measuring and analyzing information about systems, applications and infrastructure.

Monitoring helps engineers understand:

- System Health
- Performance
- Resource Usage
- Availability
- Failures

before users are significantly affected.

---

# Simple Definition

```
Infrastructure

↓

Collect Metrics

↓

Analyze

↓

Detect Problems

↓

Alert Engineers
```

---

# Real World Example

Imagine driving a car.

The dashboard shows:

- Speed
- Fuel
- Engine Temperature
- RPM
- Battery

You don't wait until the engine stops.

You monitor the indicators continuously.

Monitoring in IT works the same way.

---

# Why Monitoring?

Without Monitoring

```
Application Failure

↓

Users Complain

↓

Engineers Start Investigating

↓

Long Downtime
```

---

With Monitoring

```
Application Issue

↓

Monitoring Detects

↓

Alert Generated

↓

Engineer Responds

↓

Reduced Downtime
```

---

# Monitoring Goals

A good monitoring system should answer:

- Is the application healthy?
- Is the server healthy?
- Are users experiencing errors?
- Is CPU utilization increasing?
- Is memory almost full?
- Is disk space running out?
- Is network latency increasing?
- Is the database responding?

---

# What Can We Monitor?

Almost everything.

Examples include:

### Infrastructure

- CPU
- Memory
- Disk
- Network
- Processes
- File Systems

---

### Applications

- Response Time
- Error Rate
- Requests per Second
- Active Users
- API Failures

---

### Kubernetes

- Nodes
- Pods
- Deployments
- ReplicaSets
- Services
- Containers
- Cluster Health

---

### Databases

- Connections
- Queries
- Replication
- Storage
- Slow Queries

---

### Cloud Resources

- EC2
- Load Balancers
- S3
- RDS
- EKS
- Azure VMs
- GKE

---

# Monitoring Workflow

```
Servers

↓

Applications

↓

Metrics Collection

↓

Monitoring Server

↓

Visualization

↓

Alerts

↓

Engineers
```

---

# Monitoring Architecture

```
Linux Servers

↓

Node Exporter

↓

Prometheus

↓

Alertmanager

↓

Grafana

↓

DevOps Team
```

This is one of the most common production monitoring architectures.

---

# What is Observability?

Monitoring tells you **that** something is wrong.

Observability helps explain **why** it is wrong.

Observability is built using three pillars:

```
Metrics

↓

Logs

↓

Traces
```

Together,

they provide a more complete understanding of system behavior.

---

# Monitoring vs Observability

| Monitoring | Observability |
|------------|---------------|
| Detects Problems | Explains Problems |
| Uses Metrics | Uses Metrics, Logs & Traces |
| Shows Health | Helps Find Root Cause |
| Reactive | Supports Deep Investigation |

---

# Passive vs Active Monitoring

### Passive Monitoring

Collects information continuously.

Examples:

- CPU Usage
- Memory Usage
- Disk Utilization

---

### Active Monitoring

Actively performs checks.

Examples:

- HTTP Health Check
- API Request
- Database Connection Test
- Ping Test

---

# Monitoring Lifecycle

```
Collect Data

↓

Store Metrics

↓

Analyze

↓

Visualize

↓

Alert

↓

Troubleshoot

↓

Improve
```

---

# Key Monitoring Metrics

Infrastructure Metrics:

- CPU %
- Memory %
- Disk Usage
- Disk IOPS
- Network Throughput

Application Metrics:

- Request Rate
- Error Rate
- Response Time
- Availability

Business Metrics:

- Orders per Minute
- Login Success Rate
- Revenue
- Active Users

---

# Monitoring Frequency

Different metrics require different collection intervals.

Typical examples:

| Metric | Common Collection Interval |
|---------|----------------------------|
| CPU | 15–60 seconds |
| Memory | 15–60 seconds |
| Disk | 1–5 minutes |
| HTTP Health Check | 30–60 seconds |
| Business Metrics | Depends on the application |

The appropriate interval depends on operational requirements and system scale.

---

# Enterprise Monitoring Example

Imagine an online banking application.

```
Customers

↓

Load Balancer

↓

Application Servers

↓

Database

↓

Monitoring

↓

Prometheus

↓

Grafana

↓

Alerts
```

If CPU usage reaches 95%,

Prometheus detects it.

Alertmanager sends an alert.

Grafana displays the issue on dashboards.

Engineers investigate before users experience widespread failures.

---

# Why Monitoring Matters in DevOps

Monitoring enables:

✔ Faster Detection

✔ Faster Recovery

✔ Better Reliability

✔ Improved User Experience

✔ Capacity Planning

✔ Performance Optimization

✔ Incident Response

✔ Root Cause Analysis

---

# Common Monitoring Tools

Popular tools include:

- Prometheus
- Grafana
- Alertmanager
- Zabbix
- Nagios
- Datadog
- New Relic
- Dynatrace

This chapter focuses primarily on Prometheus and Grafana because they are widely used in cloud-native environments.

---

# Common Beginner Mistakes

### Mistake 1

Monitoring only CPU usage.

Memory, disk, network, application health and business metrics are equally important.

---

### Mistake 2

Creating dashboards without configuring alerts.

Dashboards require someone to watch them; alerts notify engineers automatically.

---

### Mistake 3

Collecting excessive metrics.

Monitor meaningful metrics that support operational decisions.

---

### Mistake 4

Ignoring historical data.

Historical trends help identify recurring problems and support capacity planning.

---

### Mistake 5

Monitoring infrastructure but ignoring the application.

Healthy servers do not necessarily mean healthy applications.

---

# Interview Questions

### Q1. What is Monitoring?

Monitoring is the continuous process of collecting and analyzing metrics to understand system and application health.

---

### Q2. Why is Monitoring important?

It helps detect issues early, reduce downtime and improve system reliability.

---

### Q3. What are the three pillars of Observability?

- Metrics
- Logs
- Traces

---

### Q4. What is the difference between Monitoring and Observability?

Monitoring detects issues, while Observability provides the information needed to understand and troubleshoot them.

---

### Q5. Name three commonly used Monitoring tools.

- Prometheus
- Grafana
- Alertmanager

---

### Q6. What are examples of Infrastructure Metrics?

- CPU Usage
- Memory Usage
- Disk Usage
- Network Usage

---

# Production Best Practices

✔ Monitor infrastructure and applications together.

✔ Configure meaningful alerts.

✔ Retain historical metrics.

✔ Build dashboards for critical systems.

✔ Monitor business KPIs alongside technical metrics.

✔ Review alert thresholds regularly.

✔ Test monitoring during failure scenarios.

✔ Document monitoring architecture.

---

# Key Takeaways

- Monitoring continuously tracks system and application health.
- It enables early detection of failures and performance issues.
- Observability combines metrics, logs and traces for deeper troubleshooting.
- Monitoring is essential for production DevOps environments.
- Prometheus and Grafana form the foundation of many modern monitoring stacks.

---

# Next Section

## 10.2 Why Monitoring?

In the next section, we will learn:

- Problems Without Monitoring
- Business Impact
- Downtime Costs
- MTTR & MTTD
- SLA, SLO & SLI
- Enterprise Examples
- Best Practices
- Interview Questions
---

# 10.2 Why Monitoring?

Every production system will eventually experience problems.

Examples include:

- Server Failure
- High CPU Usage
- Memory Leak
- Database Failure
- Network Issues
- Disk Full
- Kubernetes Node Failure

The question is not:

**"Will something fail?"**

The real question is:

**"How quickly will we detect and fix it?"**

Monitoring exists to answer that question.

---

# Life Without Monitoring

Imagine your company hosts an e-commerce website.

```
Users

↓

Website

↓

Database
```

Suddenly,

the database crashes.

Without monitoring,

the sequence becomes:

```
Database Failure

↓

Website Stops

↓

Customers Notice

↓

Support Tickets

↓

DevOps Team Informed

↓

Investigation Begins
```

The business loses money before engineers even know there is a problem.

---

# Life With Monitoring

Now imagine the same situation.

```
Database Failure

↓

Prometheus Detects

↓

Alertmanager Sends Alert

↓

Engineer Notified

↓

Problem Fixed

↓

Users Hardly Notice
```

Monitoring significantly reduces downtime.

---

# Business Impact of Downtime

Downtime affects more than just servers.

It impacts:

- Customers
- Revenue
- Company Reputation
- Employee Productivity
- Customer Trust

Example

```
Application Down

↓

Customers Leave

↓

Revenue Loss

↓

Negative Reviews
```

Monitoring helps reduce these risks.

---

# Why Companies Invest in Monitoring

Large organizations monitor systems because they want:

✔ High Availability

✔ Better Performance

✔ Faster Troubleshooting

✔ Capacity Planning

✔ Security Monitoring

✔ Business Visibility

✔ Customer Satisfaction

---

# Problems Monitoring Solves

Monitoring helps detect:

- CPU Bottlenecks
- Memory Leaks
- Disk Exhaustion
- High Latency
- Failed Deployments
- Application Errors
- Database Issues
- Network Congestion

before they become major outages.

---

# Monitoring Benefits

```
Monitoring

↓

Detect Problems

↓

Alert Engineers

↓

Fix Issues

↓

Improve Reliability
```

---

# Early Detection

Suppose CPU usage starts increasing.

```
20%

↓

40%

↓

60%

↓

80%

↓

95%
```

Monitoring detects the trend before the server becomes unresponsive.

Engineers can scale or optimize the application in advance.

---

# Capacity Planning

Monitoring historical metrics helps answer questions such as:

- When will storage become full?
- Do we need more servers?
- Should CPU be upgraded?
- Is memory sufficient?

Historical data supports infrastructure planning.

---

# Performance Optimization

Monitoring reveals:

- Slow APIs
- Slow Database Queries
- High Response Time
- Cache Misses
- Network Latency

These insights help improve application performance.

---

# Incident Response

Monitoring reduces the time required to respond to incidents.

Typical workflow:

```
Issue

↓

Alert

↓

Engineer

↓

Diagnosis

↓

Fix

↓

Recovery
```

---

# MTTD (Mean Time To Detect)

MTTD measures how long it takes to detect a problem.

```
Failure

↓

Detection

↓

MTTD
```

Lower MTTD is better.

Monitoring helps reduce MTTD.

---

# MTTR (Mean Time To Recover)

MTTR measures how quickly a service is restored.

```
Failure

↓

Investigation

↓

Fix

↓

Service Restored
```

Organizations continuously work to reduce MTTR.

---

# Example

Without Monitoring

```
Failure

↓

Detected After

45 Minutes
```

With Monitoring

```
Failure

↓

Detected In

30 Seconds
```

Faster detection usually leads to faster recovery.

---

# SLA

SLA stands for:

```
Service Level Agreement
```

It is a commitment made to customers regarding service availability or performance.

Example

```
99.9% Availability
```

---

# SLO

SLO stands for:

```
Service Level Objective
```

It is the internal performance target.

Example

```
99.95% Uptime
```

Teams often set SLOs higher than contractual SLAs.

---

# SLI

SLI stands for:

```
Service Level Indicator
```

An SLI is the actual measurement.

Examples:

- Availability
- Response Time
- Error Rate
- Latency

---

# Relationship

```
SLI

↓

Measured Value

↓

Compared Against

↓

SLO

↓

Supports

↓

SLA
```

---

# Golden Signals

Google SRE recommends monitoring four Golden Signals.

```
Latency

Traffic

Errors

Saturation
```

These provide a strong starting point for application monitoring.

---

# RED Method

Used mainly for applications.

Monitor:

```
Request Rate

↓

Error Rate

↓

Duration
```

---

# USE Method

Used mainly for infrastructure.

Monitor:

```
Utilization

↓

Saturation

↓

Errors
```

---

# What Should Be Monitored?

### Infrastructure

- CPU
- Memory
- Disk
- Network
- Processes

---

### Application

- Response Time
- Error Rate
- Requests Per Second
- Availability

---

### Database

- Connections
- Slow Queries
- Replication
- Storage

---

### Kubernetes

- Nodes
- Pods
- Deployments
- Services
- Cluster Health

---

# Enterprise Example

Imagine a banking application.

```
Customers

↓

Load Balancer

↓

Application

↓

Database
```

Monitoring tracks:

- Login Success Rate
- Payment Success Rate
- API Latency
- Database Health
- CPU Usage

If any metric crosses a threshold,

an alert is generated automatically.

---

# Monitoring Workflow

```
Infrastructure

↓

Metrics

↓

Prometheus

↓

Alertmanager

↓

Grafana

↓

DevOps Team
```

---

# Cost of No Monitoring

Without monitoring,

organizations may face:

- Longer Downtime
- Revenue Loss
- SLA Violations
- Poor Customer Experience
- Increased Operational Costs

Monitoring is an investment in reliability.

---

# Common Beginner Mistakes

### Mistake 1

Waiting for users to report problems.

Monitoring should detect issues before customers do.

---

### Mistake 2

Monitoring only infrastructure.

Applications, databases and business metrics also need monitoring.

---

### Mistake 3

Ignoring alert tuning.

Too many unnecessary alerts can lead to alert fatigue.

---

### Mistake 4

Never reviewing historical trends.

Historical metrics support capacity planning and optimization.

---

### Mistake 5

Treating monitoring as a one-time setup.

Monitoring should evolve as applications and infrastructure change.

---

# Interview Questions

### Q1. Why is Monitoring important?

Monitoring helps detect issues early, reduce downtime and improve system reliability.

---

### Q2. What is MTTD?

Mean Time To Detect — the average time taken to detect an incident.

---

### Q3. What is MTTR?

Mean Time To Recover — the average time required to restore service after an incident.

---

### Q4. What is the difference between SLA, SLO and SLI?

- SLA: Customer commitment
- SLO: Internal target
- SLI: Measured performance metric

---

### Q5. What are Google's Four Golden Signals?

- Latency
- Traffic
- Errors
- Saturation

---

### Q6. What is the RED Method?

A monitoring approach focused on:

- Request Rate
- Error Rate
- Duration

---

# Production Best Practices

✔ Monitor infrastructure, applications and business metrics.

✔ Configure actionable alerts.

✔ Reduce MTTD and MTTR.

✔ Define meaningful SLIs and SLOs.

✔ Review historical trends regularly.

✔ Test monitoring during incident simulations.

✔ Document monitoring standards.

✔ Continuously improve alert thresholds.

---

# Key Takeaways

- Monitoring enables early detection of production issues.
- Lower MTTD and MTTR improve service reliability.
- SLI, SLO and SLA help measure and manage service quality.
- The Golden Signals, RED and USE methods are widely used monitoring approaches.
- Effective monitoring is essential for reliable production systems and successful DevOps operations.

---

# Next Section

## 10.3 Monitoring Architecture

In the next section, we will learn:

- Monitoring Components
- Data Collection Flow
- Pull vs Push Model
- Monitoring Pipeline
- Prometheus Architecture
- Visualization Layer
- Alert Flow
- Production Architecture
- Best Practices
- Interview Questions
---

# 10.3 Monitoring Architecture

Now that we understand **why monitoring is important**,

let's understand **how a monitoring system actually works**.

A monitoring solution is not a single software.

It is a collection of multiple components working together.

These components continuously collect,

store,

analyze,

visualize,

and alert on system data.

---

# What is Monitoring Architecture?

Monitoring Architecture is the complete flow of monitoring data,

from the server,

to the monitoring system,

to the engineer.

Simple architecture:

```
Server

↓

Metrics

↓

Monitoring Server

↓

Database

↓

Dashboard

↓

Alert

↓

Engineer
```

---

# Why Architecture Matters?

Without understanding architecture,

you may know the tools,

but not how they work together.

For example,

when CPU usage reaches 95%,

how does Grafana know?

How is an alert sent?

Which component collected the metric?

Architecture answers these questions.

---

# High-Level Architecture

```
Linux Servers

↓

Applications

↓

Exporters

↓

Prometheus

↓

Alertmanager

↓

Grafana

↓

DevOps Team
```

Each component performs a specific task.

---

# Monitoring Components

A typical monitoring architecture contains:

```
Infrastructure

↓

Metrics Collector

↓

Time-Series Database

↓

Visualization

↓

Alerting

↓

Engineers
```

---

# Complete Production Architecture

```
                 Applications

                       │

       ┌───────────────┴───────────────┐

       │                               │

 Linux Servers                  Kubernetes

       │                               │

       └───────────────┬───────────────┘

                       │

                 Exporters

       (Node Exporter, kube-state-metrics)

                       │

                       ▼

                 Prometheus

                       │

          ┌────────────┴─────────────┐

          │                          │

     Alertmanager               Grafana

          │                          │

          ▼                          ▼

 Email / Slack / Teams       Dashboards
```

---

# Monitoring Data Flow

The monitoring workflow is:

```
Server

↓

Exporter

↓

Metrics

↓

Prometheus

↓

Store Metrics

↓

Grafana

↓

Dashboard
```

If a threshold is crossed,

Alertmanager sends notifications.

---

# Step 1 – Infrastructure

Monitoring begins with the infrastructure.

Examples:

- Linux Server
- Virtual Machine
- Docker Container
- Kubernetes Node
- Database Server
- Web Server

These systems continuously generate metrics.

---

# Step 2 – Exporters

Applications usually do not expose metrics in a monitoring-friendly format.

Exporters collect metrics.

Examples:

- Node Exporter
- MySQL Exporter
- Blackbox Exporter
- Redis Exporter
- PostgreSQL Exporter
- kube-state-metrics

```
Server

↓

Exporter

↓

Metrics
```

---

# Step 3 – Metrics Collection

Prometheus periodically collects metrics.

This process is called:

```
Scraping
```

Workflow

```
Prometheus

↓

HTTP Request

↓

Exporter

↓

Metrics Returned
```

---

# Step 4 – Time-Series Database

Prometheus stores collected metrics.

Example

```
CPU

↓

Timestamp

↓

Value
```

Example data:

| Time | CPU |
|------|------|
|10:00|30%|
|10:01|42%|
|10:02|56%|

Monitoring systems store historical values over time.

---

# Step 5 – Visualization

Grafana connects to Prometheus.

```
Prometheus

↓

Grafana

↓

Dashboard
```

Grafana creates:

- Graphs
- Gauges
- Tables
- Heatmaps
- Alerts

---

# Step 6 – Alerting

Suppose:

```
CPU > 90%
```

Prometheus evaluates the alert rule.

```
Alert Rule

↓

Alertmanager

↓

Email

Slack

Teams

PagerDuty
```

Engineers receive notifications immediately.

---

# Push vs Pull Model

Monitoring systems generally use two collection methods.

```
Pull Model

Prometheus

↓

Exporter

------------------

Push Model

Application

↓

Monitoring Server
```

---

# Pull Model

Prometheus uses the Pull Model.

```
Prometheus

↓

Requests Metrics

↓

Exporter Responds
```

Advantages:

- Simple
- Reliable
- Easy Service Discovery

---

# Push Model

Some monitoring systems use Push.

```
Application

↓

Sends Metrics

↓

Monitoring Server
```

Examples:

- StatsD
- Telegraf
- Pushgateway (for specific Prometheus use cases)

---

# Why Prometheus Uses Pull?

Advantages:

✔ Automatic Discovery

✔ Simpler Health Checks

✔ Easier Scaling

✔ Better Control

✔ Centralized Collection

---

# Time-Series Data

Monitoring data changes over time.

Example

```
Time

↓

CPU %

↓

Memory %

↓

Network %

↓

Disk %
```

Every metric includes:

- Metric Name
- Timestamp
- Value
- Labels

---

# Metric Example

```
node_cpu_seconds_total

↓

Timestamp

↓

Value

↓

Labels
```

Example labels:

```
instance=server1

job=node-exporter

cpu=0
```

Labels allow filtering and aggregation.

---

# Monitoring Pipeline

```
Infrastructure

↓

Exporter

↓

Prometheus

↓

Time-Series Database

↓

Grafana

↓

Engineer
```

---

# Alert Pipeline

```
Metric

↓

Alert Rule

↓

Alertmanager

↓

Notification

↓

Engineer

↓

Incident Response
```

---

# Dashboard Workflow

```
Prometheus

↓

Query

↓

Grafana

↓

Dashboard

↓

User
```

Dashboards update automatically as new metrics arrive.

---

# Enterprise Monitoring Example

An e-commerce company runs:

- 50 Linux Servers
- 300 Kubernetes Nodes
- 2000 Pods
- 20 Databases

Monitoring architecture:

```
Infrastructure

↓

Exporters

↓

Prometheus

↓

Alertmanager

↓

Grafana

↓

DevOps Team
```

Thousands of metrics are collected every minute.

---

# High Availability Monitoring

Large organizations often deploy multiple Prometheus servers.

```
Servers

↓

Prometheus A

Prometheus B

↓

Grafana
```

This improves reliability and reduces the impact of monitoring component failures.

---

# Monitoring Architecture Summary

```
Infrastructure

↓

Exporters

↓

Prometheus

↓

Time-Series Database

↓

Grafana

↓

Dashboards

↓

Alertmanager

↓

Notifications

↓

Engineers
```

---

# Common Beginner Mistakes

### Mistake 1

Thinking Grafana stores monitoring data.

Grafana visualizes data.

Prometheus stores the metrics.

---

### Mistake 2

Confusing Exporters with Prometheus.

Exporters expose metrics.

Prometheus collects them.

---

### Mistake 3

Believing monitoring begins with Grafana.

Monitoring starts with infrastructure and metric collection.

---

### Mistake 4

Using Push when Pull is more appropriate.

Prometheus is designed primarily around the Pull model.

---

### Mistake 5

Ignoring historical metrics.

Historical data is valuable for trend analysis and capacity planning.

---

# Interview Questions

### Q1. What are the major components of a monitoring architecture?

- Exporters
- Prometheus
- Alertmanager
- Grafana

---

### Q2. What is an Exporter?

An Exporter exposes metrics from a system or application so Prometheus can collect them.

---

### Q3. What is Scraping?

Scraping is the process of Prometheus periodically collecting metrics from Exporters.

---

### Q4. What is the difference between the Pull and Push models?

In the Pull model, the monitoring system requests metrics.

In the Push model, applications send metrics to the monitoring system.

---

### Q5. Does Grafana store monitoring data?

No.

Grafana visualizes data stored in systems such as Prometheus.

---

### Q6. Why are labels important in Prometheus metrics?

Labels provide metadata that makes metrics easy to filter, group and aggregate.

---

# Production Best Practices

✔ Use the Pull model wherever possible.

✔ Deploy Exporters close to monitored systems.

✔ Separate metric collection from visualization.

✔ Build redundant monitoring for critical environments.

✔ Secure metric endpoints.

✔ Retain historical metrics.

✔ Document monitoring architecture.

✔ Test alert pipelines regularly.

---

# Key Takeaways

- Monitoring architecture consists of data collection, storage, visualization and alerting components.
- Exporters expose metrics that Prometheus scrapes.
- Prometheus stores metrics in a time-series database.
- Grafana visualizes metrics and builds dashboards.
- Alertmanager delivers notifications when alert conditions are met.
- Understanding monitoring architecture is essential before learning Prometheus.

---

# Next Section

## 10.4 Metrics vs Logs vs Traces

In the next section, we will learn:

- What are Metrics?
- What are Logs?
- What are Traces?
- Differences Between Metrics, Logs and Traces
- Observability
- Enterprise Examples
- Best Practices
- Interview Questions
---

# 10.4 Metrics vs Logs vs Traces

Modern production systems generate enormous amounts of data.

Imagine an e-commerce application.

```
Users

↓

Frontend

↓

Backend

↓

Database
```

Every second,

the system generates:

- CPU Usage
- API Requests
- Error Messages
- Login Attempts
- Database Queries
- Payment Transactions

Not all of this information is the same.

In modern observability,

this data is divided into three categories:

```
Metrics

Logs

Traces
```

These are known as the **Three Pillars of Observability**.

---

# Three Pillars of Observability

```
Observability

│

├── Metrics

├── Logs

└── Traces
```

Each pillar answers different questions.

---

# What are Metrics?

Metrics are **numerical measurements collected over time**.

Examples:

- CPU Usage
- Memory Usage
- Disk Usage
- Network Traffic
- Request Count
- Error Rate

Metrics answer questions like:

- Is the server healthy?
- Is CPU usage increasing?
- Is memory full?
- How many requests are arriving?

---

# Metrics Example

```
Time

10:00 → CPU 30%

10:01 → CPU 45%

10:02 → CPU 62%

10:03 → CPU 88%
```

Metrics are ideal for creating graphs and alerts.

---

# Characteristics of Metrics

✔ Numeric Values

✔ Time-Based

✔ Lightweight

✔ Efficient Storage

✔ Ideal for Dashboards

✔ Good for Alerting

---

# What are Logs?

Logs are detailed records of events generated by applications or systems.

Examples:

- User Login
- Payment Success
- API Error
- Server Startup
- Database Connection
- Authentication Failure

Logs answer questions like:

- What happened?
- When did it happen?
- Which user was affected?
- What error occurred?

---

# Log Example

```
2026-07-02 10:30:21

INFO

User Login Successful

User: Rahul
```

Another example:

```
2026-07-02 10:32:10

ERROR

Database Connection Failed
```

---

# Characteristics of Logs

✔ Detailed

✔ Human Readable

✔ Event-Based

✔ Useful for Troubleshooting

✔ High Storage Requirement

✔ Can Contain Stack Traces

---

# What are Traces?

Traces show how a single request travels through multiple services.

Example

```
User Request

↓

Frontend

↓

API Gateway

↓

Authentication

↓

Payment

↓

Database
```

A trace records the entire journey.

---

# Why Traces?

Suppose an API takes:

```
5 Seconds
```

Where is the delay?

```
Frontend?

Backend?

Database?

Cache?

Network?
```

Tracing helps answer these questions.

---

# Trace Example

```
Request

↓

Frontend

200 ms

↓

Backend

400 ms

↓

Database

3.8 sec

↓

Response
```

The trace clearly shows that the database is causing most of the delay.

---

# Characteristics of Traces

✔ Request Journey

✔ Distributed Systems

✔ Microservices

✔ Latency Analysis

✔ Root Cause Analysis

---

# Metrics vs Logs vs Traces

| Metrics | Logs | Traces |
|---------|------|---------|
| Numeric Data | Event Records | Request Flow |
| Lightweight | Detailed | End-to-End Journey |
| Best for Dashboards | Best for Debugging | Best for Performance Analysis |
| Time-Series | Text-Based | Request Timeline |

---

# Real Production Example

Imagine a customer places an order.

### Metrics

```
Orders Per Minute

↓

150
```

Shows business activity.

---

### Logs

```
Order Created

↓

Payment Completed

↓

Email Sent
```

Shows application events.

---

### Traces

```
Customer

↓

Frontend

↓

Payment Service

↓

Inventory

↓

Database

↓

Notification

↓

Response
```

Shows how the request moved through the system.

---

# Which Tool Uses What?

| Tool | Primary Data Type |
|------|--------------------|
| Prometheus | Metrics |
| Grafana | Metrics (and other supported data sources) |
| Fluent Bit | Logs |
| Fluentd | Logs |
| Loki | Logs |
| Elasticsearch | Logs |
| Jaeger | Traces |
| Zipkin | Traces |

---

# Observability Workflow

```
Application

│

├── Metrics

├── Logs

└── Traces

        ↓

Observability Platform

        ↓

Engineers
```

---

# Example Problem

A customer reports:

```
Payment Failed
```

Metrics show:

```
CPU Normal

Memory Normal
```

Logs show:

```
Database Authentication Failed
```

Trace shows:

```
Frontend

↓

Backend

↓

Database

↓

Failure
```

Together,

Metrics, Logs and Traces provide the complete picture.

---

# Which One Should You Use?

Need CPU usage?

```
Metrics
```

Need to know why login failed?

```
Logs
```

Need to identify where an API request is slow?

```
Traces
```

---

# Enterprise Architecture

```
Applications

│

├── Metrics → Prometheus

├── Logs → Loki / Elasticsearch

└── Traces → Jaeger

↓

Grafana

↓

DevOps Team
```

Grafana can visualize data from multiple observability sources.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Metrics replace Logs.

Metrics indicate that a problem exists.

Logs often explain what happened.

---

### Mistake 2

Ignoring Traces in microservices.

Distributed tracing is valuable when requests pass through many services.

---

### Mistake 3

Storing every possible log forever.

Define retention policies to balance troubleshooting needs and storage costs.

---

### Mistake 4

Alerting directly on log messages without careful planning.

Use meaningful alert rules to reduce noise.

---

### Mistake 5

Collecting data without dashboards or alerting.

Collected data should support operational decisions.

---

# Interview Questions

### Q1. What are Metrics?

Metrics are numerical measurements collected over time to monitor system and application health.

---

### Q2. What are Logs?

Logs are detailed records of events generated by systems and applications.

---

### Q3. What are Traces?

Traces record the complete path of a request across distributed services.

---

### Q4. Which pillar is best for dashboards?

```
Metrics
```

---

### Q5. Which pillar is best for debugging application errors?

```
Logs
```

---

### Q6. Which pillar is most useful for troubleshooting distributed microservices?

```
Traces
```

---

# Production Best Practices

✔ Collect Metrics, Logs and Traces together.

✔ Define appropriate retention policies.

✔ Correlate metrics with logs during investigations.

✔ Use distributed tracing for microservices.

✔ Build dashboards around critical business metrics.

✔ Configure actionable alerts.

✔ Review observability data regularly.

✔ Continuously refine dashboards and alert rules.

---

# Key Takeaways

- Metrics, Logs and Traces form the foundation of Observability.
- Metrics measure performance and resource utilization.
- Logs record detailed system and application events.
- Traces follow requests through distributed systems.
- Combining all three provides faster troubleshooting and better operational visibility.

---

# Next Section

## 10.5 Prometheus

In the next section, we will learn:

- What is Prometheus?
- Why Prometheus is Needed
- Prometheus Features
- Time-Series Database
- Pull Model
- Prometheus Components
- Production Use Cases
- Best Practices
- Interview Questions
---

# 10.5 Prometheus

Modern infrastructure can consist of:

- Hundreds of Linux Servers
- Thousands of Containers
- Multiple Kubernetes Clusters
- Databases
- Load Balancers
- APIs
- Cloud Services

Monitoring all of these manually is impossible.

A monitoring system must:

- Collect Metrics
- Store Historical Data
- Generate Alerts
- Support Dashboards
- Scale Efficiently

One of the most popular monitoring systems for cloud-native environments is **Prometheus**.

---

# What is Prometheus?

Prometheus is an open-source monitoring and alerting toolkit originally developed at SoundCloud.

Today,

it is one of the most widely used monitoring systems for:

- Kubernetes
- Docker
- Linux Servers
- Cloud Infrastructure
- Microservices

Prometheus is a graduated project of the **Cloud Native Computing Foundation (CNCF)**.

---

# Simple Definition

```
Servers

↓

Metrics

↓

Prometheus

↓

Store Metrics

↓

Grafana

↓

Dashboards

↓

Alerts
```

---

# Why Prometheus?

Imagine managing:

```
500 Servers

2000 Containers

5 Kubernetes Clusters
```

Checking CPU usage manually is impossible.

Prometheus automatically:

- Collects Metrics
- Stores Metrics
- Evaluates Rules
- Generates Alerts

---

# Why Companies Use Prometheus

Prometheus is popular because it offers:

✔ Open Source

✔ Cloud Native

✔ Kubernetes Integration

✔ Time-Series Database

✔ Powerful Query Language

✔ Built-in Alerting

✔ Easy Service Discovery

✔ Large Community

---

# Prometheus Architecture

```
Applications

↓

Exporters

↓

Prometheus Server

↓

Time-Series Database

↓

Grafana

↓

Dashboards
```

---

# Prometheus Components

```
Prometheus

│

├── Prometheus Server

├── Exporters

├── Time-Series Database

├── PromQL

├── Alert Rules

└── Alertmanager
```

Each component performs a specific role.

---

# Prometheus Server

The Prometheus Server is the core component.

Responsibilities:

- Scrape Metrics
- Store Metrics
- Execute Queries
- Evaluate Alert Rules

```
Exporter

↓

Prometheus Server

↓

Metrics Stored
```

---

# Time-Series Database

Prometheus stores metrics as **time-series data**.

Example

```
CPU

↓

Time

↓

Value
```

Example data:

| Time | CPU |
|------|------|
|10:00|35%|
|10:01|41%|
|10:02|58%|

This allows historical analysis and trend visualization.

---

# Pull Model

Prometheus uses the Pull Model.

```
Prometheus

↓

HTTP Request

↓

Exporter

↓

Metrics Returned
```

Prometheus periodically requests metrics from monitored targets.

---

# Exporters

Exporters expose metrics for Prometheus.

Popular Exporters:

- Node Exporter
- MySQL Exporter
- PostgreSQL Exporter
- Redis Exporter
- Blackbox Exporter
- kube-state-metrics

Example

```
Linux Server

↓

Node Exporter

↓

Prometheus
```

---

# Prometheus Workflow

```
Infrastructure

↓

Exporter

↓

Prometheus

↓

Store Metrics

↓

Query

↓

Grafana
```

---

# Scraping

Prometheus collects metrics at regular intervals.

This process is called:

```
Scraping
```

Example

```
Every 15 Seconds

↓

Collect CPU

↓

Collect Memory

↓

Collect Disk
```

The scrape interval is configurable.

---

# Metric Example

Prometheus metrics typically look like:

```
node_cpu_seconds_total

node_memory_MemAvailable_bytes

node_filesystem_size_bytes
```

Each metric has:

- Name
- Labels
- Value
- Timestamp

---

# Labels

Labels add metadata to metrics.

Example

```
node_cpu_seconds_total

instance="server1"

job="node-exporter"

cpu="0"
```

Labels make filtering and aggregation possible.

---

# PromQL

PromQL is the Prometheus Query Language.

It is used to query and analyze metrics.

Example

```promql
up
```

Returns the status of monitored targets.

---

Another example:

```promql
node_cpu_seconds_total
```

Returns CPU-related metrics.

PromQL will be covered in detail later in this chapter.

---

# Alert Rules

Prometheus continuously evaluates alert rules.

Example

```
CPU > 90%
```

Workflow

```
Metric

↓

Alert Rule

↓

Alertmanager

↓

Notification
```

---

# Service Discovery

Prometheus can automatically discover monitoring targets.

Examples:

- Kubernetes
- Docker
- EC2
- Consul

This reduces manual configuration.

---

# Data Retention

Prometheus stores historical metrics.

Typical retention periods include:

- 15 Days
- 30 Days
- 90 Days

The retention period depends on storage capacity and operational requirements.

---

# Prometheus Configuration

Main configuration file:

```
prometheus.yml
```

This file defines:

- Scrape Targets
- Scrape Interval
- Alert Rules
- Service Discovery
- Remote Storage

---

# High-Level Data Flow

```
Linux Server

↓

Node Exporter

↓

Prometheus

↓

PromQL

↓

Grafana

↓

Dashboard
```

---

# Enterprise Example

A company runs:

```
100 Linux Servers

↓

Node Exporter

↓

Prometheus

↓

Grafana

↓

Operations Dashboard
```

Prometheus continuously collects infrastructure metrics from all servers.

---

# Kubernetes Example

```
Pods

↓

kube-state-metrics

↓

Prometheus

↓

Grafana

↓

Cluster Dashboard
```

Prometheus monitors the health of Kubernetes resources.

---

# Prometheus Advantages

✔ Easy Installation

✔ Cloud Native

✔ Pull Model

✔ Powerful Queries

✔ Native Kubernetes Support

✔ Large Ecosystem

✔ Built-in Alerting

✔ Open Source

---

# Prometheus Limitations

Prometheus is excellent for metrics,

but it is **not designed to store logs or traces**.

Typical observability stack:

```
Metrics

↓

Prometheus

----------------

Logs

↓

Loki / Elasticsearch

----------------

Traces

↓

Jaeger
```

---

# Real Production Workflow

```
Linux Server

↓

Exporter

↓

Prometheus

↓

Alert Rules

↓

Alertmanager

↓

Slack

↓

DevOps Engineer
```

If CPU exceeds the configured threshold,

an alert is automatically generated.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Prometheus collects logs.

Prometheus collects metrics only.

---

### Mistake 2

Installing Grafana without Prometheus.

Grafana needs a data source.

Prometheus commonly provides that data.

---

### Mistake 3

Confusing Exporters with Prometheus.

Exporters expose metrics.

Prometheus collects them.

---

### Mistake 4

Using Prometheus as a long-term data warehouse.

Prometheus is optimized for operational monitoring.

Long-term storage often uses remote storage solutions.

---

### Mistake 5

Ignoring labels.

Labels are essential for effective querying and dashboard creation.

---

# Interview Questions

### Q1. What is Prometheus?

Prometheus is an open-source monitoring and alerting toolkit used to collect and store time-series metrics.

---

### Q2. What type of database does Prometheus use?

A time-series database.

---

### Q3. Which data collection model does Prometheus use?

The Pull Model.

---

### Q4. What is Scraping?

Scraping is the process of Prometheus periodically collecting metrics from exporters or applications.

---

### Q5. What is PromQL?

PromQL is the Prometheus Query Language used to query and analyze metrics.

---

### Q6. Does Prometheus collect logs?

No.

Prometheus is designed for metrics.

Logs are typically handled by systems such as Loki or Elasticsearch.

---

# Production Best Practices

✔ Use exporters instead of custom scripts whenever possible.

✔ Secure Prometheus endpoints.

✔ Configure meaningful retention periods.

✔ Label metrics consistently.

✔ Build dashboards in Grafana.

✔ Configure alert rules carefully.

✔ Monitor Prometheus itself.

✔ Back up configuration files.

---

# Key Takeaways

- Prometheus is a leading open-source monitoring system.
- It collects and stores time-series metrics.
- Prometheus uses the Pull Model to scrape metrics.
- Exporters expose metrics for Prometheus.
- PromQL enables powerful metric analysis.
- Prometheus is a core component of modern cloud-native monitoring.

---

# Next Section

## 10.6 Prometheus Architecture

In the next section, we will learn:

- Internal Components
- Scrape Workflow
- Service Discovery
- TSDB
- Alert Flow
- Query Engine
- Remote Storage
- Production Architecture
- Best Practices
- Interview Questions
---

# 10.6 Prometheus Architecture

In the previous section,

you learned what Prometheus is and why it is widely used.

Now let's understand **how Prometheus works internally**.

Understanding the architecture is essential because interviewers often ask:

- How does Prometheus collect metrics?
- Where are metrics stored?
- How are alerts generated?
- How does Grafana get monitoring data?

This section answers all of these questions.

---

# Prometheus Internal Architecture

```
                    Applications

                           │

         ┌─────────────────┴──────────────────┐

         │                                    │

   Linux Servers                     Kubernetes

         │                                    │

         └─────────────────┬──────────────────┘

                           │

                     Exporters

                           │

                     HTTP Metrics

                           │

                    Prometheus Server

         ┌────────────┬─────────────┬─────────────┐

         │            │             │

     TSDB        Rule Engine     PromQL Engine

         │            │             │

         └────────────┴─────────────┘

                      │

             Alertmanager

                      │

      Email / Slack / Teams / PagerDuty

                      │

                  Grafana

                      │

                 Dashboards
```

---

# Main Components

Prometheus consists of:

```
Prometheus

│

├── Exporters

├── Scrape Manager

├── TSDB

├── PromQL Engine

├── Rule Engine

├── Alertmanager

└── Service Discovery
```

---

# Exporters

Exporters expose metrics.

Examples:

```
Linux Server

↓

Node Exporter

↓

Metrics
```

Database Example

```
MySQL

↓

MySQL Exporter

↓

Metrics
```

---

# Scrape Manager

The Scrape Manager periodically requests metrics from exporters.

```
Prometheus

↓

HTTP GET

↓

Exporter

↓

Metrics
```

Default scrape interval is often configured as:

```
15 seconds
```

This value can be changed.

---

# Scrape Workflow

```
Exporter

↓

Metrics Endpoint

↓

Prometheus

↓

Store Metrics

↓

Evaluate Rules

↓

Dashboard
```

---

# Metrics Endpoint

Exporters expose metrics using HTTP.

Example

```
http://server:9100/metrics
```

Visiting the endpoint displays metrics similar to:

```
node_cpu_seconds_total

node_memory_MemAvailable_bytes

node_filesystem_size_bytes
```

---

# Time-Series Database (TSDB)

Prometheus stores metrics inside its built-in Time-Series Database.

Each metric consists of:

```
Metric Name

↓

Labels

↓

Timestamp

↓

Value
```

Example

```
node_memory_MemAvailable_bytes

instance=server01

value=2048000

time=10:15
```

---

# Why Time-Series?

Monitoring data changes continuously.

Example

| Time | CPU |
|------|------|
|10:00|20%|
|10:05|45%|
|10:10|65%|
|10:15|88%|

Prometheus stores every measurement with its timestamp.

---

# Labels

Labels uniquely identify metrics.

Example

```
node_cpu_seconds_total

instance="server01"

job="node-exporter"

cpu="0"

mode="idle"
```

Labels make filtering and aggregation easy.

---

# PromQL Engine

Prometheus uses PromQL to query metrics.

Workflow

```
User

↓

PromQL Query

↓

Prometheus

↓

Results
```

Example

```promql
up
```

Returns the status of monitored targets.

---

# Rule Engine

Prometheus continuously evaluates recording and alerting rules.

Example

```
CPU > 90%

↓

Alert Rule

↓

Triggered
```

---

# Alert Flow

```
Metric

↓

Prometheus Rule

↓

Alertmanager

↓

Notification

↓

Engineer
```

---

# Alertmanager

Alertmanager receives alerts from Prometheus.

Responsibilities:

- Group Alerts
- Remove Duplicate Alerts
- Silence Alerts
- Send Notifications

Supported notification channels include:

- Email
- Slack
- Microsoft Teams
- PagerDuty
- Webhooks

---

# Service Discovery

Instead of manually adding every server,

Prometheus can discover targets automatically.

Supported platforms include:

- Kubernetes
- Docker
- EC2
- Consul
- Azure
- GCE

Workflow

```
Infrastructure

↓

Service Discovery

↓

Targets

↓

Scraping
```

---

# Static Configuration

Example

```yaml
scrape_configs:

- job_name: node

  static_configs:

  - targets:

    - localhost:9100
```

Static configuration is suitable for small environments.

---

# Dynamic Discovery

In Kubernetes,

Pods are created and deleted frequently.

Prometheus automatically discovers them.

```
New Pod

↓

Kubernetes API

↓

Prometheus

↓

Monitoring Starts
```

No manual configuration is required.

---

# Prometheus Configuration File

Main configuration file:

```
prometheus.yml
```

Typical sections include:

```yaml
global:

scrape_configs:

rule_files:

alerting:
```

---

# Data Lifecycle

```
Exporter

↓

Scrape

↓

TSDB

↓

PromQL

↓

Grafana

↓

Dashboard
```

---

# Alert Lifecycle

```
Metric

↓

Threshold Crossed

↓

Alert Rule

↓

Alertmanager

↓

Notification

↓

Engineer
```

---

# Query Lifecycle

```
Grafana

↓

PromQL

↓

Prometheus

↓

TSDB

↓

Results

↓

Dashboard
```

---

# Remote Storage

Prometheus stores metrics locally.

For long-term storage,

organizations often integrate remote storage systems.

Examples:

- Thanos
- Cortex
- VictoriaMetrics
- Mimir

Workflow

```
Prometheus

↓

Remote Write

↓

Long-Term Storage
```

---

# Federation

Large organizations may deploy multiple Prometheus servers.

Federation allows one Prometheus server to collect selected metrics from others.

```
Prometheus A

Prometheus B

Prometheus C

↓

Central Prometheus
```

Useful for large-scale monitoring.

---

# High Availability

Production environments often deploy multiple Prometheus instances.

```
Exporters

↓

Prometheus A

Prometheus B

↓

Grafana
```

This improves resilience during maintenance or failures.

---

# Enterprise Architecture

```
Servers

↓

Exporters

↓

Prometheus Cluster

↓

Alertmanager

↓

Grafana

↓

DevOps Team
```

This architecture supports monitoring at enterprise scale.

---

# Common Beginner Mistakes

### Mistake 1

Thinking Prometheus pushes metrics.

Prometheus primarily **pulls** metrics.

---

### Mistake 2

Assuming Grafana stores monitoring data.

Grafana queries Prometheus but does not store metrics.

---

### Mistake 3

Ignoring labels.

Labels are essential for querying and aggregating metrics.

---

### Mistake 4

Using only static configurations in highly dynamic environments.

Service Discovery is better suited for Kubernetes and cloud environments.

---

### Mistake 5

Keeping all metrics only in local storage for long-term requirements.

Use remote storage solutions when long-term retention is needed.

---

# Interview Questions

### Q1. What are the main components of Prometheus?

- Exporters
- Scrape Manager
- TSDB
- PromQL Engine
- Rule Engine
- Alertmanager

---

### Q2. What is TSDB?

TSDB (Time-Series Database) is Prometheus' built-in database for storing metrics with timestamps.

---

### Q3. What is the purpose of the Scrape Manager?

It periodically collects metrics from exporters.

---

### Q4. What is Service Discovery?

A mechanism that automatically finds monitoring targets without manual configuration.

---

### Q5. Why are labels important?

Labels uniquely identify metrics and enable filtering, grouping and aggregation.

---

### Q6. What is Prometheus Federation?

Federation allows one Prometheus server to collect selected metrics from other Prometheus servers.

---

# Production Best Practices

✔ Use Service Discovery for dynamic environments.

✔ Configure meaningful scrape intervals.

✔ Use labels consistently.

✔ Deploy redundant Prometheus servers for critical environments.

✔ Use remote storage for long-term retention.

✔ Secure metric endpoints.

✔ Monitor Prometheus itself.

✔ Test alert rules regularly.

---

# Key Takeaways

- Prometheus consists of exporters, scraping, TSDB, PromQL, alerting and service discovery.
- Metrics are collected through the Pull model.
- TSDB stores time-series metrics efficiently.
- Alertmanager handles notifications.
- Service Discovery makes Prometheus ideal for Kubernetes and cloud-native environments.
- Understanding the architecture helps with troubleshooting and interview preparation.

---

# Next Section

## 10.7 PromQL Basics

In the next section, we will learn:

- What is PromQL?
- Query Types
- Instant vs Range Queries
- Functions
- Aggregation
- Filtering
- Labels
- Production Examples
- Interview Questions
---

# 10.7 PromQL Basics

Now that we understand how Prometheus collects and stores metrics,

the next question is:

**How do we retrieve those metrics?**

This is where **PromQL** comes in.

PromQL is one of the most important skills for every DevOps Engineer working with Prometheus.

Whether you want to:

- View CPU Usage
- Monitor Memory
- Calculate Request Rate
- Build Dashboards
- Create Alerts

you will use **PromQL**.

---

# What is PromQL?

PromQL stands for:

```
Prometheus Query Language
```

It is the query language used to retrieve and analyze metrics stored in Prometheus.

Think of it like:

```
SQL

↓

Database

----------------

PromQL

↓

Prometheus
```

SQL queries relational databases.

PromQL queries time-series metrics.

---

# Why PromQL?

Imagine Prometheus has collected millions of metrics.

How do we find:

- CPU Usage?
- Memory Usage?
- Pod Count?
- Error Rate?
- Network Traffic?

PromQL helps answer these questions.

---

# PromQL Workflow

```
Exporter

↓

Prometheus

↓

Metrics Stored

↓

PromQL Query

↓

Result

↓

Grafana Dashboard
```

---

# Query Types

PromQL supports two major query types.

```
PromQL

│

├── Instant Query

└── Range Query
```

---

# Instant Query

Returns the latest value.

Example

```promql
up
```

Result

```
1

1

1

0
```

Meaning:

```
1 = Healthy

0 = Down
```

---

# Range Query

Returns metric values over a period of time.

Example

```promql
node_cpu_seconds_total[5m]
```

Returns CPU metrics collected during the last 5 minutes.

---

# Metric Names

Every metric has a unique name.

Examples

```promql
up

node_cpu_seconds_total

node_memory_MemAvailable_bytes

node_filesystem_size_bytes
```

---

# Labels

Metrics contain labels.

Example

```
node_cpu_seconds_total

instance="server01"

job="node-exporter"

cpu="0"

mode="idle"
```

Labels make filtering possible.

---

# Query Using Labels

Example

```promql
up{job="node-exporter"}
```

Returns only Node Exporter targets.

---

Another example

```promql
up{instance="server01:9100"}
```

Returns metrics only for one server.

---

# Multiple Labels

```promql
up{job="node-exporter",instance="server01:9100"}
```

Both conditions must match.

---

# Comparison Operators

Examples

```promql
up == 1

up == 0

node_memory_MemAvailable_bytes > 1000000
```

Supported operators

```
==

!=

>

<

>=

<=
```

---

# Arithmetic Operations

Example

```promql
node_memory_MemAvailable_bytes /
node_memory_MemTotal_bytes
```

You can perform:

```
+

-

*

/
```

---

# Rate Function

One of the most common PromQL functions.

Example

```promql
rate(node_cpu_seconds_total[5m])
```

Calculates the per-second average increase over the last five minutes.

Used for:

- CPU
- Network
- Requests
- Counters

---

# Increase Function

Example

```promql
increase(http_requests_total[10m])
```

Returns how much the counter increased during the last 10 minutes.

---

# Sum Function

Example

```promql
sum(node_memory_MemAvailable_bytes)
```

Adds values together.

---

# Average Function

Example

```promql
avg(node_load1)
```

Returns the average.

---

# Maximum

```promql
max(node_load1)
```

---

# Minimum

```promql
min(node_load1)
```

---

# Count

```promql
count(up)
```

Returns the number of matching metrics.

---

# Aggregation

Example

```promql
sum by(instance)

(node_memory_MemAvailable_bytes)
```

Groups results by instance.

---

Another example

```promql
avg by(job)

(node_cpu_seconds_total)
```

---

# Topk

Find highest values.

Example

```promql
topk(5,node_load1)
```

Shows the top five highest values.

---

# Bottomk

Example

```promql
bottomk(5,node_load1)
```

Shows the lowest five values.

---

# Sort

Ascending

```promql
sort(node_load1)
```

Descending

```promql
sort_desc(node_load1)
```

---

# Time Range Selectors

Examples

```promql
[1m]

[5m]

[15m]

[30m]

[1h]

[24h]
```

---

# Logical Operators

Examples

```
and

or

unless
```

Useful for combining queries.

---

# Regular Expressions

Example

```promql
up{instance=~"server.*"}
```

Returns all instances beginning with:

```
server
```

---

# Alert Query Example

CPU Alert

```promql
100 -

(avg by(instance)

(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)

> 90
```

If CPU usage exceeds 90%,

an alert can be triggered.

---

# Memory Usage Example

Available Memory

```promql
node_memory_MemAvailable_bytes
```

Memory Usage %

```promql
100 *

(1 -

(node_memory_MemAvailable_bytes /

node_memory_MemTotal_bytes))
```

---

# Filesystem Usage

```promql
100 *

(1 -

(node_filesystem_avail_bytes /

node_filesystem_size_bytes))
```

---

# Network Traffic

Receive

```promql
rate(node_network_receive_bytes_total[5m])
```

Transmit

```promql
rate(node_network_transmit_bytes_total[5m])
```

---

# Request Rate

```promql
rate(http_requests_total[5m])
```

Very common in web applications.

---

# Error Rate

Example

```promql
rate(http_requests_total{status=~"5.."}[5m])
```

Calculates server error rate.

---

# Kubernetes Example

Running Pods

```promql
kube_pod_status_phase
```

Node Count

```promql
count(kube_node_info)
```

Container Restarts

```promql
increase(kube_pod_container_status_restarts_total[1h])
```

---

# Dashboard Workflow

```
Prometheus

↓

PromQL

↓

Grafana

↓

Dashboard
```

Every Grafana panel usually executes one or more PromQL queries.

---

# Enterprise Example

An organization monitors:

```
100 Servers

↓

Prometheus

↓

PromQL

↓

CPU Dashboard

↓

Memory Dashboard

↓

Disk Dashboard

↓

Alerts
```

Thousands of queries execute automatically every minute.

---

# Common Beginner Mistakes

### Mistake 1

Using the wrong metric name.

Always verify available metrics first.

---

### Mistake 2

Ignoring labels.

Labels are essential for filtering results correctly.

---

### Mistake 3

Using `rate()` on metrics that are not counters.

`rate()` is designed for monotonically increasing counters.

---

### Mistake 4

Writing complex queries before understanding simple ones.

Start with basic metric queries.

---

### Mistake 5

Forgetting the time range selector when using functions like `rate()` or `increase()`.

---

# Interview Questions

### Q1. What is PromQL?

PromQL is the Prometheus Query Language used to retrieve and analyze time-series metrics.

---

### Q2. What is the difference between an Instant Query and a Range Query?

- Instant Query returns the latest value.
- Range Query returns values over a specified time period.

---

### Q3. What is the purpose of labels in PromQL?

Labels identify and filter metrics, allowing grouping and aggregation.

---

### Q4. Which function is commonly used to calculate the rate of increase for counters?

```promql
rate()
```

---

### Q5. Which function returns the top N values?

```promql
topk()
```

---

### Q6. Why is PromQL important?

PromQL enables dashboards, alerting, capacity planning and troubleshooting by querying Prometheus metrics.

---

# Production Best Practices

✔ Learn commonly used infrastructure metrics.

✔ Use labels consistently.

✔ Keep dashboard queries efficient.

✔ Use aggregation functions for cluster-level metrics.

✔ Test alert queries before deploying them.

✔ Use recording rules for frequently executed complex queries.

✔ Document commonly used PromQL queries.

✔ Build reusable dashboards.

---

# Key Takeaways

- PromQL is the query language for Prometheus.
- It supports instant and range queries.
- Labels enable filtering and aggregation.
- Functions such as `rate()`, `sum()`, `avg()` and `topk()` are widely used.
- PromQL powers Grafana dashboards and Prometheus alert rules.
- Strong PromQL skills are essential for production monitoring and DevOps interviews.

---

# Next Section

## 10.8 Node Exporter

In the next section, we will learn:

- What is Node Exporter?
- Why Node Exporter is Needed
- Installation
- Exposed Metrics
- Prometheus Integration
- Common Metrics
- Production Best Practices
- Interview Questions
---

# 10.8 Node Exporter

Prometheus can collect metrics only if an application exposes them.

A Linux server itself does not automatically expose metrics in a Prometheus-compatible format.

To solve this,

Prometheus uses **Exporters**.

The most commonly used exporter for Linux servers is **Node Exporter**.

Node Exporter is one of the first components installed in almost every Prometheus monitoring setup.

---

# What is Node Exporter?

Node Exporter is an open-source Prometheus Exporter that collects hardware and operating system metrics from Linux systems.

It exposes these metrics over HTTP,

allowing Prometheus to scrape them.

---

# Simple Definition

```
Linux Server

↓

Node Exporter

↓

Metrics Endpoint

↓

Prometheus

↓

Grafana
```

---

# Why Node Exporter?

Without Node Exporter

```
Linux Server

↓

No Metrics

↓

Prometheus Cannot Monitor
```

---

With Node Exporter

```
Linux Server

↓

Node Exporter

↓

CPU

Memory

Disk

Network

↓

Prometheus
```

Prometheus can now monitor the server.

---

# What Does Node Exporter Monitor?

Node Exporter collects hundreds of system metrics.

Examples include:

- CPU Usage
- Memory Usage
- Disk Usage
- Disk I/O
- Network Traffic
- File Systems
- Load Average
- Boot Time
- Processes
- File Descriptors
- System Uptime

---

# Node Exporter Architecture

```
Linux Server

↓

Operating System

↓

Node Exporter

↓

HTTP Metrics

↓

Prometheus

↓

Grafana
```

---

# Installation Workflow

```
Download

↓

Extract

↓

Run Node Exporter

↓

Open Port 9100

↓

Configure Prometheus

↓

View Metrics
```

---

# Download Node Exporter

Example

```bash
wget https://github.com/prometheus/node_exporter/releases/latest/download/node_exporter-*.linux-amd64.tar.gz
```

Extract

```bash
tar -xvf node_exporter-*.tar.gz
```

---

# Run Node Exporter

```bash
./node_exporter
```

By default,

Node Exporter starts on:

```
Port 9100
```

---

# Verify Node Exporter

Open:

```
http://SERVER_IP:9100/metrics
```

You should see many Prometheus metrics.

Example

```
node_cpu_seconds_total

node_memory_MemAvailable_bytes

node_load1
```

---

# Configure Prometheus

Edit:

```
prometheus.yml
```

Example

```yaml
scrape_configs:

- job_name: node-exporter

  static_configs:

  - targets:

    - 192.168.1.10:9100
```

Reload Prometheus.

Prometheus now starts collecting server metrics.

---

# Verify Target

Open the Prometheus web interface.

Navigate to:

```
Status

↓

Targets
```

Healthy target:

```
UP
```

If the target is unreachable,

it will display:

```
DOWN
```

---

# Important Metrics

---

## CPU Metrics

Example

```text
node_cpu_seconds_total
```

Used for:

- CPU Usage
- CPU Idle
- CPU Busy
- CPU Core Statistics

---

## Memory Metrics

Example

```text
node_memory_MemAvailable_bytes

node_memory_MemTotal_bytes
```

Monitor:

- Free Memory
- Used Memory
- Cached Memory
- Buffers

---

## Disk Metrics

Examples

```text
node_filesystem_size_bytes

node_filesystem_avail_bytes
```

Used to calculate:

- Disk Usage
- Free Space
- Storage Capacity

---

## Disk I/O

Example

```text
node_disk_read_bytes_total

node_disk_written_bytes_total
```

Monitor:

- Read Speed
- Write Speed
- Storage Activity

---

## Network Metrics

Examples

```text
node_network_receive_bytes_total

node_network_transmit_bytes_total
```

Monitor:

- Incoming Traffic
- Outgoing Traffic
- Network Throughput

---

## System Load

Example

```text
node_load1

node_load5

node_load15
```

Represents average system load over:

- 1 Minute
- 5 Minutes
- 15 Minutes

---

## Uptime

Example

```text
node_time_seconds

node_boot_time_seconds
```

Used to calculate server uptime.

---

## Filesystem Metrics

Example

```text
node_filesystem_files

node_filesystem_files_free
```

Monitor inode usage.

---

## Process Metrics

Examples

```text
node_procs_running

node_procs_blocked
```

Useful for identifying process bottlenecks.

---

# Example PromQL Queries

CPU

```promql
100 -

(avg by(instance)

(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)
```

---

Memory

```promql
100 *

(1 -

(node_memory_MemAvailable_bytes /

node_memory_MemTotal_bytes))
```

---

Disk Usage

```promql
100 *

(1 -

(node_filesystem_avail_bytes /

node_filesystem_size_bytes))
```

---

Network Receive

```promql
rate(node_network_receive_bytes_total[5m])
```

---

Network Transmit

```promql
rate(node_network_transmit_bytes_total[5m])
```

---

# Enterprise Monitoring Example

Suppose an organization has:

```
50 Linux Servers
```

Each server runs:

```
Node Exporter

↓

Prometheus

↓

Grafana Dashboard
```

The DevOps team can monitor all servers from a single dashboard.

---

# Dashboard Example

Typical Linux dashboard includes:

- CPU Usage
- Memory Usage
- Disk Usage
- Disk I/O
- Network Traffic
- Load Average
- Uptime
- File System Usage

---

# Node Exporter Workflow

```
Linux Server

↓

Node Exporter

↓

Port 9100

↓

Prometheus

↓

PromQL

↓

Grafana
```

---

# Security Considerations

Node Exporter exposes system metrics.

Production recommendations:

✔ Restrict network access.

✔ Use firewalls.

✔ Place behind private networks when possible.

✔ Enable TLS or a reverse proxy if exposing externally.

✔ Monitor only trusted hosts.

---

# Common Beginner Mistakes

### Mistake 1

Installing Node Exporter but forgetting to add it to `prometheus.yml`.

Prometheus cannot scrape metrics until the target is configured.

---

### Mistake 2

Port **9100** blocked by a firewall.

Prometheus cannot reach Node Exporter.

---

### Mistake 3

Thinking Node Exporter monitors applications.

Node Exporter monitors the operating system.

Applications often require their own exporters.

---

### Mistake 4

Using Node Exporter for Windows.

Windows uses **windows_exporter** (formerly WMI Exporter).

---

### Mistake 5

Ignoring filesystem metrics.

Running out of disk space is a common production issue.

---

# Interview Questions

### Q1. What is Node Exporter?

Node Exporter is a Prometheus Exporter that exposes Linux operating system metrics.

---

### Q2. Which default port does Node Exporter use?

```
9100
```

---

### Q3. What kind of metrics does Node Exporter expose?

- CPU
- Memory
- Disk
- Network
- Load
- File Systems
- Processes

---

### Q4. How does Prometheus collect Node Exporter metrics?

By scraping the `/metrics` HTTP endpoint.

---

### Q5. Does Node Exporter monitor applications?

No.

It primarily monitors the Linux operating system and hardware.

---

### Q6. Where can you verify that Prometheus is successfully scraping Node Exporter?

In the Prometheus web UI:

```
Status

↓

Targets
```

---

# Production Best Practices

✔ Install Node Exporter on every Linux server.

✔ Secure port **9100**.

✔ Label servers consistently.

✔ Monitor disk usage and inode usage.

✔ Build reusable Grafana dashboards.

✔ Configure alerts for CPU, memory and disk thresholds.

✔ Keep Node Exporter updated.

✔ Monitor Node Exporter availability itself.

---

# Key Takeaways

- Node Exporter is the standard Prometheus Exporter for Linux servers.
- It exposes operating system metrics over HTTP.
- Prometheus scrapes metrics from port **9100** by default.
- Grafana visualizes these metrics through dashboards.
- Node Exporter is one of the most widely deployed components in Prometheus-based monitoring systems.

---

# Next Section

## 10.9 kube-state-metrics

In the next section, we will learn:

- What is kube-state-metrics?
- Why Kubernetes Needs kube-state-metrics
- Installation
- Kubernetes Object Metrics
- Prometheus Integration
- Dashboard Examples
- Production Best Practices
- Interview Questions
---

# 10.9 kube-state-metrics

Monitoring a Kubernetes cluster involves two different kinds of information.

The first type is **Node Metrics**.

Examples:

- CPU Usage
- Memory Usage
- Disk Usage
- Network Traffic

These metrics come from **Node Exporter**.

However,

there is another type of information that Node Exporter cannot provide.

Examples:

- Number of Pods
- Deployment Status
- Replica Count
- Namespace Information
- StatefulSet Status
- DaemonSet Status
- Job Status

These are **Kubernetes Object Metrics**.

To collect them,

Prometheus uses **kube-state-metrics**.

---

# What is kube-state-metrics?

kube-state-metrics is an open-source service that listens to the Kubernetes API Server and exposes metrics about Kubernetes objects.

Unlike Node Exporter,

it does **not** monitor CPU or memory usage.

Instead,

it reports the current state of Kubernetes resources.

---

# Simple Definition

```
Kubernetes API

↓

kube-state-metrics

↓

Prometheus

↓

Grafana
```

---

# Why kube-state-metrics?

Without kube-state-metrics

```
Prometheus

↓

CPU

Memory

Disk

↓

No Deployment Information
```

---

With kube-state-metrics

```
Prometheus

↓

Pods

Deployments

Namespaces

ReplicaSets

Jobs

DaemonSets

↓

Complete Cluster Visibility
```

---

# Difference Between Node Exporter and kube-state-metrics

```
Node Exporter

↓

Linux Metrics

----------------

kube-state-metrics

↓

Kubernetes Object Metrics
```

Both are commonly deployed together.

---

# Architecture

```
Kubernetes API Server

↓

kube-state-metrics

↓

Prometheus

↓

Grafana

↓

Dashboards
```

---

# How It Works

kube-state-metrics watches Kubernetes resources.

Whenever a resource changes,

it updates its metrics.

Workflow

```
Pod Created

↓

API Server Updated

↓

kube-state-metrics

↓

Prometheus Scrapes

↓

Grafana Updates
```

---

# Installation

The easiest method is Helm.

Example

```bash
helm repo add prometheus-community \
https://prometheus-community.github.io/helm-charts

helm repo update

helm install kube-state-metrics \
prometheus-community/kube-state-metrics
```

---

# Verify Installation

```bash
kubectl get pods -n default
```

or in the namespace where it is installed.

Example

```
kube-state-metrics-xxxxx
```

---

# Metrics Endpoint

By default,

Prometheus scrapes metrics exposed by kube-state-metrics.

Example endpoint

```
http://kube-state-metrics:8080/metrics
```

---

# What Does kube-state-metrics Monitor?

Examples include:

- Pods
- Deployments
- ReplicaSets
- StatefulSets
- DaemonSets
- Jobs
- CronJobs
- Nodes
- Namespaces
- Persistent Volumes
- Persistent Volume Claims
- Services
- ConfigMaps
- Secrets (metadata only, not secret values)

---

# Common Metrics

---

## Pod Metrics

Example

```text
kube_pod_info

kube_pod_status_phase

kube_pod_created
```

Useful for:

- Pod Count
- Pod Status
- Pod Age

---

## Deployment Metrics

Example

```text
kube_deployment_status_replicas

kube_deployment_spec_replicas
```

Monitor:

- Desired Replicas
- Available Replicas
- Updated Replicas

---

## ReplicaSet Metrics

Example

```text
kube_replicaset_status_replicas
```

---

## StatefulSet Metrics

Example

```text
kube_statefulset_status_replicas
```

---

## DaemonSet Metrics

Example

```text
kube_daemonset_status_number_ready
```

---

## Namespace Metrics

Example

```text
kube_namespace_created
```

---

## Node Metrics

Example

```text
kube_node_info
```

Provides Kubernetes node metadata.

---

## PVC Metrics

Example

```text
kube_persistentvolumeclaim_status_phase
```

Useful for monitoring storage claims.

---

## Job Metrics

Example

```text
kube_job_status_succeeded

kube_job_status_failed
```

---

# Example PromQL Queries

Number of Nodes

```promql
count(kube_node_info)
```

---

Running Pods

```promql
count(kube_pod_status_phase{phase="Running"})
```

---

Failed Pods

```promql
count(kube_pod_status_phase{phase="Failed"})
```

---

Deployment Replicas

```promql
kube_deployment_status_replicas
```

---

Available Deployments

```promql
kube_deployment_status_replicas_available
```

---

Namespaces

```promql
count(kube_namespace_created)
```

---

PVC Count

```promql
count(kube_persistentvolumeclaim_info)
```

---

Failed Jobs

```promql
kube_job_status_failed
```

---

# Dashboard Example

A Kubernetes dashboard may display:

- Running Pods
- Pending Pods
- Failed Pods
- Node Count
- Deployment Status
- Namespace Count
- ReplicaSet Status
- StatefulSet Health
- PVC Status

---

# Monitoring Workflow

```
Kubernetes Cluster

↓

API Server

↓

kube-state-metrics

↓

Prometheus

↓

Grafana

↓

Dashboard
```

---

# Enterprise Example

Suppose an organization runs:

```
10 Kubernetes Clusters

↓

kube-state-metrics

↓

Prometheus

↓

Grafana

↓

Operations Dashboard
```

Engineers can monitor thousands of Kubernetes resources in real time.

---

# Node Exporter vs kube-state-metrics

| Node Exporter | kube-state-metrics |
|---------------|--------------------|
| Linux Metrics | Kubernetes Object Metrics |
| CPU | Pods |
| Memory | Deployments |
| Disk | ReplicaSets |
| Network | StatefulSets |
| Load | Namespaces |

Both are required for complete Kubernetes monitoring.

---

# Common Beginner Mistakes

### Mistake 1

Expecting kube-state-metrics to report CPU or memory usage.

Those metrics come from Node Exporter or other resource metrics providers.

---

### Mistake 2

Thinking kube-state-metrics modifies Kubernetes objects.

It is read-only.

---

### Mistake 3

Installing Node Exporter but forgetting kube-state-metrics.

You will miss Kubernetes object-level metrics.

---

### Mistake 4

Confusing Kubernetes object metrics with application metrics.

Applications may expose their own metrics separately.

---

### Mistake 5

Ignoring Deployment and Pod health metrics.

Cluster resource state is just as important as infrastructure metrics.

---

# Interview Questions

### Q1. What is kube-state-metrics?

kube-state-metrics exposes metrics about the current state of Kubernetes objects.

---

### Q2. Does kube-state-metrics collect CPU and memory metrics?

No.

It collects Kubernetes object state, not operating system resource usage.

---

### Q3. Where does kube-state-metrics get its information?

From the Kubernetes API Server.

---

### Q4. What kinds of resources does kube-state-metrics monitor?

- Pods
- Deployments
- ReplicaSets
- StatefulSets
- DaemonSets
- Namespaces
- Jobs
- PVCs
- Nodes

---

### Q5. Why are Node Exporter and kube-state-metrics both needed?

Node Exporter provides infrastructure metrics, while kube-state-metrics provides Kubernetes object metrics.

---

### Q6. Which monitoring system typically scrapes kube-state-metrics?

```
Prometheus
```

---

# Production Best Practices

✔ Deploy kube-state-metrics in every Kubernetes cluster.

✔ Use it together with Node Exporter.

✔ Monitor Pod and Deployment health.

✔ Build Grafana dashboards using Kubernetes object metrics.

✔ Configure alerts for failed Pods and unavailable Deployments.

✔ Keep kube-state-metrics updated.

✔ Secure access to the metrics endpoint.

✔ Monitor kube-state-metrics itself.

---

# Key Takeaways

- kube-state-metrics exposes the state of Kubernetes resources.
- It complements Node Exporter by providing Kubernetes object metrics.
- Prometheus scrapes these metrics and Grafana visualizes them.
- It is essential for monitoring Pods, Deployments, StatefulSets, Jobs and other Kubernetes resources.
- Together, Node Exporter and kube-state-metrics provide a complete view of Kubernetes infrastructure and cluster health.

---

# Next Section

## 10.10 Alertmanager

In the next section, we will learn:

- What is Alertmanager?
- Why Alertmanager is Needed
- Alert Workflow
- Alert Rules
- Routing
- Grouping
- Silencing
- Notification Channels
- Production Best Practices
- Interview Questions
---

# 10.10 Alertmanager

Collecting metrics is only half of monitoring.

Imagine a production server.

```
CPU

↓

98%
```

Prometheus knows the CPU is high.

But if nobody is informed,

the problem remains unnoticed.

This is where **Alertmanager** comes in.

Alertmanager is responsible for notifying the right people at the right time.

Without Alertmanager,

Prometheus would collect metrics,

but engineers might never know something is wrong.

---

# What is Alertmanager?

Alertmanager is an open-source component of the Prometheus ecosystem responsible for handling alerts generated by Prometheus.

It receives alerts,

groups them,

filters duplicates,

applies routing rules,

and sends notifications.

---

# Simple Definition

```
Prometheus

↓

Alertmanager

↓

Engineer
```

---

# Why Alertmanager?

Without Alertmanager

```
Prometheus

↓

CPU 98%

↓

No Notification
```

---

With Alertmanager

```
Prometheus

↓

Alertmanager

↓

Slack

↓

Email

↓

PagerDuty

↓

Engineer
```

---

# Alert Flow

```
Metric

↓

Alert Rule

↓

Prometheus

↓

Alertmanager

↓

Notification

↓

Engineer
```

---

# Complete Architecture

```
Node Exporter

↓

Prometheus

↓

Alert Rule

↓

Alertmanager

↓

Email

Slack

Teams

PagerDuty

↓

DevOps Engineer
```

---

# Alert Lifecycle

```
Metric Collected

↓

Rule Evaluated

↓

Threshold Crossed

↓

Alert Fired

↓

Notification Sent

↓

Issue Fixed

↓

Alert Resolved
```

---

# Why Not Send Alerts Directly?

Prometheus intentionally delegates notification management.

Alertmanager provides:

✔ Alert Routing

✔ Alert Grouping

✔ Duplicate Suppression

✔ Silencing

✔ Scheduling

✔ Notification Retry

---

# Alert Rules

Prometheus defines alert rules.

Example

```yaml
groups:

- name: cpu-alerts

  rules:

  - alert: HighCPUUsage

    expr: 100 -

      (avg by(instance)

      (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)

      > 90

    for: 5m

    labels:

      severity: critical

    annotations:

      summary: High CPU Usage
```

---

# Understanding the Rule

```
CPU Usage

↓

Greater Than 90%

↓

For 5 Minutes

↓

Fire Alert
```

The `for` field prevents alerts from firing due to short-lived spikes.

---

# Alert States

Alerts move through different states.

```
Inactive

↓

Pending

↓

Firing

↓

Resolved
```

---

# Inactive

Condition is false.

Example

```
CPU = 35%
```

No alert.

---

# Pending

Condition became true,

but the `for` duration has not yet elapsed.

Example

```
CPU = 95%

↓

2 Minutes

↓

Waiting
```

---

# Firing

Condition remains true for the configured duration.

```
CPU = 95%

↓

5 Minutes

↓

Alert Fired
```

---

# Resolved

Metric returns to normal.

```
CPU = 30%

↓

Alert Cleared
```

---

# Notification Channels

Alertmanager supports many destinations.

Examples:

- Email
- Slack
- Microsoft Teams
- PagerDuty
- Opsgenie
- Discord
- Webhooks

---

# Routing

Different alerts can be sent to different teams.

Example

```
CPU Alerts

↓

Infrastructure Team

----------------

Database Alerts

↓

DBA Team

----------------

Application Alerts

↓

Development Team
```

---

# Routing Example

```yaml
route:

  receiver: default

  routes:

  - match:

      severity: critical

    receiver: pagerduty
```

Critical alerts go to PagerDuty.

---

# Receivers

Receivers define where notifications are sent.

Example

```yaml
receivers:

- name: email-team

- name: slack-team

- name: pagerduty
```

---

# Grouping

Without grouping,

100 failing servers could generate:

```
100 Emails
```

With grouping,

```
100 Alerts

↓

1 Notification
```

Grouping reduces alert noise.

---

# Group By Example

```yaml
group_by:

- alertname

- instance
```

Alerts with matching labels are grouped together.

---

# Duplicate Suppression

Suppose:

```
CPU Alert

↓

Sent

↓

Still High
```

Alertmanager avoids repeatedly sending the same notification within configured intervals.

---

# Silencing

Sometimes maintenance is planned.

Example

```
Server Upgrade

↓

CPU High

↓

Ignore Alerts

↓

Maintenance Complete
```

Silences temporarily suppress notifications without deleting alert rules.

---

# Inhibition

Suppose a server goes down.

This may also trigger:

- CPU Alert
- Memory Alert
- Disk Alert

Instead of sending multiple alerts,

Alertmanager can suppress dependent alerts when a higher-priority alert is already active.

---

# Retry Mechanism

If notification delivery fails,

Alertmanager retries according to its configuration.

```
Send Notification

↓

Failed

↓

Retry

↓

Delivered
```

---

# Alertmanager Configuration

Main configuration file:

```
alertmanager.yml
```

Common sections include:

```yaml
route:

receivers:

templates:

inhibit_rules:
```

---

# Email Example

```yaml
receivers:

- name: email-team

  email_configs:

  - to: devops@example.com
```

---

# Slack Example

```yaml
receivers:

- name: slack-team

  slack_configs:

  - channel: "#alerts"
```

---

# Enterprise Workflow

```
Linux Server

↓

Node Exporter

↓

Prometheus

↓

Alertmanager

↓

Slack

↓

On-Call Engineer

↓

Issue Fixed
```

---

# Real Production Example

A production Kubernetes cluster monitors:

- CPU
- Memory
- Disk
- Node Health
- Pod Health
- Deployment Status

Whenever a critical issue occurs,

Alertmanager automatically notifies the on-call engineer.

---

# Common Alert Examples

Examples include:

- CPU > 90%
- Memory > 85%
- Disk > 80%
- Node Down
- Pod CrashLoopBackOff
- Deployment Unavailable
- Certificate Expiring Soon
- High API Error Rate

---

# Common Beginner Mistakes

### Mistake 1

Creating alert rules without configuring Alertmanager.

Alerts are generated but never delivered.

---

### Mistake 2

Using thresholds that are too aggressive.

This creates unnecessary alerts.

---

### Mistake 3

Ignoring the `for` field.

Transient spikes can trigger noisy alerts.

---

### Mistake 4

Sending every alert to every engineer.

Use routing based on ownership and severity.

---

### Mistake 5

Never testing alert rules.

Always verify that notifications reach the intended recipients.

---

# Interview Questions

### Q1. What is Alertmanager?

Alertmanager is the Prometheus component responsible for receiving, grouping, routing and sending alert notifications.

---

### Q2. Does Prometheus send emails directly?

No.

Prometheus evaluates alert rules and sends alerts to Alertmanager, which handles notifications.

---

### Q3. What is the purpose of the `for` field in an alert rule?

It ensures that a condition remains true for a specified duration before the alert fires.

---

### Q4. What is alert grouping?

Grouping combines similar alerts into fewer notifications to reduce alert noise.

---

### Q5. What is alert silencing?

Silencing temporarily suppresses notifications, commonly during planned maintenance.

---

### Q6. Name five notification channels supported by Alertmanager.

- Email
- Slack
- Microsoft Teams
- PagerDuty
- Webhooks

---

# Production Best Practices

✔ Use meaningful alert thresholds.

✔ Configure the `for` field to avoid false positives.

✔ Group related alerts.

✔ Route alerts to the correct teams.

✔ Test alert delivery regularly.

✔ Silence alerts during planned maintenance.

✔ Keep Alertmanager configuration under version control.

✔ Review and tune alerts to reduce alert fatigue.

---

# Key Takeaways

- Alertmanager handles notifications generated from Prometheus alerts.
- It supports routing, grouping, silencing and duplicate suppression.
- Alert rules are evaluated by Prometheus, while Alertmanager manages delivery.
- Well-designed alerting reduces downtime and speeds incident response.
- Alertmanager is a critical component of every production Prometheus monitoring stack.

---

# Next Section

## 10.11 Grafana

In the next section, we will learn:

- What is Grafana?
- Why Grafana is Needed
- Grafana Architecture
- Data Sources
- Dashboards
- Panels
- Variables
- Alerting
- Production Best Practices
- Interview Questions
---

# 10.11 Grafana

Collecting metrics is important,

but raw numbers are difficult to understand.

For example,

suppose Prometheus returns:

```
node_cpu_seconds_total

324567.23
```

Does this mean the server is healthy?

Most engineers cannot determine system health by looking at raw metrics.

This is why **Grafana** is used.

Grafana converts metrics into beautiful dashboards,

making monitoring easy to understand.

---

# What is Grafana?

Grafana is an open-source visualization and analytics platform.

It connects to monitoring systems,

queries their data,

and displays the results as dashboards.

Grafana does **not** collect metrics itself.

Instead,

it retrieves data from data sources such as Prometheus.

---

# Simple Definition

```
Prometheus

↓

Grafana

↓

Dashboards

↓

Engineers
```

---

# Why Grafana?

Without Grafana

```
Prometheus

↓

Thousands of Metrics

↓

Difficult to Read
```

---

With Grafana

```
Prometheus

↓

Grafana

↓

Charts

↓

Dashboards

↓

Easy Monitoring
```

---

# Grafana Architecture

```
Infrastructure

↓

Prometheus

↓

Grafana

↓

Dashboard

↓

DevOps Engineer
```

---

# Grafana Workflow

```
Prometheus

↓

PromQL Query

↓

Grafana

↓

Visualization

↓

Dashboard
```

---

# What Can Grafana Visualize?

Grafana supports:

- Line Charts
- Bar Charts
- Pie Charts
- Gauges
- Tables
- Heatmaps
- Stat Panels
- Time Series Graphs
- Logs
- Traces

---

# Data Sources

Grafana supports many data sources.

Examples:

- Prometheus
- Loki
- Elasticsearch
- InfluxDB
- MySQL
- PostgreSQL
- Graphite
- CloudWatch
- Azure Monitor
- Google Cloud Monitoring

One Grafana instance can connect to multiple data sources simultaneously.

---

# Dashboard

A Dashboard is a collection of panels that display related metrics.

Example

```
Linux Dashboard

↓

CPU

Memory

Disk

Network
```

Each dashboard provides a quick overview of system health.

---

# Panels

Dashboards consist of Panels.

Example

```
Dashboard

│

├── CPU Panel

├── Memory Panel

├── Disk Panel

└── Network Panel
```

Each panel displays one or more queries.

---

# Example Panel Query

Grafana uses PromQL when Prometheus is the data source.

Example

```promql
100 -

(avg by(instance)

(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)
```

The result is displayed as a graph or gauge.

---

# Dashboard Variables

Variables make dashboards reusable.

Example

Instead of creating one dashboard per server,

create a variable.

```
Instance

↓

server01

server02

server03
```

Users select the server from a drop-down menu.

---

# Time Range

Grafana supports different time ranges.

Examples:

```
Last 5 Minutes

Last 1 Hour

Last 24 Hours

Last 7 Days

Last 30 Days
```

Dashboards automatically refresh based on the selected range.

---

# Auto Refresh

Grafana dashboards can refresh automatically.

Examples:

```
5 Seconds

10 Seconds

30 Seconds

1 Minute
```

Useful for production monitoring.

---

# Dashboard Layout Example

```
Linux Dashboard

--------------------------------

CPU Usage

Memory Usage

--------------------------------

Disk Usage

Network Usage

--------------------------------

Load Average

System Uptime
```

---

# Kubernetes Dashboard

Typical Kubernetes dashboards display:

- Cluster Health
- Node Status
- Pod Status
- Deployment Status
- Namespace Usage
- CPU Usage
- Memory Usage
- Network Traffic

---

# Alerting

Grafana also supports alerting.

Workflow

```
PromQL Query

↓

Threshold

↓

Grafana Alert

↓

Email

Slack

Teams
```

In many environments, Prometheus Alertmanager remains the primary alerting component, while Grafana alerting is used where appropriate.

---

# Dashboard Sharing

Dashboards can be:

- Exported
- Imported
- Shared
- Version Controlled

Dashboards are stored as JSON.

---

# Dashboard Export

Example

```
Dashboard

↓

Export JSON

↓

Git Repository
```

This makes dashboards portable across environments.

---

# Folder Organization

Organize dashboards into folders.

Example

```
Production

Development

Kubernetes

Linux

Databases

Applications
```

---

# Enterprise Example

A company monitors:

```
200 Linux Servers

↓

Prometheus

↓

Grafana

↓

Linux Dashboard

↓

Operations Team
```

The Operations Team monitors all infrastructure from one location.

---

# Common Dashboards

Examples:

- Linux Monitoring
- Kubernetes Cluster
- Docker Containers
- NGINX
- MySQL
- PostgreSQL
- JVM Applications
- Redis
- Kafka

Grafana Labs also provides many community dashboards.

---

# Dashboard Workflow

```
Infrastructure

↓

Exporter

↓

Prometheus

↓

PromQL

↓

Grafana

↓

Dashboard
```

---

# Benefits of Grafana

✔ Beautiful Dashboards

✔ Multiple Data Sources

✔ Powerful Visualizations

✔ Variables

✔ Alerting

✔ Dashboard Sharing

✔ Community Dashboards

✔ Open Source

---

# Common Beginner Mistakes

### Mistake 1

Thinking Grafana stores metrics.

Grafana visualizes data.

The data is stored in systems such as Prometheus.

---

### Mistake 2

Creating one dashboard per server.

Use dashboard variables instead.

---

### Mistake 3

Adding too many panels.

Keep dashboards simple and focused.

---

### Mistake 4

Using slow or inefficient queries.

Optimize PromQL queries for better dashboard performance.

---

### Mistake 5

Ignoring dashboard permissions.

Restrict access to production dashboards where appropriate.

---

# Interview Questions

### Q1. What is Grafana?

Grafana is an open-source visualization platform used to create dashboards from monitoring data.

---

### Q2. Does Grafana collect metrics?

No.

Grafana queries data from external data sources such as Prometheus.

---

### Q3. What is a Grafana Dashboard?

A Dashboard is a collection of panels displaying related monitoring data.

---

### Q4. What is a Panel?

A Panel is an individual visualization within a dashboard.

---

### Q5. Can Grafana connect to multiple data sources?

Yes.

Grafana supports many data sources simultaneously.

---

### Q6. What is the purpose of dashboard variables?

Variables make dashboards reusable and interactive by allowing users to select values such as servers, namespaces or clusters.

---

# Production Best Practices

✔ Organize dashboards into folders.

✔ Use dashboard variables.

✔ Keep dashboards focused.

✔ Optimize PromQL queries.

✔ Version-control exported dashboards.

✔ Configure appropriate access permissions.

✔ Build dashboards for infrastructure, applications and Kubernetes separately.

✔ Review dashboards regularly to ensure they remain useful.

---

# Key Takeaways

- Grafana is the visualization layer of modern monitoring systems.
- It connects to Prometheus and many other data sources.
- Dashboards are composed of reusable panels.
- Variables simplify dashboard reuse across multiple environments.
- Grafana is widely used in production for infrastructure, application and Kubernetes monitoring.

---

# Next Section

## 10.12 Grafana Dashboards

In the next section, we will learn:

- Dashboard Design Principles
- Creating Dashboards
- Panel Types
- Variables
- Dashboard Organization
- Dashboard Import & Export
- Enterprise Dashboard Examples
- Best Practices
- Interview Questions
---

# 10.12 Grafana Dashboards

Installing Grafana is only the beginning.

The real value of Grafana comes from creating dashboards that help engineers quickly understand system health.

A good dashboard should answer questions like:

- Is the server healthy?
- Is CPU usage increasing?
- Are Kubernetes Pods healthy?
- Which application is failing?
- Is the database under heavy load?

The purpose of a dashboard is to provide information at a glance.

---

# What is a Dashboard?

A Dashboard is a collection of panels displaying related metrics.

Example

```
Linux Dashboard

↓

CPU

Memory

Disk

Network

Load
```

Instead of running multiple queries manually,

all important information appears on a single screen.

---

# Dashboard Components

```
Dashboard

│

├── Variables

├── Panels

├── Queries

├── Time Range

└── Refresh Interval
```

Each component contributes to the overall monitoring experience.

---

# Dashboard Workflow

```
Prometheus

↓

PromQL

↓

Grafana Panel

↓

Dashboard

↓

Engineer
```

---

# Good Dashboard Design

A dashboard should be:

✔ Simple

✔ Easy to Read

✔ Fast

✔ Actionable

✔ Organized

Avoid unnecessary visual clutter.

---

# Types of Dashboards

Most organizations create separate dashboards for different purposes.

Examples:

```
Infrastructure Dashboard

Application Dashboard

Kubernetes Dashboard

Database Dashboard

Business Dashboard
```

---

# Infrastructure Dashboard

Typical panels include:

- CPU Usage
- Memory Usage
- Disk Usage
- Disk I/O
- Network Traffic
- Load Average
- System Uptime

---

# Kubernetes Dashboard

Typical panels include:

- Node Status
- Pod Count
- Running Pods
- Pending Pods
- Failed Pods
- Deployment Status
- Namespace Usage
- Cluster CPU
- Cluster Memory

---

# Application Dashboard

Example panels:

- Requests Per Second
- Response Time
- Error Rate
- Active Users
- API Latency
- Cache Hit Rate

---

# Database Dashboard

Monitor:

- Connections
- Query Rate
- Slow Queries
- Replication Lag
- CPU
- Memory
- Disk Usage

---

# Business Dashboard

Business dashboards focus on KPIs.

Examples:

- Orders Per Minute
- Revenue
- Successful Payments
- Failed Payments
- Active Users
- New Registrations

---

# Panel Types

Grafana supports many visualization types.

---

## Time Series

Best for:

- CPU
- Memory
- Network
- Disk

```
Time

↓

Graph
```

---

## Stat Panel

Displays a single value.

Example

```
CPU

42%
```

---

## Gauge

Useful for percentages.

Example

```
Memory

68%
```

---

## Bar Chart

Useful for comparing values.

Example

```
Server A

Server B

Server C
```

---

## Pie Chart

Useful for percentage distribution.

Example

```
Production

Development

Testing
```

---

## Table

Displays detailed metric values.

Useful for:

- Pod Lists
- Server Lists
- Status Reports

---

## Heatmap

Useful for:

- Request Distribution
- Latency Analysis

---

# Dashboard Variables

Variables make dashboards reusable.

Example

```
Server

↓

server01

server02

server03
```

Instead of creating three dashboards,

one dashboard can monitor all servers.

---

# Variable Types

Common variables:

- Instance
- Namespace
- Cluster
- Job
- Pod
- Node

---

# Dashboard Filters

Users can filter dashboards.

Example

```
Cluster

↓

Production

Development
```

or

```
Namespace

↓

default

monitoring

kube-system
```

---

# Time Range

Users can change dashboard duration.

Examples:

```
Last 15 Minutes

Last 1 Hour

Last 24 Hours

Last 7 Days

Last 30 Days
```

---

# Refresh Interval

Dashboards automatically refresh.

Examples:

```
5 Seconds

10 Seconds

30 Seconds

1 Minute
```

---

# Dashboard Folder Structure

Example

```
Grafana

│

├── Linux

├── Kubernetes

├── Databases

├── Applications

├── Networking

└── Business
```

Folders improve organization.

---

# Dashboard Import

Grafana supports importing dashboards.

Workflow

```
Dashboard JSON

↓

Import

↓

Ready to Use
```

Thousands of community dashboards are available.

---

# Dashboard Export

Workflow

```
Dashboard

↓

Export JSON

↓

Git Repository

↓

Version Control
```

This allows dashboards to be shared across teams and environments.

---

# Dashboard Permissions

Example

```
Admin

↓

Edit

----------------

Developer

↓

View

----------------

Guest

↓

Limited Access
```

Restrict access based on roles.

---

# Dashboard Example

```
Infrastructure Dashboard

--------------------------------

CPU

Memory

Disk

--------------------------------

Network

Load

Processes

--------------------------------

Alerts

System Health
```

---

# Kubernetes Dashboard Example

```
Cluster Health

↓

Node Status

↓

Pod Status

↓

Deployment Status

↓

Resource Usage

↓

Alerts
```

---

# Enterprise Dashboard Workflow

```
Infrastructure

↓

Prometheus

↓

Grafana

↓

Dashboard

↓

Operations Center
```

Large organizations often display dashboards on dedicated monitoring screens.

---

# Dashboard Best Practices

✔ Keep related metrics together.

✔ Use meaningful titles.

✔ Avoid too many panels.

✔ Highlight critical metrics.

✔ Use variables.

✔ Use consistent naming.

✔ Optimize queries.

✔ Keep dashboards responsive.

---

# Common Beginner Mistakes

### Mistake 1

Adding every metric to one dashboard.

Create multiple focused dashboards instead.

---

### Mistake 2

Using complicated layouts.

Simple dashboards are easier to understand.

---

### Mistake 3

Ignoring dashboard refresh intervals.

Too frequent refreshes may increase load.

---

### Mistake 4

Hardcoding server names.

Use dashboard variables.

---

### Mistake 5

Not documenting dashboards.

Each dashboard should have a clear purpose.

---

# Interview Questions

### Q1. What is a Grafana Dashboard?

A Dashboard is a collection of panels used to visualize monitoring data.

---

### Q2. What is a Panel?

A Panel is an individual visualization displaying one or more metrics.

---

### Q3. Why are Variables used?

Variables make dashboards reusable by allowing users to select instances, namespaces, clusters and other values dynamically.

---

### Q4. Can Grafana dashboards be exported?

Yes.

Dashboards can be exported as JSON files and imported into other Grafana instances.

---

### Q5. Why should dashboards be separated by category?

It improves readability, organization and operational efficiency.

---

### Q6. Name five common dashboard types.

- Infrastructure
- Kubernetes
- Application
- Database
- Business

---

# Production Best Practices

✔ Build dashboards for different audiences.

✔ Use variables instead of duplicate dashboards.

✔ Keep critical dashboards lightweight.

✔ Store dashboards in version control.

✔ Apply role-based access.

✔ Optimize PromQL queries.

✔ Review dashboards regularly.

✔ Remove unused dashboards.

---

# Key Takeaways

- Dashboards transform raw metrics into actionable insights.
- Different dashboards should focus on infrastructure, applications, Kubernetes or business metrics.
- Variables improve dashboard flexibility and reuse.
- Good dashboard design improves operational visibility and incident response.
- Grafana dashboards are a critical part of modern DevOps monitoring.

---

# Next Section

## 10.13 Logging Fundamentals

In the next section, we will learn:

- What is Logging?
- Why Logging is Important
- Log Types
- Log Levels
- Structured Logging
- Centralized Logging
- Production Examples
- Best Practices
- Interview Questions
---

# 10.13 Logging Fundamentals

Monitoring tells us **that** a problem exists.

Logging tells us **what actually happened**.

Imagine a production application.

Users suddenly report:

- Login Failed
- Payment Failed
- API Returning Error
- Database Timeout

Monitoring may show:

```
Error Rate Increased
```

But it cannot explain exactly why.

To understand the reason,

engineers examine **logs**.

---

# What is Logging?

Logging is the process of recording events generated by applications, operating systems, databases and infrastructure.

Logs contain detailed information about system activities.

Examples:

- User Login
- File Access
- API Request
- Database Query
- Application Error
- Security Event

---

# Simple Definition

```
Application

↓

Events

↓

Logs

↓

Storage

↓

Search

↓

Troubleshooting
```

---

# Why Logging?

Without Logs

```
Application Error

↓

Unknown Cause

↓

Long Investigation
```

---

With Logs

```
Application Error

↓

Log Search

↓

Root Cause Found

↓

Issue Fixed
```

---

# Real World Example

Suppose a customer says:

```
Payment Failed
```

Monitoring shows:

```
Payment Error Rate Increased
```

Logs reveal:

```
Payment Gateway Timeout
```

Now engineers know exactly where to investigate.

---

# What Information Does a Log Contain?

A typical log contains:

- Timestamp
- Log Level
- Application Name
- Host Name
- Message
- User Information
- Request ID
- Error Details

Example

```
2026-07-02 11:15:20

ERROR

payment-service

Transaction Failed

CustomerID=10521

Timeout
```

---

# Logging Workflow

```
Application

↓

Generate Logs

↓

Store Logs

↓

Search Logs

↓

Troubleshoot
```

---

# Sources of Logs

Logs can come from many systems.

Examples:

- Linux Servers
- Docker Containers
- Kubernetes Pods
- Databases
- Web Servers
- APIs
- Security Devices
- Cloud Services

---

# Types of Logs

Organizations generally collect different categories of logs.

---

## Application Logs

Generated by applications.

Example

```
User Login

Order Created

Payment Failed
```

---

## System Logs

Generated by the operating system.

Examples:

- Service Started
- Process Stopped
- Kernel Messages
- Login Events

Linux example:

```
/var/log/messages

/var/log/syslog
```

---

## Web Server Logs

Generated by web servers.

Examples:

- Apache
- NGINX

Typical information:

- Client IP
- URL
- Response Code
- Response Time

---

## Database Logs

Generated by databases.

Examples:

- MySQL
- PostgreSQL
- MongoDB

Typical events:

- Slow Queries
- Connections
- Errors
- Replication

---

## Security Logs

Security events include:

- Login Attempts
- Failed Authentication
- Firewall Events
- SSH Access
- Privilege Changes

---

## Audit Logs

Audit logs record administrative activities.

Examples:

- User Created
- Role Updated
- Configuration Changed
- Policy Modified

---

# Log Levels

Logs are categorized using severity levels.

```
TRACE

↓

DEBUG

↓

INFO

↓

WARN

↓

ERROR

↓

FATAL
```

---

## TRACE

Very detailed diagnostic information.

Mostly used during development.

---

## DEBUG

Developer debugging information.

Usually disabled in production.

Example

```
DEBUG

Connecting to Database
```

---

## INFO

Normal application events.

Example

```
INFO

Application Started
```

---

## WARN

Potential issue.

Application continues running.

Example

```
WARN

Disk Usage 80%
```

---

## ERROR

Operation failed.

Example

```
ERROR

Database Connection Failed
```

---

## FATAL

Critical failure.

Application cannot continue.

Example

```
FATAL

Unable to Start Application
```

---

# Structured vs Unstructured Logs

---

## Unstructured Log

```
Database connection failed.
```

Harder to search.

---

## Structured Log

```json
{
  "time":"2026-07-02T11:20:00Z",
  "level":"ERROR",
  "service":"payment",
  "message":"Database connection failed"
}
```

Structured logs are easier to parse and analyze.

---

# Log Format

A common production log contains:

```
Timestamp

↓

Level

↓

Service

↓

Host

↓

Message
```

Example

```
2026-07-02 11:25:45

ERROR

inventory-service

server-02

Unable to connect to database
```

---

# Log Rotation

Log files continuously grow.

Without rotation,

a disk can become full.

Typical workflow:

```
Log File

↓

Rotate

↓

Compress

↓

Archive

↓

Delete Old Logs
```

Linux commonly uses:

```
logrotate
```

---

# Log Retention

Organizations define how long logs should be kept.

Examples:

- 7 Days
- 30 Days
- 90 Days
- 1 Year

Retention depends on:

- Compliance
- Storage
- Business Requirements

---

# Centralized Logging

Instead of checking logs on every server,

organizations collect them in one place.

```
Servers

↓

Log Collector

↓

Central Storage

↓

Search

↓

Dashboard
```

Centralized logging simplifies troubleshooting.

---

# Logging in Kubernetes

Container logs are generated by Pods.

Workflow

```
Pod

↓

Container Logs

↓

Log Collector

↓

Centralized Logging Platform
```

This prevents logs from being lost when Pods are recreated.

---

# Enterprise Example

An e-commerce platform runs:

```
Frontend

↓

Backend

↓

Payment

↓

Database
```

Each component generates logs.

All logs are collected into a centralized logging platform where engineers can search using:

- User ID
- Request ID
- Error Code
- Timestamp

---

# Logging Best Practices

✔ Use structured logs.

✔ Include timestamps.

✔ Include log levels.

✔ Include request IDs.

✔ Avoid logging sensitive information.

✔ Rotate logs.

✔ Centralize logs.

✔ Define retention policies.

---

# Common Beginner Mistakes

### Mistake 1

Logging everything as `ERROR`.

Use the correct log level.

---

### Mistake 2

Not including timestamps.

Without timestamps,

troubleshooting becomes difficult.

---

### Mistake 3

Logging passwords or secrets.

Sensitive information should never appear in logs.

---

### Mistake 4

Keeping logs only on local servers.

Use centralized logging.

---

### Mistake 5

Ignoring log rotation.

Large log files can consume all available disk space.

---

# Interview Questions

### Q1. What is Logging?

Logging is the process of recording events generated by applications and systems.

---

### Q2. Why is Logging important?

Logging helps identify, investigate and troubleshoot production issues.

---

### Q3. Name common log levels.

- TRACE
- DEBUG
- INFO
- WARN
- ERROR
- FATAL

---

### Q4. What is Structured Logging?

Structured logging stores log data in a machine-readable format such as JSON.

---

### Q5. Why is centralized logging important?

It allows engineers to search and analyze logs from multiple systems in one location.

---

### Q6. What is log rotation?

Log rotation archives or removes old log files to prevent excessive disk usage.

---

# Production Best Practices

✔ Use structured JSON logs.

✔ Synchronize server time using NTP.

✔ Include request and correlation IDs.

✔ Protect sensitive data.

✔ Configure log rotation.

✔ Centralize logs.

✔ Monitor logging infrastructure.

✔ Regularly review retention policies.

---

# Key Takeaways

- Logging records detailed system and application events.
- Logs complement monitoring by explaining what happened.
- Log levels help prioritize issues.
- Structured logging improves searchability and automation.
- Centralized logging is essential for modern distributed applications.

---

# Next Section

## 10.14 Fluent Bit

In the next section, we will learn:

- What is Fluent Bit?
- Why Fluent Bit is Needed
- Architecture
- Log Collection
- Kubernetes Integration
- Output Plugins
- Production Best Practices
- Interview Questions
---

# 10.14 Fluent Bit

In modern production environments,

applications generate thousands of log entries every second.

Imagine an organization with:

- 500 Linux Servers
- 2,000 Docker Containers
- 5 Kubernetes Clusters
- Hundreds of Microservices

If engineers manually log in to each server to read log files,

troubleshooting becomes nearly impossible.

This is why organizations use **log collectors**.

One of the fastest and most lightweight log collectors available today is **Fluent Bit**.

---

# What is Fluent Bit?

Fluent Bit is a lightweight, open-source log processor and forwarder.

It collects logs from various sources,

processes them,

and forwards them to centralized logging systems.

It is widely used in:

- Kubernetes
- Docker
- Linux Servers
- Cloud Platforms
- Edge Devices

---

# Simple Definition

```
Application

↓

Logs

↓

Fluent Bit

↓

Central Logging

↓

Search

↓

Engineers
```

---

# Why Fluent Bit?

Without Fluent Bit

```
Server

↓

Local Logs

↓

Manual Login

↓

Troubleshooting
```

---

With Fluent Bit

```
Server

↓

Fluent Bit

↓

Central Log Platform

↓

Search

↓

Dashboard
```

Logs become searchable from one place.

---

# Why Companies Use Fluent Bit

Organizations choose Fluent Bit because it is:

✔ Lightweight

✔ Fast

✔ Low Memory Usage

✔ Kubernetes Friendly

✔ Cloud Native

✔ Highly Scalable

✔ Easy to Configure

✔ Supports Hundreds of Plugins

---

# Fluent Bit Architecture

```
Applications

↓

Log Files

↓

Fluent Bit

↓

Processing

↓

Output Plugin

↓

Loki

Elasticsearch

Splunk

Kafka

Cloud
```

---

# Fluent Bit Components

```
Fluent Bit

│

├── Input

├── Parser

├── Filter

├── Buffer

└── Output
```

Each stage performs a specific task.

---

# Input

Inputs define where logs come from.

Examples:

- Files
- Docker
- Journald
- Syslog
- TCP
- UDP
- Kubernetes

---

Example

```
Application

↓

/var/log/app.log

↓

Fluent Bit
```

---

# Parser

Parsers convert logs into structured data.

Example

Input

```
2026-07-02 INFO Login Successful
```

After Parsing

```
Timestamp

Level

Message
```

Structured logs are easier to search and analyze.

---

# Filters

Filters modify log records.

Examples:

- Add Fields
- Remove Fields
- Rename Fields
- Kubernetes Metadata
- Mask Sensitive Data

Example

```
Original Log

↓

Add Namespace

↓

Forward
```

---

# Buffer

Logs are temporarily stored in memory or on disk before being sent to the destination.

```
Logs

↓

Buffer

↓

Output
```

Buffering helps prevent log loss during temporary network issues.

---

# Output

Outputs determine where logs are sent.

Popular destinations:

- Elasticsearch
- Loki
- Kafka
- Splunk
- Amazon S3
- CloudWatch
- Google Cloud Logging
- Azure Monitor

---

# Fluent Bit Workflow

```
Application

↓

Input

↓

Parser

↓

Filter

↓

Buffer

↓

Output

↓

Central Logging
```

---

# Kubernetes Architecture

```
Pod

↓

Container Logs

↓

Fluent Bit DaemonSet

↓

Loki

↓

Grafana
```

One Fluent Bit Pod usually runs on each Kubernetes node.

---

# Why DaemonSet?

A DaemonSet ensures:

```
Every Node

↓

One Fluent Bit Pod
```

Every node automatically collects local container logs.

---

# Log Collection Example

```
Container

↓

stdout

↓

Container Runtime

↓

Log File

↓

Fluent Bit

↓

Loki
```

---

# Common Inputs

Examples:

- Tail Files
- Systemd
- Docker
- Kubernetes
- TCP
- UDP
- Forward

---

# Common Filters

Examples:

- Kubernetes Filter
- Modify Filter
- Grep Filter
- Record Modifier
- Nest
- Lua

---

# Common Outputs

Examples:

- Loki
- Elasticsearch
- Kafka
- Splunk
- HTTP
- S3
- CloudWatch
- Azure Blob Storage

---

# Sample Configuration

Input

```ini
[INPUT]
    Name tail
    Path /var/log/*.log
```

Output

```ini
[OUTPUT]
    Name stdout
    Match *
```

This configuration reads log files and prints them to standard output.

---

# Kubernetes Example

Typical deployment:

```
Kubernetes Cluster

↓

DaemonSet

↓

Fluent Bit

↓

Loki

↓

Grafana
```

This is one of the most common cloud-native logging architectures.

---

# Enterprise Example

An enterprise runs:

```
100 Kubernetes Nodes

↓

100 Fluent Bit Pods

↓

Central Loki Cluster

↓

Grafana

↓

Operations Team
```

Every application log is collected automatically.

---

# Fluent Bit vs Fluentd

| Fluent Bit | Fluentd |
|------------|----------|
| Lightweight | Feature Rich |
| Written in C | Written in Ruby |
| Lower Memory Usage | Higher Memory Usage |
| Edge Devices | Central Aggregator |
| Faster Startup | More Plugins |

Many organizations use both together.

---

# Benefits of Fluent Bit

✔ Lightweight

✔ High Performance

✔ Low CPU Usage

✔ Kubernetes Native

✔ Reliable Buffering

✔ Flexible Plugin System

✔ Cloud Native

✔ Production Ready

---

# Common Beginner Mistakes

### Mistake 1

Collecting every log file.

Only collect logs that provide operational value.

---

### Mistake 2

Sending logs directly without buffering.

Temporary network failures can cause log loss.

---

### Mistake 3

Ignoring parsing.

Structured logs are much easier to search and analyze.

---

### Mistake 4

Not filtering sensitive data.

Passwords, tokens and personal information should never be forwarded.

---

### Mistake 5

Running Fluent Bit as a Deployment instead of a DaemonSet in Kubernetes.

DaemonSets ensure one collector per node.

---

# Interview Questions

### Q1. What is Fluent Bit?

Fluent Bit is a lightweight log processor and forwarder used to collect and send logs to centralized logging platforms.

---

### Q2. Why is Fluent Bit popular in Kubernetes?

Because it is lightweight and commonly deployed as a DaemonSet to collect logs from every node.

---

### Q3. What are the major Fluent Bit components?

- Input
- Parser
- Filter
- Buffer
- Output

---

### Q4. Why is buffering important?

Buffering helps prevent log loss during temporary connectivity or destination failures.

---

### Q5. Name some Fluent Bit output destinations.

- Loki
- Elasticsearch
- Kafka
- Splunk
- Amazon S3
- CloudWatch

---

### Q6. Why is Fluent Bit preferred over Fluentd on Kubernetes nodes?

Because it consumes fewer CPU and memory resources while providing excellent performance.

---

# Production Best Practices

✔ Deploy Fluent Bit as a DaemonSet in Kubernetes.

✔ Enable buffering.

✔ Parse logs into structured formats.

✔ Filter sensitive information.

✔ Monitor Fluent Bit health.

✔ Rotate logs appropriately.

✔ Secure communication with logging backends.

✔ Test log forwarding after upgrades.

---

# Key Takeaways

- Fluent Bit is a lightweight log collector and forwarder.
- It is widely used in Kubernetes and cloud-native environments.
- It collects logs, processes them and forwards them to centralized logging systems.
- DaemonSets allow one Fluent Bit instance to run on every Kubernetes node.
- Fluent Bit is one of the most widely adopted log collection tools in modern DevOps platforms.

---

# Next Section

## 10.15 Fluentd

In the next section, we will learn:

- What is Fluentd?
- Fluentd Architecture
- Fluentd vs Fluent Bit
- Plugins
- Log Aggregation
- Enterprise Deployments
- Best Practices
- Interview Questions
---

# 10.15 Fluentd

As organizations grow,

they collect logs from:

- Linux Servers
- Kubernetes Clusters
- Docker Containers
- Applications
- Databases
- Cloud Services

Sometimes,

a lightweight log collector like Fluent Bit is enough.

However,

large enterprises often require:

- Advanced Log Processing
- Complex Routing
- Data Transformation
- Multiple Outputs
- Plugin Extensibility

This is where **Fluentd** is commonly used.

---

# What is Fluentd?

Fluentd is an open-source log collector and log processor.

It collects logs from multiple sources,

processes them,

transforms them,

and forwards them to different storage or analytics platforms.

Fluentd is one of the most popular centralized logging tools in enterprise environments.

---

# Simple Definition

```
Applications

↓

Logs

↓

Fluentd

↓

Processing

↓

Central Storage

↓

Search
```

---

# Why Fluentd?

Without Fluentd

```
Application Logs

↓

Different Servers

↓

Manual Investigation
```

---

With Fluentd

```
Applications

↓

Fluentd

↓

Central Platform

↓

Search

↓

Troubleshooting
```

---

# Why Companies Use Fluentd

Fluentd provides:

✔ Flexible Routing

✔ Large Plugin Ecosystem

✔ Data Transformation

✔ Multiple Outputs

✔ Centralized Logging

✔ Enterprise Integration

✔ Reliable Delivery

✔ Open Source

---

# Fluentd Architecture

```
Applications

↓

Input Plugins

↓

Parser

↓

Filter

↓

Buffer

↓

Output Plugins

↓

Elasticsearch

Loki

Kafka

Splunk

Cloud Storage
```

---

# Fluentd Components

```
Fluentd

│

├── Input

├── Parser

├── Filter

├── Buffer

├── Router

└── Output
```

Each component processes log data before forwarding it.

---

# Input Plugins

Input plugins collect logs.

Common inputs:

- Tail Files
- Syslog
- HTTP
- TCP
- UDP
- Docker
- Kubernetes
- Journald

Example

```
Application

↓

/var/log/app.log

↓

Fluentd
```

---

# Parsing

Logs are parsed into structured fields.

Example

Original

```
INFO User Login Successful
```

Parsed

```
Timestamp

Level

Service

Message
```

Structured logs improve searching and analytics.

---

# Filters

Filters modify log records.

Examples:

- Remove Fields
- Rename Fields
- Add Metadata
- Mask Passwords
- Change Formats
- Enrich Records

---

# Routing

Fluentd can send different logs to different destinations.

Example

```
Application Logs

↓

Elasticsearch

----------------

Security Logs

↓

Splunk

----------------

Audit Logs

↓

Amazon S3
```

---

# Buffer

Before forwarding,

logs are buffered.

```
Logs

↓

Buffer

↓

Destination
```

Buffering protects against temporary destination failures.

---

# Output Plugins

Popular outputs include:

- Elasticsearch
- Loki
- Kafka
- Splunk
- Amazon S3
- CloudWatch
- Azure Monitor
- Google Cloud Logging

---

# Fluentd Workflow

```
Logs

↓

Input

↓

Parser

↓

Filter

↓

Buffer

↓

Router

↓

Output
```

---

# Plugin System

One of Fluentd's biggest strengths is its plugin ecosystem.

Categories include:

- Input Plugins
- Parser Plugins
- Filter Plugins
- Output Plugins
- Formatter Plugins
- Storage Plugins

Thousands of plugins are available.

---

# Example Configuration

Input

```conf
<source>
  @type tail
  path /var/log/app.log
</source>
```

Output

```conf
<match **>
  @type stdout
</match>
```

This configuration reads a log file and prints log records to standard output.

---

# Kubernetes Architecture

Large Kubernetes deployments often use:

```
Pods

↓

Fluent Bit

↓

Fluentd

↓

Elasticsearch

↓

Kibana
```

Here,

Fluent Bit collects logs from nodes,

while Fluentd performs aggregation and advanced processing.

---

# Enterprise Architecture

```
Applications

↓

Fluent Bit

↓

Fluentd

↓

Kafka

↓

Elasticsearch

↓

Kibana

↓

Operations Team
```

This architecture supports very large environments.

---

# Fluent Bit vs Fluentd

| Fluent Bit | Fluentd |
|------------|----------|
| Lightweight | Feature Rich |
| Lower Memory Usage | Higher Memory Usage |
| Fast Collection | Advanced Processing |
| Edge Collector | Central Aggregator |
| Written in C | Written in Ruby |

---

# When to Use Fluentd?

Use Fluentd when you need:

- Multiple Destinations
- Complex Routing
- Log Enrichment
- Advanced Filtering
- Enterprise Processing
- Large Plugin Support

---

# Common Use Cases

- Kubernetes Logging
- Security Monitoring
- Compliance Logging
- Cloud Logging
- Audit Collection
- Application Logging
- Database Logging

---

# Enterprise Example

Suppose an organization has:

```
300 Servers

↓

10 Million Logs

↓

Fluentd Cluster

↓

Elasticsearch

↓

Kibana
```

Engineers can search logs across the entire infrastructure from one interface.

---

# Benefits of Fluentd

✔ Highly Flexible

✔ Plugin-Based

✔ Enterprise Ready

✔ Multiple Outputs

✔ Reliable Buffering

✔ Structured Logging

✔ Data Enrichment

✔ Cloud Native

---

# Common Beginner Mistakes

### Mistake 1

Using Fluentd on every Kubernetes node when Fluent Bit would be more efficient.

---

### Mistake 2

Ignoring buffering.

Without buffering,

temporary outages may result in lost log records.

---

### Mistake 3

Sending every log to every destination.

Route logs based on business requirements.

---

### Mistake 4

Collecting excessive DEBUG logs in production.

This increases storage costs and reduces signal-to-noise ratio.

---

### Mistake 5

Not monitoring Fluentd itself.

Log pipelines should also be monitored.

---

# Interview Questions

### Q1. What is Fluentd?

Fluentd is an open-source log collector and processor used to aggregate, transform and forward logs.

---

### Q2. What is the difference between Fluent Bit and Fluentd?

Fluent Bit is lightweight and optimized for log collection.

Fluentd provides advanced processing, routing and plugin capabilities.

---

### Q3. What are Fluentd's main components?

- Input
- Parser
- Filter
- Buffer
- Router
- Output

---

### Q4. Why is Fluentd commonly used in enterprises?

Because it supports advanced log processing, routing and integration with many storage platforms.

---

### Q5. Can Fluentd send logs to multiple destinations?

Yes.

It can route logs to multiple outputs simultaneously.

---

### Q6. What is the role of buffering?

Buffering protects logs during temporary destination failures and improves reliability.

---

# Production Best Practices

✔ Use Fluent Bit for edge collection.

✔ Use Fluentd for centralized processing.

✔ Enable persistent buffering.

✔ Parse logs into structured formats.

✔ Secure communication using TLS.

✔ Monitor Fluentd resource usage.

✔ Rotate and archive logs appropriately.

✔ Keep configuration under version control.

---

# Key Takeaways

- Fluentd is a powerful enterprise log collector and processor.
- It supports advanced routing, transformation and aggregation.
- It works well alongside Fluent Bit in Kubernetes environments.
- Its plugin ecosystem makes it highly extensible.
- Fluentd is widely adopted in large-scale production logging architectures.

---

# Next Section

## 10.16 Loki

In the next section, we will learn:

- What is Loki?
- Loki Architecture
- Log Storage
- Labels
- LogQL
- Grafana Integration
- Production Best Practices
- Interview Questions
---

# 10.16 Loki

As organizations grow,

they generate millions of log entries every day.

Traditional log management systems often become:

- Expensive
- Complex
- Resource Intensive

Grafana Labs introduced **Loki** to solve this problem.

Loki is designed specifically for cloud-native environments and integrates seamlessly with Grafana.

Unlike traditional logging systems,

Loki indexes **labels instead of the full log content**.

This makes Loki lightweight, cost-effective and highly scalable.

---

# What is Loki?

Loki is an open-source log aggregation system developed by Grafana Labs.

It stores application and infrastructure logs efficiently and integrates directly with Grafana.

Loki is inspired by Prometheus.

Just as Prometheus stores metrics,

Loki stores logs.

---

# Simple Definition

```
Applications

↓

Logs

↓

Fluent Bit

↓

Loki

↓

Grafana

↓

Search
```

---

# Why Loki?

Without Loki

```
Logs

↓

Many Servers

↓

Manual Search
```

---

With Loki

```
Logs

↓

Centralized

↓

Search

↓

Dashboard
```

---

# Why Companies Use Loki

Loki provides:

✔ Lightweight Architecture

✔ Low Storage Cost

✔ Native Grafana Integration

✔ Kubernetes Friendly

✔ Label-Based Indexing

✔ Fast Search

✔ Cloud Native

✔ Open Source

---

# Loki Architecture

```
Applications

↓

Fluent Bit

↓

Loki

↓

Object Storage

↓

Grafana

↓

DevOps Team
```

---

# Loki Components

```
Loki

│

├── Distributor

├── Ingester

├── Storage

├── Querier

├── Query Frontend

└── Compactor
```

Each component has a specific responsibility.

---

# Distributor

The Distributor receives incoming log streams.

```
Fluent Bit

↓

Distributor
```

Responsibilities:

- Validate Logs
- Route Logs
- Load Balance Requests

---

# Ingester

The Ingester temporarily stores logs in memory before writing them to permanent storage.

```
Distributor

↓

Ingester

↓

Storage
```

---

# Storage

Loki stores logs in object storage.

Examples:

- Amazon S3
- Google Cloud Storage
- Azure Blob Storage
- Local Filesystem
- MinIO

Unlike Elasticsearch,

Loki keeps indexing lightweight.

---

# Querier

The Querier retrieves logs.

Workflow

```
Grafana

↓

Log Query

↓

Querier

↓

Results
```

---

# Query Frontend

The Query Frontend improves query performance by:

- Splitting Queries
- Caching Results
- Parallel Execution

---

# Compactor

Compactor optimizes stored log data.

Responsibilities:

- Merge Data
- Reduce Storage Usage
- Improve Query Performance

---

# Loki Data Flow

```
Application

↓

Logs

↓

Fluent Bit

↓

Distributor

↓

Ingester

↓

Storage

↓

Grafana
```

---

# Labels

Loki indexes labels instead of log messages.

Example

```
job="nginx"

namespace="production"

pod="frontend-01"
```

Labels make searching much faster while reducing storage overhead.

---

# Example Log

```
2026-07-02

ERROR

Payment Failed

UserID=1025
```

Labels

```
service=payment

namespace=production

pod=payment-5d89
```

---

# What Makes Loki Different?

Traditional logging systems:

```
Index Entire Log
```

Loki:

```
Index Labels Only
```

This significantly reduces infrastructure costs.

---

# LogQL

Loki uses:

```
LogQL
```

LogQL is the query language for Loki.

It is similar in style to PromQL.

---

# Basic LogQL Query

Show logs from one application.

```logql
{job="nginx"}
```

---

Filter ERROR logs.

```logql
{job="payment"} |= "ERROR"
```

---

Filter WARNING logs.

```logql
{job="payment"} |= "WARN"
```

---

Search Multiple Labels

```logql
{namespace="production",app="frontend"}
```

---

Regular Expression Example

```logql
{job="nginx"} |~ "5[0-9][0-9]"
```

Matches HTTP 5xx errors.

---

# Grafana Integration

```
Loki

↓

Grafana

↓

Explore

↓

Dashboard

↓

Logs
```

Grafana provides an "Explore" interface specifically for searching logs.

---

# Kubernetes Example

```
Pods

↓

Container Logs

↓

Fluent Bit

↓

Loki

↓

Grafana
```

This is one of the most popular Kubernetes logging architectures.

---

# Enterprise Architecture

```
Applications

↓

Fluent Bit

↓

Loki Cluster

↓

Object Storage

↓

Grafana

↓

Operations Team
```

---

# Loki vs Elasticsearch

| Loki | Elasticsearch |
|------|---------------|
| Label Indexing | Full Text Indexing |
| Lower Storage Cost | Higher Storage Cost |
| Lightweight | Resource Intensive |
| Grafana Native | Kibana Native |
| Optimized for Kubernetes | General Purpose Search |

---

# Loki vs Fluent Bit

| Loki | Fluent Bit |
|------|-------------|
| Stores Logs | Collects Logs |
| Query Engine | Forwarder |
| Search | Processing |
| Backend | Collector |

They work together rather than replace each other.

---

# Typical Logging Stack

```
Application

↓

Fluent Bit

↓

Loki

↓

Grafana
```

This combination is commonly known as the **PLG Stack**.

---

# Enterprise Example

An enterprise has:

```
300 Kubernetes Nodes

↓

Fluent Bit

↓

Loki

↓

Grafana

↓

DevOps Team
```

Engineers can search logs from every application using a single Grafana interface.

---

# Benefits of Loki

✔ Lightweight

✔ Cost Effective

✔ Fast Queries

✔ Kubernetes Native

✔ Native Grafana Integration

✔ Easy Scaling

✔ Open Source

✔ Label-Based Storage

---

# Common Beginner Mistakes

### Mistake 1

Thinking Loki collects logs.

Log collection is typically performed by Fluent Bit or Fluentd.

---

### Mistake 2

Creating too many labels.

High-cardinality labels can negatively affect performance.

---

### Mistake 3

Sending logs directly from applications without a collector.

Use Fluent Bit or Fluentd for reliable collection.

---

### Mistake 4

Confusing LogQL with PromQL.

PromQL queries metrics.

LogQL queries logs.

---

### Mistake 5

Not configuring log retention.

Old logs should be archived or removed according to business requirements.

---

# Interview Questions

### Q1. What is Loki?

Loki is a log aggregation system developed by Grafana Labs.

---

### Q2. What makes Loki different from Elasticsearch?

Loki indexes labels instead of the full log content, reducing storage and infrastructure costs.

---

### Q3. What is LogQL?

LogQL is Loki's query language used for searching and filtering logs.

---

### Q4. Does Loki collect logs?

No.

Log collectors such as Fluent Bit or Fluentd send logs to Loki.

---

### Q5. Why is Loki popular in Kubernetes?

Because it is lightweight, scalable and integrates natively with Grafana.

---

### Q6. What is the PLG Stack?

- Prometheus
- Loki
- Grafana

A popular cloud-native observability stack.

---

# Production Best Practices

✔ Use Fluent Bit as the log collector.

✔ Use labels carefully.

✔ Avoid high-cardinality labels.

✔ Store logs in object storage.

✔ Configure retention policies.

✔ Secure Loki endpoints.

✔ Monitor Loki performance.

✔ Back up configuration files.

---

# Key Takeaways

- Loki is a lightweight log aggregation system from Grafana Labs.
- It stores logs efficiently using label-based indexing.
- Fluent Bit commonly forwards logs to Loki.
- Grafana provides a powerful interface for searching and visualizing Loki logs.
- Loki is one of the most widely adopted logging backends for Kubernetes and cloud-native environments.

---

# Next Section

## 10.17 Elasticsearch

In the next section, we will learn:

- What is Elasticsearch?
- Elasticsearch Architecture
- Indexes
- Shards
- Replicas
- Search Engine
- Logging Pipeline
- Production Best Practices
- Interview Questions
---

# 10.17 Elasticsearch

Modern organizations generate enormous amounts of data every day.

Examples include:

- Application Logs
- Web Server Logs
- Database Logs
- Security Logs
- Audit Logs
- Kubernetes Logs
- Cloud Logs

Searching these logs manually is impossible.

Organizations need a system that can:

- Store Logs
- Index Data
- Search Quickly
- Scale Horizontally
- Handle Millions of Records

One of the most widely used search and analytics engines is **Elasticsearch**.

---

# What is Elasticsearch?

Elasticsearch is an open-source distributed search and analytics engine.

It stores structured and unstructured data,

creates indexes,

and allows extremely fast searching.

Although Elasticsearch can store many types of data,

it is commonly used for:

- Log Analytics
- Application Search
- Security Monitoring
- Observability
- Full-Text Search

---

# Simple Definition

```
Applications

↓

Logs

↓

Fluentd / Fluent Bit

↓

Elasticsearch

↓

Kibana

↓

Search
```

---

# Why Elasticsearch?

Without Elasticsearch

```
Millions of Log Files

↓

Manual Search

↓

Slow Investigation
```

---

With Elasticsearch

```
Logs

↓

Indexed

↓

Search

↓

Results

↓

Troubleshooting
```

---

# Why Companies Use Elasticsearch

Elasticsearch provides:

✔ Distributed Architecture

✔ Full-Text Search

✔ High Availability

✔ Horizontal Scaling

✔ REST API

✔ Fast Queries

✔ Analytics

✔ Open Source

---

# Elasticsearch Architecture

```
Applications

↓

Log Collector

↓

Elasticsearch Cluster

↓

Kibana

↓

Engineers
```

---

# Elasticsearch Components

```
Elasticsearch

│

├── Cluster

├── Nodes

├── Index

├── Shards

├── Replicas

└── Documents
```

---

# Cluster

A Cluster is a collection of Elasticsearch nodes working together.

Example

```
Cluster

│

├── Node 1

├── Node 2

└── Node 3
```

The cluster distributes data across nodes.

---

# Node

A Node is an individual Elasticsearch server.

Each node stores part of the data and participates in indexing and searching.

```
Cluster

↓

Node
```

---

# Document

A Document is the basic unit of data stored in Elasticsearch.

Documents are stored in JSON format.

Example

```json
{
  "service":"payment",
  "level":"ERROR",
  "message":"Payment Timeout",
  "timestamp":"2026-07-02T11:30:00Z"
}
```

---

# Index

An Index is similar to a table in a relational database.

Example

```
logs-2026

↓

Documents
```

Different applications may store logs in different indexes.

Examples:

```
nginx-logs

application-logs

security-logs
```

---

# Shards

Large indexes are divided into smaller pieces called **Shards**.

Example

```
Index

↓

Shard 1

Shard 2

Shard 3
```

Sharding improves scalability and search performance.

---

# Replicas

Replicas are copies of primary shards.

Purpose:

- High Availability
- Fault Tolerance
- Faster Searches

Example

```
Primary Shard

↓

Replica Shard
```

If one node fails,

another copy remains available.

---

# Data Flow

```
Application

↓

Logs

↓

Fluentd

↓

Elasticsearch

↓

Index

↓

Search

↓

Kibana
```

---

# Indexing

When a log arrives,

Elasticsearch:

```
Receive Data

↓

Parse JSON

↓

Create Index

↓

Store Document

↓

Ready for Search
```

---

# Search Workflow

```
User

↓

Search Query

↓

Elasticsearch

↓

Matching Documents

↓

Results
```

Searches are typically completed in milliseconds.

---

# REST API

Elasticsearch exposes a REST API.

Example

Retrieve cluster information:

```bash
GET /
```

Search an index:

```bash
GET /logs/_search
```

---

# Query Example

Example search request:

```json
{
  "query": {
    "match": {
      "level": "ERROR"
    }
  }
}
```

Returns documents where:

```
level = ERROR
```

---

# Full-Text Search

Unlike simple databases,

Elasticsearch supports:

- Partial Matches
- Word Matching
- Phrase Search
- Fuzzy Search
- Wildcards

This makes it ideal for searching logs and documents.

---

# Enterprise Architecture

```
Applications

↓

Fluent Bit

↓

Fluentd

↓

Elasticsearch Cluster

↓

Kibana

↓

Operations Team
```

---

# High Availability

Production clusters typically contain multiple nodes.

```
Node 1

Node 2

Node 3

↓

Cluster
```

If one node fails,

others continue serving requests.

---

# Scaling

As data grows,

new nodes can be added.

```
3 Nodes

↓

6 Nodes

↓

10 Nodes
```

The cluster redistributes shards automatically.

---

# Common Use Cases

Elasticsearch is widely used for:

- Log Analytics
- Security Information and Event Management (SIEM)
- Application Monitoring
- Audit Logging
- E-commerce Search
- Document Search
- Website Search

---

# Elasticsearch vs Database

| Elasticsearch | Relational Database |
|---------------|---------------------|
| Search Engine | Transaction Database |
| JSON Documents | Tables & Rows |
| Full-Text Search | SQL Queries |
| Horizontal Scaling | Primarily Vertical Scaling |
| Log Analytics | Business Transactions |

---

# Elasticsearch vs Loki

| Elasticsearch | Loki |
|---------------|------|
| Full-Text Indexing | Label-Based Indexing |
| General Search Platform | Log Aggregation |
| Higher Storage Usage | Lower Storage Usage |
| Kibana | Grafana |

---

# Enterprise Example

Suppose an organization generates:

```
50 Million Logs Per Day

↓

Fluentd

↓

Elasticsearch Cluster

↓

Kibana

↓

Operations Team
```

Engineers can search logs from across the organization within seconds.

---

# Benefits of Elasticsearch

✔ Fast Search

✔ Distributed Architecture

✔ High Availability

✔ REST API

✔ JSON Support

✔ Horizontal Scaling

✔ Powerful Analytics

✔ Enterprise Ready

---

# Common Beginner Mistakes

### Mistake 1

Creating too many indexes.

Too many small indexes increase memory usage.

---

### Mistake 2

Ignoring shard planning.

Too many or too few shards can reduce performance.

---

### Mistake 3

Keeping logs forever.

Configure index lifecycle and retention policies.

---

### Mistake 4

Running a single-node production cluster.

Use multiple nodes for high availability.

---

### Mistake 5

Using Elasticsearch as the primary transactional database.

Elasticsearch is optimized for search and analytics, not as a replacement for OLTP databases.

---

# Interview Questions

### Q1. What is Elasticsearch?

Elasticsearch is a distributed search and analytics engine used for storing, indexing and searching data.

---

### Q2. What is an Index?

An Index is a logical collection of related documents.

---

### Q3. What is a Document?

A Document is a JSON object stored in Elasticsearch.

---

### Q4. What are Shards?

Shards divide an index into smaller pieces for scalability and performance.

---

### Q5. Why are Replicas important?

Replicas improve availability, fault tolerance and search performance.

---

### Q6. Why is Elasticsearch commonly used in logging platforms?

Because it provides powerful full-text search, analytics and scalable storage for large volumes of log data.

---

# Production Best Practices

✔ Plan shard sizes carefully.

✔ Configure replica shards.

✔ Enable index lifecycle management (ILM).

✔ Use structured JSON logs.

✔ Secure cluster access.

✔ Monitor cluster health.

✔ Back up indexes regularly.

✔ Scale horizontally as data grows.

---

# Key Takeaways

- Elasticsearch is a distributed search and analytics engine.
- Data is stored as JSON documents inside indexes.
- Shards and replicas provide scalability and high availability.
- It is widely used for centralized logging and log analytics.
- Elasticsearch is a core component of the traditional EFK logging stack.

---

# Next Section

## 10.18 Kibana

In the next section, we will learn:

- What is Kibana?
- Kibana Architecture
- Dashboards
- Discover
- Visualizations
- Index Patterns
- Enterprise Use Cases
- Best Practices
- Interview Questions
---

# 10.18 Kibana

Collecting logs with Elasticsearch is only the first step.

Imagine millions of logs are stored inside Elasticsearch.

How do engineers:

- Search Logs?
- Create Dashboards?
- Investigate Errors?
- Monitor Security Events?
- Analyze Application Behavior?

This is where **Kibana** comes in.

Kibana is the visualization and analytics interface for Elasticsearch.

It allows engineers to search, analyze and visualize data stored in Elasticsearch.

---

# What is Kibana?

Kibana is an open-source data visualization and analytics platform developed for Elasticsearch.

It provides a web interface for:

- Searching Logs
- Creating Dashboards
- Building Visualizations
- Monitoring Systems
- Security Analytics

Kibana is one of the core components of the Elastic Stack.

---

# Simple Definition

```
Applications

↓

Logs

↓

Elasticsearch

↓

Kibana

↓

Search

↓

Dashboards
```

---

# Why Kibana?

Without Kibana

```
Elasticsearch

↓

REST API

↓

Raw JSON

↓

Difficult Analysis
```

---

With Kibana

```
Elasticsearch

↓

Kibana

↓

Dashboards

↓

Visualizations

↓

Search
```

Engineers can analyze data visually.

---

# Kibana Architecture

```
Applications

↓

Fluentd

↓

Elasticsearch

↓

Kibana

↓

Users
```

---

# Kibana Features

Kibana provides:

✔ Dashboards

✔ Visualizations

✔ Discover

✔ Lens

✔ Maps

✔ Canvas

✔ Machine Learning Integration

✔ Alerting

---

# Kibana Components

```
Kibana

│

├── Discover

├── Dashboards

├── Visualizations

├── Lens

├── Dev Tools

├── Alerts

└── Stack Management
```

---

# Discover

The Discover section allows users to search raw log data.

Example

```
ERROR

↓

Payment

↓

Server-02
```

Results appear immediately.

Typical filters include:

- Time
- Service
- Log Level
- Host
- Namespace

---

# Dashboards

Dashboards combine multiple visualizations.

Example

```
Infrastructure Dashboard

↓

CPU

↓

Memory

↓

Errors

↓

Requests
```

---

# Visualizations

Kibana supports:

- Line Charts
- Bar Charts
- Pie Charts
- Data Tables
- Heat Maps
- Maps
- Metric Cards

---

# Lens

Lens provides a drag-and-drop interface for creating visualizations.

Workflow

```
Field

↓

Drag

↓

Chart Created
```

Useful for users who prefer not to write queries manually.

---

# Dev Tools

Dev Tools allow engineers to execute Elasticsearch API requests.

Example

```http
GET _cluster/health
```

Check available indexes:

```http
GET _cat/indices?v
```

Search logs:

```http
GET logs-*/_search
```

---

# Index Patterns (Data Views)

Kibana uses **Data Views** (formerly called Index Patterns) to identify which Elasticsearch indexes should be queried.

Example

```
logs-*

↓

All Log Indexes
```

or

```
nginx-*

↓

NGINX Logs
```

---

# Searching Logs

Example

```
Level = ERROR

AND

Service = Payment
```

or

```
Host = server01
```

Kibana supports advanced filtering.

---

# Time Filter

Users can search logs from different periods.

Examples

```
Last 15 Minutes

Last 1 Hour

Last 24 Hours

Last 7 Days
```

---

# Dashboard Workflow

```
Logs

↓

Elasticsearch

↓

Kibana Dashboard

↓

Operations Team
```

---

# Security Monitoring

Kibana is widely used for security analytics.

Examples:

- Failed Login Attempts
- SSH Access
- Firewall Events
- Authentication Failures
- Audit Logs

Security teams investigate incidents using Kibana dashboards.

---

# Enterprise Example

Suppose an organization has:

```
500 Servers

↓

Fluentd

↓

Elasticsearch

↓

Kibana

↓

Operations Dashboard
```

Engineers search logs across every server from one interface.

---

# Typical Dashboards

Examples include:

### Infrastructure Dashboard

- CPU Usage
- Memory Usage
- Disk Usage
- Host Status

---

### Application Dashboard

- Error Rate
- Response Time
- Request Volume
- API Performance

---

### Security Dashboard

- Failed Logins
- Authentication Events
- Firewall Activity
- User Sessions

---

### Kubernetes Dashboard

- Pod Logs
- Namespace Logs
- Deployment Events
- Container Errors

---

# Search Workflow

```
User

↓

Kibana

↓

Search Query

↓

Elasticsearch

↓

Matching Documents

↓

Results
```

---

# Kibana vs Grafana

| Kibana | Grafana |
|---------|----------|
| Elasticsearch Native | Multi Data Source |
| Log Analytics | Monitoring Dashboards |
| Discover & Search | Metrics Visualization |
| Elastic Stack | Prometheus, Loki and many others |

Many organizations use both tools together.

---

# Enterprise Architecture

```
Applications

↓

Fluent Bit

↓

Elasticsearch

↓

Kibana

↓

Operations Team
```

---

# Benefits of Kibana

✔ Fast Search

✔ Rich Dashboards

✔ Powerful Visualizations

✔ Security Analytics

✔ Log Exploration

✔ Elastic Integration

✔ REST API Support

✔ Open Source

---

# Common Beginner Mistakes

### Mistake 1

Creating dashboards before organizing indexes.

Plan index naming and retention first.

---

### Mistake 2

Ignoring time filters.

Incorrect time ranges may appear to return "missing" data.

---

### Mistake 3

Using wildcard searches everywhere.

Specific filters generally perform better.

---

### Mistake 4

Giving every user administrative access.

Apply role-based access control.

---

### Mistake 5

Never deleting old indexes.

Use Index Lifecycle Management (ILM).

---

# Interview Questions

### Q1. What is Kibana?

Kibana is the visualization and analytics interface for Elasticsearch.

---

### Q2. What is the purpose of Discover?

Discover is used to search and analyze raw log data.

---

### Q3. Can Kibana create dashboards?

Yes.

It supports dashboards, visualizations and reporting.

---

### Q4. What are Data Views (formerly Index Patterns)?

They define which Elasticsearch indexes Kibana queries.

---

### Q5. Can Kibana execute Elasticsearch API requests?

Yes.

Using the **Dev Tools** console.

---

### Q6. What is the difference between Kibana and Grafana?

Kibana is optimized for Elasticsearch data, while Grafana supports multiple monitoring and logging data sources.

---

# Production Best Practices

✔ Use meaningful index names.

✔ Configure Data Views properly.

✔ Apply role-based access.

✔ Create focused dashboards.

✔ Use ILM for index retention.

✔ Monitor Elasticsearch cluster health.

✔ Secure Kibana with authentication.

✔ Back up dashboards and saved objects.

---

# Key Takeaways

- Kibana is the visualization layer of the Elastic Stack.
- It provides dashboards, search and analytics for Elasticsearch.
- Discover is used for searching raw logs.
- Dashboards help visualize infrastructure, applications and security events.
- Kibana is widely used for centralized logging and operational analytics.

---

# Next Section

## 10.19 EFK Stack

In the next section, we will learn:

- What is the EFK Stack?
- EFK Architecture
- Data Flow
- Kubernetes Integration
- Enterprise Deployment
- Advantages & Limitations
- Production Best Practices
- Interview Questions
---

# 10.19 EFK Stack

Modern applications generate logs from:

- Linux Servers
- Kubernetes Pods
- Docker Containers
- Databases
- APIs
- Microservices

These logs are useful only if they can be:

- Collected
- Processed
- Stored
- Indexed
- Searched
- Visualized

One of the most popular centralized logging solutions is the **EFK Stack**.

EFK stands for:

```
Elasticsearch

↓

Fluentd

↓

Kibana
```

Together,

these tools provide complete log management.

---

# What is the EFK Stack?

The EFK Stack is a centralized logging architecture.

It combines:

- Fluentd → Collects Logs
- Elasticsearch → Stores & Indexes Logs
- Kibana → Searches & Visualizes Logs

---

# Simple Definition

```
Applications

↓

Fluentd

↓

Elasticsearch

↓

Kibana

↓

Engineers
```

---

# Why EFK?

Without EFK

```
100 Servers

↓

100 Log Files

↓

Manual Search

↓

Slow Troubleshooting
```

---

With EFK

```
100 Servers

↓

Fluentd

↓

Elasticsearch

↓

Kibana

↓

Centralized Search
```

---

# Components

```
EFK

│

├── Elasticsearch

├── Fluentd

└── Kibana
```

Each component has a different responsibility.

---

# Elasticsearch

Responsibilities:

- Store Logs
- Index Data
- Search
- Analytics

---

# Fluentd

Responsibilities:

- Collect Logs
- Parse Logs
- Filter Logs
- Buffer Logs
- Forward Logs

---

# Kibana

Responsibilities:

- Search Logs
- Dashboards
- Visualizations
- Reporting

---

# Complete Architecture

```
Applications

↓

Log Files

↓

Fluentd

↓

Elasticsearch Cluster

↓

Kibana

↓

DevOps Team
```

---

# Data Flow

```
Application

↓

Generate Log

↓

Fluentd

↓

Parse

↓

Filter

↓

Elasticsearch

↓

Index

↓

Kibana

↓

Search
```

---

# Kubernetes Architecture

A common Kubernetes deployment:

```
Pods

↓

Container Logs

↓

Fluentd DaemonSet

↓

Elasticsearch

↓

Kibana
```

Fluentd collects logs from every Kubernetes node.

---

# Why DaemonSet?

A DaemonSet guarantees:

```
Every Node

↓

One Fluentd Pod
```

This ensures all container logs are collected.

---

# Enterprise Architecture

```
Applications

↓

Fluentd

↓

Kafka (Optional)

↓

Elasticsearch Cluster

↓

Kibana

↓

Operations Center
```

Kafka is often used to improve reliability and scalability in very large environments.

---

# Log Processing

Fluentd performs:

```
Collect

↓

Parse

↓

Filter

↓

Buffer

↓

Forward
```

Only processed logs are stored.

---

# Searching Logs

Example

```
ERROR

↓

payment-service

↓

Last 15 Minutes
```

Kibana searches Elasticsearch and displays matching log entries.

---

# Typical Dashboards

Infrastructure Dashboard

- Server Errors
- CPU Alerts
- Memory Alerts

---

Application Dashboard

- API Errors
- Login Failures
- Payment Failures

---

Security Dashboard

- Failed SSH
- Authentication Errors
- Firewall Logs

---

Audit Dashboard

- User Activity
- Role Changes
- Configuration Changes

---

# Scaling

Large organizations often deploy:

```
Fluentd

↓

Elasticsearch Cluster

↓

3 Master Nodes

↓

10 Data Nodes

↓

Kibana
```

This supports high log volumes and redundancy.

---

# High Availability

```
Applications

↓

Multiple Fluentd Instances

↓

Multiple Elasticsearch Nodes

↓

Multiple Kibana Instances
```

This reduces single points of failure.

---

# Advantages

✔ Centralized Logging

✔ Fast Search

✔ Distributed Architecture

✔ Rich Dashboards

✔ Scalable

✔ Highly Available

✔ Enterprise Ready

✔ Open Source

---

# Limitations

EFK requires:

- More Memory
- More CPU
- Storage Planning
- Shard Planning
- Index Lifecycle Management

Large clusters require operational expertise.

---

# Enterprise Example

Suppose an organization has:

```
500 Servers

↓

20 Million Logs

↓

Fluentd

↓

Elasticsearch

↓

Kibana

↓

Operations Team
```

Engineers can search millions of logs within seconds.

---

# EFK Workflow

```
Applications

↓

Logs

↓

Fluentd

↓

Elasticsearch

↓

Kibana

↓

Search

↓

Troubleshooting
```

---

# EFK vs PLG

| EFK | PLG |
|-----|-----|
| Elasticsearch | Prometheus |
| Fluentd | Loki |
| Kibana | Grafana |
| Full-Text Search | Label-Based Logging |
| Resource Intensive | Lightweight |
| General Purpose | Cloud-Native Focus |

Both architectures are widely used.

Choice depends on infrastructure and operational requirements.

---

# Common Beginner Mistakes

### Mistake 1

Running Elasticsearch on a single node in production.

Deploy multiple nodes for resilience.

---

### Mistake 2

Ignoring Index Lifecycle Management.

Old indexes consume large amounts of storage.

---

### Mistake 3

Collecting every DEBUG log in production.

This increases storage costs significantly.

---

### Mistake 4

Not buffering logs before forwarding.

Temporary failures can result in data loss.

---

### Mistake 5

Never monitoring the EFK Stack itself.

The logging platform should also be monitored.

---

# Interview Questions

### Q1. What is the EFK Stack?

The EFK Stack consists of Elasticsearch, Fluentd and Kibana for centralized logging.

---

### Q2. What is the role of Fluentd?

Fluentd collects, processes and forwards logs.

---

### Q3. What is the role of Elasticsearch?

Elasticsearch stores, indexes and searches log data.

---

### Q4. What is the role of Kibana?

Kibana provides dashboards, search and visualization for Elasticsearch data.

---

### Q5. Why is EFK popular?

Because it provides centralized, scalable and searchable logging.

---

### Q6. What is the biggest challenge with EFK?

Managing Elasticsearch clusters efficiently as log volume grows.

---

# Production Best Practices

✔ Use structured JSON logs.

✔ Enable buffering in Fluentd.

✔ Configure ILM (Index Lifecycle Management).

✔ Deploy Elasticsearch with replicas.

✔ Secure Kibana using authentication.

✔ Monitor Elasticsearch cluster health.

✔ Archive old logs.

✔ Separate production and development indexes.

---

# Key Takeaways

- EFK is a centralized logging solution.
- Fluentd collects and processes logs.
- Elasticsearch stores and indexes logs.
- Kibana provides dashboards and search capabilities.
- EFK remains one of the most widely used enterprise logging architectures.

---

# Next Section

## 10.20 PLG Stack

In the next section, we will learn:

- What is the PLG Stack?
- PLG Architecture
- Prometheus + Loki + Grafana
- Metrics & Logs Together
- Kubernetes Integration
- Enterprise Deployment
- Best Practices
- Interview Questions
---

# 10.20 PLG Stack

As cloud-native applications became more popular,

organizations needed an observability stack that was:

- Lightweight
- Kubernetes Native
- Open Source
- Easy to Scale
- Cost Effective

Instead of using the traditional EFK Stack,

many organizations adopted the **PLG Stack**.

PLG stands for:

```
Prometheus

↓

Loki

↓

Grafana
```

Together,

these three tools provide monitoring, logging and visualization.

---

# What is the PLG Stack?

The PLG Stack is a cloud-native observability solution.

It combines:

- Prometheus → Metrics
- Loki → Logs
- Grafana → Dashboards

Each component focuses on a different part of observability.

---

# Simple Definition

```
Applications

↓

Prometheus

↓

Metrics

----------------

Applications

↓

Loki

↓

Logs

----------------

Grafana

↓

Dashboards
```

---

# Why PLG?

Without PLG

```
Metrics

↓

One Tool

Logs

↓

Another Tool

↓

Multiple Dashboards
```

---

With PLG

```
Metrics

↓

Prometheus

↓

Grafana

----------------

Logs

↓

Loki

↓

Grafana

↓

Single Dashboard
```

Engineers use one interface for both metrics and logs.

---

# Components

```
PLG

│

├── Prometheus

├── Loki

└── Grafana
```

---

# Prometheus

Responsibilities:

- Collect Metrics
- Store Time-Series Data
- Execute PromQL Queries
- Generate Alerts

Examples:

- CPU
- Memory
- Disk
- Network
- Kubernetes Metrics

---

# Loki

Responsibilities:

- Store Logs
- Label-Based Indexing
- LogQL Queries
- Centralized Logging

Examples:

- Application Logs
- Container Logs
- System Logs

---

# Grafana

Responsibilities:

- Dashboards
- Visualization
- Metrics
- Logs
- Alerting
- Correlation

Grafana combines data from Prometheus and Loki.

---

# Complete Architecture

```
Linux Servers

↓

Node Exporter

↓

Prometheus

↓

Grafana

----------------

Applications

↓

Fluent Bit

↓

Loki

↓

Grafana
```

---

# Kubernetes Architecture

A common Kubernetes deployment:

```
Pods

↓

Container Logs

↓

Fluent Bit

↓

Loki

↓

Grafana

----------------

Pods

↓

Metrics

↓

Prometheus

↓

Grafana
```

Grafana becomes the single observability portal.

---

# Data Flow

Metrics

```
Applications

↓

Exporters

↓

Prometheus

↓

Grafana
```

Logs

```
Applications

↓

Fluent Bit

↓

Loki

↓

Grafana
```

---

# Unified Dashboard

A Grafana dashboard can display:

- CPU Usage
- Memory Usage
- Pod Status
- Network Traffic
- Error Logs
- API Errors
- Request Rate

All from one interface.

---

# Why Cloud-Native Teams Prefer PLG

PLG offers:

✔ Kubernetes Integration

✔ Lower Storage Cost

✔ Simple Deployment

✔ Native Grafana Support

✔ Fast Log Search

✔ Powerful Metrics

✔ Open Source

✔ Excellent Community Support

---

# Example Production Workflow

Suppose a user reports:

```
Website Slow
```

Engineers first check:

```
Grafana Dashboard

↓

CPU High?
```

Then immediately switch to:

```
Loki Logs

↓

Database Timeout
```

Without changing tools.

---

# Correlating Metrics and Logs

One of PLG's biggest advantages is correlation.

Example

```
CPU Usage Increased

↓

Open Related Logs

↓

Database Timeout Found

↓

Root Cause Identified
```

This significantly reduces troubleshooting time.

---

# Enterprise Architecture

```
Applications

↓

Fluent Bit

↓

Loki

↓

Grafana

----------------

Node Exporter

↓

Prometheus

↓

Grafana

↓

DevOps Team
```

---

# Scaling

As infrastructure grows:

```
Prometheus Cluster

↓

Loki Cluster

↓

Grafana

↓

Thousands of Servers
```

Each component can scale independently.

---

# High Availability

Production deployments usually include:

```
Multiple Prometheus Servers

↓

Multiple Loki Nodes

↓

Multiple Grafana Instances
```

This minimizes downtime.

---

# PLG vs EFK

| PLG | EFK |
|------|------|
| Prometheus | Elasticsearch |
| Loki | Fluentd |
| Grafana | Kibana |
| Metrics + Logs | Logs Focus |
| Label-Based Logs | Full-Text Search |
| Lower Resource Usage | Higher Resource Usage |
| Kubernetes Native | Enterprise Search |

Both architectures are valid.

The choice depends on organizational requirements.

---

# Typical Use Cases

PLG is widely used for:

- Kubernetes Monitoring
- Container Platforms
- Cloud-Native Applications
- DevOps Observability
- Microservices
- CI/CD Monitoring

---

# Enterprise Example

Suppose an organization has:

```
20 Kubernetes Clusters

↓

Prometheus

↓

Loki

↓

Grafana

↓

Network Operations Center
```

Engineers monitor thousands of Pods and millions of log entries from a unified interface.

---

# Benefits

✔ Lightweight

✔ Cloud Native

✔ Open Source

✔ Easy Integration

✔ Unified Dashboards

✔ Cost Effective

✔ Scalable

✔ Kubernetes Friendly

---

# Common Beginner Mistakes

### Mistake 1

Thinking Grafana stores logs.

Grafana visualizes data.

Loki stores logs.

---

### Mistake 2

Installing Loki without a log collector.

Use Fluent Bit or Fluentd to forward logs.

---

### Mistake 3

Using Prometheus for logs.

Prometheus stores metrics only.

---

### Mistake 4

Creating too many labels in Loki.

High-cardinality labels can impact performance.

---

### Mistake 5

Ignoring alerting.

Monitoring without alerts delays incident response.

---

# Interview Questions

### Q1. What is the PLG Stack?

The PLG Stack consists of Prometheus, Loki and Grafana for cloud-native observability.

---

### Q2. What is the role of Prometheus?

Prometheus collects and stores metrics.

---

### Q3. What is the role of Loki?

Loki stores and indexes logs using labels.

---

### Q4. What is the role of Grafana?

Grafana visualizes metrics and logs from multiple data sources.

---

### Q5. Why is PLG popular for Kubernetes?

Because it is lightweight, cloud-native and integrates seamlessly with Kubernetes.

---

### Q6. What is the biggest advantage of PLG?

A unified observability platform for metrics, logs and dashboards with efficient resource usage.

---

# Production Best Practices

✔ Use Node Exporter for Linux metrics.

✔ Use Fluent Bit for log collection.

✔ Store logs in Loki.

✔ Build dashboards in Grafana.

✔ Configure Prometheus alerts.

✔ Secure all observability components.

✔ Monitor the monitoring stack itself.

✔ Use infrastructure as code for observability deployments.

---

# Key Takeaways

- PLG is a modern cloud-native observability stack.
- Prometheus handles metrics.
- Loki stores logs.
- Grafana visualizes both metrics and logs.
- PLG is lightweight, scalable and widely used in Kubernetes environments.
- It provides a unified operational view that simplifies monitoring and troubleshooting.

---

# Next Section

## 10.21 Monitoring Best Practices

In the next section, we will learn:

- Designing an Effective Monitoring Strategy
- Golden Signals
- RED & USE Methodologies
- Alert Design
- Dashboard Design
- Capacity Planning
- Production Best Practices
- Interview Questions
---

# 10.21 Monitoring Best Practices

Monitoring tools alone do not guarantee a reliable production environment.

Even with Prometheus, Grafana, Loki, Alertmanager and other modern tools,

poor monitoring practices can still result in:

- Missed Incidents
- Alert Fatigue
- Long Downtime
- Slow Root Cause Analysis
- Poor Customer Experience

Effective monitoring requires a well-designed strategy.

---

# What are Monitoring Best Practices?

Monitoring Best Practices are proven techniques used to design monitoring systems that are:

- Reliable
- Actionable
- Scalable
- Easy to Maintain

Their goal is to detect problems early and reduce Mean Time to Resolution (MTTR).

---

# Goals of Monitoring

A good monitoring system should answer questions like:

- Is the application healthy?
- Are users experiencing errors?
- Is performance degrading?
- Are infrastructure resources sufficient?
- Can we detect failures before customers do?

---

# Monitoring Strategy

A typical monitoring strategy includes:

```
Infrastructure

↓

Applications

↓

Databases

↓

Networking

↓

Business Metrics

↓

Alerts

↓

Dashboards
```

Every layer should be monitored.

---

# The Four Golden Signals

Google's Site Reliability Engineering (SRE) recommends monitoring four key signals.

```
Latency

↓

Traffic

↓

Errors

↓

Saturation
```

These are known as the **Four Golden Signals**.

---

## 1. Latency

Latency measures how long a request takes.

Examples:

- API Response Time
- Database Query Time
- Page Load Time

High latency usually indicates performance problems.

---

## 2. Traffic

Traffic measures demand on the system.

Examples:

- Requests Per Second
- Active Users
- Transactions Per Minute
- Network Throughput

Traffic helps with capacity planning.

---

## 3. Errors

Errors indicate failed operations.

Examples:

- HTTP 500 Errors
- Failed Logins
- Payment Failures
- Database Errors

Error rates should always be monitored.

---

## 4. Saturation

Saturation measures resource utilization.

Examples:

- CPU Usage
- Memory Usage
- Disk Space
- Connection Pool Usage

High saturation often leads to performance degradation.

---

# RED Method

The RED Method is commonly used for monitoring web services.

```
Request Rate

↓

Error Rate

↓

Duration
```

---

## Request Rate

Measures how many requests the application handles.

Example:

```
500 Requests/Second
```

---

## Error Rate

Measures the percentage of failed requests.

Example:

```
2%

↓

Errors
```

---

## Duration

Measures request latency.

Example:

```
Average Response Time

250 ms
```

---

# USE Method

The USE Method is commonly applied to infrastructure.

```
Utilization

↓

Saturation

↓

Errors
```

---

## Utilization

How busy is the resource?

Example:

```
CPU Usage

65%
```

---

## Saturation

How much work is waiting?

Examples:

- CPU Queue
- Disk Queue
- Network Queue

---

## Errors

Hardware or software failures.

Examples:

- Disk Read Errors
- Network Packet Loss
- File System Errors

---

# What Should Be Monitored?

## Infrastructure

- CPU
- Memory
- Disk
- Network
- Processes
- Uptime

---

## Kubernetes

- Nodes
- Pods
- Deployments
- ReplicaSets
- StatefulSets
- Jobs

---

## Applications

- Response Time
- Error Rate
- Request Rate
- Active Sessions
- API Performance

---

## Databases

- Connections
- Slow Queries
- Replication
- CPU
- Storage

---

## Business Metrics

- Orders
- Payments
- Revenue
- Active Users
- Registrations

Business metrics are just as important as technical metrics.

---

# Dashboard Design Best Practices

Good dashboards should:

✔ Focus on one purpose

✔ Highlight critical metrics

✔ Avoid unnecessary panels

✔ Display trends

✔ Show current status

---

Example:

```
Infrastructure Dashboard

↓

CPU

Memory

Disk

Network

Alerts
```

---

# Alert Design Best Practices

Good alerts should be:

✔ Actionable

✔ Specific

✔ Tested

✔ Prioritized

✔ Routed to the correct team

---

Poor Alert Example

```
Something is Wrong
```

---

Good Alert Example

```
Production API

↓

Response Time > 2 Seconds

↓

For 5 Minutes
```

---

# Alert Severity Levels

Example:

```
INFO

↓

WARNING

↓

CRITICAL
```

Each severity should have a different response procedure.

---

# Alert Fatigue

Too many alerts cause engineers to ignore notifications.

Example:

```
500 Alerts

↓

Engineer Ignores

↓

Real Incident Missed
```

Reduce unnecessary alerts through proper tuning.

---

# Capacity Planning

Monitoring should help predict future resource needs.

Examples:

- CPU Growth
- Memory Trends
- Disk Growth
- Traffic Growth

Historical metrics support informed capacity decisions.

---

# Monitoring the Monitoring System

Monitor:

- Prometheus
- Grafana
- Loki
- Alertmanager
- Fluent Bit
- Elasticsearch

If the monitoring platform fails,

production visibility is lost.

---

# Logging Best Practices

✔ Use structured logs

✔ Include timestamps

✔ Include correlation IDs

✔ Avoid logging secrets

✔ Rotate logs

✔ Archive old logs

---

# Security Best Practices

- Enable authentication
- Use HTTPS/TLS
- Restrict network access
- Encrypt backups
- Apply role-based access control (RBAC)

Monitoring systems often contain sensitive operational information.

---

# Documentation

Document:

- Dashboards
- Alert Rules
- Runbooks
- Escalation Procedures
- Ownership

Clear documentation speeds incident response.

---

# Enterprise Monitoring Architecture

```
Applications

↓

Metrics

↓

Prometheus

↓

Grafana

----------------

Applications

↓

Logs

↓

Loki

↓

Grafana

----------------

Alerts

↓

Alertmanager

↓

Engineers
```

---

# Incident Workflow

```
Issue

↓

Alert

↓

Engineer

↓

Dashboard

↓

Logs

↓

Root Cause

↓

Fix

↓

Incident Closed
```

---

# Common Beginner Mistakes

### Mistake 1

Monitoring only infrastructure.

Applications and business metrics are equally important.

---

### Mistake 2

Creating too many dashboards.

Maintain focused dashboards with clear objectives.

---

### Mistake 3

Alerting on every metric.

Only alert on conditions requiring action.

---

### Mistake 4

Ignoring capacity trends.

Monitoring is valuable for both operations and planning.

---

### Mistake 5

Never reviewing monitoring rules.

Thresholds should evolve with the application.

---

# Interview Questions

### Q1. What are the Four Golden Signals?

- Latency
- Traffic
- Errors
- Saturation

---

### Q2. What is the RED Method?

- Request Rate
- Error Rate
- Duration

Used for monitoring services and APIs.

---

### Q3. What is the USE Method?

- Utilization
- Saturation
- Errors

Used primarily for infrastructure monitoring.

---

### Q4. Why is alert fatigue dangerous?

Engineers may ignore notifications, causing critical incidents to be missed.

---

### Q5. Why should monitoring systems themselves be monitored?

Because failures in the monitoring platform reduce or eliminate operational visibility.

---

### Q6. Why are business metrics important?

They measure customer and business outcomes, complementing technical metrics.

---

# Production Best Practices

✔ Monitor infrastructure, applications and business KPIs.

✔ Follow the Four Golden Signals.

✔ Use RED for services and USE for infrastructure.

✔ Design meaningful dashboards.

✔ Configure actionable alerts.

✔ Continuously review thresholds.

✔ Monitor observability components.

✔ Maintain documentation and runbooks.

---

# Key Takeaways

- Effective monitoring requires strategy, not just tools.
- The Four Golden Signals provide a strong foundation for service monitoring.
- RED and USE methodologies simplify metric selection.
- Dashboards and alerts should be actionable and easy to understand.
- Monitoring should include infrastructure, applications, logs and business metrics.
- Continuous improvement is essential for a mature observability platform.

---

# Next Section

## 10.22 Monitoring & Logging Interview Questions (Master Revision)

In the next section, we will cover:

- Beginner Interview Questions
- Intermediate Interview Questions
- Advanced Production Questions
- Kubernetes Monitoring Questions
- Prometheus & Grafana Questions
- Logging Questions
- Scenario-Based Questions
- Real Interview Tips
- Quick Revision Notes
---

# 10.22 Monitoring & Logging Interview Questions (Master Revision)

This section is a complete revision of everything covered in the Monitoring & Logging chapter.

The questions are grouped by difficulty level so you can prepare for:

- Freshers Interviews
- 2–5 Years DevOps Interviews
- Senior DevOps Interviews
- Kubernetes Interviews
- Production Scenario Interviews
- Cloud Interviews

---

# Beginner Interview Questions

---

## Q1. What is Monitoring?

Monitoring is the continuous observation of infrastructure, applications and services to ensure they are healthy and performing correctly.

---

## Q2. Why is Monitoring important?

Monitoring helps:

- Detect failures
- Reduce downtime
- Improve performance
- Generate alerts
- Support troubleshooting

---

## Q3. What are Metrics?

Metrics are numerical measurements collected over time.

Examples:

- CPU Usage
- Memory Usage
- Disk Usage
- Request Count

---

## Q4. What are Logs?

Logs are detailed records of events generated by systems and applications.

---

## Q5. What are Traces?

Traces record the complete journey of a request through distributed systems.

---

## Q6. What are the Three Pillars of Observability?

```
Metrics

Logs

Traces
```

---

## Q7. What is Prometheus?

Prometheus is an open-source monitoring system that collects and stores time-series metrics.

---

## Q8. What is Grafana?

Grafana is an open-source visualization platform used to create dashboards from monitoring data.

---

## Q9. What is Alertmanager?

Alertmanager handles alerts generated by Prometheus and sends notifications.

---

## Q10. What is Node Exporter?

Node Exporter exposes Linux system metrics for Prometheus.

---

# Intermediate Interview Questions

---

## Q11. Explain the Prometheus Architecture.

Prometheus architecture includes:

- Exporters
- Scrape Manager
- TSDB
- PromQL Engine
- Rule Engine
- Alertmanager

---

## Q12. What is TSDB?

TSDB is Prometheus' built-in Time-Series Database used for storing metrics with timestamps.

---

## Q13. What is Scraping?

Scraping is the process where Prometheus periodically requests metrics from exporters.

---

## Q14. What is PromQL?

PromQL is Prometheus Query Language used to query metrics.

---

## Q15. What is a Label?

Labels are key-value pairs attached to metrics.

Example

```
job=node-exporter

instance=server01
```

---

## Q16. Why are Labels important?

Labels enable:

- Filtering
- Grouping
- Aggregation

---

## Q17. Difference between Instant Query and Range Query?

Instant Query returns the latest value.

Range Query returns values over a specified time period.

---

## Q18. Difference between rate() and increase()?

rate()

Calculates the average per-second increase.

increase()

Calculates the total increase over a period.

---

## Q19. What is kube-state-metrics?

It exposes Kubernetes object metrics such as Pods, Deployments and ReplicaSets.

---

## Q20. Difference between Node Exporter and kube-state-metrics?

Node Exporter:

Infrastructure metrics

kube-state-metrics:

Kubernetes object metrics

---

# Grafana Interview Questions

---

## Q21. Does Grafana store metrics?

No.

Grafana visualizes data stored in external data sources.

---

## Q22. What is a Dashboard?

A collection of panels showing related metrics.

---

## Q23. What is a Panel?

An individual visualization inside a dashboard.

---

## Q24. What are Variables?

Variables allow dashboards to be reused across multiple servers or environments.

---

## Q25. Which data sources can Grafana connect to?

Examples:

- Prometheus
- Loki
- Elasticsearch
- MySQL
- PostgreSQL
- CloudWatch

---

# Logging Interview Questions

---

## Q26. What is Logging?

Logging is the recording of application and system events.

---

## Q27. Why are Logs important?

Logs explain why an event occurred and help identify the root cause of problems.

---

## Q28. Name common log levels.

- TRACE
- DEBUG
- INFO
- WARN
- ERROR
- FATAL

---

## Q29. What is Structured Logging?

Structured logging stores logs in a machine-readable format such as JSON.

---

## Q30. Why is centralized logging important?

It allows engineers to search logs from multiple systems in one location.

---

# Fluent Bit Interview Questions

---

## Q31. What is Fluent Bit?

A lightweight log collector and forwarder.

---

## Q32. Why is Fluent Bit used in Kubernetes?

Because it runs efficiently as a DaemonSet and collects logs from every node.

---

## Q33. Explain Fluent Bit architecture.

```
Input

↓

Parser

↓

Filter

↓

Buffer

↓

Output
```

---

# Fluentd Interview Questions

---

## Q34. Difference between Fluent Bit and Fluentd?

Fluent Bit

- Lightweight
- Edge Collection

Fluentd

- Advanced Processing
- Enterprise Routing

---

## Q35. Why use Fluentd?

For advanced routing, filtering and log transformation.

---

# Loki Interview Questions

---

## Q36. What is Loki?

A log aggregation system developed by Grafana Labs.

---

## Q37. What is LogQL?

Loki's query language.

---

## Q38. Difference between Loki and Elasticsearch?

Loki indexes labels.

Elasticsearch indexes full documents.

---

# Elasticsearch Interview Questions

---

## Q39. What is Elasticsearch?

A distributed search and analytics engine.

---

## Q40. What is an Index?

A logical collection of documents.

---

## Q41. What is a Document?

A JSON record stored inside Elasticsearch.

---

## Q42. What are Shards?

Shards divide indexes into smaller pieces.

---

## Q43. Why are Replicas used?

High Availability

Fault Tolerance

Improved Search Performance

---

# Kibana Interview Questions

---

## Q44. What is Kibana?

The visualization platform for Elasticsearch.

---

## Q45. What is Discover?

The interface used to search raw logs.

---

## Q46. What is a Data View?

A configuration defining which Elasticsearch indexes Kibana queries.

---

# Architecture Questions

---

## Q47. Explain the EFK Stack.

```
Fluentd

↓

Elasticsearch

↓

Kibana
```

---

## Q48. Explain the PLG Stack.

```
Prometheus

↓

Loki

↓

Grafana
```

---

## Q49. Which stack is better?

It depends.

EFK is commonly used where powerful full-text search is required.

PLG is popular for cloud-native and Kubernetes environments.

---

# Production Questions

---

## Q50. A server CPU reaches 100%.

What will you check?

Typical investigation:

- Grafana Dashboard
- Prometheus Metrics
- Running Processes
- Logs
- Recent Deployments
- Alerts

---

## Q51. Application is slow but CPU is normal.

What could be wrong?

Possible causes:

- Database latency
- Network issues
- External API delays
- Lock contention
- Application code

---

## Q52. Prometheus target shows DOWN.

Possible reasons:

- Exporter stopped
- Firewall blocking access
- Incorrect target configuration
- DNS issue
- Network failure

---

## Q53. Why are alerts not being delivered?

Possible causes:

- Alertmanager not running
- Routing configuration issue
- Receiver misconfiguration
- Network connectivity
- Notification provider issue

---

## Q54. Kubernetes Pods are crashing.

What should you investigate?

- Pod Logs
- Events
- Resource Limits
- Liveness Probe
- Readiness Probe
- Image Pull Errors

---

## Q55. Logs are missing from Grafana.

Possible causes:

- Fluent Bit failure
- Loki unavailable
- Incorrect labels
- Retention policy
- Query filters

---

## Q56. Disk usage reaches 95%.

Immediate actions:

- Identify large files
- Rotate logs
- Remove unnecessary data
- Expand storage if needed
- Investigate abnormal growth

---

## Q57. Alert fatigue occurs.

How do you fix it?

- Reduce noisy alerts
- Increase thresholds where appropriate
- Group related alerts
- Use the `for` duration
- Remove obsolete alerts

---

# Kubernetes Monitoring Questions

---

## Q58. Which tools monitor Kubernetes?

Examples:

- Prometheus
- kube-state-metrics
- Node Exporter
- Grafana
- Loki
- Fluent Bit

---

## Q59. What metrics should be monitored?

- Node Health
- Pod Status
- Deployment Availability
- CPU
- Memory
- Network
- Storage

---

## Q60. Why monitor both Nodes and Pods?

Nodes indicate infrastructure health, while Pods reflect application workload health.

---

# SRE Questions

---

## Q61. What are the Four Golden Signals?

- Latency
- Traffic
- Errors
- Saturation

---

## Q62. Explain the RED Method.

- Request Rate
- Error Rate
- Duration

---

## Q63. Explain the USE Method.

- Utilization
- Saturation
- Errors

---

# Scenario Questions

---

## Q64. Users report slow login.

How would you investigate?

1. Check dashboards.
2. Review alerts.
3. Inspect application logs.
4. Verify database performance.
5. Check recent deployments.
6. Correlate metrics and logs.

---

## Q65. Website is completely down.

What should you check?

- Load Balancer
- DNS
- Application
- Database
- Network
- Kubernetes
- Logs
- Alerts

---

## Q66. How do you reduce MTTR?

- Effective monitoring
- Meaningful alerts
- Centralized logging
- Runbooks
- Automation

---

# Quick Revision

Monitoring

↓

Metrics

↓

Prometheus

↓

Grafana

---

Logging

↓

Fluent Bit

↓

Loki

↓

Grafana

---

Traditional Logging

↓

Fluentd

↓

Elasticsearch

↓

Kibana

---

Observability

↓

Metrics

Logs

Traces

---

# Top Interview Tips

✔ Understand architecture diagrams.

✔ Learn Prometheus workflows.

✔ Practice PromQL.

✔ Learn LogQL basics.

✔ Understand Kubernetes monitoring.

✔ Know Alertmanager flow.

✔ Practice production troubleshooting scenarios.

✔ Explain concepts with real-world examples.

---

# Final Chapter Summary

After completing this chapter, you should be able to:

- Design a complete monitoring solution.
- Build dashboards in Grafana.
- Collect metrics using Prometheus.
- Collect logs using Fluent Bit and Fluentd.
- Store logs in Loki or Elasticsearch.
- Search logs using Grafana or Kibana.
- Configure alerts with Alertmanager.
- Monitor Kubernetes clusters effectively.
- Apply monitoring best practices in production.
- Confidently answer Monitoring & Logging interview questions.

---

# Congratulations 🎉

You have successfully completed **Chapter 10 – Monitoring & Logging**.

You now understand:

- Monitoring
- Logging
- Observability
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
- EFK Stack
- PLG Stack
- Monitoring Strategies
- Production Best Practices

These concepts form one of the most important pillars of modern DevOps and Site Reliability Engineering (SRE).

---

# Next Chapter

# Chapter 11 — Security & DevSecOps

In the next chapter, we will cover:

- DevSecOps Fundamentals
- CIA Triad
- Authentication vs Authorization
- Encryption
- SSL/TLS
- Secrets Management
- HashiCorp Vault
- IAM
- Kubernetes Security
- Docker Security
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
- Interview Questions