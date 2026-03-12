---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
---

# Aurora

MySQL compatible, relational database engine that combines speed and availability

Up to five times better performance than MySQL at a price point one tenth that of a commercial database

**Things to know:**

Start with 10GB, scales in 10GB increments to 64TB (Storage Autoscaling)
Compute resources can scale up to 32vCPUs and 244GB of Memory.

**2 copies of your data is contained in each availability zone**, with minimum of 6 availability zones
- 6 copies of your data

**Scaling Aurora**

Handles the loss of up to two copies of data
- Without affecting database write availability
Up to three copies without affecting read availability.

Self-healing - Continuously scanned for errors and repaired automatically

**Two Types of Aurora Replicas:**

**Aurora Replicas (currently 15)**
	**-** Automated failover
**MySQL Read Replicas (currently 5)**

**Backups**
Automated backups are always enabled on DB Instances
Can take snapshots with Aurora
Do not impact database performance
**Can share Aurora Snapshots with other AWS accounts.**

## Related
- [[databases-moc]]
- [[postgres-operators|operators]]
- [[rds-backups-multi-az-and-read-replicas]]
- [[start-mongo]]
