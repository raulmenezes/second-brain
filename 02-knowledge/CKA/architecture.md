---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/networking
---

# Architecture

[[kubernetes]]
Master and Node


**Node**
- Worker machines in K8s cluster
- Has multiple pods
- 3 processes must be installed on every Node
	- Container Runtime
	- Kubelet
		- Interacts with both the container and node
		- Starts the pod with a container inside
	- Kube Proxy
		- Forwards the requests to the pod

Master
- 4 Process run on every master node
	- API Server
		- Cluster Gateway
			- Update Query
			- Gatekeeper for authentication
			-

## Related
- [[ha-architecture]]
- [[overview-kibernetes]]
