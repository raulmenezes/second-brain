---
tags:
  - area/databases
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/database
  - topic/project
  - topic/snippets
---

# Model Cloning Popup Server

## Scope

This note is the canonical runbook for cloning and importing model data between environments.

CWB Popup Server - 3.98.118.220
UBS Popup Server - 18.157.121.8
Demo Popup Server - 18.135.240.136

**#### Copy clone script to server which has the source model**

The script to clone a model `clone_model.sh` is located inside the Server repository inside the scripts folder

To copy the script to a server run:
`scp clone_model.sh \[server\]:`
E.g.
`scp clone_model.sh paal.infra.logicalglue.net:`

After copying the script over, you will need to make the script executable - `chmod +x clone_model.sh`

**#### Modify Script to Clone Requested Model**

SSH into server and modify the clone_model script:

Variables to change:
`DB_HOST`: Database Host - Required parameter If the source database is on Amazon RDS
`IS_SOURCE_REMOTE`: `true` if RDS, `false` if we hosted
`A`: App Name - Instance where model is exported from e.g. `app-cwb`
 `MOID`: Model Number - Current model id 
`PID`: Project Number - Current project id
`O`: Organisation - Current organisation the model is located

##### Not needed with new clone and import model script

~~##### Get New Model ID & Project ID~~

~~Connect to the database where the new model will be cloned.~~

~~If managed postgres database:
`sudo -u  psql`~~

~~If Amazon RDS:
`psql -d  -h  -U `
e.g.
For app-mixer RDS, SSH into cuba then run:
`psql -d app-mixer -h eu-w-2-db-uat-2-cluster.cluster-c3jq2c4k37lt.eu-west-2.rds.amazonaws.com -U app-mixer`~~

~~To get Amazon RDS db_host endpoint and password run `ansible-vault edit group_vars/rds` (From ansbile folder)~~

~~**Find New Model ID**
`SELECT max(model_id) + 1 AS new_model_id FROM masterdb.model;`~~

~~**Find New Project ID**
`SELECT max(project_id) + 1 AS new_project_id FROM masterdb.project;`~~

#### Run Clone Model Script

When exporting a model from Amazon RDS, we can export the password: 
(Password can be found when running the command locally - `ansible-vault edit group_vars/rds`)
NOTE: Add a space at the start of the command to prevent the password showing up in the history

` export PGPASSWORD=‘’`

After changing all the required variables run the clone script: 
`./clone_model.sh`
Check the new clone model is inside the `/tmp` folder

~~**!!!!!!Copy the Manual Steps that is displayed!!!!**
These will be needed to import the model into the new database.~~

#### Move cloned model to new app instance machine

SSH with the `-A` option to:
- DB machine if we hosted it, or 
- Any of machine that has the connection to the database if it is RDS.

e.g. `ssh -A paal`

Copy cloned model from previous machine to new app instance machine.

`rsync -az --info=progress2 : .`
e.g. 
`rsync -az --info=progress2 cwb-ui-a.infra.logicalglue.net:/tmp/clone_model_641 .`

##### Move cloned model to tmp folder and decompress files

`cp -r  /tmp/`
e.g.
`cp -r clone_model_641/ /tmp/`

~~Go to cloned model inside tmp folder and decompress files:
`gzip -d *.gz`~~

#### Align model's feature set  before import

Update feature set's user id with one found in the new app instance:

**Get User ID:**
Connect to database and get a user id e.g. Hani's user id
`sudo -u  psql`
`select * from masterdb.users where username like '%hani%';` or `select * from masterdb.users where username like '%hh%';`

**Edit DB Clean SQL File:**
Edit the db clean sql file e.g. `NN_db__clean.sql` inside the clone model folder.
Search for the text `updated_by` and on the second search instance of the text you will see a table. 
Update the `updated_by` field number to the user id found previously and save.

~~#### Running Manual Steps Commands
**Check Model ID and Project ID haven't changed**
Run a last check that the model id number and project id number haven’t changed before running the manual steps.
Run each Manual Steps command and check the output after each one.
After running the 7th command copy the model id and replace it on the 8th command `` and continue running the commands.
Finally login and check that the project and model are now available on the app instance.~~

#### Copy import script to server where model will be imported
The script to import models `import_model.sh` is located inside the Server repository inside the scripts folder

To copy the script to a server run:
`scp import_model.sh \[server\]:`

After copying the script over, you will need to make the script executable - `chmod +x import_model.sh`

#### Modify Import Script to import cloned model files

SSH into server and modify the import model script:

Variables to change:
`DB_HOST`: Database Host - Required parameter If the target database is on Amazon RDS
`IS_TARGET_REMOTE`: `true` if RDS, `false` if we hosted
`APP_NAME`: New App Name - Instance where model is exported from e.g. `app-mixer`
`NEW_ORGANISATION`: New organisation the model will go into
`MANUAL_STEPS` - Optional if you want to run the manual steps to import the model (but why would you?)

These values can be found inside the `import_values.txt` file found inside the cloned model folder
`MOID`: Source Model ID
`PROJECT_ID`: Source Project ID
`MODEL_UUID`: Source Model UUID

#### Run Import Model Script
`./import_model.sh`
Finally login and check that the project and model are now available on the app instance.

#### Clean Up 

##### Cleaning model transaction history data
Test that Inference works with Live datasource on the model.
Go to the Deployment History page and click on the `Clear All` button to remove all Live transactions.

##### Delete audit_data for demo, validation testing and training
Connect to database and get the model UUID
`SELECT model_id, model_uuid FROM masterdb.model WHERE model_id='';`

Check what audit_data is available to delete:
`select distinct(datasource), count(1) from model_.audit_data group by datasource;`
Delete each datasource of audit_data:
`delete from model_.audit_data where datasource = 'demo';`
`delete from model_.audit_data where datasource = 'validation';`
`delete from model_.audit_data where datasource = 'testing';`
`delete from model_.audit_data where datasource = 'training';`

#### Link up Synthetic data file
If there is an existing project with the data, we can just use that project's upload_id and update the cloned project upload_id.

However, if the synthetic data does not exist. We can create a new project and upload the data file we need.
We can then copy the upload_id field from the newly created project (SD_PROJECT_ID) and update our cloned project upload_id (PROJECT_ID). 

NOTE: Delete the created project after we have generated the upload_id

`SELECT project_id, upload_id FROM masterdb.project WHERE project_id='';`

`UPDATE masterdb.project SET upload_id='' WHERE project_id='';`

#### Extra - Troubleshooting Model

###### Is Model Ready (when model not showing in new project)
If the model has been import successfully but it is not showing up. It could be because the //**is_model_ready**// field is set to false inside masterdb.model.
Check the model field for //**is_model_ready**//:
`SELECT model_id, model_uuid, is_model_ready FROM masterdb.model WHERE model_id='';`

If //**is_model_ready**// is false:
`UPDATE masterdb.model SET is_model_ready=true WHERE model_id='';`

###### Invalid UUID
In some cases when cloning a model a few fields have invalid UUIDs. 
In this case we must fix the length in order to be able to run Manual Step  commands.
We must then check that the UUID inside master.model and the model schema match up.

###### Issue with XGBoost Model
Step 1 
Copy the correct model_store from original XGBoost Model. Replace the **XXXX** with the model id.
`\copy (select model_id, model_store from masterdb.model Where model_id=XXXX) To '/tmp/update-data.csv' With CSV DELIMITER ',' HEADER;`

Step 2
Change the model_id number in the csv file to the new model id in the new database

Step 3
Create a temp table to hold the data
`CREATE TEMP TABLE temp_model_updates (model_id INTEGER, model_store VARCHAR);`

Step 4
Copy the data in to the temp table:
`\copy temp_model_updates(model_id, model_store) FROM '/tmp/update-data.csv' WITH CSV HEADER;`

Step 5
Update the model store with the data in the temp table:
`UPDATE masterdb.model SET model_store = temp.model_store FROM temp_model_updates temp WHERE model_id = temp.model_id;`

## Related
- [[databases-moc]]
- [[model-cloning-popup-server]]
- [[clone-model]]
- [[check-storage-in-postgresql]]
