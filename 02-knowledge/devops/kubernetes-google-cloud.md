---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/gcp
  - topic/javascript
  - topic/kubernetes
---

# Kubernetes   Google Cloud

Creating a Kubernetes Engine cluster

gcloud container clusters create [name]

Get authentication credentials for the cluster - to interact with the cluster.

gcloud container clusters get-credentials [CLUSTER-NAME]

Deploying an application to the cluster

kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0

Expose application to external traffic - Kubernetes Service - Kubernetes resource

kubectl expose deployment hello-server --type=LoadBalancer --port 8080

Inspect Service
kubectl get service

Delete the cluster
gcloud container clusters delete [name]

abstractions in Kubernetes allow you to deploy containerized applications to a cluster without tying them specifically to individual machines.

Kubernetes created a Pod to host your application instance. 
A Pod is a Kubernetes abstraction that represents a group of one or more application containers

Deployment creates Pods with containers inside them
Each Pod is tied to the Node where it is scheduled

Nodes
A Pod always runs on a Node. 
A Node is a worker machine in Kubernetes and may be either a virtual or a physical machine, depending on the cluster
A Node can have multiple pods

![[attachments/pasted-graphic-1-10.png]]

## Related
- [[devops-moc]]
- [[kubernetes-data-science-repo]]
- [[google-container-engine]]
- [[helm-kubernetes]]
