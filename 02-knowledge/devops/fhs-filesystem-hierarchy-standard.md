---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
---

# FHS filesystem hierarchy standard

Linux foundation 
**bin**
basic binaries for applications like ls, cat

**sbin**
system binaries that a system administrator would use
(Standard user wouldn’t have permission)

single user mode - boots you in a root user to allow you to do system repairs

**boot**
everything your system OS needs to boot

**dev**
Area where drivers will access
Hardware devices:
disk - sda (partition on the disk would be sda1)
webcam

**etc -** edit to configure
Configurations are stored, things system-wide such as apt

**lib**
files that applications can use to perform functions
Required by the binaries in bin and sbin

**media /mnt**
Mounted drives 
e.g. Floppy disk, USB stick, external hard drive
Now automatically mounted to media
/mnt if you want to do it manually

**var**
directories that are expected to grow in size
e.g. 
logs (for system and apps)
crash
tmp

**proc** 
information about system processes and resources

**root**
root users home folder
Need root permission to store files here

**run**
files

**lib**
files

**lib**
files

## Related
- [[devops-moc]]
- [[elastic-file-system-efs]]
- [[ebs-elastic-block-storage]]
- [[elastic-load-balancers]]
