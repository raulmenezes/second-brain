---
tags:
  - area/databases
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/database
  - topic/project
  - topic/snippets
  - topic/testing
---

# Clone Model

Copy script to server
scp clone_model server:

Optional
Make file executable 
chmod +x 

Look into the environment config file for the DBHost

paal.infra.logicalglue.net

ssh into server and modify clone_model 

DB_HOST = remote host
App Name Model 
Project 
Org

**From:**
Models - 1355
Project - 92

**TO:**
Model - 142
Project - 168

1333

Old - YeEeVWPefIYAcIbezAxi

New - BPFAzIAsVidXVCiramFu

clone_model_3999

Export Password
# export PGPASSWORD=‘’
ung6mooM0faiQu3ohp0eePieg

ansible-vault edit group_vars/rds

Check able to connect to remote database
psql -d app-moose -h  -U app-moose 

psql -d app-moose -h rds-ew2-d-1-cluster.cluster-c3jq2c4k37lt.eu-west-2.rds.amazonaws.com -U app-moose
m3XtbJKRx3oudoh4

psql -d app-metadata -h eu-metadata-test-db-instance-1.ch1kbbtig0or.eu-west-2.rds.amazonaws.com -U app-metadata

psql -d app-mixer -h eu-w-2-db-uat-2-cluster.cluster-c3jq2c4k37lt.eu-west-2.rds.amazonaws.com - U app-mixer 

Connect to database of place where the project and model will go to check numbers:
sudo -u  psql

Find latest Model id
# select max(model_id) from masterdb.model;

Find latest Project id
select max(project_id) from masterdb.project;

Run clone model script
./clone_model.sh

Optional
If errors occur delete folder before running the script again 
ls -lh

rm -rf  

SSH into database we are moving the project&model:

# ssh -A 

# rsync -az —info=progress2 : 
# rsync -az —info=progress2 **cwb-ui-a**.infra.logicalglue.net:/tmp/**clone_model_641** .
rsync -az --info=progress2 cwb-ui-a.infra.logicalglue.net:/tmp/clone_model_641 .

/tmp/clone_model_3423

scp -r **cwb-ui-a**.infra.logicalglue.net:/tmp/**clone_model_497** /Users/raulmenezes
scp -r clone_model_497 **paal**.infra.logicalglue.net:

/tmp/clone_model_641

scp -r **cwb-ui-a**.infra.logicalglue.net:/tmp/**clone_model_497** /Users/raulmenezes

Move folder to tmp and decompress files
cp -r clone_model_**641**/ /tmp/

gzip -d *.gz
 

Need to check userId to make sure they are aligned

Find a value userid on database the model is moving to.
sudo -u  psql

select * from masterdb.users where username like ‘%hani%’; 
select * from masterdb.users where username like ‘%hh% 

amono - Hani 180
paal - Hani 186

Meta - 6

Go to feature_sets; part and look for the updated_by number edit the userid
nano/vim NN_db_1010_clean.sql

Last check that the model number and project number haven’t changed before running the manual steps

Run the first manual step and check the database:
sudo -u  psql
select * from masterdb.project where project_id = 2182;

sudo -u app-moose psql
app-moose

7 on 8 command we will need to get the model_id from previous command
Run the next few commands and stop at the  command 
Login and check project and model are on the new location. Test Inference and clean history

UPDATE masterdb.model SET is_model_ready=true WHERE model_uuid='389fcfa4-c8eb-4c25-82b7-0272faa54ff6';
UPDATE masterdb.model SET testing_stats_id='326b059e-3619-4611-aa3a-defe2a37bf48' WHERE model_uuid='389fcfa4-c8eb-4c25-82b7-0272faa54ff6';

SELECT model_id, model_uuid, is_model_ready, training_stats_id, testing_stats_id, whole_stats_id FROM masterdb.model where model_id = 3551;
SELECT statistics_id, gini, ks, rmse, mae, mape, instances, normalised_rmse, normalised_mae FROM model_6e595729_2c79_4b65_9e12_4f8ec91d9ea7.statistics;

95

UPDATE masterdb.model SET testing_stats_id=‘61c5f5ad-ad85-45eb-9bde-900e57f23123’ WHERE model_id='2';

61c5f5ad-ad85-45eb-9bde-900e57f23123

 be210aff-30ac-4d5e-9181-4001812aa6de |  0.46311107971979 |    | 231535.980129351 | 123256.391922421 | 6207.33915526946 |     40000 |  0.115882825889233 | 0.0616893279260585
 3f106a68-1c80-436a-bcd3-fa03bb5bac8d | 0.462120373064241 |    | 234432.836661974 | 123962.033705717 | 8337.56111927247 |     27989 |  0.117336919827542 | 0.0620447349342937
 61c5f5ad-ad85-45eb-9bde-900e57f23123 | 0.462560691771596 |    | 228381.372835552 | 122132.631606601 | 500.726798760073 |      6013 |  0.114364210662793 | 0.0611591122184742

model_8e5e1acd_f2c2_4033_b420_ae9154fe238

Use tux

## Related
- [[databases-moc]]
- [[model-cloning-popup-server]]
- [[model-cloning-popup-server]]
- [[create-new-instance]]
