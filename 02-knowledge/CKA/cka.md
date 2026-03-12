---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/kubernetes
  - topic/snippets
  - topic/testing
---

# CKA

kubectl run nginx --image=nginx

--dry-run=client

**Impertive vs Declarative statements**

Imperatively means running kubectl commands

Declaratively means writing manifests using YAML

**Role-based access control (RBAC)**

kubectl create namespace development

Create a new service account named "sa” 
kubecrl create serviceaccount sa -n development

Create a cluster role called "pod-reader," having permission to get pod and list pods.

kubectl create clusterrole pod-reader --verb=get,list,watch --resource=pods

Add role pod-reader to service account sa   
kubectl create clusterrolebinding pod-reader --clusterrole=pod-reader --serviceaccount=development:sa

Test if the sa is allowed to read pods
kubectl auth can-i list pods --development target --as system:serviceaccount:development:sa

Current version of cluster
kubectl get nodes -o wide

Restart the kubelet
sudo systemctl daemon-reload
sudo systemctl restart kubelet

kubectl scale deployment/nginx-deployment --replicas=2

kubectl set image deployment/nginx-deployment nginx=nginx:1.8

## Related
- [[devops-moc]]
- [[udemy-cka]]
- [[vpc-lab]]
- [[docker-txai]]
