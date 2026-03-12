---
tags:
  - area/devops
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/database
---

# Deploy New Instance

Go to regions.yml file and add new instance to a region: 
- Instance name
- Index
- Version
- Backends

E.g.
Under instances for eu-omega add:
app-multiclass:
      index: 25
      version: v5.10
      backends: chad

If new version: versions.yml

Run

./deploy app-multiclass

Optional
Check the logs

SSH into primary backend to look at logs:

tail -f -app-multiclass/main.log

Find the new account created for the instance

cat ~app-multiclass-v5-13/main.log | grep sysadmin

ansible-vault edit group_vars/rds

## Related
- [[devops-moc]]
- [[load-balancer-issue]]
- [[deploy-equlfax-to-dev-now]]
- [[partitioning-the-aws-instance]]
