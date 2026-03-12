---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
  - topic/snippets
---

# AWS Command Line

Create a User with Programmatic Access (CLI)
Create a Group - Admin Group - Admin Access Access Key ID + Secret Key

Create a new EC2 Instance

Create a new Key pair - to connect to instance

Move key pair to ssh directory 
Chmod 400 .pem

**Commands:**
ssh ec2-user@XX.XX.XX. -i NAME_OF_KEY.pem 

sudo su

aws configure 

aws s3 ls - list all buckets

aws s3 mb s3://testbucket

cd .aws - Contains config and credentials

## Related
- [[devops-moc]]
- [[basic-commands]]
- [[kops-commands]]
- [[useful-commands]]
