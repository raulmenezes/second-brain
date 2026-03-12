---
tags:
  - status/archive
  - topic/docker
  - topic/java
  - topic/javascript
  - topic/llm
  - topic/networking
  - topic/snippets
  - topic/testing
---

# SetUp Development Environment on macOS

**--Installing Software**
**Installing Homebrew**
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
**Recommeneded Software**
brew install git
brew install vim
brew cask install java
brew install maven
brew install mysql
brew cask install mysqlworkbench
brew cask install sublime-text
brew cask install intellij-idea
brew cask install visual-studio-code 
brew install node
brew cask install smcfancontrol
brew install ssh-copy-id
brew install elasticsearch@2.4
 
**Optional Software**
brew cask install slack;
brew cask install skype;
brew cask install virtualbox;
From the App Store - memory clean 2

## **--Create SSH**
ssh-keygen -t rsa -f ~/.ssh/github_sytel_rsa -C "**\[your_name\]** GitHub macOS" -P ""
cat ~/.ssh/github_sytel_rsa.pub | pbcopy
 
## **--Create config file**
subl ~/.ssh/config
Put this insdie:
# Git GitHub Host [github.com](http://github.com/) HostName [github.com](http://github.com/) User git ForwardAgent yes ForwardX11 yes IdentityFile "~/.ssh/github_sytel_rsa" AskPassGUI no BatchMode yes PasswordAuthentication no StrictHostKeyChecking no
 
## **--Create Aliases**
subl ~/.bash_aliases
Put this inside:
alias commit='git add . && git commit -m "message to rebase"' alias crp='git add . && git commit -m "message to rebase" && git push -f' alias crpd='git add . && git commit -m "message to rebase" && git push -f && git checkout dev && git fetch -p && git pull && git branch -d' alias delbranch='git fetch -p && git pull && git branch -d' alias dev='git checkout dev && git fetch -p && git pull' alias editalias='subl /Users/**yourname**/.bash_aliases*' alias editbash='subl /Users/**yourname**/.bash_profile' alias ll='ls -AFGhl' alias plist='launchctl list | grep homebrew' alias pull='git fetch -p && git pull' alias rebase='git fetch -p && git rebase -i origin/dev' alias reload='source /Users/**yourname**/.bash_profile' alias rmignore='git rm --cached `git ls-files -i -X .gitignore`' alias sl='cat ~/.ssh/config | grep Host | grep -v HostName | grep -v StrictHostKeyCheckin | tr -s " " . | tr -s "\t" . | cut -d "." -f 2' alias vdestroy='vagrant destroy --force' alias vh='vagrant halt' alias vp='vagrant provision --provision-with' alias vpo='vagrant provision' alias vr='vagrant reload --no-provision' alias vs='vagrant ssh' alias vu='vagrant up --no-provision'
alias ns='npm run start'
alias s='git status'
alias l='git log'
alias ..='cd ..'
alias docker_clean_ps='docker rm $(docker ps --filter=status=exited --filter=status=created -q)'
alias dps='docker ps -a'
alias chrome="/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome" 

## **--Create profile**
subl ~/.bash_profile
export PATH="/usr/local/sbin:$PATH" export GIT_PROMPT_ONLY_IN_REPO=1 BASH_COMPLETION="$(brew --prefix)/share/bash-completion/bash_completion" GIT_PROMPT="$(brew --prefix bash-git-prompt)/share/gitprompt.sh"
files=("/Users/**yourname**/.bash_aliases" "${BASH_COMPLETION}" "${GIT_PROMPT}")
for i in ${files\[@\]}; do   if \[\[ -f "${i}" \]\]; then         source "${i}"     else         echo "Can't find '${i}'."     fi done
## **--Git Configuration**
git config --global [user.name](http://user.name/) "John Doe"
git config --global user.email [johndoe@example.com](mailto:johndoe@example.com)
git config --global core.editor "subl -n -w"
git config --global push.default current
 
## **-- Extra commands**
brew install homebrew/versions/bash-completion2
brew install bash-git-prompt
brew install bash
sudo subl /etc/shells  → Put this inside:   /usr/local/bin/bash
chsh -s /usr/local/bin/bash

## Related
- [[archive-moc]]
- [[setup-git-environment-with-github]]
- [[Server basic commands]]
- [[git]]
