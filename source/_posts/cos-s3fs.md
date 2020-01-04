---
title: cos s3fs
tags: [cos]
categories:
  - 指南
date: 2020-01-04 17:18:42
---

s3fs命令

Applications that expect to read and write to a NFS-style filesystem can use
s3fs, which can mount a bucket as directory while preserving the native object
format for files. This allows you to interact with your cloud storage using
familiar shell commands, like ls for listing or cp to copy files, as well as
providing access to legacy applications that rely on reading and writing from
local files. For a more detailed overview, visit the project’s official
README.

本文将学习如何将一个cos的bucket mount为文件系统。

## 安装

brew cask install osxfuse  
brew install s3fs

## 配置

### 得到credential文件

可以是HMAC或者IAM API KEY

#### HMAC credential文件

从IBM Cloud中的COS instance->Service Credentials获得cos_hmac_keys。存储到一个文件中：  
格式如下：

<access_key>:<secret_key>

### 运行命令挂载

s3fs  -o url=http{s}:// –o passwd_file=<credentials_file>  
其中bucket为cos里面需要挂载的bucket。mountpoint为local file的地址（绝对地址），endpoint可以在IBM
Cloud的cos里面找到，对应为bucket所在的endpoint。credentials_file就是刚才保存的文件。  
运行后可以执行  
`df -h` 查看挂载结果

