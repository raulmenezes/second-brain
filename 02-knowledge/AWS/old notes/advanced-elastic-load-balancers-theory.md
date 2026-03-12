---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# Advanced Elastic Load Balancers Theory

**Sticky Sessions**
Enable users to stick to the same EC2 instance.
Can be useful if you are storing information locally to that instance.

**Cross Zone Load Balancing**
Enables to load balance across multiple availability zones

![[attachments/pasted-graphic-7.png]]

**Path Patterns**
Allow to direct traffic to different EC2 instances based on the URL contained in the request.
E.g. to a different AZ for /images in the URL

## Related
- [[devops-moc]]
- [[elastic-load-balancers]]
- [[ebs-elastic-block-storage]]
- [[load-balancer-issue]]
