---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/gcp
  - topic/javascript
  - topic/kubernetes
  - topic/snippets
---

# Google Container Engine

**Set Zone**
gcloud config set compute/zone europe-west1-c

**Defaults in the gcloud command-line tool** 
gcloud config list

**Get clusters**
gcloud container clusters list

**Get Deployments**
kubectl get deployments (aka deploy)

## Run a container image

**Create a cluster**

gcloud container clusters create example-cluster

**Ensure kubectl has authentication credentials:**

gcloud auth application-default login

**Run the container:**

kubectl run hello-node --image=gcr.io/google-samples/node-hello:1.0 --port=8080

**Expose the container**

kubectl expose deployment hello-node --type="LoadBalancer"

**Get external IP address for the hello-node**

kubectl get service hello-node

**View the app**
http://EXTERNAL-IP:8080

## **Clean up**

**Delete the services you created to remove the load balancing** 
kubectl delete service hello-node

**Delete the cluster**
gcloud container clusters delete example-cluster

brew cask install virtualbox

## Related
- [[devops-moc]]
- [[google-cloud-essentials]]
- [[kubernetes-google-cloud]]
- [[overview-kibernetes]]
