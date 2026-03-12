---
tags:
  - area/devops
  - area/knowledge
  - topic/docker
  - topic/gcp
  - topic/kubernetes
  - topic/networking
  - topic/project
  - topic/snippets
---

# Module 1

## **Authenticate Kubectl**
gcloud container clusters get-credentials bootcamp --zone us-central1-f

## Containers 
are a way of isolating programs or processess from each other.
The primary aim of containers is to make them easy to depoly in a way that they don't cause programs to break

## Get List of Gcloud projects
*gcloud config list project*

## **Build Docker Image**

sudo docker build -t py-web-server:v1 .

## Run web serve Docker
sudo docker run -d -p 8888:8888 --name py-web-server -h my-web-server py-web-server:v1

curl http://localhost:8888
sudo docker rm -f py-web-server

## **Rebuild the docker image with an image name that includes gcr.io project prefix**
export GCP_PROJECT=`gcloud config list core/project --format='value(core.project)'`
sudo docker build -t "gcr.io/${GCP_PROJECT}/py-web-server:v1" .

## Make Image Public 
sudo gcloud docker push -- gcr.io/${GCP_PROJECT}/py-web-server:v1

(External) 8888:8888 (Internal)

## Related
- [[devops-moc]]
- [[module-2]]
- [[module-4]]
- [[module-3]]
