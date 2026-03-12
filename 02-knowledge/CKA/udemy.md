---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# Udemy

Deploy Microservices to the AWS Cloud

Commands:

minikube start
minikube ip

kubectl get all
kubectl get pods
kubectl get po --show-labels
kubectl get po --show-labels -l release=0
kubectl describe service[svc] [service name]
kubectl delete po --all
kubectl delete rs [replicaset name]

kubectl delete -f pod.yml 
kubectl delete -f . 

kubectl  -it exec [podName] sh

https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/#-strong-api-overview-strong-

**Apply Filename**

Kubectl apply -f 

**Information about the pod**
Kubectl describe pod webapp

List the files inside the webapp pod 
Kubectl  exec webapp ls 

Terminal inside the pod
kubectl  -it exec webapp sh

ClusterIP 
Only internal traffic e..g MicroService to MicroService

NodePort:
Export a port through the Node
Anymore number greater than 30000

Service is long living stable IP address 

Ingress Service ?

**Selector**
- Which pods are going to be represented by the Service
- Matches the labels in pod

Metadata block of **Pod** add **Label** which matches selector in **Service**

As many labels and selectors as we want

Second pod with new release 

A Deployment will create a replicaset 
When updating an image 
Two replicasets are made
The old ReplicaSet is kept for rollback

![[attachments/pasted-graphic-20.png]]

Kubectl rollout status deploy [name] - See progress of rollout
Kubectl rollout history deploy [name] - History of Revisions 
Only used of emergency:
Kubectl rollout undo deploy [name] --to-revision=2
 

10 - Networking and Service Discovery 

Containers in the same Pod can use localhost port to talk to each other

Namespace - partitioning 
Similar to a package 

![[attachments/pasted-graphic-21.png]]

kubectl get ns #List all namespaces
kubectl get po -b kube-system 

Kubernetes uses the default namespace by default. Need to specific what namespace to do get or describe if not in default namespace.

Put third party pods in different namespaces

Kube-DNS-Service

Kubernetes automatically handles the config on the pods created.
Pods connect to the DNS service to locate other pods
Accessing MySQL from a Pod

Fully Qualified Domain Names (FQDN)
E.g. database.default.svc.cluster.local

Micoservice 

Integration Database other systems are able to access it
Each micoservice will maintain its own datastore
Able to have multiple types of databases 

Kubernetes Persistence and Volumes

Upgrade to MongoDB

Persistence Volumes
Add volumnMounts to target where the container data will be stored
What folder mongoDb is storing its data

Instead of hard coding the path in the deployment yaml file
We can add a pointer to the configuration file 
Easier to update in one location

New Kinds  PersistenceVolumeClaim (pvc)
Requirements

![[attachments/pasted-graphic-22.png]]

PersistenceVolume
How (implementation)

![[attachments/pasted-graphic-1-12.png]]

Link them together using a StorageClass
storageClassName
Setup different classes of storage
Hard drive / SSD

## Related
- [[databases-moc]]
- [[databases]]
