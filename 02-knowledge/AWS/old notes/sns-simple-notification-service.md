---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
---

# SNS   Simple Notification Service

Makes it easy to setup, operate and send notifications from the cloud.
Capability to publish messages from an application and immediately deliver them to subscribers or other applications.

Push notifications to Apple, Google, Fire Os and Windows devices as well as Android devices in China with Baidu Cloud Push
Also Deliver notifications by SMS text message or email to SQS queues or any HTTP endpoint

Allows you to group multiple recipients using topics.
A topic is an "access point" for allowing recipients to dynamically subscribe for identical copies of the same notification

One topic can support deliveries to multiple endpoint types:
SNS delivers appropriately formatted copies of your message to each subscriber e.g. iOS or Android

To prevent messages being lost - stored redundantly across multiple availability zones

**Exam Tips**

Instantaneous push based delivery
Flexible message delivery over multiple transport protocols
Inexpensive, pay as you go model with no up-front costs
Web-based AWS Management Console offers the simplicity of a point and click interface

**SNS vs SQS**

Both Messaging Services in AWS
SNS - Push
SQS - Polls (Pulls)

**Elastic Transcoder** 

Media Transcoder in the cloud
Convert media files to different formats e.g. smartphones, PCs
Provides transcoding presets for popular output formats - settings for devices e.g. iPhone 5 vs iPhone X
S3 bucket -> Lambda Function -> Elastic Transcoder -> S3 Bucket

## Related
- [[s3-simple-storage-service]]
- [[simple-work-flow-service-swf]]
