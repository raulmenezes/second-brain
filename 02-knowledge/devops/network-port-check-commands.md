---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/kubernetes
  - topic/monitoring
  - topic/networking
  - topic/snippets
---

# Netstat  pant  grep 53

sudo lsof -i :53

# Alerts Issues

1)

Three of the LBs - adoge, acolt, lb-ca-a and lb-ca-b (Ubuntu 18.04.5 LTS): 
Port 53 is being used by systemd-resolve which is affecting **dnsmasq.service**

systemd-r 775 systemd-resolve   12u  IPv4  18669      0t0  UDP localhost:domain 
systemd-r 775 systemd-resolve   13u  IPv4  18670      0t0  TCP localhost:domain (LISTEN)

Ubuntu: How To Free Up Port 53, Used By systemd-resolved
https://www.linuxuprising.com/2020/07/ubuntu-how-to-free-up-port-53-used-by.html

Solution: Need more time to investigate the issue

2)

scan 

**smartd.service** which looks to be having problems looking for drives

Problem creating device name scan list
In the system's table of devices NO devices found to scan

Changes to /etc/smartd.conf ?

**Solution**:
sudo systemctl reset-failed

3)

tickets and phabricator 

**cloud-config.service**
(Failed to Apply the settings specified in cloud-config)

When running the python script it is unable to find the **run_dir** attribute

AttributeError: 'Paths' object has no attribute 'run_dir'

**Solution -** sudo systemctl reset-failed
Needs more time to look into issue

4) 

**yoga**

Server Certificate is removed / missing.

Could not load server certificate file 
"/var/lib/postgresql/9.5/main/lg-server.crt": No such file or directory

**Solution:**
We do not use Postgres on this server anymore.
sudo systemctl disable postgresql@9.5-main.service
sudo systemctl reset-failed

5)

**ruly**

**openipmi.service  -** LSB: OpenIPMI Driver init script

***Failed to start LSB: OpenIPMI Driver init script.***

**ureadahead.service** - Read required files in advance

Error while tracing: No such device
Stopped Read required files in advance.

**smartd.service** 

**Solution -** sudo systemctl reset-failed

6)

scan
ElasticSearch taking up 275 GB

/home/service-elk/data/elk-index/nodes/0/indices

Elasticsearch indices taking up a lot of space. 

Solution:
As we need the indices we will be migrating the data to AWS. For now sudo systemctl reset-failed

7) 
Useful Commands : df -h

**Paal** running out of space on root
Postgres 
 /home/pgdata/9.5/main/base  Solution - root disk space was running out. 
Moved large Postgresql logs (/var/log/postgresql) to home directory as it on a different disk space

9)

kops-p.infra (k8s cluster managment)

Unable to ssh into instance  Solution:  Server is not meant to be up for the whole time. Silenced the alerts until we can come up with a better way to monitor

## Related
- [[devops-moc]]
- [[basic-commands]]
- [[kops-commands]]
- [[kubernetes-data-science-repo]]
