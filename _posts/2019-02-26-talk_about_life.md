---
layout:     post
title:      数学与生活--0.99循环等于1吗？
subtitle:   生活和数学一样，总是充满诗意和意外。比如，你以为我要举一个例子。
date:       2019-02-26
author:     Yang xuemeng
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - 随笔
    - 数学理论
---

## 前言

每个人都带着面具生活，面具下的我们都是孤独的，都是无法吟唱的。因此，我会选择在深夜去研究一个数学问题：0.99循环等于1吗？

### 猜想

我一直觉得自己猜问题的能力很强，或者说推测的运气很好。直到姣仔跟我说女生的第六感才比较好后，我便习惯性的将选择权交给了她，导致现在猜测能力一般般了。不过若是基于推理的话，就不是猜测了，我来证明一下0.99循环=1好了！

### 证明过程

step 1、首先要知道一些基本知识：
```
A）有理数的全体分割可以构成实数集合。
B）实数是完备的。
```

step 2、对全体有理数进行分割，按照2个界分别作2种分割。为了方便描述，我们记0.99循环为a吧。
一种是以a为界，得到分割的2个集合：A和B。A={x|x属于Q，x<a}，B={x|x属于Q，x>=a}.
另一种是以1为界，得到C和D。C={x|x属于Q，x<1},D={x|x属于Q，x>=1}.
那么此时只要证明这2个分割是同一种分割，即可以证明a=1。也即只要证明集合A=C就行了。

step 3、对于任意数字t属于A，则t<a,可以推出t<1,那么t就是C中元素。则A属于C。对于任意数字t属于C，则t<1,令t=p/q(有理数可以用两个整数相除表示), 则有p/q<1,那么1-t = 1-p/q = (q-p)/q，p和q都是整数，所以1-t >= 1/q. 又一定存在一个整数n，使得10的n次方即10^n>q. 那么1/(10^n) < 1/q.  所以1-t>1/(10^n),此时可得 t<1-1/(10^n). 又1-1/(10^n)=0.99999（n个9）< 0.9999循环(无数的9)，所以t<a.因此t是A中的元素，即C属于A。

step 4、A属于C，C属于A，你中有我，我中有你。我就是你，你就是我，A=C。两个分割等价，那么a=1, 即0.999循环=1.

## 后记

证明这个问题已经是凌晨00:26了，睡觉。。。数学还是比生活简单一点啊。。。







