---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# S3 Version Control

Stores all versions of an object (including all writes and even if you delete an object (places a delete marker) )
Great backup tool
Once enabled, Versioning cannot be disabled (only suspended)
Integrates with **Lifecycle** rules
MFA Delete capability - additional layer of security 

With versioning the size of of the buckets will be larger since we are keeping the previous versions
Overriding files with a new version that have been set public will be changed to private.

**S3 - Lifecycle Management**
Manage objects during their lifetime
Automate transition to tiered storage e.g. Glacier storage class
Expire your objects

Lifecycle Rule:
Can be applied to current versions or previous version of a file

**Cross Region Replication**
Requires bucket versioning to be enabled on both the source and destination buckets
Regions must be unique 
Can change the storage class when replicating on a different region
Files in an existing bucket are not replicated automatically
Delete marker are not replicated
Deleting individual version or delete markers will not be replicated 

**S3 Transfer Acceleration**
Utilises the CloudFront Edge Network to accelerate your upload to S3
Use a distinct URL to upload directly to an edge location which will then transfer that file to S3 bucket e.g. acloudguru.s3-accelerate.amazonaws.com

## Related
- [[devops-moc]]
- [[web-identity-federation-and-cognito]]
- [[questions-power-user-access-allows]]
- [[overall-summary]]
