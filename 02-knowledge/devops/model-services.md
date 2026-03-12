---
tags:
  - area/devops
  - area/knowledge
  - topic/ai
  - topic/docker
  - topic/kubernetes
  - topic/llm
  - topic/snippets
---

# Model services

export HOST_WORKSPACE_FOLDER=$(pwd)

**Wrapper**
docker compose --profile=rfp-wrapper -f deployment/docker-compose.yml -f  deployment/docker-compose-ci-cd.yml config > deployment/docker-compose-complete.yml
docker compose --profile=rfp-wrapper -f  deployment/docker-compose-complete.yml build
docker compose --profile=rfp-wrapper -f deployment/docker-compose-complete.yml up

**Transformer**
docker compose --profile=rfp-transformer -f deployment/docker-compose.yml -f  deployment/docker-compose-ci-cd.yml config > deployment/docker-compose-complete.yml
docker compose --profile=rfp-transformer -f deployment/docker-compose-complete.yml up

**UI**
docker compose --profile=rfp-ui -f deployment/docker-compose.yml -f  deployment/docker-compose-ci-cd.yml config > deployment/docker-compose-complete.yml
docker compose --profile=rfp-ui -f deployment/docker-compose-complete.yml up

docker compose --profile=rfp-ui -f deployment/docker-compose.yml config > deployment/docker-compose-complete.yml
docker compose --profile=rfp-ui -f deployment/docker-compose-complete.yml up

docker compose --profile=nlp2sql-transact-solution -f deployment/docker-compose-complete.yml up

## Related
- [[devops-moc]]
- [[sample-pods-and-services-yaml]]
- [[microservice-helm-and-argocd]]
- [[udemy-10-network-service-discovery]]
