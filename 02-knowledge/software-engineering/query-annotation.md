---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/database
  - topic/java
  - topic/spring
---

# @Query Annotation

Better to handle complexity than a query DSL
Reuse exisiting JPQL in your data access layer
Advanced query functionality
Eager loading control("fetch")

**@Query Options**

@Query("select m from Model m where m.name = :***modelname***")

List queryByName(@Param("***modelname***") String name);

**Native Queries**

@Query(value = "select * from Model where name = ?0", nativeQuery = true)
List queryByName(String name);

(Get locked into your database platform)

**Modifiable Query**

@Modifying 
@Query ("update Model m set n.name = ?1")
int updateByName(String name);

**JPA Named Queries**
App startup validates queries rather than at runtime

**Paging and Sorting**

Page type
Adding Pageable page parameter to query
Pageable page = new PageRequest(0,2);
Sort sort = new Sort(Sort.Direction.ASC, "name")

## Related
- [[software-engineering-moc]]
- [[questions]]
- [[query-dsl-domain-specific-language]]
- [[protractor-e2e-testing]]
