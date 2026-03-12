---
tags:
  - area/devops
  - area/knowledge
  - topic/ai
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# Overview Kibernetes

Desired state management
Feed the cluster a specific configuration
It will be up to the services to run that config in the infrastructure 

Cluster contains:

Master Node - watching over the worker nodes

Worker 
Container host (Where the application lives)
Inside it has this Kubelet process that communicates with the K8 cluster service

Kubectl
CLI to interface with API to deploy and mange clusters
E.g. 
Kubectl run hello-minikube

Run an application on the cluster

Kubectl cluster-info

View information about the cluster

Kubectl get nodes

List all the nodes part of the cluster

![[attachments/pasted-graphic-18.png]]

When you install Kubernetes on a system you also get:

API Server
API act as a frontend
User command line interfaces

etcd
Stores the configuration data 
Kubelet
Agent that runs on each node on the cluster.
Makes sure the containers are ru

nning as expected on the Nodes.

Container Runtime
Used to run containers e.g. Docker

Controller
Brain behind the orchestration. Responsible for when containers or nodes go down 

Scheduler
Distribution of work with the nodes

Kube proxy

IPVS

![[attachments/pasted-graphic-19.png]]

## Related
- [[helm-kubernetes]]
- [[kubernetes]]
