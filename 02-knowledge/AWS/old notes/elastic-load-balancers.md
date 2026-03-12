---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/networking
---

# Elastic Load Balancers

Three Load Balancer Types:

**Application Load Balancer**

Best suited for **HTTP and HTTPS traffic**
Operate at Layer 7 and are application aware
Intelligent, and you can create advanced request routing, sending specified requests to specific web servers

**Network Load Balancer**

Best suited for **TCP** traffic where extreme performance is required.
Operates at connection level Layer 4 
Capable of handling millions of requests per second while maintaining ultra-low latencies

**Classic Load Balancer**

Legacy load balancers
For HTTP/HTTPS applications and use Layer 7 - specific features, such as X-Forwarded and sticky sessions.
Can also use Layer 4 for applications that rely purely on the TCP protocol.

504 error means the gateway has 
Issues with either at the Web Server layer or Database Layer.
Identify where the app is failing and scale it up or out where possible

If you need the IPv4 address from your end user look for the **X-Forward-For** header

Instances are monitored by ELB as reported as:
- InService
- OutofService

Load Balances have their own DNS name. You are never given an IP address

Read ELB FAW for Classic Load Balancers

(10 Question)

**Target Group**
Different groups e.g. EU, America and Australia

## Related
- [[devops-moc]]
- [[advanced-elastic-load-balancers-theory]]
- [[load-balancer-issue]]
- [[elasticache]]
