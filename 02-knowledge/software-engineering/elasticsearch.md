---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/ai
  - topic/aws
  - topic/monitoring
---

# ElasticSearch

Horizontally scaleable search engine
Shard is an inverted index of documents

**Search Engines are good at**  Finding documents that contain specific terms and phrases
Socring and sorting documents according to **relevance**
Filtering/ Grouping docs and aggregating data

**Kibana** 
Web UI for searching and visualising, 
Complex aggregations, graphs and charts
Used for Log analysis

**Logstash/ Beats**
Ways to feed data into Elasticsearch
Not just logs
Amazon S3 Logs

**X-Pack - Paid Add-on (Also Free tier)**
Security
Alerting 
Monitoring Reporting
Machine Learning
Graph Exploration

**Concepts:**
**Documents**
JSON structure

**Types**
Schema and mapping shared by documents 
(ES 6 only one type is allowed per index)

**Indices**
An index powers search into all documents within a collection of types.
Contain inverted indices that let you search across everything within them at once

**Inverted Index**

![[attachments/pasted-graphic-5.png]]

**TF-IDF** 
Term Frequency * Inverse Document Frequency

**Term Frequency** 
How often a term appears in a given document

**Document Frequency** is how often a term appears in all documents

**Term Frequency / Document Frequency** measures the relevance of a term in a document

## Related
- [[software-engineering-moc]]
- [[questions]]
- [[encapsulated-objects-can-contain-related-data-and-code]]
- [[jpa-entity-relationships]]
