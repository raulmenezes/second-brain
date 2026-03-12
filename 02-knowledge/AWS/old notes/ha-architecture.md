---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/javascript
  - topic/snippets
  - topic/testing
---

# HA Architecture

Launch Configuration needed before doing ASG(Auto Scaling Groups)

![[attachments/pasted-graphic-1-1.png]]

One Write Master Node on a single EC2 instance which syncs to a S3 bucket
Use an AMI to build the EC2 instance which users will read blogs - Able to create ASG as well
Sits behind Load Balances 

![[attachments/pasted-graphic-2-1.png]]

Reboot with failover - Failing from one AZ to another

## Related
- [[architecture]]
- [[vpc-virtual-private-cloud]]
- [[s3-security-and-encryption]]
