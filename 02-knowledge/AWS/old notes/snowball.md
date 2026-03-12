---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/networking
---

# Snowball

Petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of AWS
Addresses common challenges with large scale data transfers:
- High network costs
- Long Transfer times
- Security concerns

50TB or 80TB size
Multiple layers of security
	Tamper-resistant enclosures
	256-bit encryption
	Industry standard Trusted Platform Module (TPM) designed to ensure both security and full chain of custody of data
AWS performs a software erasure of the Snowball appliance

**Snowball Edge** 

Snowball Edge is a 100TB data transfer device with on-board storage and compute capabilities.
Uses:
Move large amounts of data
Temporary storage their for large local datasets
Support Local workloads in remote or offline locations.

E.g. In Planes

Connects to existing applications and infrastructure using standard storage interfaces,
streamlining the data transfer process and minimising setup and integration

Can cluster together to form a local storage tier and process your data on-premises,
helping ensure your applications continue to run even when they are not able to access the cloud.

**Snowmobile**
Exabyte-scale data transfer service - extremely large amounts of data to AWS
100PB per Snowmobile - 45 foot long ruggedised shipping container
Data center migration

## Related
- [[devops-moc]]
- [[storage-gateway]]
- [[questions-power-user-access-allows]]
- [[aws-overall-summary]]
