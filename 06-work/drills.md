---
tags:
  - area/ai-ml
  - area/knowledge
  - topic/ai
  - topic/kubernetes
  - topic/llm
---

# Drills

Wealth

Gitops
./cluster-provisioning/genai-ew2-u-1/genai-ew2-u-1-env.sh 

**Deploy Normal services:**

Deployments/Services - Pods 

**Knatives**

Name of the Knative resource type:
*services.serving.kative.dev*

All wiring for istio 

**Gateway** and **VirtualServices**

Installation - LB is created

**Kserver**
**Inferencing use cases**

**ClusterServing Runtimes**

**Inference Services**

**Support model caching**

**Multiple type of models**

Spot instance - spot instance GPU

Kops get all

Shows all available groups
e.g. spot-group-gpu

Nims didn’t work on G5 machines

Cluster scale up doesn’t work sometimes ?  
helm upgrade --install nim-llama-3-sqlcoder-8b ./llm-custom-runtimes --values ./llm-custom-runtimes/values-defog-sqlcoder-7b-nvidia-nim.yaml --values ./llm-custom-runtime/values-spot.yaml -n genai

helm upgrade --install NAME ./llm-custom-runtimes --values ./llm-custom-runtimes/VALUES.yaml --values ./llm-custom-runtime/values-spot.yaml -n genai

Knative holds the request for you until pod is up
Activator 

NIM Profile - FP8    master - sanctions_screening

## Related
- [[ai-ml-moc]]
