---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/snippets
---

# Components

Orchestration tool



Worker Node
###### **Components**
Pod #pod
- Smallest unit of K8s
- Abstraction over container
- Usually 1 Application per Pod
- New IP address on re-creation
- Ephemeral

Service #service
- permanent IP address
- lifecycle of Pod and Service not connected
- External / Internal services

Ingress
- Domain name routing

ConfigMap #configmap
- External configuration of your application (e.g. Database URL, username)

Secret #secret
- Store secret Data
- Base64 encoded

Volume
- Local or Remote Storage
- K8s doesn't manage data persistance

Deployment
- Stateless
- DB can't be replicated with Deployment

StatefulSet
- Stateful apps or Database


![[attachments/k8s-components.png]]

## Related
- [[vpc-endpoints]]
- [[cloudfront]]
