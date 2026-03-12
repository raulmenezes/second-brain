---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# Storage Gateway

Connects an on-premises **software appliance** with cloud-based storage to provide seamless
And secure integration between an organisation’s on premises IT environment and AWS’s storage infrastructure.
Enables you to securely store data to the AWS cloud for scalable and cost effective storage

Software available for download as a virtual machine (VM) image that you install on a host in your datacenter.
Supports either VMware ESXi or Microsoft Hyper-V.
Install -> Connect to AWS account -> AWS Management Console to create the storage gateway option that is right

**Three types of Storage Gateway**

**File Gateway (NFS)**
Files are stored as objects in your S3 buckets
- Access through a Network File System (NFS) mount point.
Ownership, permissions and timestamps are durably stored in S3 in the user-metadata of the object associated with the file.

Once objects are transferred to S3, they can be managed as native S3 objects, and bucket polices such as versioning, lifecycle management,
And cross-region replication apply directly to objects stored in your bucket.

![[attachments/pasted-graphic.png]]

**Volume Gateway (iSCS)**

Volume interface presents your applications with disk volumes using the iSCSI block protocol
Asynchronously backed up as point in-time snapshots of your volumes, and store in the cloud as Amazon EBS snapshots
Snapshots are incremental backups that capture only changed blocks.
All snapshot storage is also compressed to minimise your storage charges

	**1) Stored Volumes**
Store your primary data locally, while asynchronously backing up that data to AWS.
Provide on-premises applications with low-latency access to their **entire datasets**
	while providing durable off-site backups

Able to create storage volumes and mount them as iSCSI devices from your on-premises applications servers.

Data written to on-premises storage hardware. Data is asynchronously backed up to S3 in the form of Amazon Elastic Block Store (EBS) snapshots.
1 GB - 16TB in size for Stored Volumes.

![[attachments/pasted-graphic-1.png]]

	**2) Cached Volumes**

**Tape Gateway (VTL)**

## Related
- [[api-gateway]]
- [[s3-simple-storage-service]]
