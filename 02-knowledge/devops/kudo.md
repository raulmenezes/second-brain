---
tags:
  - area/devops
  - area/knowledge
  - topic/ai
  - topic/aws
  - topic/docker
  - topic/javascript
  - topic/kubernetes
---

# Kudo

Kubernetes Universal Declarative Operator 
Universal operator Configured via YAML Provide Plans as a way of sequencing and abstract 

**Operator Package**
**Repository**
**KUDO Manager**
- Kubernetes controllers that understand KUDO operators and know how to execute plans
**Plan**
- **operator's main workflow unit**

Operator Plans
Runbooks
Every operator must contain at least a deploy plan
Plans are made up of phases, and phases have one or more steps

plan: deploy
├── phase: bootstrap-node
│   └── step: start-bootstrap-node
├── phase: master-nodes
│   └── step: start-master-nodes
└── phase: agent-nodes
│   └── step: start-agent-nodes
└── phase: deploy-cleanup
    └── step: remove-bootstrap-node

Orchestrate tasks through phases and steps Structured runback which can be executed by software Deploy Backup Restore Upgrade

**CLI Installation**
https://kudo.dev/docs/cli/installation.html#cli-installation

**Cert manager Installation**
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.8.0/cert-manager.yaml

Install KUDO CLI
kubectl kudo init  

 kubectl get crds kubectl get operators
kubectl api-resources --api-group kudo.dev

![[attachments/pasted-graphic-3-10.png]]

## Related
- [[devops-moc]]
- [[cloudfront]]
- [[udemy-cka]]
- [[docker]]
