---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/snippets
---

# AWS K8

Installing Kops:
https://kops.sigs.k8s.io/getting_started/install/

Install kubectl on server

Creating a kops IAM User with permissions : 
Inside IAM Create new Group
Groups -> kops
Find and attach 5 Access Policy Names 

Create new User Add User -> kops

Programmatic access
Add user to group and click on the kops group

Note down - Access Key and Secrete Access Key
Never share the keys with anyone

Configure the number of nodes:

kops edit ig nodes --name {NAME}
kops get ig --names {NAME}

Configure the master node:
kops edit ig master-eu-west-2a ${NAME} 
 

![[attachments/pasted-graphic-24.png]]

## Related
- [[devops-moc]]
- [[aws-command-line]]
- [[what-is-docker]]
- [[overview-kibernetes]]
