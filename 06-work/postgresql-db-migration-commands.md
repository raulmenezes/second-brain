---
tags:
  - area/resources
  - topic/aws
  - topic/database
  - topic/project
  - topic/snippets
  - type/snippet
---

# PostgreSQL DB Migration Commands

export PGPASSWORD='<redacted>'

psql -d app-mixer -h rds-ew2-d-1-cluster.cluster-c3jq2c4k37lt.eu-west-2.rds.amazonaws.com -U app-mixer

 5821

 SELECT project_id, upload_id FROM masterdb.project WHERE project_id='5821';
chxWoRvgQquPRSGUwCfz
 2

 SELECT project_id, upload_id FROM masterdb.project WHERE project_id='5820';
 old - ocFgqGjZLcoQMdGEgPYE

 UPDATE masterdb.project SET upload_id='chxWoRvgQquPRSGUwCfz' WHERE project_id='5820';

 5822

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='5823';
GUClhHdsmLZgglanYJLC

SELECT project_id, upload_id FROM masterdb.project WHERE project_id='5822';
old - rVTwscRHkhoSnshqDZKc

UPDATE masterdb.project SET upload_id='GUClhHdsmLZgglanYJLC' WHERE project_id='5822';

UPDATE masterdb.project SET upload_id='GUClhHdsmLZgglanYJLC' WHERE project_id='5825';

## Related
- [[work-moc]]
- [[resources-moc]]
