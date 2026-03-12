---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/monitoring
  - topic/testing
---

# API Gateway

For developers to publish, maintain, monitor, and secure APIs at any scale.
Create an API that acts as a “Front Door” for applications to access data, business logic, or functionality from your back-end services such as applications running on EC2

**What API Gateway Does:**
 Expose HTTPS endpoints to define a REST API 
Serverless connect to services like Lambda & DynamoDB 
Send each API endpoint to a different target
Run efficiently with low cost
Scale effortlessly
Track and control usage by API key
Throttle requests to prevent attacks
Connect to CloudWatch to log all requests for monitoring
Maintain multiple versions of your API

**Configure API Gateway**
Define API (container) 
Define Resources and nested Resources (URL paths)
For each Resource - 
	Select supported HTTP methods 
	Set security 
	Choose Target e.g. EC2, Lambda
	Set request and response transformations

**Exam Tips**
Caching capabilities to increase performance
Low cost and scales automatically
Throttle API gateway to prevent attacks
Log results on CloudWatch
If using multiple domains with API Gateway ensure you have enabled CORS on API Gateway
CORS is enforced by the client

## Related
- [[storage-gateway]]
- [[vpc-virtual-private-cloud]]
- [[ui-tech-interview]]
