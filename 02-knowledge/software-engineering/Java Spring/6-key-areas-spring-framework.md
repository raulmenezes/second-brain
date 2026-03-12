---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/database
  - topic/docker
  - topic/java
  - topic/networking
  - topic/spring
  - topic/testing
---

# 6 Key Areas   Spring Framework

**Core**
***Dependency Injection*** container -> Creates and maintains objects and their dependencies
internationalisation
Validation
Data binding

**Web**
Handling Web Request -> Spring MVC / Spring Web Flux
Servlet Api - object that receives a request and generates a response

Low level API - Not easy to use and less productive

**Spring MVC**

![[attachments/screenshot-2019-03-17-at-09-15-01.png]]

Higher level API
Clear speration of concerns  

**Spring WebFlux**
Reactive Programming
Asynchronous execution

**AOP** (Aspect oriented programming)
programming paradigm that increase modularity by allowing the separation of cross cutting concerns
(span multiple tiers or layers of an application)
E.g. Adding @PreAuthorize

**Data Access**
Easier for applications to interact with data
Database transaction - a series of database operations that must happen together or not at all

Done in Spring with @Transcational
Types of transcations -  Declarative Programmatic and rollbacks

Exception Translation -> Different Vendors have different execptions

![[attachments/image-1.tiff]]

**Integration**
How one application talks to another
Expose operations and run operations on other systems
E.g Rest Template Abstracts and handles the connections to the web service

**Testing**
Comes with built in mocks to make testing easier and faster
Support for cleaning up after tests

**Other Spring Projects**

**Spring Data**
Extends Spring Data Access capabilities
Adds new ways of interacting with  different types of databases E.g. non-relational and cloud based data services
Consistent model for data access 
Series of sub-projects per supported data store
Built in methods for save, delete operations
Spring Data + JPA does the hard work of taking the data stored in the object and translating it/ mapping it to be stored into the targeted store

(Getting Started with Spring Data JPA - Dan Bunker)
Spring Data REST

**Spring Cloud**
Help to build distributed systems - applications linked together in a network (microService single domain)
Microservice needs to find/ discover other microservice 
@EnableDiscoveryClient - find other services and others can find it

**Spring Security** 
Authentication and Authorization
Protection against attacks like session fixation or clickjacking

## Related
- [[software-engineering-moc]]
- [[spring-framework]]
- [[spring-framework-questions]]
- [[spring-configuration-options]]
