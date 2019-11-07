---
layout:     post
title:      ctr模型和相关性模型里的数据增强(样本采样、加权、构造)
subtitle:   从线上系统探探正负样本对模型的影响
date:       2019-11-07
author:     Yang xuemeng
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - 模型算法
    - 数学理论
---

## 前言

每个人都带着面具生活，面具下的我们都是孤独的，都是无法吟唱的。因此，我会选择在深夜去研究一个数学问题：0.99循环等于1吗？

### 猜想

我一直觉得自己猜问题的能力很强，或者说推测的运气很好。直到姣仔跟我说女生的第六感才比较好后，我便习惯性的将选择权交给了她，导致现在猜测能力一般般了。不过若是基于推理的话，就不是猜测了，我来证明一下0.99循环=1好了！

### 证明过程

step 1、首先要知道一些基本知识：