---
tags:
  - area/devops
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/database
  - topic/docker
  - topic/networking
---

# NLQ

**Database**
docker run --platform linux/amd64 --name transactsqldb --rm -p 1433:1433 -d [temnxai.azurecr.io/genai/transactsqldb](http://temnxai.azurecr.io/genai/transactsqldb) 
**Docker** 
export PASSWORD="esoucf1wKV1LQPLo7PMlSDvw3AsNId2YtfI3V0weSA=="
export HOST_IP=$(ipconfig getifaddr en0)
export DB_CONNECTION_STRING="mssql+pyodbc://genai:$PASSWORD@$HOST_IP:1433/coresqldb?driver=ODBC+Driver+18+for+SQL+Server&TrustServerCertificate=yes"
export DB_METADATA=/home/app/resources/transact-metadata.yaml
export NLQ_RESOURCES=/home/app/resources
docker run --platform linux/amd64 --rm -p 8080:8080 -e DB_CONNECTION_STRING=$DB_CONNECTION_STRING -e DB_METADATA=$DB_METADATA -e NLQ_RESOURCES=$NLQ_RESOURCES [temnxai.azurecr.io/genai/nlq-server:cdbf5ea](http://temnxai.azurecr.io/genai/nlq-server:cdbf5ea) 

**Repo Run**
export PASSWORD="esoucf1wKV1LQPLo7PMlSDvw3AsNId2YtfI3V0weSA=="
export HOST_IP=127.0.0.1
export DB_CONNECTION_STRING="mssql+pyodbc://genai:$PASSWORD@$HOST_IP:1433/coresqldb?driver=ODBC+Driver+18+for+SQL+Server&TrustServerCertificate=yes"
export DB_METADATA=`pwd`/resources/transact-metadata.yaml
poetry run start

## Related
- [[devops-moc]]
- [[Ansible]]
- [[snowball]]
- [[dns]]
