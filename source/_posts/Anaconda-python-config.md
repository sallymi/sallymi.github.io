---
title: Anaconda python config
tags: []
categories:
  - 指南
date: 2020-01-04 17:13:10
---

We can use Anaconda to config Python environment which is using for Deep
learning. We introduce some general configuration and setups for Anaconda and
Python in MacOS.

## Conda

### verify conda installation

> $ conda –version

> conda 4.5.4

### update conda to latest version

> $ conda update conda

### create or activate environment

> $ conda create –name snowflake biopython

this command will create a new environment for biopython library, the location
is /envs/snowflakes. –name can be replaces by -n, which has the same
functionality. Can check `conda -h` for help.

> $ conda create -n bunnies python=3 Astroid Babel

This command create a second environment to include Astroid and Babel lib
based on python 3, the name is bunnies, which include in /envs/bunnies.

> $ source activate snowflakes

This command activate the environment

> $ conda info -e

The current environment has a * at the beginning of location

> $ source activate base

switch to another environment

> $ source deactivate

switch to root folder of the system

> $ conda create -n flowers –clone snowflakes

copy the environment snowflakes and name as flowers

> $ conda remove -n flowers –all

remove the environment flowers

### manage Python with conda

> $ conda search –full –name python

seach for all libs with “python”

> $ python –version

check for the versions in the environment  
note: if you have alias in ~/.zshrc, you should remove it  
and make sure to use `source activate` to switch to the environment before
using python command

> $ conda list

check which python version or other applications installed in this environment

> $ conda install –name bunnies beautifulsoup4

This command will install a new lib to environment bunnies. Make sure you
specify the environment name with –name, or else the lib will be installed to
current environment.

> $ conda search beautifulsoup4

To check whether beautifulsoup4 can be installed by conda.

Note: if the lib cannot be installed by conda, you can search from
Anaconda.org

> $ conda install –channel <https://conda.anaconda.org/pandas> bottleneck

Note: if the lib cannot be installed by conda or from Anaconda.org, you can
use `pip install`, make sure to switch to then environment before install lib.

### remove

> $ conda remove -n bunnies iopro

This command will remove iopro lib from bunnies environment

> $ conda remove -n snakes –all

This command will remove snakes environment