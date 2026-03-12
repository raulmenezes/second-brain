---
tags:
  - status/archive
  - topic/snippets
  - topic/testing
---

# Setup Git Environment with GitHub

**Move to your SSH folder**
cd ~/.ssh
**Generate GitHub SSH Key**:
ssh-keygen -t rsa -f github_yourname_rsa -C "GitHub Your Name"  
**Copy SSH Public Key and Add it to your GitHub account**
cat github_yourname_rsa.pub | pbcopy
**Add SSH Configuration for this key** subl ~/.ssh/config  **Past the content of the SSH Public Key to your GitHub account**  (https://github.com/settings/keys)

## Related
- [[archive-moc]]
- [[setup-development-environment-on-macos]]
