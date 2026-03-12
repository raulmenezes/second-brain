---
tags:
  - area/devops
  - area/knowledge
  - topic/ansible
  - topic/database
  - topic/kubernetes
  - topic/monitoring
  - topic/snippets
---

# Setup Prometheus Monitoring  on Kubernetes using Helm and Prometheus…

1.Creating all configuration of YAML files yourself and execute them in right order
- Stateful Sets for Prometheus, Alertmanager, Grafana, ConfigMap, Secrets    

2. Using an operator
- Manager for all Prometheus Components

Statful Set & deployment  Manage its Pod Replicas 

Manages the combination of all components as one unit 
- Find Prometheus operator
- Deploy in K8s Cluster

3. Using Helm

Stateful application
e.g. Database
e.g. Application that stores data

![[attachments/pasted-graphic-5-8.png]]

![[attachments/pasted-graphic-4-10.png]]

## Related
- [[prometheus-monitoring]]
- [[helm-kubernetes]]
- [[Ansible]]
