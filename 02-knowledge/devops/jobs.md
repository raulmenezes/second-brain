---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/docker
  - topic/kubernetes
  - topic/snippets
---

# Jobs

Finite executed pods

**Three types of Jobs**
- Nonparallel jobs
- Parallel jobs with a fixed completion count
- Parallel jobs with a task queue

Creates Replacement if pod goes down
Jobs are not deleted after completion

apiVersion: batch/v1
kind: Job
metadata:
  name: helloworld
spec:
  # completion: 2
  # parallelism: 2
  # backoffLimit: 2
  # activeDeadlineSeconds: 10
  template:
    spec:
      containers:
      - name: busybox
        image: busybox
        command: \["sleep", "60"\]
        # command: \["echo", "Hello World Kubernetes!"\]
      restartPolicy: Never

## Related
- [[devops-moc]]
- [[storage-class]]
- [[dynamodb]]
- [[components]]
