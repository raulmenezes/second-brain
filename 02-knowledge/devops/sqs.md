---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# SQS

- Gives you access to a message queue that can be used to store messages while waiting for a computer to process them
- Distributed queue system that enabled web service applications to quickly and reliably queue messages that one component in the application generates to be consumed by another component
- Queue is a temporary repository for messages that are awaiting processing

Can decouple the components of an application so they run independently, easing message management between components
Any components of a distributed application can store messages in a fail-safe queue.
Messages can contain up to **256KB** of text in any format.
Any component can later retrieve the messages programmatically using Amazon SQS APO

Queue acts as a buffer between:
The component producing and saving data
The component reviving the data for processing
Queue resolves issues that arise:
if the producer is producing work faster than the consumer can process it
if the producer or consumer are only intermittently connected to the network

There are two types of Queue
- Standard Queues (default)
- Fifo Queues

**Standard Queue**
Have a nearly unlimited number of transactions per second.
Guarantee that a message is delivered at least once.
Occasionally, more than once copy of a message might be delivered out of order. 
Provide best-effort ordering which ensures that messages are generally delivered in the same order as they are sent

**FIFO Queue**
First In First One Delivery and exactly-once processing
The order in which messages are sent and received is strictly preserved
A message is delivered once and remains available until a consumer processes and deletes it
Duplicates are not introduced into the queue.

Also support message groups that allow multiple ordered message groups within a single queue.
Limited to 300 transactions per second (TPS) but have all the capabilities of standard queues.

**Exam**

SQS pull based, not pushed based
Messages can be kept in the queue from 1 minute to 14 days; The default retention period is 4 days

**Visibility Time Out**
Amount of the time that the message is invisible in the SQS queue after a reader picks up that message
Provided the job is processed before the visibility time out expires, the message will then be deleted from the queue.
If the job is not processed within that time, the message will become visible again and another reader will process it.
This could result in the same message being delivered twice
Visibility timeout maximum is 12 hours
Guarantees that you message will be processed at least once

SQS long polling is a way to retrieve messages from your SQS queues.
While the regular short polling returns immediately, long polling doesn't return a respone until a message arrives in the message queue, or the long poll times out.

## Related
- [[devops-moc]]
- [[questions-power-user-access-allows]]
- [[dns]]
- [[kinesis-101]]
