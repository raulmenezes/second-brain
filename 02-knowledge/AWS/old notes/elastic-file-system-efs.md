---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# Elastic File System (EFS)

File storage service for EC2(Elastic Compute Cloud) Instances
Create and configure file systems quickly with the interface
Storage capacity is elastic - grows and shrink automatically

Only can mount one EBS volume to EC2 (can’t be shared)
EFS can be shared with two EC2 instances

Create file system access:

Same security group

 Mount -t efs -o tls (ESF file system id):/ /var/www/html/ 

Supports the Network File System Version 4 (NFSv4) protocol
Only pay for the storage you use (no pre-provisioning required.)
Scales up to petabytes 
Supports thousands of concurrent NFS connections
Data is stored across multiple AZ's within a region
Read After Write Consistency

**Placement Groups**

**Two types of Placement Group**

**Clustered Placement Group**

Grouping of instances within a single Availability Zone
Applications that need low network latency high network throughput
Only certain instances can be launched in this group
Can’t span multiple availability zones

**Spread Placement Group**

Each instance placed on distinct underlying hardware
Application with critical instanced that should be kept separate from each other. (Business Risk)

Can’t merge placement groups
Can’t move existing instances into placement groups. Need to create an AMI

## Related
- [[ebs-elastic-block-storage]]
- [[elastic-load-balancers]]
