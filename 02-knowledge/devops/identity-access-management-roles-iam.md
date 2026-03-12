---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/snippets
---

# Identity Access Management Roles   (IAM)

Roles to enable us to interact with the AWS platform.
Without having to pass our EC2 instances access key ids and access password 

Create new Role
Service - EC2
Permission - Admin Access
Name - Admin Access

Create/Use EC2 Instance

SSH into Instance and delete creds on .aws

Attach Role to EC2 Instance

Actions -> Instance Settings -> Attach Replace IAM Role

New IAM role on instance

Roles are more secure than storing your access key and secret access key on individual EC2 instances
Roles can be assigned to instances using both the console and command line
Roles are universal - can be used in any region

## Related
- [[devops-moc]]
- [[iam-identity-access-management]]
- [[web-identity-federation-and-cognito]]
- [[aws-command-line]]
