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
```
- Instance name
- Index
- Version
- Backends

```

E.g.
app-multiclass:
      index: 25
      version: v5.10
      backends: chad

Run
`./deploy app-multiclass`

Optional
Check the logs

SSH into primary backend to look at logs:

`tail -f -app-multiclass/main.log`

ansible-vault edit group_vars/rds

## Related
- [[partitioning-the-aws-instance]]
