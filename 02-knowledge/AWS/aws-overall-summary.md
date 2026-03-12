---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
  - topic/snippets
---

# Overall Summary

**S3 & IAM Summary**

Identity Access Management :
- Users
- Groups 
- Roles - Assigned to AWS Resources
- Policies - JSON format

IAM is **universal** (not specific regions) 

**Root account**
Account that first setup your AWS account
Has Admin access

New Users have:
- **No permissions** when first created
- Assigned Access Key ID & Secret Access Keys when first created
	- Used for APIs and Command Line
	- Only able to view once

Can create and customise your own password rotation policies

**S3 (Simple Storage Service)**
- Object-based storage
- Files can be from 0 Bytes to 5 TB
- Unlimited storage 
- Files are stored in buckets
- Universal namespace - must be unique globally
- All are Private by default

Setup Account Control for you bucket using: 
**Bucket Policies** - Bucket wide
**Access Control Lists** - Files or folders

Access logs which log all request made to the S3 bucket

Read after Write consistency For New Objects
Eventual Consistency for overwrite PUTS and DELETES

**Cost of S3**
**Storage Request and Data Retrievals**
**Data Transfer**
**Management & Replication**

**S3 Classes of storage**

**S3** **Standard**
99.99% availability & durability
Stored redundantly across multiple devices in multiple facilities 
Sustains the loss of 2 facilities concurrently

**S3 - IA - Infrequently Accessed**
Accessed less frequently but requires rapid access when needed
Lower fee than S3 but changed a retrieval fee

**S3 One Zone - IA**
Lower-cost option
No multiple Availability Zone data resilience

**S3 - Intelligent Tiering**
Automatically moving data to the most cost-effective access tier
Without performance impact or operational overhead

**S3 Glacier**
Low-cost storage class for data archiving
Retrieval times configurable form minutes to hours

**S3 Glacier Deep Archive**
Lowest cost storage class
Retrieval time of 12 hours is acceptable

**Encryption in Transit** by SSL/TLS

**Encryption At Rest** (Server Side) is achieved by :
S3 Managed Keys - SSE-S3 (Server Side Encryption)
AWS Key Management Service, Managed Keys - SSE-KMS
Server Side Encryption With Customer Provided Keys - SSE-C

**Cross Region Replication**
Versioning must be enabled on both the source and destination buckets
Regions must be unique
Files in an existing bucket are not replicated automatically
All future updated files will be replicated automatically
Delete markers are not replicated 
Deleting individual version or delete markers will not be replicated.

**Lifecycle Policies** 
Automates moving objects between the different storage tiers. 
Can be used in conjunction with versioning
Can be applied to current versions and previous versions.

**S3 Transfer Acceleration** - Improve Speed and Performance

**CloudFront** 

**Edge Location**
Location where content will be cached
(Separate to an AWS Region/AZ)
Not just READ only (can write to them too put an object) - Transfer Acceleration
Objects are cached for the life of the TTL (Time To Live)
Can clear cached objects but will be charged

**Origin**
Origin of all the files that the CDN will distribute e.g. S3 Bucket, EC2 Instance

**Distribution** 
Name given to the CDN which consists of a collection of Edge Locations

**Web Distribution**
Typically used for Websites

**RTMP**
Used for Media Streaming

**Snowball**
Disk used to move large data in and out of S3

**Storage Gateway** 
Physical or virtual appliance that can be used to cache S3 locally at a customer's site

**File Gateway (NFS) - Network File Systems**
For flat files stored directly on S3

**Volume Gateway** 

**Stored Volumes**
Entire Dataset is stored on site and is asynchronously backed up to S3

**Cached Volumes**
Entire Dataset is stored on S3 and the most frequently accessed data is cached on site

**Gateway Virtual Tape Library**
Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam etc

S3 FAQ -  https://aws.amazon.com/s3/faqs/

Power User - Access to all AWS services except the management of groups and users within IAM
SAML (Security Assertion Markup Language 2.0) - you can give your federated users single sign-on (SSO) access to the AWS Management Console.

**Lock Polices**

S3 Object Lock store objects using a write once, read many (WORM) model.
- Prevent object from changes and deletion
- Can be on Individual objects or applied across the bucket
- Comes in two modes

Governance mode 
- Users can't overwrite or delete an object version or alter its lock settings

Compliance Mode
- Protected object version can't be overwritten or deleted by an user (even root user) during the retention period
Legal Holds - Prevents object version from being overwritten or deleted.  Glacier Vault lock
Easily deploy and enforce compliance controls for individual S3 Glacier vaults with a Vault Lock policy
- Once locked the policy an no longer be changed

**S3 Performance**
S3 Prefix
The middle part between the bucket name and the object e.g. mybucketname/folder1/subfolder1/myfile.jpg -> /folder1/subfolder1

S3 has low latency 100-200 ms

multipart upload - improve upload
s3 byte range fetch - improve download

S3 Select 

retrieve only a subset of data from an object using SQL

glacier select 
highly regulated industries
Write data directly to amazon glacier to satisfy compliance needs

AWS organizations
 management account

Enable/Disable AWS services using SCP Service Control Polices either on OU or on individual accounts.

**——————————————————————————————————————————**

**EC2 Summary**

**EC2 - Elastic Compute Cloud**
Resizable compute capacity in the cloud

**Four different Pricing Models**
**On Demand**
Pay a fixed rate by the hour/ by the second with no commitment

**Reserved**
Capacity reservation 
- Significant discount on the hourly charge for an instance
- Contract Terms 1 / 3 Year Terms.
- Can’t move to another region

**Spot**
Bid whatever Price you want for instance capacity
Provides even greater saving if your application has flexible start and end times
Can be terminated by Amazon but will not be charged for hour usage

**Dedicated Hosts**
Physical EC2 server dedicated for your use.
Can help reduce costs by allowing you to use your existing server-bound software licenses

**EBS - Elastic Block Store**
Virtual hard disk in the cloud
Termination Protection is turned off by default
Block-based storage
On an EBS-backed instance
- the default action is for the **root EBS volume to be deleted** when the instance is terminated
- Any additional volumes are saved

EBS Root Volume of your Default AMI's cannot be encrypted.
- Can use a third party tool to encrypt the root volume. 
- Can be done when creating AMI's in the AWS console or using the API
- Additional volumes can be encrypted

**Security Group**

All Inbound traffic is blocked by default
All Outbound traffic is allowed
Changes to Security Groups take effect immediately
Can have any number of EC2 instances within a security group
Can have multiple security groups attached to EC2 Instances
Stateful - Opening a port opens for both inbound and outbound
Cannot block specific IP addresses, need to use Network Access Control Lists
Can specify allow rules but not deny rules

**EBS Types** 

**General Purpose SSD**
Balances price and performance for a wide variety of transactional workloads
Most Work Loads
gp2
1GB - 16TB
16,000

**Provisioned IOPS SSD**
Designed for mission-critical applications (Highest performance)
Databases
io1
4GB - 16TB
64,000

**Throughput Optimised HDD**
Designed for frequently accessed, throughput intensive workloads
Big Data & Data Warehouse
st1
500GB - 16TB
500

**Cold HDD**
Designed for less frequently accessed workloads (Lowest cost)
File Servers
sc1
500GB - 16TB
250

**EBS Magnetic**
Previous generation HDD
Workloads where data is infrequently accessed
standard
1 GB - 1TB 
40-200

**EBS Snapshot**
Volumes exist on EBS where as Snapshots exist on S3
Snapshots are incremental - Only blocks that have changed since your last snapshot are moved to S3.
Can create AMI's from both Volumes and Snapshots
Volumes always in same availability zone as the EC2 instance

**Migrating EBS**
Move EC2 volume from on AZ to another
- Take snapshot 
- Create an AMI from the snapshot 
- Use the AMI to launch the EC2 instance in a new AZ

Move the EC2 volume from one region to another 
- Copy the AMI from one region to the other (Extra Step)

**EBS Encryption**
Snapshots of encrypted volumes are encrypted automatically 
Volumes restored from encrypted snapshots are encrypted automatically
Share snapshots but only if they are unencrypted.
Snapshots can be shared with other AWS accounts or made public

**EBS vs Instance store**
Instance Store Volumes are sometimes called Ephemeral Storage
Instance Store Volumes cannot be stopped. If the underlying host fails you will lose your data
EBS can be stopped. You will not lose the data on this instance if it stopped
Can reboot both you will not lose your data
By default both ROOT volumes will be deleted on termination.
However, with EBS volumes you can tell AWS to keep the root device volume

**CloudWatch**
Used for monitoring performance
With EC2 will monitor events every 5 minutes by default
Can have 1 minute intervals by turning on detailed monitoring
Can create CloudWatch alarms which trigger notifications
CloudWatch is about performance. CloudTrail is all about auditing (Monitors API calls in the AWS platform) E.g. who setup an EC2 instance

**What can I do with CloudWatch**
Dashboards - See what is happening with your AWS environment
Alarms allows you to set Alarms that notify you when particular thresholds are hit
Events - helps to respond to state changes in your AWS resources
Logs - CloudWatch Logs help you to aggregate, monitor and store logs

**CLI (Command line)**
Need to setup access on IAM  (Access Key ID & Secret Access Key)

**Roles**
More secure than storing your access key and secrete access key on individual EC2 instances
Much easier to manage
Assigned to an EC2 instance after it is created using both the console & command line
Universal - can use them in any region

**Bootstrap scripts**
Bootstrap scripts run when an EC2 instance first boots
Can be for Automating software installs and updates

**Instance Meta data & User Data**
Used to get information about an instance
curl http://169.254.169.254/latest/meta-data/ (private IP address and public IP address)
curl http://169.254.169.254/latest/user-data

**EFS (Elastic File System)**
Supports the Network File System v4 (NFSv4) protocol
Only pay for storage you use
Can scale up to the petabytes
Can support thousands of concurrent NFS connections
Data is stored access multiple AZ's within a region
Read after Write consistency

**EC2 Placement Groups**

Clustered Placement Group
- Low Network Latency / High Network Throughput
- Same AZ, close as possible

Spread Placement Group
- Individual Critical EC2 instances
- Different AZ Zone and hardware
- Only have maximum of 7 instances per AZ

Partitioned
- Multiple EC2 instances HDFS, HBase and Cassandra
- Can Span multiple AZ 

Name specified for a placement group must be unique within your AWS account
Only certain type of instances can be launched in a placement group 
- (Compute, Optimized, GPU, Memory Optimized, Storage Optimized)
Recommends **homogenous** instances within clustered placement groups
Can’t merge placement groups
Can't move existing instance into a placement group. Must:
- Create an AMI from your existing instance
- Launch a new instance from the AMI into a placement group

Can't delete a snapshot of an EBS Volume that is used as the root device of a registered AMI
aws ec2 create-snapshot
Can change the permission to a role even if it is already assigned to an existing EC2 instance
Can't attach an EBS volume to more than one EC2 instance at the same time
18 out of 23
**——————————————————————————————————————————**

**Databases Summary**

**RDS (OLTP) Online Transaction processing**
- SQL
- MySQL
- PostgreSQL
- Oracle
- Aurora
- MariaDB

**DynamoDB (NoSQL)**
**Red Shift OLAP (Online Analytical Processing)**

**ElasticCache** 
- Memcached 
- Redis

**Relational Databases**   
Runs on Virtual Machines 
Cannot log into these operating systems
Patching of the RDS OS and DB is Amazon's responsibility
RDS is not serverless
Aurora Serverless is Serverless

**Two types of Backups for RDS** 
Automated Backups
Database Snapshots

**Read Replica** 
Can be Multi-AZ
Used to increase performance
Must have backups turned on
Can be in different regions 
Can be Aurora or MySQL
Can be promoted to master but will break the replication with the Read Replica

**Multi-AZ**
Used For DR (Data recovery)
Can force a failover from one AZ to another by rebooting the RDS instance

Encryption at rest is supported which is done using the Key Management Service (KSM) service
Once the RDS instance is encrypted
- the data stored at rest in the underlying storage is encrypted 
- as are its automated backups, read replicas and snapshots

**DynamoDB**
Stored on SSD
Spread Across 3 geographically distinct data centres
Eventual Consistent Reads (Default)
Strongly Consistent Reads
Perform Operations using a user-defined primary key
Primary key can either be single-attribute or a composite

**RedShift**
Used for business intelligence
Only available in 1 AZ

**RedShift Backup**
Enabled by default with a 1 day retention period
Maximum retention period is 35 days
Redshift always attempts to maintain at least three copies of your data 
- (the original and replica on the compute nodes and a backup in Amazon S3)
Can also asynchronously replicate your snapshots to S3 in another region for disaster recovery

**Aurora**
2 copies of your data is contained in each AZ with a minimum of 3 AZ. 
- 6 Copies of you data
Can share Aurora Snapshots with other AWS accounts.
2 types of replicas available. Aurora Replicas and MySQL replicas. 
- Automated failover is only available with Aurora Replicas.
Aurora has automated backups turned on by default. 
- Can also take Snapshots with Aurora. 
- Can share these snapshots with other AWS accounts.

**Elasticache**
Used to increase database and web application performance
Redis is Multi-AZ
Can do backups and restores of Redis
Need to scale horizontally use Memcached

RDS instance - can select the AZ that it is deployed
RDS Reserved instances are available for multi-az deployments
Run a EBS Database on an EC2 is the recommended storage option
MySQL port number 3306
Error node in the response from the Amazon RDS API - check for RDS error
provisioned IOPS over standard storage - For Online Transaction processing
with a DB security group the RDS instance port number is automatically applied to the RDS DB Security Group.

https://aws.amazon.com/rds/faqs/

20 out of 24

**——————————————————————————————————————————**

**DNS Summary (Route 53)**

**Route 53** 
ELBs do not have pre-defined IPv4 addresses; you resolve to them using a DNS name
Understand the different between an 
- Alias Record (like People’s name with Telephone numbers and a CNAME (Batman see Bruce Wayne)
- Choose an Alias Record over a CNAME

**Common DNS Types**
SOA Records
NS Records
A Record
CNAMES
MX Records
PTR Records

**Routing Policies with Route 53**

**Simple Routing**
Only have one record with multiple IP addresses. 
If multiple values in a record, Route 53 returns all values to the user in a random order

**Weighted Routing**
Route53 will send 20% of the traffic (EAST-1) and 80% of the traffic (WEST-1)

**Latency-based Routing**
Based on the user’s location. 
Route 53 will send the traffic to the lowest latency

**Failover Routing**
Active and Passive environment. 
If health check fails sends user to the passive environment.

**Geolocation Routing**
Send the European customers to EU-West and US customers to US-East

**Geoproximity Routing (Traffic Flow Only)**
Route traffic to your resources based on the geographic location of your users and your resources
Optionally choose to route more traffic or less to a given resource by a specifying a value known as a bias.
A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource

**Multivalue Answer Routing**
Same as simple based routing except with health checks

**Health Checks**
Can set health checks on individual record sets
If a record set fails a health check it will be removed from Route53 until it passes the health check
Can set SNS notifications to alert you if a health check is failed

Route 53 limit to 50 domain names but can be increased by contacting AWS support
7 out of 7

**——————————————————————————————————————————**
VPC from memory
**VPC Summary**

**VPC Overview**
As a Logical datacenter in AWS
Consist of IGWs (Or Virtual Private Gateways), 
Route Tables, Network Access Control Lists, Subnets, and Security Groups
1 Subnet = 1 Availability Zone
Security Groups are Stateful - Network Access List are Stateless
No Transitive Peering

**Building VPC**
When creating a VPC a default :
- Route Table
- Network Access Control List (NACL)
- Security Group

Won’t create any subnets or internet gateways

Amazon always reserves 5 IP addresses within your subnets
Only have 1 Internet Gateway per VPC
Security Groups can’t span VPCs

**NAT Instances (Network Address Translation)**
After creating NAT instance, Disable Source/ Destination check on the Instance
Must be in a public subnet
Must be a route out of the private subnet to the NAT instance in order for this to work
Amount of traffic the NAT instance can support depends on the instance size.
High Availability using Autoscaling Groups, multiple subnets in different AZs and a script to automate failover
Behind a Security Group

**NAT Gateway**
Not behind Security Group
Instance has a route in its Route Table to the NAT Gateway
Redundant inside the Availability Zone
Starts at 5Gbps - 45 Gbps
No need to patch or associate with Security Group
Automatically assigned a public IP address
Remember to update your route tables

**Network ACL’s**
VPC automatically comes a default network ACL which allows all outbound and inbound traffic
Custom Network ACLs by default denies all inbound and outbound traffic until you add rules
Each subnet in your VPC must be associated with a network ACL
- If one is not specified a **default** network ACL is used
Can block IP addresses using network ACLs
Can associate a network ACL with multiple subnets (but not the other way around)
Separate Inbound and Outbound rule and each rule can allow or deny traffic

**ELBs**
Need a minimum of two public subnets to deploy an internet facing load balancer

**VCL Flow Logs**
Cannot enable flow logs for VPCs that are peered with your VPC unless the peer VPC is in your account
Cannot tag a flow log
After a flow log is created, we cannot change its configuration e.g. associate a different IAM role with the flow log

**IP Traffic not monitored:** 
Traffic generated by instances when they contact the Amazon DNS server
- (If you use your own DNS server then all traffic to that DNS server is logged)
Traffic generated by a windows instance for Amazon Windows license activation
Traffic to and from 169.254.169.254 for instance metadata
Traffic to the reserved IP address for the default VPC router

**Bastions vs NAT Gateways/Instance**
A NAT Gateway or NAT Instance is used to provide internet traffic to EC2 instances in private subnets
Bastion is used to securely administer EC2 instances (Using SSH or RDP)
Bastion are called Jump Boxes
Cannot use a NAT Gateway as a Bastion host

**Direct Connect** 
Directly connects your data center to AWS
Useful for high throughput workloads (e.g. lots of network traffic
 If you need a stable and reliable secure connection.

**VPC Endpoint** 
Enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without requiring
	- an Internet gateway, NAT device, VPC connection or AWS Direct Connect connection
Instances in your VPC do not require public IP addresses to communicate with resource in the service.
Traffic between your VPC and the other service does not leave the Amazon network

Endpoints are virtual devices.
Horizontally scaled, redundant, and highly available VPC components
Allow communication between instances in your VPC and services without imposing availability risks or bandwidth constraints on your network traffic

**Two types of VPC Endpoints** 

- Interface Endpoint
- Gateway Endpoint
	- Amazon S3 
	- DynamoDB

Watch Summary Video

By default, any user-created VPC subnet WILL NOT automatically assign public IPv4 addresses to instances 
- the only subnet that does this is the “default” VPC subnets automatically created by AWS in your account.
Create an Elastic IP address and associate it with your instance to make it reachable from the outside world

In a custom VPC with new subnets in each AZ, there is a route that supports communication across all subnets/AZs. Plus a default SG with an allow rule 'All traffic, all protocols, all ports, from anything using this default SG'.

15 out of 20

**——————————————————————————————————————————**

**HA Architecture Summary**

**Types of Load Balancers**
Application Load Balancer - distribute traffic based on rules for target group, condition, and priority.
Network Load Balancer - designed for high performance traffic that is not conventional web traffic.
Classic Loader Balancer

504 Error means the gateway has timed out
- Application not responding within the idle timeout period
- Webserver or Database Server

IPv4 address of end user on the X-Forward-For header

Instances monitored by ELB are reported as **InService** or **OutofService**
- Health Checks check the instance health
- Load Balances have their own DNS name. Never given an IP address

Read the ELB FAQ for Classic Load Balancers - https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/introduction.html

**Advanced Load Balancing Theory** 

Sticky Sessions enable your users to stick to the same EC2 instance
- Useful if you are storing information locally to that instance
Cross Zone Load Balancing enables you to load balance across multiple availability zones

Path patterns allow you to direct traffic to different EC2 instances based on the URL contained in the request

**CloudFormation** 
Scripting your cloud environment
Quick Start - CloudFormation templates built by AWS Solution Architects allowing you to create complex environments very quickly

**Elastic Beanstalk**
Quickly deploy and manage applications in the AWS Cloud without worrying about the infrastructure that runs those applications
Simply upload application and everything is handled automatically

not built an autoscaling group to invoke the launch configuration you specified.
Durability refers to the on-going existence of the object or resource.
RDS database into multiple availability zones - can't use the secondary database as an independent read node

10 out of 15

**——————————————————————————————————————————**

**Application Summary**

**SQS**
a way to de-couple your infrastructure
Pull-based (not pushed)
Messages are 256KB in size
Kept in the queue from 1 minute to 14 days
- The default retention period is 4 days

**Standard SQS**
- Not guaranteed and messages can be delivered more than once
**FIFO SQS**
- Order is strictly maintained and messages are delivered only once

**Visibility Time Out**
- Amount of time that the message is invisible in the SQS queue after a reader picks up that message. 
- Provided the job is processed before the visibility time out expires, the message will then be deleted from the queue.
- If the job is not processed within that time, the message will become visible again and another reader will process it
- This could result in the same message being delivered twice.
- Visibility timeout maximum is 12 hours

SQS guarantees that you message will be processed at least once

Long polling is a way to retrieve messages from Amazon SQS queues. 
While the regular short polling returns immediately (even if the message queue being polled is empty),
Long polling doesn’t return a response until a message arrives in the message queue, or the long poll times out.

**SWF vs SQS**

SQS has a retention period of up to 14 days
- Message-oriented API
- Duplicated messages can happen
- Need to implement you own application-levels tracking 
SWF (simple) workflow executions can last up to 1 year
- Task-oriented API
- Task is assigned only once and is never duplicated
- Keeps track of all the tasks and events in an application.

**SWF Actors**
**Workflow Starters**
- An application that can initiate a workflow
	- E.g. website following the placement of an order or a mobile app searching for bus times.

**Deciders**
- Control the flow of activity tasks in a workflow execution
- If something has finished in a workflow, a decider decides what to do next

**Activity Workers**
- Carry out the activity tasks

**SNS (Simple Notification Service) Benefits**
Instantaneous, push-based delivery
Simple APIs and easy integration with applications
Flexible message delivery over multiple transport protocols
Inexpensive, pay-as-you-go model with no up-front costs
Web-based AWS Management Console offers the simplicity of a point-and-click interface

**SNS vs SQS**
Both Messaging Services in AWS
SNS - Push
SQS - Polls (Pulls)

**Elastic Transcoder** 
Media transcoder in the cloud 
Coverts media files from their original source format in to different formats that will play on smartphones, tablets and PCs

**API Gateway**
Gateway into the AWS resources
Caching capabilities to increase performance
Low cost and scales automatically
Throttle API Gateway to prevent attacks.
Log results on CloudWatch
Enable CORS on API Gateway - for multiple domains
CORS enforced by client 

**Kinesis**

**Kinesis Streams**
- Consist of shards
- Capacity depends on number of shards
- Stored for 24 hours

**Kinesis Firehose**
- No data persistence
- Used as soon as data entered e.g. ElasticSearch / Redshift

**Kinesis Analytics**
- Analyse data on the fly until its stored on S3, ElasticSearch

**Cognito**
Federation allows users to authenticate with a Web Identity Provider (Google & Facebook)
Identity Broker which handles interaction between your applications and the Web ID provider  (don’t need to write code)

User authenticates first with the Web ID Provider
- receives an authentication token
- exchanged for temporary AWS credentials allowing them to assume an IAM role

**User pool** is user based
- Handles things like user registration authentication and account recovery

**Identity pools** authorise access to your AWS resources

When you create a topic on SNS an Amazon Resource Name is created
9 out of 11

**——————————————————————————————————————————**

**Serverless Summary**

**Traditional vs Serverless Architecture**

**Traditional**
Elastic Load balancer -> EC2 -> Database (RDS)

**Serverless**
API Gateway -> Lambda -> DynamoDB

**Lambda**
Scales out (not up) automatically
Functions are independent, 1 event = 1 function
Functions can trigger other lambda functions
- 1 event can = x functions if functions trigger other functions

AWS X-ray allows you to debug what is happening (For complex architecture)

Learn what cannot trigger lambda

5 out of 5

## Related
- [[s3-simple-storage-service]]
- [[storage-gateway]]
- [[s3-version-control]]
