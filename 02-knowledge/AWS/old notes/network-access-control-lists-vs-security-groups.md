---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
  - topic/snippets
---

# Network Access Control Lists vs Security Groups

VPC automatically comes with a default network ACL
- Default it allows all outbound and inbound traffic.

You can create custom network ACLs.
- By default, each custom network ACL denies all inbound and outbound traffic until you add rules

Each subnet in your VPC must be associated with a network ACL.
- If you don't explicitly associate a subnet with a network ACL, the subnet is automatically associated with the default network ACL

Block IP Addresses using network ACLs not Security Groups

A Network ACL can associate with multiple subnets
Subnet can be associated with only one network ACL at a time.
When you have associated a network ACL with a subnet, the previous association is removed

Network ACLs contain a numbered list of rules that is evaluated in order, starting with the lowest numbered rule

Network ACLs have separate inbound and outbound roles and each rule can either allow or deny traffic

Network ACLs are stateless, responses to allowed inbound traffic are subject to rules for outbound traffic (and vice versa)

## Related
- [[identity-access-management-roles-iam]]
