---
tags:
  - area/devops
  - area/knowledge
  - topic/database
  - topic/kubernetes
  - topic/monitoring
  - topic/snippets
---

# Helm kubernetes

Package manager for Kubernetes
- apt, yum and homebrew 
Packages YAML files and distribute them in public and private respositories.

For deploying Elastic Stack for Logging
Yaml files for all these files: Stateful Set Config Map
Secrete K8s User with permissions Services

Helm Charts
Bundle of YAML files
Create your own Helm Charts with Helm Push them to Helm Repo

E.g.
Database Apps - MySQL

Monitoring Apps - Prometheus 

helm search NAME

**Templating Engine** Deployment and Service configuration almost the same (Without Helm separate YAML files for each one) Common blueprint Dynamic Values are replaced by placeholders with the values.yaml file.

![[attachments/pasted-graphic-6-6.png]]

Practical for CI/CD - Replace the values on the build 

Same application across different environments

**Directory Structure** 

myChart/
- Chart.yaml - meta info about chart (name version list of dependency)
- values.yaml - values for the template files (Default values you can override)
- charts/ - charts dependencies 
- template - actual template files

helm install CHARTNAME

**Value injection into template files**

helm install OURNAME --values=my-values.yaml CHARTNAME 

**Release Management**

**Helm Version 2 two parts:** Client (Helm CLI) => Server (Tiller)

Downside:
- Tiller has too much power inside of kubernetes cluster 
- Security Issues 
**Helm Version 3** Tiller removed 
Loses release management feature 

**Helm Commands:**

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install grafana bitnami/grafana

helm repo list

kubectl port-forward svc/grafana 8081:3000

**Helm status:**
description of the release last deployment time 

helm status RELEASE_NAME

kubectl scale --replicas=2

## Related
- [[devops-moc]]
- [[overview-kibernetes]]
- [[kubernetes]]
- [[kubernetes-google-cloud]]
