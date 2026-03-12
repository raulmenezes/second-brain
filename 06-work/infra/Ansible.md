---
tags:
  - area/devops
  - area/knowledge
  - topic/ansible
  - topic/aws
  - topic/kubernetes
  - topic/monitoring
  - topic/networking
  - topic/snippets
---


Roles are special kind of Playbook that are fully self-contained with:
tasks, variables, configurations templates and other supporting files

python3 -m venv infra
source infra/bin/activate

Logicalglue1!@
Gee9Aesh
Abu*M(o7
app_cwb: ung6mooM0faiQu3ohp0eePieg
uat key - Lie9kooQui3Roo 
Meta: 55RQGjPpLVjuKh7

**A****i****W****#13-54@****N**

ansible --version will show the configuration file used
Lie9kooQui3Roo

# Using Ansible

Ad-Hoc: ansible [group hostname] -m

ansible linux -m ping

ansible linux -a "cat /etc/os-release"

Playbook: ansible-playbook [play]

ansible-playbook my-playbook.yml

Check Mode
Dry-run for ad-hoc commands and Playbooks 
Validate Playbook runs before making state changes on target systems 

ansible linux -C -m yum -a "name=httpd state=latest"

ansible-playbook  -C my-playbook.yml 

Diff Mode

ansible linux  -C -D -m yum -a "name=httpd state=latest"

Documentation Command

ansible-doc [type] [device] [list]

ansible-doc -t connection -l

ansible -h

ansible -m homebrew -a “name=bat state=latest” localhost

ansible -m copy -a "src=master.gitconfig dest=~/.gitconfig" localhost

![[attachments/pasted-graphic-1-8.png]]

Task
Action + Parameters

![[attachments/pasted-graphic-17.png]]

![[attachments/pasted-graphic-11-3.png]]

ansible-inventory --graph --vars

Documentation

**ansible-inventory** to verify the inventory and config

Display current inventory in yaml format
ansible-inventory --list -y

Instead of using default we can pass inventory file
ansible-inventory -i [name of inventory] --list

Verify a machine is presence in the inventory

ansible [machine name] --list-hosts

![[attachments/pasted-graphic-1-9.png]]

Configuring Ansible

![[attachments/pasted-graphic-2-8.png]]

Privilege Escalation:

ansible-config dump --only-changed

Roles:

![[attachments/pasted-graphic-3-6.png]]

![[attachments/pasted-graphic-4-6.png]]

ansible -m setup localhost
a way in gathering facts

Playbook
Play
Task

---
    - name: ilovenano (play)
      hosts: centos
      tasks:
        - name:
          apt:
            name:
            state:

## Related
- [[setup-prometheus-monitoring-on-kubernetes-using-helm-and-prometheus]]
- [[dns]]
- [[elasticache]]
