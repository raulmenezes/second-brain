---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/monitoring
  - topic/networking
---

# CloudWatch

Monitoring your AWS resources, as well as the applications that you run on AWS

**Compute**
EC2 Instance
Autoscaling Groups
Elastic Load ~Balancers
Route53 Health Checks

**Storage & Content delivery**
EBS Volumes Storage Gateways
CloudFront

EC2
**Host Level Metric Consist of:** CPU
Network 
Disk 
Status Check

**CloudTrail - CCTV**
Recording users and resource activity of AWS Management Console actions and API calls.
Identify which users and accounts call AWS:
	The source IP address from which calls were made
	- When the calls occurred 

CloudWatch monitors **performance**
CloudTrail monitors **API calls** in the AWS platform.

CloudWatch with EC2 will monitor events every **5 mins by default**
Can have **1 minute** intervals by turning on **detailed monitoring** 
Can create CloudWatch alarms which trigger notifications.
CloudWatch performance
CloudTrail auditing

Dashboards - See what is happening with your AWS environments
Alarms - Notify you when particular service thresholds are hit 
Events - CloudWhat events help you respond to state changes in your AWS resources.

## Related
- [[cloudfront]]
- [[cloudformation]]
- [[lambda]]
