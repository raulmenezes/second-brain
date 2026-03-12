---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/networking
---

# DynamoDB

NoSQL database service all applications that need consistent, single-digit millisecond latency at any scale.

Fully managed database and supports both document and key value data models.

Flexible data model

**Basics of DynamoDB**

Stored on SSD storage
Spread across 3 geographically distinct data centres

**Eventual Consistent Reads (Default)**

Consistency across all copies of data is usually reached within a second.
Repeating a read after a short time should return the updated data (Best Read Performance)

**Strongly Consistent Reads**
Returns a result that reflects all writes that received a successful response prior to the read

## Related
- [[devops-moc]]
- [[lambda]]
- [[module-4]]
- [[module-2]]
