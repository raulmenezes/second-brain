---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
---

# Web Identity Federation & Cognito

Web Identity Federation
Give your users access to AWS resources after they have authenticated with web-based identity provider e.g. Amazon, Facebook
Trade for temporary AWS security credentials

**Cognito provides Web Identity Federation**

Sign-up and sign-in to your apps 
Access for guest users
Acts as a **Identity Broker** between app and **Web ID provider** (No additional code)
Synchronises user data for multiple devices 
Recommend for all mobile applications AWS

**User Pool**
User directories used to manage **sign-up and sign-in functionality** for applications
Generates a JSON Web Token (JWTs)
User based

**User Identity**
Provide temporary **AWS credentials to access** AWS services like S3 or DynamoDB

![[attachments/pasted-graphic-1-2.png]]

Push synchronisation using SNS

## Related
- [[devops-moc]]
- [[iam-identity-access-management]]
- [[identity-access-management-roles-iam]]
- [[s3-version-control]]
