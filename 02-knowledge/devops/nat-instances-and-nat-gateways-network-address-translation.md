---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# NAT Instances & NAT Gateways   Network address translation

Allows Private Subnets to talk to the internet E.g. To download package

NAT Instance - Rarely used now (Use Gateways instead)

NAT Gateway better for scaleability 

**NAT Instances**
When creating a NAT instance, disable source/destination check on the instance
NAT instances must be in a **public subnet**
There must be a route out of the private subnet to the NAT instance, in order for this to work - Add to Route Table 
Amount of traffic that NAT instances can support depends on the instances size.
- (If you are bottlenecking, increase the instance size)
You can create high availability using Autoscaling Groups, multiple subnet in different AZs and a script to automate failover.
Behind a Security Group e.g. WebDMZ group

**NAT Gateways**
Redundant inside the Availability Zone
Preferred by the enterprise
Start at 6Gbps and scales currently to 45Gbps
No need to patch
Not associated to security group
Automatically assigned to a public IP address
Remember to update your route tables
No need to disable Source/Destination checks

If you have resources in multiple AZs and they share one NAT gateway, in the event that NAT gateway's AZ is down, resources in the other AZ lose internet access.
To create an Availability Zone-independent architecture, create a NAT gateway in each AZ and configure your routing to ensure that resources use the NAT gateway in the same AZ

## Related
- [[devops-moc]]
- [[network-access-control-lists-vs-security-groups]]
- [[advanced-elastic-load-balancers-theory]]
- [[manage-azure-subscription-by-using]]
