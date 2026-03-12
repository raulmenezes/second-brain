---
tags:
  - area/devops
  - area/knowledge
---

# Manual Deployment

https://phabricator.live.logicalglue.net/w/developers/deploying/

N=2022.10-00

edit version number in **build.gradle**
```
./gradlew validateLicenses
cp ./build/reports/license/dependency-license.json ./
git add build.gradle dependency-license.json && git commit -m "releasing $N" && git tag v$N
git push origin $(git rev-parse --abbrev-ref HEAD) v$N
./gradlew build standardDistTar distZip -x mkdocs
```

lg-rel-5.16.0.1-metadata.tar

Upload to Nexus:   /lg/builds as 'Directory'

![[attachments/ai-studio-custom-build.png]]

`./update app-xxx`

## Related
- [[create-build-and-deploy]]
- [[deploy-new-instance]]
