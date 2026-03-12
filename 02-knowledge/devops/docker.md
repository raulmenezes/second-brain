---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/java
---

# Docker

docker run --rm -d --name txai \
    -e TXAI_REQUIRE_HTTPS=false \
    -e TXAI_DB_HOST=host.docker.internal \
    -e TXAI_DB_PORT=5432 \
    -e TXAI_SSL_MODE=disable \
    -e TXAI_BIND_ADDRESS=host.docker.internal \
    -e JAVA_HOME='/opt/java/openjdk' \
    -e TXAI_REDIS_HOST=host.docker.internal \
    -e TXAI_REDIS_PORT=6379 \
    -e TXAI_STACK_HOST=host.docker.internal \
    -e TXAI_IDP_HOST=host.docker.internal:8080 \
    -v /Users/raulmenezes/code/temenos/server/cloud/keys/:/home/txai/.logical-glue/keys \
    -e TXAI_CLIENT_ID_OVERRIDE=true \
    -p 8100:8100 \
    nexus.live.logicalglue.net/txai:dev_2

docker run -d --restart=always -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin -e DB_VENDOR=h2 nexus.live.logicalglue.net/keycloak:18.1.1-teamcity

## Related
- [[devops-moc]]
- [[docker-setup]]
- [[what-is-docker]]
- [[cka]]
