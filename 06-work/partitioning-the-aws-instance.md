---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/networking
---

# Partitioning the AWS instance

Update machine and restart machine:   sudo apt update

sudo apt upgrade
sudo systemctl reboot

Check to see we have 2 disks: xvda, xvdb
 

sudo lsblk

cd /
sudo mv /home /home-backup

sudo mkdir /home

create filesystem as this currently does not have filesystem

sudo mkfs -t ext4 /dev/xvdb

sudo lsblk -f
sudo mount /dev/xvdb /home

Check /home is on xvdb sudo lsblk

sudo rsync -apXS /home-backup/ /home/

Find out the id for the disk that is mounted

sudo blkid

Copy the UUID to the stab file:

sudo vi /etc/fstab

Add the UUID for the mounted disk e.g. UUID=5bf9d0ec-7da7-4f22-b81e-e90994875604   /home        ext4   defaults,relatime        0 2

Check to see if unmouting the /home found automatically mounts it back:  cd /
ls home
sudo umount home
ls home  sudo mount -a  ls home

## Related
- [[devops-moc]]
- [[deploy-new-instance]]
- [[baseline-infrastructure]]
- [[route53-routing-policies-aws]]
