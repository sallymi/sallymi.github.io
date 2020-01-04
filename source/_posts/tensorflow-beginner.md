---
title: tensorflow beginner
tags: [tensorflow, nltk]
categories:
  - 指南
date: 2020-01-04 17:15:21
---

Start with TensorFlow

## install Tensorflow with Anaconda

create tensorflow environment

> $ conda create -n tensorflow pip python=2.7 # or python=3.3, etc.

Switch the environment

> $ source activate tensorflow

Issue a command of the following format to install TensorFlow inside your
conda environment:

> (targetDirectory)$ pip install –ignore-installed –upgrade TF_PYTHON_URL
>
> (targetDirectory)$ pip install –ignore-installed –upgrade

<https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-1.8.0-py2-none-
any.whl>

## validate the installation

> $ python
>
> import tensorflow as tf
>
> hello = tf.constant(‘Hello, TensorFlow!’)
>
> sess = tf.Session()
>
> print(sess.run(hello))

The output should be:

> Hello, TensorFlow!

## install nltk error

Resource punkt not found.

Please use the NLTK Downloader to obtain the resource:

import nltk

nltk.download(‘punkt’)

> python
>
> import nltk
>
> nltk.download