---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/javascript
  - topic/kubernetes
  - topic/snippets
---

# Kops commands

kops edit cluster {NAME} 

export EDITOR=nano

Edit Nodes

Instance group for our nodes
Instance gross for our master
kops edit ig nodes --name NAME

kops get ig   --name NAME

kops edit ig {NAME OF MASTER} --name ${NAME} 

kops update cluster ${NAME} --yes 

kops validate cluster --state s3://txai-prod-temenos-com-state-store

kops rolling-update cluster --state s3://txai-prod-temenos-com-state-store

s3://txai-prod-temenos-com-state-store

kops get ig --name azur.k8s.local --state s3://temenos-com-uat-kops-state-store
kops edit ig nodes --name azur.k8s.local --state s3://temenos-com-uat-kops-state-store

kops get ig --name txai-eu-p.k8s.local --state s3://txai-prod-temenos-com-state-store
kops edit ig nodes --name txai-eu-p.k8s.local --state s3://txai-prod-temenos-com-state-store

kops update cluster --name txai-eu-p.k8s.local --state s3://txai-prod-temenos-com-state-store

kops upgrade cluster  --name txai-eu-p.k8s.local --state s3://txai-prod-temenos-com-state-store

kops update cluster --name txai-eu-p.k8s.local --state s3://txai-prod-temenos-com-state-store

performing a rolling-updating on our master nodes

kops rolling-update cluster $KOPS_NAME --instance-group master-eu-west-1a --yes

kops delete cluster --name 

t3.large

apiVersion: kops.k8s.io/v1alpha2
kind: InstanceGroup
metadata:
  creationTimestamp: "2020-08-10T16:28:05Z"
  generation: 1
  labels:
    kops.k8s.io/cluster: txai-eu-p.k8s.local
  name: nodes
spec:
  image: 099720109477/ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20200716
  machineType: t3.small
  maxSize: 2
  minSize: 2
  nodeLabels:
    kops.k8s.io/instancegroup: nodes
  role: Node
  subnets:
  - eu-west-2a
  - eu-west-2b
  - eu-west-2c

apiVersion: kops.k8s.io/v1alpha2
kind: InstanceGroup
metadata:
  creationTimestamp: "2020-09-29T09:30:06Z"
  generation: 2
  labels:
    kops.k8s.io/cluster: azur.k8s.local
  name: nodes
spec:
  image: 099720109477/ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-20200907
  machineType: t3.xlarge
  maxSize: 2
  minSize: 2
  nodeLabels:
    kops.k8s.io/instancegroup: nodes
  role: Node
  subnets:
  - eu-west-2a
  - eu-west-2b
  - eu-west-2c

## Related
- [[aws-command-line]]
