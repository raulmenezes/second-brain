---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/java
  - topic/spring
  - topic/testing
---

# Query DSL   Domain Specific Language

Customised extension of a software language that address a specific business purpose 

E.g.
findByStateLike( String stateName)
where state is in the model
Query preser will match findBy, queryBy readBy countBy getBy - JPA entity attribute names

findFirstBy

**And / Or**
E.g. findbyStateAndCountry

**Equals / Is / Not**

E.g. findByStateNot

**Like / NotLike**

trying to match a portion of the criteria filter value

**StartingWith  / EndingWith / Containing**

**Less Than (Equal) / Before / After**

findbyCreatedDateBefore

**True / False**
findByActiveTrue

**IsNull**

**In**

When you need to test if a column value is part of a collection or set of values or not

**IgnoreCase**

perform a case insensitive comparison

**OrderByCountryAsc / Desc**

**First / Top / Distinct**

Limit the results returned by the query
E.g.
findTop5ByStateLike("A")

## Related
- [[software-engineering-moc]]
- [[query-annotation]]
- [[jpa-and-spring-data]]
- [[6-key-areas-spring-framework]]
