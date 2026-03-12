---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/azure
  - topic/database
  - topic/monitoring
  - topic/networking
---

# CCP   Certified Cloud Practitioner (CLF CO1)

**Cloud Computing**
Responsible for configuring cloud service and code, someone else takes care of the rest.

**Evolution of Cloud Hosting:**
Dedicated Server
- Utilised by a single Customer
- Overpaying
Virtual Private Server (VPS)
- Hypervisor Multiple Virtual Machines on one machine
Shared Hosting
- One machine shared by many businesses
- Poor 
Cloud Hosting

Cloud Service Provider
- can be chained together 
- Via Single Unified API
- Metered billing
- Automation

**Four most Common Types of cloud service:**
Compute - ECS Networking - VPC Storage - EBS
Database - RDS

**Types of Cloud Computing**

SasS - Software as a Service (For Customers)
Product run and managed by the service provider
e.g. Salesforce, Gmail, Office365

PaaS - Platform as a Service (For Developers
Focus on the deployment and management of your apps.
e.g.heroku

IaaS - Infrastructure as a Service
Blocks for cloud IT, provides access to networking features, computers and data storage.
e.g. AWS

**Cloud Computing Deployment Models**

Public Cloud
e.g. Startups, SasS

Private Cloud (On-Premise) e.g. OpenStack
e.g. Strict Regulatory Compliance

Hybrid Cloud
VPN / Direct Connection
e.g. Banks FinTech

Cross-Cloud
e.g. Azure Arc, Anthos

**Creating AWS Account**

Identity and Access Management (**IAM**) -
Creating a new User Adding User to groups  Creating a new Group and adding Policies to it. E.g. Admin Group

Policy: **PowerUserAccess**
Full Access to AWS but not Users and groups.

Services that are Global. S3  CloudFront  **Metered Billing**

AWS Budgets  Sends email when threshold is met using SNS (Simple Notification Service)

**Billing Alarm**

Cloudwatch -
Collection of services

Logs,
Alarms
metrics

Setup MFA

**Kondratiev waves** (Innovation Wave or K-Wave)
Cycle like phenomena in the global world economy

**Burning platform**
Company abandons old technology for new technology

**Evolution of Computing Power**

Computing power
Throughput measured at which a computer can complete a computational task.

AWS Service Offering:
Elastic Compute Cloud (EC2)
AWS Inferentiare (Inf1) - GPU Computing AWS Bracket - Quantum Computing

**Benefits of the Cloud**
**Agility** - Increase speed and agility
**Pay as you go pricing** - Trade capital expense for variable expense 
**Economy of scale** - Benefit from massive economies of scale
**Global Reach** - Go global in minutes **Security**
**Reliability** - Stop spending money on running and maintaining data centers
**High Availability**
**Scalability** - Benefit from massive economies of scale
**Elasticity**
 
OG Six Advantages to the Cloud  Trade capital expense for variable expense - Pay on Demand

Benefit from massive economies of scale
- Sharing the cost with other customers

Stop guessing capacity
- Scale up or down

Increase speed and agility
- Launch resource within a few clicks in minutes
  Stop spending money on running and maintaining data centres
- Focus on your own customers

Go global in minutes
- Deploy your app in multiple regions around the world with a few clicks.

 **AWS Global Infrastructure**

**Regions** - 25
Geographically distinct locations consisting of one or more AZs
Physically isolated from another
Location, power and water supply.
All billing information appears in US-East-1

 **Availability Zones - 81**
Physical Location made up of one or more datacenter
Each region usually has 3 AZs
A Subnet is associated with an Availability Zone

**Direct Connection Locations - 108 Points of Presence - 275+ Local Zone - 11 Wavelength Zones - 17**

**Fault Tolerance**
**Fault domain**
- It will not cascade outside that domain 
**Fault Level** - collection of fault domains
E.g.
Fault Level - Region Fault Domain - AZ (independent failure Zone)
  **AWS Global Network (1:50)**
Interconnections between AWS Global Infrastructure
**Edge Location** act as on and off ramps to the network

**AWS Global Accelerator** **AWS S3 Transfer Acceleration**
Use Edge Locations as an on-ramp

**Amazon CloudFront (CDN)** **Use Edge Locations** **as an off-ramp**
Storage and compute near the end user

**Point of Presence (PoP)**
- for content delivery or expedited upload
- Resources: 
Edge Locations 
- Hold cached data

Regional Edge Caches
- Datacenters that hold much larger caches of less popular files

![[attachments/pasted-graphic-29.png]]

**AWS Services using PoPs (****content delivery** **or** **expedited upload****)**
 CloudFront - CDN service S3 Transfer Acceleration - generate URL to be used by end users to upload files AWS Global Accelerator - optimal path from the end users to your web-servers

**AWS Direct Connect**
- Private/dedicated connection between your datacenter, office co-location and AWS
High speed connection from on-premise to AWS

![[attachments/pasted-graphic-1-16.png]]

**AWS Local Zones**
Data centers close to populated area for low latency performance in that area.

**Wavelength Zones**
Edge Computing on 5G Networks - low latency
Subnet tied to a Wavelength Zone 

**Data Residency**
Physical location where cloud resources reside.

**Compliance Boundaries**
Organisation describes where data and cloud resources are allowed to reside.

**Data Sovereignty**
Legal authority asserted over data because its physical location is within jurisdictional boundaries.

**AWS Config** 
Policy as Code service.
Rules to continuous check AWS resources configuration.
Send alerts or auto-remediate. 

**AWS Outpost**
Physical rack of services 
Data will reside where the Outpost physically resides

**IAM Policy**
Deny access to AWS Regions Service Control Policy (SCP) permissions applied organisation wide.

**AWS Ground Station** Lets you control satellite communications
E.g. Weather forecasting, communications

**Cloud Architecture**

**High Availability**  No single point of failure  
Elastic Load Balancer

**High Scalability**
Increase capacity
Vertical - Scaling Up (Bigger Server)
Horizontal - Scaling Out (More Servers)

**High Elasticity** 
Automatically increase or decrease servers

**High Fault Tolerant**
No single point of failure Fail-overs
- Shift traffic to redundant system

**High Durability**
Disaster Recovery (DR)
**CloudEndure Disaster Recovery**
Replicates machines in a low cost staging area.

**Business Continuity Plan (BCPP)** Document on how to handle unplanned disruption in services

Recovery Point Objective (RPO) Recovery Time Objective (RTO)

![[attachments/pasted-graphic-2-13.png]]

**Disaster Recovery Options**
Backup & Restore - Hours
Pilot Light - 10mins
Warm Standby - Minutes
Multi-site Active/active - Real-time

Recovery Time Objective (RTO)

**Management and Development Tools**

**AWS Management Console**
Web-based - build, manage and monitor everything

**PowerShell**
Command-line shell and scripting language. 

**Amazon Resource Names (ARNs)**

Uniquely identify AWS resources. Format: arn:partition:service:region:account-id:resource-id
e.g. arn:aws:s3:us-east-1:4213:user/bob

**Infrastructure as Code (IaC)**

**AWS CloudFormation (CFN)**
Declarative
What you see is what you get - Explicit More verbose but zero chance of mis configuration
Uses scripting languages e.g. JSON YAML, XML

**AWS Cloud Development Kit (CDK)**
Imperative Say what you want - rest is filled in Implicit
Less verbose
Uses programming language - Python Ruby JavaScript

4:00:00

**Access Keys**
Must be granted access 
Access key and Secret

**Shared Responsibility Model**
Cloud security framework

![[attachments/pasted-graphic-3-8.png]]

**EC2**
 **Compute**

**VM, Containers and Serverless**

Virtual Machines Amazon LightSail - managed virtual server service.

Containers

Elastic Container Service (ECS)
Container orchestration service

Elastic Container Registry (ECR)
Repository for container images

ECS Fargate
Serverless orchestration container service
(Pay on demand per running container

**Elastic Kubernetes Service(EKS)**
Fully managed Kubernetes service

**High Performance Computing Services**
Nitro System
Dedicated hardware and lightweight hypervisor
Supercomputer to perform large computation problems 

**Edge Computing**
Pushing computing outside your network e.g. on phones and IoT Devices

**Cost and Capacity Management**

AWS Batch Plans and executes your batch computing workloads

AWS Compute Optimizer Reduce costs and improve performance by analzying your previous usage history

**Storage**
 **Elastic Block Store (EBS) - Block**
Directly accessed by the OS Only a single write Volume
E.g. Virtual hard drive attached to VM

**AWS Elastic File Storage (EFS) - File**
Stored with data and metadata
Multiple connections via a network share Supports multiple reads and writing locks the file.
e.g. File share where multiple users need access to the same drive

**AWS Simple Storage Service (S3) - Object**
Stored with data, metadata and Unique ID
Supports multiple reads and writes (no locks)

**Storage Classes**

**S3 Standard (default)**
99.99% Availability
Replicated across at least 3 AZs

**S3 Intelligent Tiering** ML to analyse object usage to appropriate storage class
Data moved to the most cost effective access tier

**S3 Standard-IA (Infrequent Access)**
Cheaper if you access files less than once a month
Additional retrieval fee applied
50% less than Standard

**S3 One-Zone-IA**
Objects only exist in one AZ.
99.5% Availability
Cheaper than Standard IA by 20%
Reduced durability - Data could be destroyed
A retrieval fee applied

**S3 Glacier**
Long term cold storage Retrieval of data can take minutes to hours but cheap storage

**S3 Glacier Deep Archive**
Lowest storage class
Data retrieval time is 12 hours

**Snow Family**

Snowcone - 14 TB
Snowball Edge - 80TB
Snowmobile - 100 PB Storage

![[attachments/pasted-graphic-4-8.png]]

**Database**

Relational database
- structured data (tabular data)
Non-relational database
- semi-structured data

Data Warehouse
- Analytic workloads
- Column-oriented data-store to quickly aggregate column data

DynamoDB
- serverless NoSQL key/value and document database

DocumentDB
- NoSQL document database (MongoDB compatible)

Relational Database Service (RDS)
Relational database service

MySQL
MariaDB - Fork of MySQL
Postgres (PSQL)
Aurora - fully managed database 
Aurora Serverless 
- serverless on-demand version of Aurora
- Cold Starts

Redshift
- Petabyte-size data-warehouse

ElastiCache
- Redis or Memcached
- In-memory caching

![[attachments/pasted-graphic-30.png]]

![[attachments/pasted-graphic-1-17.png]]

![[attachments/pasted-graphic-2-14.png]]

To make notes on:

![[attachments/pasted-graphic-3-9.png]]

![[attachments/pasted-graphic-4-9.png]]

![[attachments/pasted-graphic-5-7.png]]

![[attachments/pasted-graphic-6-5.png]]

![[attachments/pasted-graphic-7-4.png]]

  

![[attachments/pasted-graphic-8-3.png]]

![[attachments/pasted-graphic-9-3.png]]

![[attachments/pasted-graphic-10-2.png]]

![[attachments/pasted-graphic-11-4.png]]

![[attachments/pasted-graphic-12-1.png]]

![[attachments/pasted-graphic-13-2.png]]

![[attachments/pasted-graphic-14-1.png]]

![[attachments/pasted-graphic-15-1.png]]

![[attachments/pasted-graphic-16-1.png]]

![[attachments/pasted-graphic-17-1.png]]

![[attachments/pasted-graphic-18-1.png]]

![[attachments/pasted-graphic-19-1.png]]

![[attachments/pasted-graphic-20-1.png]]

![[attachments/pasted-graphic-21-1.png]]

![[attachments/pasted-graphic-22-1.png]]

![[attachments/pasted-graphic-23-1.png]]

![[attachments/pasted-graphic-24-1.png]]

![[attachments/pasted-graphic-25-1.png]]

![[attachments/pasted-graphic-26-1.png]]

![[attachments/pasted-graphic-27-1.png]]

![[attachments/pasted-graphic-28-1.png]]

![[attachments/pasted-graphic-29-1.png]]

![[attachments/pasted-graphic-30-1.png]]

  **Goverance**

![[attachments/pasted-graphic-31.png]]

![[attachments/pasted-graphic-32.png]]

AWS

![[attachments/pasted-graphic-33.png]]

![[attachments/pasted-graphic-34.png]]

![[attachments/pasted-graphic-35.png]]

![[attachments/pasted-graphic-36.png]]

Quick Sight 
Pinpoint 
SES

![[attachments/pasted-graphic-37.png]]

![[attachments/pasted-graphic-38.png]]

![[attachments/pasted-graphic-39.png]]

Serverless can Scale to Zero meaning when not in use the server less resource cost nothing
Pay for value

![[attachments/pasted-graphic-40.png]]

Windows

![[attachments/pasted-graphic-41.png]]

**Logging**

![[attachments/pasted-graphic-42.png]]

![[attachments/pasted-graphic-43.png]]

![[attachments/pasted-graphic-44.png]]

![[attachments/pasted-graphic-45.png]]

![[attachments/pasted-graphic-46.png]]

**ML and AI - 10:32:34**

![[attachments/pasted-graphic-47.png]]

![[attachments/pasted-graphic-48.png]]

![[attachments/pasted-graphic-49.png]]

![[attachments/pasted-graphic-50.png]]

![[attachments/pasted-graphic-51.png]]

![[attachments/pasted-graphic-52.png]]

![[attachments/pasted-graphic-53.png]]

![[attachments/pasted-graphic-54.png]]

![[attachments/pasted-graphic-55.png]]

![[attachments/pasted-graphic-56.png]]

![[attachments/pasted-graphic-57.png]]

![[attachments/pasted-graphic-58.png]]

![[attachments/pasted-graphic-59.png]]

![[attachments/pasted-graphic-60.png]]

![[attachments/pasted-graphic-61.png]]

![[attachments/pasted-graphic-62.png]]

TCO (Total Cost of Ownership) and Migration

![[attachments/pasted-graphic-63.png]]

![[attachments/pasted-graphic-64.png]]

![[attachments/pasted-graphic-65.png]]

![[attachments/pasted-graphic-66.png]]

![[attachments/pasted-graphic-67.png]]

![[attachments/pasted-graphic-68.png]]

![[attachments/pasted-graphic-69.png]]

**AWS Budget Report - send daily, weekly or monthly reports** 

![[attachments/pasted-graphic-70.png]]

![[attachments/pasted-graphic-71.png]]

**Security**

![[attachments/pasted-graphic-72.png]]

![[attachments/pasted-graphic-73.png]]

![[attachments/pasted-graphic-74.png]]

![[attachments/pasted-graphic-75.png]]

![[attachments/pasted-graphic-76.png]]

![[attachments/pasted-graphic-77.png]]

![[attachments/pasted-graphic-78.png]]

**AWS Inspector**

![[attachments/pasted-graphic-79.png]]

![[attachments/pasted-graphic-80.png]]

![[attachments/pasted-graphic-81.png]]

![[attachments/pasted-graphic-82.png]]

![[attachments/pasted-graphic-84.png]]

![[attachments/pasted-graphic-85.png]]

![[attachments/pasted-graphic-86.png]]

![[attachments/pasted-graphic-87.png]]

Study Variatues

![[attachments/pasted-graphic-88.png]]

![[attachments/pasted-graphic-89.png]]

**Amazon QuickSight** is the most appropriate service in the scenario.  It is a fully-managed service that allows for insightful business intelligence reporting with creative data delivery methods, including graphical and interactive dashboards.

**Amazon S3 Transfer Acceleration** enables fast, easy, and secure transfers of files over long distances between your client and an S3 bucket.

**AWS Certificate Manager** allows the web administrator to maintain one or several SSL/TLS certificates

**AWS Personal Health Dashboard** - display scheduled maintenance activities

**Amazon CloudFront** supports country-level location-based web content personalization with a feature called Geolocation Headers.

**Route53** allows different resources to serve content based on the origin of the request

Upgrade to EC2” is the feature that allows customers to “create a copy of the LightSail instance in EC2”.

**AWS Service Catalog** can be used to create & deploy portfolio of products within AWS infrastructure.

**AWS Organizations**
AWS service or feature can be used to restrict the individual API actions that users and roles in each member account can access

Infrastructure automation tools:
**AWS OpsWorks AWS CloudFormation**

**AWS Support plan**
Business  - technical support through phone calls
Enterprise - Infrastructure Event Management without additional costs

AWS Artifact is your go-to, central resource for compliance-related information that matters to you

**AWS Cost Management tools**
Create budgets and receive notifications as well as terminate AWS resources if budget thresholds are exceeded

**AWS Cost and Usage report** - view the most granular data about your AWS bill?

## Related
- [[devops-moc]]
- [[aws-cloud-practitioner]]
- [[sns-simple-notification-service]]
- [[vpc-virtual-private-cloud]]
