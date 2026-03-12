---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
---

# Prod Deployment database

**On azero update the timeout:**
cd /etc/systemd/system
sudo vi lg-app-quilt.service
sudo systemctl daemon-reload

Comment out two of the servers mono and flux and run:
./update app-quilt

After it has completed comment outa zero and uncomment mono and flux and run:
./update app-quilt

## Related
- [[databases-moc]]
- [[rds-relational-databases]]
- [[databases]]
- [[model-cloning-popup-server]]
