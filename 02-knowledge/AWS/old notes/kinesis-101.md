---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/kubernetes
---

# Kinesis 101

Streaming Data
data that is generated continuously by thousands of data sources
E.g. Purchases from an online store, Stock prices, Social Networking Data

Load and analyse streaming data. 
Provides the ability to build custom applications for business needs

**Three different types of Kinesis**

Kinesis Streams
- Consist of shards
- Capacity depends on number of shards
- Stored for 24 hours

Kinesis Firehose
- No data persistence
- Used as soon as data entered e.g. ElasticSearch / Redshift

Kinesis Analytics
- Analyse data on the fly until its stored on S3, ElasticSearch

## Related
- [[devops-moc]]
- [[questions-power-user-access-allows]]
- [[kubernetes]]
- [[overview-kibernetes]]
