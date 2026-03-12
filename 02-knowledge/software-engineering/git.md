---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/angular
  - topic/snippets
  - topic/testing
---

# GIt

**Generate Key**
ssh-keygen -t rsa -C “raul” -b 4096 -f ~/.ssh/gitlab_rsa

**Copy Key for Github / GitLab / Etc**
cat ~/.ssh/gitlab_rsa.pub|pbcopy

**Edit Config**
subl ~/.ssh/config

**Add this :** 

# Git GitLab
Host gitlab.com
HostName gitlab.com
User git
IdentityFile “~/.ssh/gitlab_rsa”
PasswordAuthentication no
StrictHostKeyChecking no

**Test by SSH into the website e.g.** 
ssh gitlab.com

## Related
- [[software-engineering-moc]]
- [[directive]]
- [[highcharts]]
- [[redux]]
