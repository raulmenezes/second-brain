---
tags:
  - area/databases
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/database
  - topic/networking
  - topic/snippets
  - topic/testing
---

# Create New Instance

https://web.microsoftstream.com/video/d9c9f475-0c74-45d3-83d1-e9e397c1bbf7

Create EC2 instance on AWS
Ensure correct inbound rules are enabled for instance

SSH into instance and enable 

you added it the /etc/hosts file Faking or DNS

id_mouth found in  **~/.ssh**
ssh-add id_mouth

Bootstrap instance:

Ssh and change root ssh key on server

ssh -i "id_mouth" ubuntu@54.74.180.53 

Allow root ssh into instance

sudo su -
sudo nano /root/.ssh/authorized_keys

You should now be able to ssh into root:

ssh -i "id_mouth" root@54.74.180.53 

Add the record to DNS

# ./bootstrap  

Fill in regions.yml file

If using AWS RDS:
ansible-vault edit group_vars/rds

# ./play 

**If  you get a “No package matching 'filebeat' is available" error** 

In the base_system
On line 30 update the cache_valid_time to 1

sagu
sagdup 
sudo apt autoremove

sudo systemctl reboot

sudo systemctl restart lg-app-mixer.service

sudo systemctl restart lg-app-mixer.service

Deploy instance

./deploy app-cara

tail -f ~app-cara/main.log

*Python script*
*Commented out line 12, 15, 22 and 23* 

8702

Redis

Add Redis hostnames to machine region e.g. ec2-eu-west-1

redis_a_u: \[name of redis-host\] 
redis_b_u: \[name of redis-host\] 

Ps -ef | grep [name]

Get password in first startup - main.log file

# cat main.log | grep sysadmin

Regenerate new Certifications 
- .play [name]

Test cluster to deploy and decommission 

Edit 
ansible-vault edit group_vars/rds

Ssh to instance

psql -h \[DATABASE-ENDPOINT\] -d postgres -U postgres

Create the users and roles

CREATE ROLE “\[APP-NAME\]” WITH LOGIN PASSWORD ‘password’

GRANT “\[APP-NAME\]” to postgres;

**Check you are able to connect with new created user**
psql -h \[DATABASE-ENDPOINT\] -d postgres -U postgres --password --command=“CREATE DATABASE “\” \[NAME\]\”” WITH OWNER ‘\[NAME\]’”

CREATE ROLE “APPNAME” WITH LOGIN PASSWORD 'APPNAME';
GRANT "APPNAME" TO postgres;
CREATE DATABASE "APPNAME" OWNER “APPNAME”;
GRANT ALL PRIVILEGES ON DATABASE "APPNAME" TO "APPNAME";

eu-c-1-test-1-cluster.cluster-csjawf2hgebu.eu-central-1.rds.amazonaws.com
app-ubs-test

## Related
- [[databases-moc]]
- [[check-storage-in-postgresql]]
- [[model-cloning-popup-server]]
- [[nginx]]
