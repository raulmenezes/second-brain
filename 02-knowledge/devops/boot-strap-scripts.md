---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
  - topic/monitoring
  - topic/networking
---

# Boot Strap Scripts

EC2 Instance -> Configure Instance 

Give AdminAcess in **IAM Role**

**Advanced Details - > Bootscript script**

#!/bin/bash
yum update -y
yum install httpd -y
Service httpd start
chkconfig httpd on
cd /var/www/html
echo “ Hello Cloud Gurus Welcome to my Webpage” > index.html
aws s3 mb s3://bucketName
aws s3 cp index.html s3://bucketName

**EC2 Instance Meta Data**

Get information about the instance

Print out bootstrap Script on EC2
curl http://169.254.169.254/latest/user-data

Meta data options on EC2
curl http://169.254.169.254/latest/meta-data/

Save IP to Text file
curl http://169.254.169.254/latest/meta-data/public-ipv4 > myip.txt

## Related
- [[devops-moc]]
- [[storage-class]]
- [[elk-stack-elasticstack-logs]]
- [[kubernetes-data-science-repo]]
