---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
  - topic/monitoring
  - topic/networking
  - topic/snippets
---

# Basic commands for servers

sudo apt update

sudo apt list --upgradable

Start system upgrade process
sudo apt upgrade

Remove all locally downloaded deb packages:

sudo apt autoremove
sudo apt clean

Create New Account
sudo adduser [name]

Grant this new user account with administrative privileges

sudo usermod -a -G sudo ubuntu_user

s -u app-multiclass psql 

view /etc/nginx/sites-enabled/default 

collection of tools for system monitoring, (disk, cpu, memory), sysstat let you collect some metrics and use historical data

network statistics, you can see what is your traffic, daily/weekly/monthly/etc...

tool for I/O monitoring, you can easily check which process generate high disk usage

network usage monitor

bandwidth monitor

top on steroids 

system statistics/graphs, it has a lot of plugins ready to use (disk, memory, cpu, uptime, apache traffic, nginx traffic, memcached, mysql), if something is missing you can write your own script and monitor whatever you need.

- sysstat
- vnstat
- iotop
- iftop
- bwm-ng
- htop
- munin

apt-get install sysstat vnstat iotop iftop bwm-ng htop munin

## Related
- [[devops-moc]]
- [[kops-commands]]
- [[aws-command-line]]
- [[useful-commands]]
