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

俗语云：一看脸蛋二看腰，三维曲线硬指标。 又云：美不美，先看腿，骚不骚，再看腰。。。等等，好像跑偏了。。。But the point is: 我们对一个事物美丑与否的评价是基于一些指标的，或是主管，或是可观，都会以一些feature为基准数据。图像的精美度，可以分为两大类，technical和aesthetic。NIMA是一个同时兼顾二者的方法。
    
NIMA方法很简单，核心是loss的改进。EMD（推土机距离EMD is defined as the minimum cost to move the mass of one distribution to another）loss function。这样从一个分类问题变成一个分布预估的问题。

```
from keras import backend as K
def EMD_loss(y_true, y_pred):
    cdf_ytrue = K.cumsum(y_true, axis=-1)
    cdf_ypred = K.cumsum(y_pred, axis=-1)
    samplewise_emd = K.sqrt(K.mean(K.square(K.abs(cdf_ytrue - cdf_ypred)), axis=-1))
    return K.mean(samplewise_emd)
```
该文的network framework也比较简单，在imagenet的预训练网络上稍作修改即可。如下图所示：
          ![framework](https://github.com/lebronyxm/lebronyxm.github.io/raw/master/img/nima-framework.png)
中间的网络可以是inception这些较大的，也可以是mobilenet这些小巧的。注意原始网络去掉最后一层后，加一个dropout，然后再接10类的FC layer。
```
base_model = keras.applications.nasnet.NASNetMobile(input_shape=input_size, include_top=False, weights=None,pooling='avg')
x = Dropout(0.75)(base_model.output)
x = Dense(10, activation='softmax')(x)
model = Model(base_model.input, x)
```
## 数据

主要是用AVA数据集训练，255000张。图不多训练起来还是比较快的。由于很多pre-trained模型的输入已resize到了224\*224，所以有人在网盘上存了224\*224的AVA数据集，大概5G左右。

