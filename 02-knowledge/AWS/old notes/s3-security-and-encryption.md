---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/snippets
---

# S3 Security & Encryption

Buckets are private by default
	Setup Access control by:
		Bucket Policies
		Access Control Lists

**Encryption In Transit**
	SSL/TLS 

**Encryption At Rest (Server Side)**
	S3 Managed Keys - SSE-S3
	AWS Key Management Service, Managed Keys - SSE-KMS
	Server Side Encryption With Customer Provided Keys - SSE-C

**Client Side Encryption**
	Encryption Object before passing it to S3

## Related
- [[devops-moc]]
- [[aws-command-line]]
- [[aws-cloud-practitioner]]
- [[launch-config-and-auto-scaling-groups]]
