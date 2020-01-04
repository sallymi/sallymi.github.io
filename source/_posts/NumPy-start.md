---
title: NumPy start
tags: [python, numpy]
categories:
  - 指南
date: 2020-01-04 17:17:33
---

从零开始学习NumPy

## 介绍

### 什么是NumPy

作为初级学习者，没有什么Python经验，一开始就来学习NumPy，不知道中间会遇到什么拦路虎，走着看吧，需要补什么就抓过来啃啃。

首先，发音。“南派”记住了，别读成“努屁”了。好，现在开始记录什么是NumPy。根据官方法典的记载，NumPy是Python中科学计算的基础软件包。ok，少不了要补一些Python的语法知识。还有一个要点，NumPy是一个软件包。软件包按我的理解就是把一大堆对象、函数、API什么都统统封装在一起，用一些简单的调用就能完成一个复杂的事情。那么看看NumPy里都封装了些什么。

  * 数组
  * 对数组的操作函数

基本上就是这两个东东吧。“NumPy提供多维数组对象，多种派生对象（如掩码数组、矩阵），以及用于快速操作数组的函数及API“。包括：

  * 数学
  * 逻辑
  * 数组形状变换
  * 排序
  * 选择
  * I/O
  * 离散傅立叶变换
  * 基本线性代数
  * 基本统计运算
  * 随机模拟

先暂且这么罗列着吧，究竟是什么东西，慢慢深入好了。所以“科学计算”大白话就是从高中到大学你所学到的代数、高数、等等跟数学有关的东西。有没有例外？不知道。

### 和Python原生数组array的区别

说到NumPy的核心，就是数组。那NumPy来自于Python，和Python的原生数组有什么联系和区别呢？带着这个问题，我们先看看NumPy的数组具体是啥。官方来源
“NumPy封装了python原生的同数据类型的n维数组，为了保证其性能优良，其中有许多操作都是代码在本地进行编译后执行的”。抓要点，1，
NumPy对Python原生数组进行了封装，并且改良和加固了n维数组的封装。2，n维数组是同数据类型的。3，改良了性能。

具体展开说一下区别：

  * NumPy数组在创建时具有固定的大小，与Python的原生数组对象（可以动态增长）不同。 更改ndarray的大小将创建一个新数组并删除原来的数组。
  * NumPy数组中的元素都需要具有相同的数据类型，因此在内存中的大小相同。 例外情况：Python的原生数组里包含了NumPy的对象的时候，这种情况下就允许不同大小元素的数组。
  * NumPy数组有助于对大量数据进行高级数学和其他类型的操作。 通常，这些操作的执行效率更高，比使用Python原生数组的代码更少。
  * 越来越多的基于Python的科学和数学软件包使用NumPy数组; 虽然这些工具通常都支持Python的原生数组作为参数，但它们在处理之前会还是会将输入的数组转换为NumPy的数组，而且也通常输出为NumPy数组。 换句话说，为了高效地使用当今科学/数学基于Python的工具（大部分的科学计算工具），你只知道如何使用Python的原生数组类型是不够的 - 还需要知道如何使用NumPy数组。

划重点：

  1. NumPy数组固定大小
  2. NumPy数组的元素数据类型相同
  3. NumPy数组很重要！！！

## NumPy安装

工欲善其事必先利其器。看一下想使用NumPy要做些什么事情。  
推荐方案：在操作系统上安装NumPy  
重点说Pip和Mac怎么安装

### Pip

先决条件，在机器上安装好Python和Pip  
接下来这行命令就是安装NumPy

> python -m pip install –user numpy scipy matplotlib ipython jupyter pandas
> sympy nose

### Homebrew

> brew tap homebrew/science && brew install python numpy scipy matplotlib

## 快速入门

例1，3D空间的点坐标[1,2,1]。rank = 1, axis = 3。ndim = 1, shape=(3,)  
解读：axis是纬度或者轴，3D是三维的，所以轴的长度为3。rank是轴的数目，它只有一个轴，所以轴的数目为1。

例2，n行m列的矩阵，ndim=n, shape=（n,m），size=n*m

例3，[[ 0, 1, 2, 3, 4],  
[ 5, 6, 7, 8, 9],  
[10, 11, 12, 13, 14]]，  
ndim = 2, shape = (3, 5)

NumPy的数组类为ndarray，别名array。在这里要区别numpy.array和Python类库的array.array是不一样的，array.array只处理一维数组。

### 创建

> import numpy as np  
> a = np.array([2,3,4])  
> b = np.array([(1.5,2,3), (4,5,6)])  
> c = np.array( [ [1,2], [3,4] ], dtype=complex )  
> np.zeros( (3,4) )  
> np.ones( (2,3,4), dtype=np.int16 )  
> np.empty( (2,3) )  
> np.arange( 10, 30, 5 )  
> np.linspace( 0, 2, 9 )

详解  
np.array: 将序列的序列转换成二维数组，将序列的序列的序列转换成三维数组，输入的是数列  
np.zeros: 创建一个由0组成的数组,输入的是shape  
np.ones：创建一个由1数组的数组，输入的是shape  
np.empty：内容是随机的并且取决于存储器的状态，输入的是shape  
np.arange：该函数返回数组而不是列表，输入的是起始值，终止值，步长  
np.linspace：和arrange函数类似，但它接收我们想要的元素数量而不是步长作为参数

### 打印

> print(a)

如果数组太大而无法打印，NumPy将自动跳过数组的中心部分并仅打印角点  
要禁用此行为并强制NumPy打印整个数组，你可以使用 set_printoptions 更改打印选项

### 数组操作

数组上的算术运算符使用元素级别。计算结果会产生一个新的数组，并在每个元素上进行计算并填充到新的数组上。