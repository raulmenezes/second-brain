---
tags:
  - area/devops
  - area/knowledge
  - topic/ansible
  - topic/docker
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# MicroService, Helm and ArgoCD

**Change docker image name/ profile** 
 
export PROFILE_NAME=demo_credit_scoring_retail  docker compose --profile=${PROFILE_NAME} -f deployment/docker-compose.yml -f deployment/docker-compose-prod.yml config > deployment/docker-compose-complete.yml

docker compose --profile=${PROFILE_NAME} -f deployment/docker-compose-complete.yml build

docker push quay.io/logicalglue/proxy_etl:NAME 

sed -i '' '4,5d' deployment/docker-compose-complete.yml

kompose -f deployment/docker-compose-complete.yml convert

**Use the generated files for deployment and service files.**

helm create NAME

helm template name ./name > helm-name.yml
 

kubectl config get-contexts
kubectl config current-context kubectl config use rmenezes@txai-ew2-u-1 kubectl config use admin@txai-ew2-u-1 
ansible-vault decrypt /Users/raulmenezes/code/glue/infrastructure/k8s/cluster-users/admin-txai-ew2-u-2.conf

## Related
- [[model-services]]
- [[encrypted-root-device-volumes-and-snapshots]]
- [[create-build-and-deploy]]
