---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/networking
---

# RDS Backups + Multi   AZ & Read Replicas

**Two different types of Backups for RDS:**

**Automated Backups**
Recover your database to any point in time within a retention period
Retention period can be between one and 35 days.
Daily snapshots and will also store transaction logs throughout the day

AWS will choose the most recent daily backup, then apply transaction logs relevant to that day.
Allows to do a point in time recovery down to a second within the retention period.

Enabled by default and stored in S3, where you get free storage space equal to the size of your database.
Backups are taken within a defined window.
During backup, storage I/O may suspend while your data is being backed up and may experience latency.

**Database Snapshots**
Done manually.
Stored even after you delete the original RDS instance, unlike automated backups

**Restoring Backups (Automatic & Manual Snapshot)**
Restored version of the database will be a new RDS instance with a new DNS endpoint

**Encryption At Rest**
Supported for MySQL, Oracle, SQL Server, PostgreSQL, MariaDB & Aurora

Encryption done using the AWS key Management Service (KMS).
Once the RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted as are its automated backups,
Read replicas and snapshots.

**Multi-AZ**

Exact copy of your production database in another Availability Zone
AWS handles replication for you - synchronised to the stand by database

Used for database maintenance, Instance failure, AZ failure
	Automatically failover to the standby
Can force a failover from one AZ to another by rebooting the RDS instance

Used for **Disaster Recovery** only
For performance improvement you need **Read Replicas**.

**Read Replica**
Allow you to have a read-only copy of your production database.
Achieved by using Asynchronous replication from the primary RDS instance to the read replica.
Used for very read-heavy database workloads

Used for scaling not for (DR) Disaster Recovery
**Must have automatic backup turned** **on** in order to deploy a read replica
Can have up to 5 read replica copies of any database
Can have read replicas of read replicas (but watch out for latency)
Each read replica will have its own DNS end point 
Read replicas can have Multi-AZ
Can create read replicas of Multi-AZ source databases

Read replicas can be promoted to be their own databases. This break replication
You can have read replica in a second region.

## Related
- [[databases-moc]]
- [[check-storage-in-postgresql]]
- [[aurora]]
- [[databases]]
