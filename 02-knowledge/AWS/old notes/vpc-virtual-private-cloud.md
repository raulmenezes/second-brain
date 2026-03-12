---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# VPC   Virtual Private Cloud

Provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
Control over the virtual networking environment, including selection of your own IP address range creation subnets, a configuration of route tables and network gateways

E.g. Create a public-facing subnet for your webservers that has access to the Internet
Place your backend systems such as databases or application servers in a private facing subnet with no Internet access 

Have multiple layers of security, including security groups and network access control lists, to help control access to EC2 instances in each subnet
Can create a hardware virtual private network (VPN) connection between you corporate datacenter and your VPC and leverage the AWS cloud as an extension of your corporate datacenter

**VPC Features**

Launch instances into a subnet of your choosing
Assign custom IP address ranges in each subnet
Configure route tables between subnets
Create internet gateway and attach it to our VPC
Much better security control over your AWS resources
Instance security group
Subnet network access control lists (ACLS)

**Default VPC vs Custom VPC**
Default VPC is user friendly allowing you to immediately deploy instances
All Subnets in default VPC have a route out to the internet
Each EC2 instances has both a public and private IP address

**VPC Peering**
Allows you to connect one VPC with another via a direct network route using private IP addresses
Instances behave as if they were on the same private network
You can peer VPC's with other AWS accounts as well as with other VPCs in the same account.
Peering is in a star configuration e.g. 1 Central VPC peers with 4 others. **No transitive peering**
You can peer between regions

Security Groups are Stateful
Network Access Control Lists are Stateless

![[attachments/pasted-graphic-6.png]]

## Related
- [[devops-moc]]
- [[vpc-lab]]
- [[kubernetes-google-cloud]]
- [[ccp-certified-cloud-practitioner-clf-co1]]
