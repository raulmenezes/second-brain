---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
---

# Lambda

Compute Service where you can upload code and create a Lambda function

AWS takes care of provisioning and managing the servers that you use to run the code.

You don’t have to worry about OS, patching, scaling, etc.

**Event Drive**
Where AWS Lambda runs your code in response to events
Changes to data in S3 bucket or an Amazon DynamoDB table 

**Response to HTTP Request**
Using Amazon API Gateway or API calls made using AWS SDKs.

Continuous Scaling

Scales out (not up) automatically
Functions are independent, 1 event = 1 function
Functions can trigger other lambda functions, 1 event can = X functions

AWS **X-ray** allows you to debug complicated architectures
Lambda can do things globally, you can use it to backup S3 buckets to other S3 buckets

RDS is not serverless 

**Ultimate Extraction Layer**
Data Centres
Hardware
Assembly Code/Protocols 
High Level Languages
Operating Systems
Application Layer/ AWS APIS
AWS Lambda

## Related
- [[vpc-lab]]
- [[cloudwatch]]
