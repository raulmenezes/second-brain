---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
---

# Check Storage in Postgresql

Log into primary instance with issue

SSH into primary box
Connect to database

s -u [dbname] psql
s -u app-moose psql

Find the database cluster is taking most of the space

Database size queries:
https://phabricator.live.logicalglue.net/w/new_joiner_notes/sql_db_size/useful_sql_queries/

E.g.
Find largest cluster in database

![[attachments/pasted-graphic-13-1.png]]

Note:
New release will have house keeping features 
Models in Trash/Failed/Rejected states will be cleared after a few days

Solutions:

1. Ask users to remove old models in databases
2. Expanding the size of home  directory

![[attachments/pasted-graphic-16.tiff]]

df -h
For expanding the home partition:
Go into the AWS console and click on the EC2 instance and change the size of the home disk
- Note: You can expand but not shrink a disk size on aws

After changing the size on AWS console you need to ssh into the instance and tell it of the change:
 
growpart /dev/xvdb 1

## Related
- [[databases-moc]]
- [[create-new-instance]]
- [[model-cloning-popup-server]]
