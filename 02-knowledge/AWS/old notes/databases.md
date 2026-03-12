---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/networking
  - topic/spring
---

# Databases

**Relational databases on AWS:**
SQL Server
Oracle
MySQL Server
PostgreSQL
Aurora
MariaDB

RDS has two key features:
- Multi-AZ - For Disaster Recovery
- Read Replicas - For Performance

Connection string 
Update the DNS to new if Database fails

No automatic fail recovery 

Non Relational Databases are:
	DynamoDB

Connection = Table
Document = Row
Key Value Pairs = Fields

**Data Warehousing**

Use for business intelligence
Tools like Cognos, Jaspersoft, SQL Server Reporting Services, Oracle Hyperion, SAP NetWeaver
Use different type of architecture both from a database perspective and infrastructure layer
AWS Warehouse Solution is called **Redshift**

Pulls in very large and complex data sets
Used by management to do queries on Data (E.g. Current Performance Vs Targets)

Online Transaction Processing (OLTP) differs from Online Analytics Processing (OLAP) in terms of types of queries you will run

E.g. OLTP
Order number 2120121
Pulls up a row of data such as
Name, Data, Address, etc.

E.g. OLAP
Net Profit for EMEA and Pacific for the Digital Radio Product
Pull is large number of records

**ElasticCache**

Web service that makes it easy to deploy, operate and scale an **in-memory cache** in the cloud
Improves the performance of web applications by **allowing you to retrieve information from fast**, managed, in-memory caches,
Instead of on slower disk-based databases.
Speed up performance for existing databases frequent identical queries.

Supports two open-source in-memory caching engines:
Memcached
Redis

## Related
- [[databases-moc]]
- [[rds-relational-databases]]
- [[prod-deployment-database]]
- [[database-initialization-with-spring]]
