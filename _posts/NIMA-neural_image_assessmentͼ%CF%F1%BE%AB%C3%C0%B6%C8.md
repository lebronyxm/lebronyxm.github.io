---
layout:     post
title:      NIMA-Neural Image Assessment图像精美度
subtitle:   评价图像的美观程度
date:       2018-09-26
author:     Yang xuemeng
header-img: img/post-bg-universe.jpg
catalog: true
tags:
    - 图像
    - 论文笔记
---

## 前言

最近要做一些和图像精美度相关的工作，看了一篇Google的paper：Neural Image Assessment。其实年前就看过了。。。最近参考了一些别人复现的代码，自己也复现了一下，后续会用到工作项目中。

## 正文

俗语云：一看脸蛋二看腰，三维曲线硬指标。 又云：美不美，先看腿，骚不骚，再看腰。。。等等，好像跑偏了。。。But the point is: 我们对一个事物美丑与否的评价是基于一些指标的，或是主管，或是可观，都会以一些feature为基准数据。图像的精美度，可以分为两大类，technical和aesthetic。

