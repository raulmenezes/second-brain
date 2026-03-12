---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/kubernetes
---

# Module 4

git clone https://github.com/GoogleCloudPlatform/continuous-deployment-on-kubernetes.git

cd continuous-deployment-on-kubernetes

gcloud compute images create jenkins-home-image --source-uri https://storage.googleapis.com/solutions-public-assets/jenkins-cd/jenkins-home-v3.tar.gz

Namespaces allow you to use the same resource manifests across mutiple environments

https://cloud.google.com/solutions/jenkins-on-container-engine-tutorial

export FRONTEND_SERVICE_IP=$(kubectl get -o jsonpath="{.status.loadBalancer.ingress\[0\].ip}"  --namespace=production services gceme-frontend)

## Related
- [[devops-moc]]
- [[module-2]]
- [[module-3]]
- [[module-1]]
