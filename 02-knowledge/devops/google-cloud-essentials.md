---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/gcp
  - topic/kubernetes
  - topic/networking
  - topic/project
  - topic/snippets
---

# Google Cloud Essentials

Compute Engine > VM Instances

Create a new instance with gcloud

gcloud compute instances create [name] --machine-type [type] --zone [zone]

gcloud compute instances create gcelab2 --machine-type n1-standard-2 --zone us-central1-c 

sudo su - 
apt-get update 
apt-get install nginx -y

SSH into your instance using  gcloud

gcloud compute ssh [name] --zone [zone]

gcloud compute ssh gcelab2 --zone us-central1-c

Setting a default compute zone

gcloud config set compute/zone [zone]

gcloud config set compute/zone us-central1-a

Network Load Balancer

Create an L3 network load balancer targeting your instance group:

gcloud compute forwarding-rules create nginx-lb \
--region us-central1 \ 
--ports=80 \ 
--target-pool nginx-pool

List all Google Compute Engine forwarding rules in your project.

gcloud compute forwarding-rules list

HTTP(s) Load Balancer

Create a health check

gcloud compute http-health-checks create http-basic-check

Define an HTTP service and map a port name to the relevant port for the instance group

gcloud compute instance-groups managed \
set-named-ports nginx-group \ 
--named-ports http:80

Create a backend service

gcloud compute backend-services create nginx-backend \ 
--protocol HTTP --http-health-checks http-basic-check --global

Add the instance group into the backend service

gcloud compute backend-services add-backend nginx-backend 
--instance-group nginx-group \ 
--instance-group-zone us-central1-a \ 
--global

Create a backend service

gcloud compute backend-services create nginx-backend \ 
--protocol HTTP --http-health-checks http-basic-check --global

Create a backend service

gcloud compute backend-services create nginx-backend \ 
--protocol HTTP --http-health-checks http-basic-check --global

## Related
- [[devops-moc]]
- [[google-container-engine]]
- [[kubernetes-google-cloud]]
- [[cloudfront]]
