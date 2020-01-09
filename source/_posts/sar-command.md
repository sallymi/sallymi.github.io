---
title: sar command
tags: [sar]
categories:
  - 指南
date: 2020-01-09 13:20:58
---

IBM Cloud 的 storage 有以下几种类型：
Local storage
嵌入在 disk，对虚拟机主机来说是本地存储。目前在新的 DC，都是 SSD，来提供最佳性能。

Portable SAN storage
仅仅对VSI 开放的辅助存储。创建在 flash storage cluster 上的。这种架构具备很好的弹性可以提供更大的容量。如果主机错误，使用了 San 存储的 VSI 可以自动迁移到其他的主机并重启。
如果要在 IBM 网络的任意 DC 迁移主机数据，可以考虑使用 portable storage。对数据库程序很有效，可以在 VSI 之间迁移大数据集合。
所有的备用磁盘都是 portable storage。在任何时候可以卸载并挂到其他的 VS 上。

补充的存储，例如 NFS，block storage， object storage。

我们有时候碰到问题是 IO wait 过长，我们可以用sar命令来检查
https://blog.csdn.net/danielmoore/article/details/79083180
是统计磁盘使用详情
sar -d -p -f

可以得到数值高的设备

sar -n DEV
显示网络接口信息
00:00:01        IFACE   rxpck/s   txpck/s    rxkB/s    txkB/s   rxcmp/s   txcmp/s  rxmcst/s

IFACE：LAN接口
rxpck/s：每秒钟接收的数据包
txpck/s：每秒钟发送的数据包
rxbyt/s：每秒钟接收的字节数
txbyt/s：每秒钟发送的字节数
rxcmp/s：每秒钟接收的压缩数据包
txcmp/s：每秒钟发送的压缩数据包
rxmcst/s：每秒钟接收的多播数据包