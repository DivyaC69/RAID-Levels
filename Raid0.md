
## RAID 0 

**Requirement** - HDD-> 2 disks(20GB minimum each) 

```bash
lsblk 
```
Installing Package called multiple disk and device management
```bash
yum install mdadm
```
Level below indicates the Raid level
```bash
mdadm --create --verbose /dev/md0 --level=0 --raid-devices=2 /dev/sdb /dev/sdc
```
Creating an ext4 file system from disk partitions
```bash						   
mkfs.ext4 /dev/md0
```
Creating mount point
```bash
mkdir /mnt/raid0-drive
```
Mounting
```bash
mount /dev/md0 /mnt/raid0-drive
```
Displays the amount of disk space available on the filesystem
```bash
df -Th
```
