---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
---

# Encrypted Root Device   Volumes & Snapshots

Root can’t be encrypted by default 

Snapshots of encrypted volumes are encrypted automatically
Volumes restored from encrypted snapshots are encrypted automatically
You can share snapshots but only if they are unencrypted
These snapshots can be shared with AWS accounts or made public

Steps to encrypt root device volumes:
1. Create Snapshot of unencrypted root device volume
2. Copy Snapshot and select encrypt option
3. Create AMI from the encrypted Snapshot
4. Use that AMI to launch new encrypted instances

## Related
- [[microservice-helm-and-argocd]]
- [[advanced-elastic-load-balancers-theory]]
- [[ebs-elastic-block-storage]]
