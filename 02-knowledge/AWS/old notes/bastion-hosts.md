---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
  - topic/snippets
---

# Bastion Hosts

Computer on  a network specifically designed and configured to withstand attacks.
Computer generally hosts and single application
	e.g. a proxy server and all other services are removed or limited to reduce the threat to the computer
Hardened in this manner primarily due to its location and purpose
- On the outside of a firewall or 
- In a demilitarised zone (DMZ) and usually involves access from untrusted networks or computers

![[attachments/pasted-graphic-9.png]]

NAT Gateway or NAT Instance is used to provide internet traffic to EC2 Instances in a private subnet
Bastion is used to securely administer EC2 instances (using SSH or RDP) (Called **Jump Boxes** in Australia)
Cannot use a NAT Gateway as a Bastion host

## Related
- [[devops-moc]]
- [[questions-power-user-access-allows]]
- [[ebs-elastic-block-storage]]
- [[elastic-file-system-efs]]
