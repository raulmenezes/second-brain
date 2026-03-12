---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
---

# Simple Work Flow Service (SWF)

Use cases vs SQS
Makes it easy to coordinate work across distributed application components
Enables applications such as :
media processing, web application backends, business process workflows, and analytics pipelines, to be designed **as a coordination of tasks.**

Tasks represent invocations of various processing steps in an application which can be performed by:
executable code, web service calls, human actions, and scripts

**SWF vs SQS**

SQS has a retention period of up to 14 days; with SWF workflow executions can last up to 1 year
SWF presents a task-oriented API
SQS offers a message-oriented API
SWF ensures that a task is assigned only once and is never duplicated
SQS needs to handle duplicated messages and may also need to ensure that a message is processed only once
SWF keeps track of all the tasks and events in an application.
SQS you need to implement your own application-level tracking especially if your application uses multiple queues

**SWF Actors**

**Workflow Starters** 
An application that can initiate a workflow
E.g. e-commerce website following the placement of an order, or a mobile app searching for bus times

**Deciders**
Control the flow of activity tasks in a workflow execution.
If something has finished (or failed) in a workflow, a Decider decides what to do next

**Activity Workers** 
Carry out the activity tasks

## Related
- [[sns-simple-notification-service]]
- [[s3-simple-storage-service]]
