---
title: problems with conda
tags: [Anaconda, Issue]
categories:
  - 指南
date: 2020-01-04 17:14:12
---

Summaries for the issues happened with conda

## conda activate not working after conda update to latest version

if using ZSH, follow below steps:

  * open up your .zshrc file usually in your home directory. if you use vim enter vim ~/.zshrc
  * remove export PATH=~/anaconda3/bin:$PATH from your .zshrc file
  * add this line . /Users/ROOT_USER_HERE/anaconda3/etc/profile.d/conda.sh to your .zshrc file