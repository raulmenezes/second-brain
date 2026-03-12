---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# Traefik

3 major components in the configuration: 

**Routers**
- manage the incoming requests.
- entrypoint, certificate resolver, and define the rules for the request

**Services**
- identify where to send requests
- port that Traefik will proxy to and any additional load balancers

**Middlewares**
- modify the request - between the routers and services
- Add headers, authentication, path-prefix

![[attachments/pasted-graphic-92.png]]

Use case:
Reverse Proxy
Ingress controller

## Related
- [[devops-moc]]
- [[atradius]]
- [[statefulset]]
- [[storage-class]]
