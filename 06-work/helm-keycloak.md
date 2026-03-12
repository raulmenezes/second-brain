---
tags:
  - area/devops
  - area/knowledge
  - topic/kubernetes
  - topic/monitoring
---

# Helm Keycloak

**UAT Keycloak:**
cat eu-west-kops-setup.sh

kops export kubecfg --admin

shorthand for --all-namespaces: kubectl -A

**Rollback release**
helm rollback MY-RELEASE 1

**List Releases**
helm list

**List Chart Repositories**
helm repo list

**Install Keycloak and Create Keycloak namespace**
helm install keycloak -f values-local.yaml bitnami/keycloak --namespace keycloak --create-namespace --wait

helm install keycloak -f values.yaml bitnami/keycloak --namespace keycloak --create-namespace --wait

**Install Keycloak** 
helm install keycloak -f values.yaml bitnami/keycloak --namespace keycloak 

**Upgrade Keycloak** 
helm upgrade -f values.yaml keycloak bitnami/keycloak --namespace keycloak

**Delete Keycloak** 
helm delete keycloak --namespace keycloak

**Display Ingress**
kubectl get ingress -n keycloak

**List all Ingress**
kubectl get ingress -A

kubectl get all -A | grep nginx

pv85j4Kqq4qeGaQ75k5UXT1b9PWISKizC4zZ2pvT

**ArgoCD**

ArgoCD is based on GitOps and implments them.

Don't need to setup kubectl, access to k8s cluster, access to cloud platforms, security challenge, no status of deployment after running apply

ArgoCD part of K8s Cluster, pulls k8s manifest changes and applies them. 
Single interface, version controlled changes, history of changes

Cluster Disaster Recovery

Access Control with Git

![[attachments/pasted-graphic-83.png]]

**ArgoCD is an K8s extension**

Uses existing k8s functions 
e.g. **/etc** to store data
e.g. k8s controllers for monitoring and comparing actual and desired states

**Working with multiple Clusters**

Able to configure one ArgoCD instance that manages an external cluster.
 Good practice to have multiple ArgoCD for each environment

Single Git branch with overlays with kustomize
 cops - terraform scripts

![[attachments/pasted-graphic-1-18.png]]

## Related
- [[devops-moc]]
- [[keycloak]]
- [[helm-kubernetes]]
- [[udemy-cka]]
