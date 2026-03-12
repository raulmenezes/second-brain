---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
---

# Storage Class

E.g  **apiVersion**: storage.k8s.io/v1
**kind**: StorageClass
**metadata**:
  **name**: slow
**provisioner**: kubernetes.io/aws-ebs
**parameters**:
  **type**: io1
  **iopsPerGB**: "10"
  **fsType**: ext4

Four types: default is gp2

kubectl get pv

Default behaviour is for the volume to be deleted if the cluster is removed.

## Related
- [[devops-moc]]
- [[storage-gateway]]
- [[statefulset]]
- [[history-of-aws]]
