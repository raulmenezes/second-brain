---
tags:
  - area/devops
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/database
  - topic/networking
---

# DNS

On Port 53 thus Route 53
DNS is used to convert human friendly domain names to Internet Protocol (IP) address
IP used to identify each other on the network

IPv6 created to solve the the address space problem

Last word in domain is top level domain name e.g. .com / .gov
Second word in domain name is the second level domain name .co(second).uk(top)

**Top level domain** 
Controlled by the internet assigned Numbers Authority (IANA) in a root zone database 
- database of all available top level domains.

**Domain Registrar**
Authority that assigns domain names directly under one or more top-level domains.

Domains are registered with InterNIC, a service of ICANN
- Enforces uniqueness of domain names across the Internet.
- Registered in a central database known as the WhoIS database

**Start of Authority Record (SOA)**

Record store information:
- Name of the server that supplied the data for the zone
- Administrator of the zone
- Current version of the data file
- Default number of seconds for the time to live file on resource records.

**Name Server Records**
Used by Top Level Domain servers to **direct traffic** to the Content DNS server which contains the authoritative DNS records.

![[attachments/pasted-graphic-3.png]]

**A record**
Stands for Address
Used by computers to translate the name of the domain to an IP address
E.g. Name to IP address like a phonebook

**Time to Live (TTL)**
TTL length a DNS record is cached on either the Resolving Server or the users own local PC is equal to the value of the "Time to Live" (TTL in second)
Lower the time to live - faster changes to DNS records take to propagate throughout the internet 

**Canonical Name**
Used to resolve one domain name to another

**Alias Records**
Used to map resource record sets in your hosted zone to Elastic Load Balancers, CloudFront distributions, or S3 buckets that are configured as websites
Map one DNS name to another 'target' DNS name

A CANAME can't be used for naked domain names (Zone apex record)
You can't have a CNAME for http://acloud.guru it must be either A record or an Alias

**Route53 Tips**
Elastic Load Balancers (ELBs) do not have pre-defined IPv4 addresses
	- Resolve by using a DNS name

Difference between an Alias Record and a CNAME
Always choose an Alias Record over a CNAME
 
**Common DNS Types**
SOA Records
NS Records
A Records
CNAMES
MX Records
PTR Records - Looking up Name against an IP address

## Related
- [[devops-moc]]
- [[lens]]
- [[vpc-endpoints]]
- [[Ansible]]
