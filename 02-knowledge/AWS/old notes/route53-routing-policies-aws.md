---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# Route53 Routing Policies AWS

Simple Routing
Weighted Routing
Latency-based Routing
Failover Routing
Geolocation Routing
Geoproximity Routing Policy (Traffic Flow Only)
Multivalue Answer Routing

**Simple Routing**
One record with multiple IP addresses
If there are multiple values in a record, Route 53 returns all values to the user in a random order.

![[attachments/pasted-graphic-4.png]]

**Weighted Routing**
Allows to split traffic based on different weights assigned.
E.g. 10% traffic go to US-EAST-1 and 90% to EU-WEST-1

**Health Checks**
Can set health checks on individual record sets
If failed will be removed from Route53 until it passes
Can set SNS notifications to alert of failure

**Latency-based Routing**
Route traffic based on the lowest network latency for your end user

Create a latency resource record set for the EC2 (or ELB) resource in each region that hosts your website
Amazon Route 53 receives  a query for the site, it selects the latency resource record set for the region that gives the user the lowest latency
Route 53 responds with the value associated with that resource recored set

**Failover Routing**
Used to create an active and passive setup.
E.g. Primary site to be in EU-WEST-2 and your secondary DR Site in AP-SOUTHEAST-2
Route53 will monitor the health of your primary site using health check

**Geolocation Routing**
Choose where traffic will be sent based on the geographic location of your users
- Location from which DNS queries originate
E.g. Send all queries from Europe to EC2 instance configured for European customers.
- Local languages and prices displayed in Euros

**Geoproximity Routing Policy (Traffic Flow Only)**
Route Traffic to your resources based on the geographic location of your users and your resources.
Optionally choose to route more traffic or less to a given resource by specifying a value (bias).
Bias expands or shrinks the size of the geographic region from which traffic is routed to a resource
Must use Route 53 Traffic Flow

**Multivalue Answer Routing**
Configure Route 53 to return multiple values such as IP addresses for your web servers in response to DNS queries
Specify multiple values for almost any record, but multivalue answer routing also checks health of each resource
**similar to simple routing but allows to put health checks on each record set**

**Register A Domain Name**

Can buy domains with AWS
Takes up to 3 days to register

## Related
- [[questions-power-user-access-allows]]
- [[encrypted-root-device-volumes-and-snapshots]]
- [[tl-weekly-duties]]
