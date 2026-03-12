---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# S3 (Simple Storage Service)

- Highly scalable object storage
- Safe place to store files (Word documents, pictures, movies)
- Files are stored in Buckets (same as folders)
- Has a universal namespace - must be unique globally 
- Object Base Store
	- Key - name of object
	- Value (sequence of bytes)
	- Version ID (versioning)
	- Metadata (data about data you are storing)
	- Subresources:
		- Access Control List
		- Torrent

0 - 5Tb File Size

Data Consistency Model
Read after Write consistency for PUTS of new Objects - 
Eventual Consistency for Overwrite PUTS and DELETES (can take time to propagate)

**S3 - Features**
Tiered Storage Available
Lifecycle Management - E.g. When a file is 30 days old move it to this tier and when its 90 days old archive it off to **Glacier**
Versioning - Multiple versions of objects in your S3 Buckets
Encryption - Encrypt them at REST
MFA Delete - Multi factor authentication for deleting objects
Secure Data using Access Control Lists and Bucket Policies 

**6 types of S3 Storage Classes**

**S3 Standard**
99.99% Availability and durability
Stored redundantly across multiple devices in multiple facilities

**S3 - IA - (Infrequently Accessed)** 
Less frequently but requires rapid access when needed
Lower fee than S3 but charged a retrieval fee

**S3 One Zone - IA**
Lower cost option for IA data
Not require multiple Availability Zone 

**S3 - Intelligent Tiering**
Optimize cost by moving data to the most cost-effective access tier 

**S3 - Glacier**
For Data archiving - costs are competitive with on premises solutions.
Retrieval times configurable from minutes to hours

**S3 - Glacier Deep Archive**
Lowest cost storage class
Retrieval time of 12 hours is acceptable 

**S3 - Charges**

**Storage** - Amount of data
**Requests** - Number of Request
**Storage Management Pricing** - Different Tiers 
**Data Transfer Pricing**
**Transfer Acceleration**
	Fast transfer of files over long distances between your end users and an S3 bucket
	Uses CloudFront - Data is routed to Amazon S3 over an optimised network path
	(Uploading to the Edge location rather than the S3 bucket itself)
**Cross Region Replication**
	Bucket in US and replicate objects in Sydney for high availability and disaster recovery

Read S3 FAQs before taking the exams (Comes up A LOT!)
Control access to buckets using either a bucket ACL or using Bucket Polices

**LAB**

Storage -> S3 Buckets (Global view of all buckets)
ACL -> Block one file but not the rest
Bucket Policy -> Works on a Bucket Level

**Restricting Bucket Access**

Bucket Policies - Applies across the whole bucket
Object Policies - Applies to individual files
IAM Policies to Users & Groups  

Management -> 
 

**S3 Object Lock**
Store objects using a write once, read many (WORM) model

## Related
- [[devops-moc]]
- [[sns-simple-notification-service]]
- [[simple-work-flow-service-swf]]
- [[storage-gateway]]
