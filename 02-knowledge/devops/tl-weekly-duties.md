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

# Tl Weekly Duties

Support channel for link:
https://phabricator.live.logicalglue.net/w/support/duties/

**Things that need to be done:**

https://grafana.live.logicalglue.net/dashboard/db/one
Go to Grafana and look at “Reboot Required”, “Pending Updates”, “Running Jobs” and “Queued Jobs”panels

**Run ./play on all Five groups:**
dev
secondary
primary
secondary db
Primary db
Load

./play dev

./play

Execute just one task
./play dev --start-at-task="download lg artifact"

./play dev --tags new-devs

Execute tasks associated with certain tag
./play dev --tags=exporter

Optional:
./list-hosts.sh dev
csshx $(./list-hosts.sh dev)

See how Busy Servers are:
top
ps -ef | grep -i jobid

ps -ef | grep -i jobid | grep -i app-moose 

sudo kill -9  

Run following commands:

sagu
sagdup 
sudo apt autoremove
 ps -ef | grep -i jobid
 
sudo systemctl reboot
uptime

Pingdom:
Tag filter by clover
Pause them

Load balancer

Set weight to 0 

ssh into lb

Check that no more logs are coming from platform
sudo tail -f /var/log/nginx/access.log

app cwb

Run following commands:

sagu
sagdup
sudo apt autoremove

s systemctl reboot

Check the logs for the new instance

tail -f -app-cara/main.log
view ~app-name/main.log

![[attachments/pasted-graphic-4-7.png]]

Ssh to database
Check user is in database

s -u [user] psql
s -u app-multiclass psql

Check if new instance is on load balancer

view /etc/nginx/sites-enabled/default

sudo nano /etc/nginx/sites-enabled/default

sudo nginx -t

sudo systemctl reload nginx 

Check Disk Space

sudo ncdu /
ls -lh 

**Mount Storage:**
df -h
lsblk

**Increase Storage size of EBS**

![[attachments/screenshot-2021-12-14-at-16-44-19.png]]

sudo growpart /dev/xvdb 1
sudo resize2fs /dev/xvdb

Don’t need to do anything for APIs

**Clover** - 2 prod servers and 1 dev server

Tag clover

Select all pause all notifications

Do updates

Select all unpause

sudo systemctl --failed
sudo systemctl status unit-name
sudo journalctl -u unit-name
Disable:
sudo systemctl reset-failed

sudo systemctl stop application.service

sudo systemctl restart lg-app-mixer.service
 
urn:lgadmin:datascience:[meta.app.logicalglue.net](http://meta.app.logicalglue.net)

Fix nginx connection issue 
Set weight to 0 

ssh into lb

Keycloak
sudo systemctl status keycloak.service 
sudo su - keycloak
tail -f keycloak-23.0.1/data/log/keycloak.log

sudo systemctl status firewalld

sudo firewall-cmd --list-all

sudo firewall-cmd --zone=public --permanent --add-port 7800/tcp
sudo firewall-cmd --reload

sudo firewall-cmd --zone=public --permanent --remove-port 7600/tcp
sudo firewall-cmd --reload

sudo firewall-cmd --new-zone=special --permanent
sudo firewall-cmd --reload
sudo firewall-cmd --zone=special --add-source=192.0.2.4/32
sudo firewall-cmd --zone=special --add-port=4567/tcp

nc -l -p 7800
nc -vz 10.249.0.12 7800

## Related
- [[devops-moc]]
- [[helm-kubernetes]]
- [[deploy-new-instance]]
- [[route53-routing-policies-aws]]
