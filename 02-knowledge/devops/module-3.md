---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# Module 3

kubectl get deployments
kubectl get replicasets

curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress\[0\].ip}"`

**Update replica field using scale command:**
kubectl scale deployment hello --replicas=5

**Check number of pods running**
kubectl get pods | grep hello- | wc -l

**Update your deployment** 
	**Change image in containers section**

kubectl edit deployment hello

**Pause a Deployment**
kubectl rollout pause deployment/hello

**Ge Status of Deployment**
kubectl rollout status deployment/hello

**Rollout command to roll back deployment to previous version**
kubectl rollout undo deployment/hello

**Verify pods have rolled back to previous version**
kubectl get pods -o jsonpath --template='{range .items\[*\]}{.metadata.name}{"\t"}{"\t"}{.spec.containers\[0\].image}{"\n"}{end}'

## Canary Deployment 

Same version as current version but add a new label/tag

## Blue-Green Deployment

kubectl create -f deployments/hello-green.yaml

**Update service to point to new version (Deployment)**
kubectl apply -f services/hello-green.yaml

**We can roll back by applying the previous service**
kubectl apply -f service/hello-blue.yaml

**Verify Version**
curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress\[0\].ip}"`/version

## Related
- [[devops-moc]]
- [[module-4]]
- [[module-2]]
- [[module-1]]
