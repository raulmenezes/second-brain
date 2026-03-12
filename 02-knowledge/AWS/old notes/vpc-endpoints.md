---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# VPC Endpoints

Enables you to privately connect your VPC to supported AWS services
Powered by PrivateLink without requiring: 
- an internet gateway, NAT device, VPN connection or AWS Direct Connect connection
Instances in your VPC do not require public IP address to communicate with resource in the service
- Traffic between your VPC and the other service **does not leave the Amazon network**

**Endpoints are** **:**
- Virtual devices
- Horizontally scaled
- Redundant
- Highly available VPC components that allow communication between instances in your VPC and services without imposing availability risks or bandwidth constraints on your network traffic

**T****wo types of VPC endpoints**

**Interface Endpoints**

Elastic network interface with a private IP address that serves as an entry point for traffic destined to a supported service. 

**Gateway Endpoints**

Amazon S3
DynamoDB

Using NAT Gateway (Access to the internet) we leave the Amazon Network, VPC Gateway does not leave our VPC network when reaching things like S3

## Related
- [[vpc-flow-logs]]
- [[vpc-lab]]
- [[components]]
