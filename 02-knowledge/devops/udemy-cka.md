---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/monitoring
  - topic/networking
  - topic/snippets
---

# Udemy CKA

2 hours - Exam
Documentation 
- https://kubernetes.io/docs
- https://kubernetes.io/blog/

**Core Concepts**

Cluster Architecture 

![[attachments/pasted-graphic-93.png]]

**Docker vs ContainerD**

**Kubernetes - Container Runtime Interface (CRI)** 
*crictl*

**containerd** 
*ctl*
*nerdctl*

**containerd** 

**etcd**
- **Distributed reliable key-value store - Simple Secure & Fast**
- **backing store for all cluster data.**

**Kube-API Server**

**E.g. kubectl get nodes**
**Kubectl command -> Kube-APIServer -> Validates request -> Etcd Cluster**

1. **Authenticate User**
2. **Validate User**
3. **Retrive data**
4. **Update ETCD**
5. **Scheduler**
6. **Kubelet**

**Kube Controller Manager**

**Controller is a process that continuously monitors the state of various components within the system**
- Works towards bring to the desired functioning state
- E.g.  Replication Controller

Node Controller /
- Monitoring the status of the nodes
- Via Kube API server
- Tests the status every 5 seconds

**Kube-controller manager - kubeadm**
*kubectl get pods -n kube-system*

**Kube Scheduler**
Deciding which pod goes on which node
E.g. Node with enough CPU for Pod

**Kubelet**

Leads all activities 

**kube-proxy**

process runs on each node
Looks for new services
IP tables rules on each node

Pod - single instance of an application - smallest object

**Create an NGINX Pod**
kubectl run nginx --image=nginx
**Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)**
kubectl run nginx --image=nginx --dry-run=client -o yaml
**Create a deployment**
kubectl create deployment --image=nginx nginx
**Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)**
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml
**Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run) and save it to a file.**
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml

## Related
- [[devops-moc]]
- [[cka]]
- [[helm-keycloak]]
- [[overview-kibernetes]]
