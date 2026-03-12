---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# CloudFront

Content delivery network (CDN)
System of distributed servers that deliver webpages and other web content to a user based on the geographic location of the user

Deliver your entire website, including dynamic, static, streaming and interactive content using a global network of edge locations.
Request for content is automatically routed to nearest edge location.

**Edge Location** 
Where content will be cached (separate to an AWS Region/Availability Zone)

**Origin**
Origin of all the files that the CDN will distribute.
E.g. S3 Bucket, an EC2 Instance, and Elastic Load Balancer or Route 53.

**Distribution** 
Name given the CDN which consist of a collection of Edge Locations.

First user queries Edge Location for a file. 
If it doesn’t have the file it will download the file from the source and cached for the time to live (in seconds)
Second user will get the file straight from the Edge Location.

**Web Distribution** - Typically used for Websites.
**RTMP** - Used for Media Streaming

Edge locations are not just READ only - you can write to them too (Put objects on to them)

Objects are cached for the life of the **TTL (Time To Live)**

Can clear cached objects, but you will be charged.

## Related
- [[cloudformation]]
- [[cloudwatch]]
