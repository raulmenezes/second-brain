---
aliases:
  - foundation-of-jpa-and-orm-object-relational-mapping
tags:
  - area/knowledge
  - area/software-engineering
  - topic/database
  - topic/java
  - topic/spring
---

# JPA and Spring Data

**Java Persistence API**
interface specification that describes the management of relational data

**Model**

@Entity
Over Model to conver to JPA Entity

Tell JPA which attribute is the primary Key and how it gets generated 
@Id
@GeneratedValue(strategy = GenerationType.AUTO)

Database will take care of incrementing the primary key

@Column
Table matching Java Object

**Repository - (Spring Data JPA tier)**

Create Interface 

Extends JpaRepository

**Controller**

@RestController
@RequestMapping(“”)

## Related
- [[software-engineering-moc]]
- [[jpa-entity-relationships]]
