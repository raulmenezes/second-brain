---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/javascript
  - topic/networking
---

# Redshift

Data Warehouse service in the cloud - petabyte-scale
Start from $0.25 per hour - $1000 per terabyte

**Can be configured as follows:** 
Single Node (160 GB)
Multi-Node
	Leader Node (manages client connections and receives queries)
	Compute Node (store data and perform queries and computations). Up to 128 Compute Nodes.

**Advanced Compression:**

**Columnar** data stores can **compressed** much more than row-based data stores
- Similar data is stored sequentially on disk

Uses multiple compression techniques

Doesn’t require **indexes** or materialised views
- Less space than traditional relational database systems.

Automatically samples data and selects the most appropriate compression scheme.

**Massively Parallel Processing (MPP)**

Automatically distributes data and query load across all nodes.
Easy to add noes to your data warehouse and enables to maintain fast query performance as your data warehouse grows.

**Backups**

Enabled by default with a 1 day retention period.
Maximum retention period is 35 days.
Attempts to maintain at least three copies of your data
(Original and replica on the compute nodes and a backup in Amazon S3)
Asynchronously replicate snapshots to S3 in another region for disaster recovery

**Redshift is priced as follows**

Compute Node Hours 
- Total number of hours for the compute nodes for the billing period

Not charged for Leader Node hours
Backups
Data transfer (only within a VPC, not outside it)

**Security Considerations:**

Encrypted in transit using SSL
Encrypted at rest using AES-256 encryption
By default RedShift takes care of key management.
- Manage your own keys through HSM (Hardware Security Module)
- AWS Key Management Service

**Availability**

Currently **only available in 1 AZ**
Can restore snapshots to new AZs in the event of an outage.

## Related
- [[devops-moc]]
- [[dns]]
- [[questions-power-user-access-allows]]
- [[architecture]]
