---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/docker
  - topic/java
  - topic/project
  - topic/snippets
  - topic/spring
---

# Spring Configuration Options

XML Based Config

Annotation Based Config
- Component Scans @Controller, @Service

Java Based Config
- Java Class to define Spring Beans
- @Configuration
- Beans are declared with @Bean annotation

Groovy Bean Definition DSL Configuration
- Declare beans in Groovy

Industry trend is to favour java based configurations

**Spring Framework Stereotype**

Used to define Spring Beans in the Spring context

![[attachments/pasted-graphic-16.png]]

Using Spring Bean Factory

![[attachments/pasted-graphic-1-7.png]]

Spring Boot Configuration

Spring Boot Starters
Spring boot starter is a pom which declares a common set of dependencies

Top level dependencies for popular Java libraries
- Brings in dependencies for the project and related Spring components

![[attachments/pasted-graphic-2-7.png]]

Spring Boot is a configuration wrapper around the Spring Framework
Web stuff goes through Spring MVC

Spring Bean Scope
7 Kinds

**Singleton** Only one instance of the bean is created in the IoC container
**Prototype** A new instance is created each time the bean is requested
Request - A single instance per http request (web-aware spring ApplicationContext)
Session - A single instance per http session (web-aware spring ApplicationContext)

Global-session -A single instance per global session (Portlet context)
Application - bean is scoped to the lifecycle of a ServletContext
Websocket - Scopes a single bean definition to the lifecycle of a WebSocket

What annotation do you use to declare a Spring component inside a Java configuration class?

@Bean will declare a Spring Bean (component)

## Related
- [[software-engineering-moc]]
- [[spring-framework-questions]]
- [[hosting-options]]
- [[spring-boot-server-side]]
