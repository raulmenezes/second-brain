---
tags:
  - area/devops
  - area/knowledge
  - topic/database
  - topic/kubernetes
---

# StatefulSet

![[attachments/pasted-graphic-1-14.png]]

 Why is identity necessary?  2 or more database instances. We get data inconsistency. 

Only one pod is allowed to read and the other is allowed to read.
Master and Slave Pods Don’t have access to the same physical storage Continuously synchronising of data with the master  

![[attachments/pasted-graphic-2-11.png]]

Configuring the cloning and data synchronisation Making remote storage available Managing and back-up

## Related
- [[devops-moc]]
- [[storage-class]]
- [[traefik]]
- [[useful-info]]
