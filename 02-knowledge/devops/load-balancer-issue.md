---
tags:
  - area/devops
  - area/knowledge
  - topic/monitoring
  - topic/networking
---

# Load Balancer Issue

Connections between ubeast 
If we get lots of connections on LBs they will start to reject incoming calls

Go to Grafana and look at “Nginx Connection”

Colt server and ubeast server 

Force to release connections:

# ssh ubeast

# s systemctl restart nginx

# Connections should drop to 0 on Grafana

E.g.
Under instances for eu-omega add:
app-multiclass:
      index: 25
      version: v5.10
      backends: chad

ps -ef | grep nginx

## Related
- [[devops-moc]]
- [[elastic-load-balancers]]
- [[deploy-new-instance]]
- [[advanced-elastic-load-balancers-theory]]
