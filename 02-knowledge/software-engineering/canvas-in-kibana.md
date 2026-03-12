---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/javascript
---

# Canvas in Kibana

**_doc**

![[attachments/pasted-graphic-4-1.png]]

Instead of creating the index dynamically from the first document. 
We can create the index beforehand to set certain settings

![[attachments/pasted-graphic-2-3.png]]

**_bulk**

Insert multiple documents
Structure is different to _doc

![[attachments/pasted-graphic-3-1.png]]

**_search**

Find all documents

![[attachments/pasted-graphic-5-1.png]]

Find all documents for places that sell soup 
Results are ranked by “relevance” (_score)
{ 	“query”: {
		“match”: {
			“business_name”: “soup”
		}
	}
}

![[attachments/pasted-graphic-6-1.png]]

Find all documents for places that sell soup 
Results are ranked by “relevance” (_score)
{ 	“query”: {
		“match”: {
			“business_name”: “soup”
		}
	}
}

Boolean combination of queries. E.g must or must_not
Find all docs with “soup” and “san francisco” in the business name 

![[attachments/pasted-graphic-11.png]]

Combinations can be boosted for different effects.
More weighting for soup

![[attachments/pasted-graphic-1-4.png]]

Highlight the matching fragments 

![[attachments/pasted-graphic-2-4.png]]

Filtering
Find soup companies with an inspection score of greater than 80

![[attachments/pasted-graphic-3-2.png]]

![[attachments/pasted-graphic-4-2.png]]

Geo Query 
Sort restaurants by distance by us

![[attachments/pasted-graphic-5-2.png]]

Geo Mapping are helpful for defining the structure of our document and more efficiently
storing/searching the data within our index
Elasticsearch automatically infers type and creates our mapping if one is not given.

GET /insepections/_mapping/

To change the mapping, delete the index and perform a bulk import again.
In Production its preferred to use the reindex API - You can add new mapping fields without needing to migrate the data

![[attachments/screenshot-2019-09-11-at-22-26-21.png]]

**Taste of Training**
- CRUD operations => PUT data
- Querying Data
- Text Analysis and Mapping
- Custom Mapping
- Node Types
- Understanding Shards

Every search query goes through Analysis - Makes full-text searchable
At index time text strings are analyzed - by default text analysis breaks up a text string into individual works (tokens) and lowercases those words

![[attachments/pasted-graphic-7-1.png]]

Text-analysis is useful for full-text search. But not for aggregations.

**Multi-fiends allow a field to be indexed in multiple ways**

PUT my_index/_doc/20 
{
	"country_name": "United States"
}

**Text** field for full text search
**Keyword** field for aggregations, sorting and exact searches

Multi-Fields in the Mapping

![[attachments/pasted-graphic-8-1.png]]

Breaks strings into tokens.
To view tokens for a string:

GET _analyze
{
	“text”: [“Hello World”],
	“analyser: “standard”
}

**Why optimise your mapping?**  Indexing every string twice:
- **Slows** down indexing
- Takes up more **disk space** (because of more analyze)

Think about how each string will be used:
- Some strings need to be **full-text searchable**
- Some strings are only used in **aggregations** or **exact searches**
- Some strings need to support both types of search

Inverted index - sorted lists of tokens and documents that match them

![[attachments/pasted-graphic-9-1.png]]

In

![[attachments/pasted-graphic-10.png]]

**Elastic Search Nodes and Index Management**

Dedicated Nodes
Controlling Shard Allocation
Index Management
Index Lifecycle Management

**Index Management**

The Rollover Pattern

Time-series Indices often use a **rollover pattern**
- Indexing is performed on an **read-write index**

![[attachments/pasted-graphic-11-1.png]]

Logs, Transactions
Not updating documents - Just increasing more documents
Writing to a specific index (alias)

When the read-write index is either too old or full, **roll it over** to a new index
- The old index can be **shrunk** and is made r**ead-only**

![[attachments/pasted-graphic-12.png]]

Eventually the data is no longer needed and the read-only index is deleted

Write Index Alias Behaviour
Using the **is_write_index** property allows for a single alias to be both the **write** alias and the **search** alias

- E.g. after **logs-1** rolls over to **logs-2** any indexing via **logs-alias** will occur on **logs-2**
- But searches using logs-alias will hit **logs-1** and **logs-2**

e.g. logs-2019-09-11-1

![[attachments/pasted-graphic-13.png]]

![[attachments/pasted-graphic-14.png]]

Reindex **kibana_sample_data_logs** to **logs_write**

## Related
- [[software-engineering-moc]]
- [[jpa-and-spring-data]]
- [[elasticsearch]]
- [[6-key-areas-spring-framework]]
