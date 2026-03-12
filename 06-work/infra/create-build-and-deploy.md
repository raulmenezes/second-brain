---
tags:
  - area/devops
  - area/knowledge
  - topic/kubernetes
  - topic/monitoring
  - topic/networking
---

# Create Build & Deploy

https://phabricator.live.logicalglue.net/w/developers/deploying/

**Checkout release branch** 

e.g. rel-5.13

**Cherry pick commit to go into Release** 

In the terminal 
N=5.16.0.0

Next update build.gradle with new version number e.g.

Set N value:
version = '5.13.0.10'

./gradlew clean
./gradlew validateLicenses

**Check changes:**  diff csshx

**Push**

git push origin $(git rev-parse --abbrev-ref HEAD) v$N

**Go to Team city and push art to nexus repo**

Go to the options 
Parameters:
Enter the version number e.g. 5.12.0.4
Dependencies: Select the correct built branch

Go to  Grafana and job check 

sudo systemctl status lg-teamcity.service

csshx machines

See how busy servers are:
top
ps -ef | grep -i jobid

## Related
- [[devops-moc]]
- [[manual-deployment]]
- [[microservice-helm-and-argocd]]
- [[4th-field-subnet-block]]
