---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/kubernetes
  - topic/networking
  - topic/project
  - topic/snippets
---

# Infra rh backup notes

Infra-rh_backup notes  
DB call failed: 
ModelBuildUUID\[3ef76728-2c39-49e5-88ee-0dab2b577d01\]: update with args 
\[UPDATE BULK_INFERENCE SET 
statistics_id = ?, finished = ?, job_id = ?, uploaded_filename = ?, upload_id = ?, start_time = ?, finish_time = ?,                                                 rows_requested = ?, rows_rejected = ?, rows_processed = ?, rejections = ?::JSONB,   result_file_id = ?, additional_models = ?WHERE id = ?, 
\[9ec1ab46-3632-4c9c-85c5-889dd098b821, true, 26, Warba-Bank-Attrition-model.csv, LxjhBzwErZIHtqFAJKqV, 2024-08-14 18:28:12.404136, 2024-08-14 18:29:22.161209065,   158906, 0, 158906, \[\],                                                              SXSWaaigNpVgWvOWrNgk, com.logicalglue.database.entities.analytics.BulkInferenceDAO$$Lambda$1086/0x00007f9ee4bbc000@70bae186, c73f8621-d829-4803-b6fb-e61817d4911f\]\]; org.springframework.jdbc.BadSqlGrammarException: PreparedStatementCallback; bad SQL grammar \[UPDATE BULK_INFERENCE SET statistics_id = ?, finished = ?, job_id = ?, uploaded_filename = ?, upload_id = ?, start_time = ?, finish_time = ?, rows_requested = ?, rows_rejected = ?, rows_processed = ?, rejections = ?::JSONB, result_file_id = ?, additional_models = ?WHERE id = ?\]

10.11.74.46
5433
app-warba
phaib4tiY3ooyoo;b4aif7vuaLie3eit

psql -d app-warba -h 10.11.74.46 -U app-warba -p 5433

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='8';
LxjhBzwErZIHtqFAJKqV

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='2';
old - EdidxmDcXfkjIFznlDaY

UPDATE masterdb.project SET upload_id='LxjhBzwErZIHtqFAJKqV' WHERE project_id='2';

=========== ===========

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='9';
JLmOZYzKyZgOEcPiVGUx

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='3';
old - rVTwscRHkhoSnshqDZKc

UPDATE masterdb.project SET upload_id='JLmOZYzKyZgOEcPiVGUx' WHERE project_id='3';

=========== ===========

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='10';
yuibemFBVenlejbyirMV

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='5';
old - wCZVzGueGdrwsPaqeEra

UPDATE masterdb.project SET upload_id='yuibemFBVenlejbyirMV' WHERE project_id='5';

=========== ===========

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='11';
UpjXWDOLHjwpZZswylrb

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='4';
old - ocFgqGjZLcoQMdGEgPYE

UPDATE masterdb.project SET upload_id='UpjXWDOLHjwpZZswylrb' WHERE project_id='4';

## Related
- [[helm-kubernetes]]
- [[elastic-load-balancers]]
