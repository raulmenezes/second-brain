---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/monitoring
---

# Prometheus Monitoring

![[attachments/pasted-graphic-3-7.png]]

 
**Metres** Format Human readable text
Metrics entries:
HELP - what the metric is  TYPE - 3 metric types
Counter  How many times it happened  Gauge What is the current value of x now  Histogram How long or how big 

**Collecting Metrics** 

Pulls over HTTP from /metrics endpoint

![[attachments/pasted-graphic-27.png]]

![[attachments/pasted-graphic-1-15.png]]

**Configuring Prometheus** 
prometheus.yml
- Which targets
- What interval

![[attachments/pasted-graphic-2-12.png]]

**Alert Manager** 
Prometheus  Difficult to scale
Monitoring of K8s Cluster Node Resources out of the box

## Related
- [[setup-prometheus-monitoring-on-kubernetes-using-helm-and-prometheus]]
