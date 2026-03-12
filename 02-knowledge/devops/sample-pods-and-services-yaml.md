---
tags:
  - area/devops
  - area/knowledge
  - topic/angular
  - topic/aws
  - topic/docker
  - topic/kubernetes
  - topic/networking
---

# Sample Pods and Services YAML

apiVersion: v1
kind: Pod
metadata:
  name: webapp
  labels:
    app: webapp
    release: "0"
spec:
  containers:
  - name: webapp
    image: richardchesterwood/k8s-fleetman-webapp-angular:release0

---

apiVersion: v1
kind: Pod
metadata:
  name: webapp-0.5
  labels:
    app: webapp
    release: "0.5"
spec:
  containers:
  - name: webapp
    image: richardchesterwood/k8s-fleetman-webapp-angular:release0-5

Service

apiVersion: v1
kind: Service
metadata:
  name: raul-webapp
spec:
  # Which pods are going to be represented by the Service
  # Network endpoint for services or users
  # Matches the labels in pod
  selector: 
    app: webapp
    release: "0.5"

  ports:
  - name: http
    port: 80
    nodePort: 30080

  type: NodePort

## Related
- [[devops-moc]]
- [[model-services]]
- [[simple-work-flow-service-swf]]
- [[sns-simple-notification-service]]
