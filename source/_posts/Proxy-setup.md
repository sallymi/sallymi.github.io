---
title: Proxy setup
tags: [Proxy, github]
categories:
  - 指南
date: 2020-01-04 17:11:34
---

The purpose of this blog is to sort out the setup of proxy in MacOS

## ShadowSocks

### using single container

> docker pull oddrationale/docker-shadowsocks
>
> docker run -d -p 2022:2022 oddrationale/docker-shadowsocks -s 0.0.0.0 -p
> 2022 -k admin -m aes-256-cfb

### kubenetes

  * deploy with a simple image
  * execute below command

> kubectl exec -it  /bin/bash
>
> apt-get update && apt-get install -y python-pip libsodium18
>
> pip install shadowsocks==2.8.2

  * execute below command

> ssserver -p 1982 -k admin -m aes-256-cfb –user nobody -d start

  * expose port

> kubectl expose deployment/shadowsocks –type=NodePort –port=1982
> –name=shadowsocks –target-port=1982

### shadowsocks client config

open server preferences -> \+ -> Address: [public ip]:port -> aes-256-cfb ->
Password: admin

set to use Auto proxy mode

## sshpass

> sshpass -p [password] ssh -t -t -o StrictHostKeychecking=no -D [port]
> [hostname]

## CMD

Http proxy for current command window

`$ export http_proxy=http://127.0.0.1:8118`

`$ export https_proxy=http://127.0.0.1:8118`

Socks5 proxy for current command window

`$ export http_proxy=socks5://127.0.0.1:8118`

`$ export https_proxy=socks5://127.0.0.1:8118`

for wget and curl to use socks5

`$ export ALL_PROXY=socks5://127.0.0.1:8118`

Cancel the proxy

`$ unset http_proxy`

`$ unset http_proxy`

`$ unset ALL_PROXY`

Set permanently in ~/.zshrc

> alias proxy_https = “export https_proxy=socks5://127.0.0.1:8118”

## Github

> git config –global http.proxy <http://127.0.0.1:8118>
>
> git config –global https.proxy <http://127.0.0.1:8118>

or socks:

> git config –global http.proxy socks5://127.0.0.1:1080
>
> git config –global https.proxy socks5://127.0.0.1:1080

cancel:

> git config –global –unset http.proxy
>
> git config –global –unset https.proxy

## IPsec/L2TP on CentOS

yum install wget  
wget <https://git.io/vpnsetup-centos> -O vpnsetup.sh && sudo sh vpnsetup.sh
