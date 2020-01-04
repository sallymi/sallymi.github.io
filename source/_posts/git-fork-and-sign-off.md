---
title: git fork and sign-off
tags: [github]
categories:
  - 指南
date: 2020-01-04 17:16:28
---

Github项目的fork和sign off操作

有些官方的项目是需要开发者fork到自己的仓库的。本文就是介绍一下整个流程。假设小A是一位开发者，它要在公开的Github仓库继续开发一些新feature。

## fork

小A首先要fork官方的Github仓库。点击Fork按钮，选择fork到自己的那个仓库里。

## clone到本地

> git clone -b some-feature  
> git add .  
> git commit -am “initial”

## push

小A将feature分支推送到自己的GitHub仓库

> git push origin some-branch

## pull request

小A来到他fork的官方仓库，点击项目的new pull request。创建一个pull request。设置好源仓库和源分支（自己的仓库和some-
branch），目标仓库和目标分支（官方仓库和分支）。

提供一个pull request的标题和间接

## sign off

有些官方项目是需要sign off的。

> git commit -s  
> 如果忘记sign off了，可以为上一个commit追加sign off  
> git commit –amend -s  
> git push -f