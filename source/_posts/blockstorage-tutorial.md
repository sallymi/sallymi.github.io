---
title: blockstorage-tutorial
tags: [blockstorage]
categories:
  - 指南
date: 2020-01-04 17:19:40
---

在Centor7上连接block storage, 并且设置backup  

## 创建block storage

blockstorage只能从IaaS平台上购买，可以根据自己的需求购买。

## 连接

### 添加Authorize Host

按照UI的指示可以为block storage添加Authorize Host。  
注意，只能添加在同一个DC的host

### Mounting block storage volume

我们使用的是CentOS7

  1. yum install iscsi-initiator-utils device-mapper-multipath
  2. modprobe dm-multipath  
systemctl start multipathd  
systemctl enable multipathd

  3. vi /etc/multipath.conf  
multipath -ll

  4. vi /etc/iscsi/initiatorname.iscsi  
编辑 InitiatorName=， 其中InitiatorName是IQN

  5. vi /etc/iscsi/iscsid.conf  
编辑，value都可以从authorized Host得到  
node.session.auth.authmethod = CHAP  
node.session.auth.username =  
node.session.auth.password =  
discovery.sendtargets.auth.authmethod = CHAP  
discovery.sendtargets.auth.username =  
discovery.sendtargets.auth.password =

  6. systemctl enable iscsi  
systemctl enable iscsid  
systemctl start iscsi  
systemctl start iscsid

  7. iscsiadm -m discovery -t sendtargets -p   
其中ip-value-from-SL-Portal指的是block storage的IP，不要错误用了authorized host的ip  
iscsiadm -m node -L automatic

  8. verify  
iscsiadm -m session  
multipath -l  
fdisk -l | grep /dev/mapper

### Creating a file system by fdisk

  1. 得到disk name  
fdisk -l | grep /dev/mapper

  2. 生成 partition  
fdisk /dev/mapper/XXX

  3. 生成file system在新的partition上  
fdisk –l /dev/mapper/XXX  
mkfs.ext3 /dev/mapper/XXXlp1  
在执行格式化命令mkfs.ext3的时候，有时候会出现以下错误：  
Could not stat /dev/mapper/3600a0980383030516e2b464b47755147p1 — No such file
or directory

The device apparently does not exist; did you specify it correctly?  
我们用下面的方法解决：  
首先rpm -qa | grep parted查看是否已经安装了partprobe命令  
执行partprobe

  4. mkdir /PerfDisk  
mount /dev/mapper/XXXlp1 /PerfDisk  
df -h

  5. Add the new file system to the system’s /etc/fstab file to enable automatic mounting on boot  
/etc/fstab  
增加下面一行  
/dev/mapper/XXXlp1 /PerfDisk ext3 defaults,_netdev 0 1

### Creating a file system by parted

parted  
(parted) select /dev/mapper/XXX  
(parted) print  
(parted) mklabel gpt  
(parted) mkpart  
(parted) quit  
mkfs.ext3 /dev/mapper/XXXlp1  
mkdir /PerfDisk  
mount /dev/mapper/XXXlp1 /PerfDisk  
df -h

## 错误排查

  1. 检查multipath To check whether multipath is picking up the devices, list the devices. If it’s configured correct, only two NETAPP devices show up.  
multipath -l

  2. 检查disks  
fdisk -l | grep Disk  
有两个disks有同样的identifier，并且/dev/mapper显示有同样的大小。  
如果只是现实了sd*, 而没有显示/dev/mapper，表示没有正确的set up

## snapshots space

### order snapshot space

在order snapshot 的时候，并没有选择是endurance或者performance，而是只询问了大小。Snapshot space is
directly tied to the source volume so if it’s performance it comes from
performance

### 手工snapshot

直接在portal上可以完成

### snapshot schedule

直接在portal上可以完成

## unmount

##修改cPanel的backup到blockstorage  
假设mount point为backup2  
rsync -azv /backup/* /backup2/  
登陆到WHM， Home > Backup > Backup Configuration.  
修改2处：

  1. default backup directory
  2. Enable to mount a backup drive

##Lun  
iscsiadm -m session -P 3  
multipath -ll

