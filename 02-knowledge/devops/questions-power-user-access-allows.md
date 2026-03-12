---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# Questions   Power User Access allows

Access to all AWS services except the management of groups and users within IAM

Users and Policy Documents are applied globally

**S3 - 29 out of 37**

S3 has eventual consistency for which HTTP Methods 
Overwrite PUTS and DELETES

Glacier
3 – 5 hours

EBS is block-based 
whereas S3 is object-based.

S3 – OneZone-IA - 99.5%

Multipart upload API for all objects when uploading a 7.5GB file to S3

Remove the ability for images to be served publicy to the site and then use signeed URL with expiry dates

AWS S3 has four different URLs styles that it can be used to access content in S3.  

Virtual Hosted Style URL
Path-Style Access URL
Static web site URL
Legacy Global Endpoint URL

Virtual style puts your bucket name 1st, s3 2nd, and the region 3rd. 
Path style puts s3 1st and your bucket as a sub domain
Legacy Global endpoint has no region.
S3 static hosting can be your own domain or your bucket name 1st, s3-website 2nd, followed by the region. 

AWS are in the process of phasing out Path style, and support for Legacy Global Endpoint format is limited and discouraged. 
However it is still useful to be able to recognize them should they show up in logs. https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html

100 S3 buckets per account

S3 availability 99.99

AWS Storage Gateway
AWS S3 managed storage to supplement on-premise storage. It can also be used within a VPC in a similar way

## Related
- [[devops-moc]]
- [[bastion-hosts]]
- [[route53-routing-policies-aws]]
- [[elastic-load-balancers]]
