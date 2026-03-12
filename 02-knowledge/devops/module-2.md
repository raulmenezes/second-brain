---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/gcp
  - topic/kubernetes
  - topic/snippets
---

# Module 2

Google Container Engine (Kubernetes running on Compute Engine)

**Create Cluster**

gcloud container clusters create bootcamp --num-nodes 5 --zone us-central1-f --scopes "https://www.googleapis.com/auth/projecthosting,storage-rw"

**Information about cluster**
kubectl cluster-info

# **Kubectl Completion command**
source <(kubectl completion bash)

git clone https://github.com/googlecodelabs/orchestrate-with-kubernetes.git

Sample has this layout :

deployments/  /* Deployment manifests */
nginx/        /* nginx config files */
pods/         /* Pod manifests */
services/     /* Services manifests */
tls/          /* TLS certificates */
cleanup.sh    /* Cleanup script */

**Single instance of nginx container**
kubectl run nginx --image=nginx:1.10.0

kubectl get pods

kubectl expose deployment nginx --port 80 --type LoadBalancer

kubectl get services

**Create 3 Pods**
kubectl scale deployment nginx --replicas 3

kubectl get pods

## PODS

**Pod represents a logical application. Collection of one or more containers**

**Volumns are data disks that live as long as a pod is alive**

**Documentation for commands**
kubectl explain
Get more information about the things e.g. POD, Service
kubectl describe

**Create Monolith Pod**
kubectl create -f pods/monolith.yaml

**Setup Port forwarding**
kubectl port-forward monolith 10080:80

**Check Logs**

kubectl logs (monolith)

**Create a stream of logs**

kubectl logs -f (monolith)

## Services

Services provide stable endpoints for pods

Uses labels to determine which pods to operate on

## Related
- [[devops-moc]]
- [[module-4]]
- [[module-3]]
- [[module-1]]
