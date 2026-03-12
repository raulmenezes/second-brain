---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/monitoring
---

# EBS   Elastic Block Storage

Persistent block storage volumes for use with EC2 instances.
Automatically replicated within its Availability Zone to protect you from component failure

5 Types of EBS Storage:
General Purpose (SSD)  - gp2
Provisioned IOPS - io1
Throughput Optimised Hard Disk Drive - st1
Cold Hard Disk Drive - sc1
Magnetic - standard 

![[attachments/pasted-graphic-2.png]]

Volumes exist on EBS - virtual hard disk
Snapshots exist on S3 - Photograph of the disk - Point in time copies of volumes
Snapshots are incremental - means that only the blocks that have changed since your last snapshot are moved to S3

(Amazon Machine Images) AMI's from both Volumes and Snapshots

Able to change EBS volume sizes ( size and storage type) 

Volumes be in same availability zone as the EC2 Instance

Move an EC2 volume from on AZ to another - Snapshot of it, create an AMI from the snapshot then use the AMI to launch the EC2 instance in a new AZ

If moving regions - need to Copy the AMI from one region to another 

**AMI Types - EBS vs Instance store**
Instance Store Volumes are sometimes called Ephemeral Storage.
Instance store volumes cannot be stopped. If host fails you will lose your data

EBS instances can be stopped. you not lose the data on the instance
Rebooting both will not lose you data

By default both ROOT volumes will be deleted on termination.
However, with EBS volumes you can tell AWS to keep the root device volume

## Related
- [[elastic-file-system-efs]]
- [[advanced-elastic-load-balancers-theory]]
