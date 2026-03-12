---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# VPC   Lab

When you create a VPC a default Route Table, Network Access Control List (NACL) and default Security Group
It won't create any subnets, nor will it create a default internet gateway
US-EAST-1A in one AWS account can be completely different availability zone to US-EAST-1A in another AWS account. The AZ are randomised
Amazon always reserve 5 IP addresses within your subnets
You can only have 1 Internet Gateway per VPC
security Groups can't span VPCs

Main Route Table where all subnets gets automatically associated with when created.
Create a separate route table for public access

Subnet -> Route Table

Route Table -> Internet Gateway
Subnets can only be associated with one Route Table 

![[attachments/pasted-graphic-8.png]]

## Related
- [[vpc-flow-logs]]
- [[vpc-virtual-private-cloud]]
- [[vpc-endpoints]]
