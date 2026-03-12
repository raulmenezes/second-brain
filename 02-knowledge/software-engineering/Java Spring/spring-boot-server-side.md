---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/database
  - topic/docker
  - topic/java
  - topic/monitoring
  - topic/project
  - topic/snippets
  - topic/spring
  - topic/testing
---

# Spring Boot   Server Side

Spring MVC provide the RESTful endpoints

@SpringBoot Application

**@Configuration** - Spring Configuration on startup
**@EnableAutoConfiguration** - Auto configures framework
**@ComponentScan** - Scans project for Spring annotations and create the beans

***SpringApplication.run(… )***
Starts Spring, creates spring context, applies annotations and sets up container 
**Properties and Environmental Configuration**

***application.properties***
Place on class path root
YAML or Properties format

***Environmental configuration***
application-{profile}.properties

Changing 
***application.properties***

[Logging.level.org](http://Logging.level.org).springframework.web=DEBUG
Server.port=8181

https://docs.spring.io/spring-boot/docs/current/reference/html/common-application-properties.html

**DataSource Pooling**
Strong connection pool improves database throughput and performance
tomcat-jdbc - default pooling strategy

**Liquibase** and **Flyway** 
Java-based database tools for refactoring and versioning
tracking, managing and applying database changes that can be used for any database with a JDBC driver

Hibernate ORM - Object relational mapping tool for Java
Domain model persistence for relational databases.

Spring Config 
Define Spring Beans using Java

Allows for -
Define the DataSource programmatically- to define multiple DataSources as we have multiple Databases
E.g. First Database for JPA code and second Database as Flyway migration

programmatically create spring bean with Java have spring boot add that to the spring context on app startup

JPA entity JPA Repo

## Related
- [[software-engineering-moc]]
- [[interview]]
