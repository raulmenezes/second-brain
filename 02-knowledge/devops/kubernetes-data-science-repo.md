---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# Kubernetes   Data science Repo

kubectl config current-context

**kops-u** 
ubuntu@18.133.184.33

**kops-p**
kops-p.infra.logicalglue.net

Useful Commands:

**Check current context**

kubectl config current-context

**Get all pods and services**
kubectl get all

Change file of workload with new version

![[attachments/pasted-graphic-7-3.png]]

Kubet logs -f 

Kubectl describe pods

Kubectl apply -f 

kubectl rollout undo deployment [DEPLOYMENT_NAME]
E.g. 
kubectl rollout undo deployment keycloak

kubectl get deploy -A

kubectl delete deploy [DEPLOYMENT_NAME]

Products
**Rayce**:
- **fundsflow_balance** -> CWB Canada cluster (Prod) 

**Karampreet** 
 UBS (Frankfort) -> UAT

Go to directory which you want to build the docker file:

**Run docker build**

docker build -t quay.io/logicalglue/proxy_etl:[client][version] .
E.g.
docker build -t quay.io/logicalglue/proxy_etl:fundsflow_balance_v0.0.4 .

docker build -t quay.io/logicalglue/proxy_etl:equifax .

**Run docker push**
docker push [quay.io/logicalglue/proxy_etl:ubs_fcm_v0.0.1](http://quay.io/logicalglue/proxy_etl:ubs_fcm_v0.0.1)

Check on quay

![[attachments/pasted-graphic-28.png]]

Copy files to your own home:

![[attachments/pasted-graphic-5-6.png]]

![[attachments/pasted-graphic-6-4.png]]

Copy work files to k8s files to your own home directory

*scp -r k8 rmenezes@kops-p:/home/rmenezes* 

*scp -r* equifax-proxy *rmenezes@kops-p:*/home/rmenezes/k8s/deployments

**Adding new subdomain**
Go to AWS Route 53

Record Type - A
Route Traffic: Alias to Application and Classic Load Balancer [Region] E.g. Canada - ca-central-1
Endpoint

Routing policy - Simple Routing

![[attachments/route-53-k8.png]]

gcloud config set compute/zone us-central1-a gcloud container clusters create \[CLUSTER-NAME\] gcloud container clusters get-credentials \[CLUSTER-NAME\] kubectl create deployment hello-server --image=[gcr.io/google-samples/hello-app:1.0](http://gcr.io/google-samples/hello-app:1.0) kubectl expose deployment hello-server --type=LoadBalancer --port 8080  
**explain command in kubectl can tell us about the Deployment object.** kubectl explain deployment **See all of the fields using the --recursive option.**
kubectl explain deployment --recursive
  kubectl get replicaset  You can also see a new entry in the rollout history: kubectl rollout history deployment/hello

kubectl rollout undo deployment/hello

kubectl delete deploy

same user will always be served from the same version. In the example below the service is the same as before, but a new sessionAffinity field has been added, and set to ClientIP. All clients with the same IP address will have their requests sent to the same version  
new deployment in production with a subset of your users, use a canary deployment. Canary deployments allow you to release a change to a small subset of your users to mitigate risk associated with new releases
 blue-green deployments is that you will need to have at least 2x the resources in your cluster necessary to host your application

kubectl cluster-info

Confirm that you have 5 pods running for the frontend, 4 for production traffic and 1 for canary releases
kubectl get pods -n production -l app=gceme -l role=frontend

export FRONTEND_SERVICE_IP=$(kubectl get -o jsonpath="{.status.loadBalancer.ingress\[0\].ip}" --namespace=production services gceme-frontend)

Creating a repository to host the sample app source code 
gcloud source repos create default

## Related
- [[devops-moc]]
- [[kubernetes-google-cloud]]
- [[helm-kubernetes]]
- [[overview-kibernetes]]
