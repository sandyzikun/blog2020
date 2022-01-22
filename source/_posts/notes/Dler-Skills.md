---
title: 浅谈深度学习技能栈
date: 2019-06-13 08:36:36
tags:
- Notes(代码笔记)
mathjax: true
---

(文章参考 https://hongbomin.com/2017/02/17/deep-learner/ ，感谢**洪柏敏**dalao的指点)

借用一下参考文章的开头：
> 深度学习，自2012年以来，一年比一年火。相比80年代的人工智能热，这一次，基于深度学习的各种智能服务确实带来了可见的惊喜。
> 深度学习在图像领域的各层面都取得了骄人的成绩，包括分割、识别等高级任务，以及去噪、二值化、超分辨率等低级任务。
> 在语音以及自然语言处理等方面也在快速发展。

是的没错，这个领域有着不可估量的发展空间与前途，在未来有着各种各样的应用。

所以我们今天来谈一谈深度学习所需要掌握的各项技能，先从最基本的谈起：

## 基础设施

### 计算机语言

* Python https://www.python.org/
* R https://www.r-project.org/
* Anaconda (一种科学计算用Python发行版，自带R的集成开发环境RStudio和Python机器学习需要用到的诸多模块如NumPy) https://www.anaconda.com/

### 朴素机器学习框架 (based on Python)

* NumPy (Python数值代数模块) https://www.numpy.org/
  * 中文文档 https://www.numpy.org.cn/
* SciPy (Python科学计算模块) https://www.scipy.org/
* SymPy (Python符号计算模块) https://www.sympy.org/zh/
* Pandas (Python数据存储模块) http://pandas.pydata.org/
  * 中文文档 https://www.pypandas.cn/
* Matplotlib (Python数据可视化模块) https://matplotlib.org/
  * 中文文档 https://www.matplotlib.org.cn/

### 深度学习框架 (based on Python)

* Theano https://deeplearning.net/software/theano/
* TensorFlow https://tensorflow.org/
  * 中文站点 https://tensorflow.google.cn/
  * 中文社区 http://www.tensorfly.cn/
  * 试用Playground https://playground.tensorflow.org/
* CNTK https://docs.microsoft.com/en-us/cognitive-toolkit/
* Keras https://keras.io/zh/

## 数学基础

* 微积分/高等数学/数学分析
* 线性代数
* 统计学基础, 包括以下三者:
  * 概率论
  * 信息论
  * 数理统计
* 数值代数(主要指的是数值计算方法与数学建模方法等)

## 朴素机器学习方法

### 常用框架

* Scikit-Learn https://scikit-learn.org/stable/

### 基础算法

* 分类 Classification
  * 逻辑回归 Logistic Regression (没错它一个分类算法名字叫回归)
* 回归 Regression
  * 线性回归算法
    * 基于 最小二乘法/最小平方法 的线性回归 Linear Regression
    * 岭回归/脊回归 Ridge Regression
    * 套索回归 Lasso Regression
    * 弹性网络回归 Elastic-Net Regression
  * 贝叶斯回归 Bayesian Regression
* 分类&回归(可以同时用于两者的算法)
  * 判别分析 Discriminant Analysis
    * 线性判别分析/Fisher判别分析 Linear Discriminant Analysis (LDA)
    * 二次判别分析 Quadratic Discriminant Analysis (QDA)
  * K最近邻 K-Nearest Neighbor (kNN)
  * 高斯过程 Gaussian Processes (GP)
  * 朴素贝叶斯 Naive Bayes (NB)
  * 决策树 Decision Trees (DT/CART)
  * 支持矢量机 Support Vector Machines (SVM)

### 高阶算法

* 聚类 Clustering
  * K均值 K-Means
  * 均值漂移 Mean Shift
  * DBSCAN
* 降维 Dimensionality Reduction
  * 主成分分析 Principal Component Analysis (PCA)

***

接下来要迈入深度学习的世界了

## 几大深度学习课题

* 计算机视觉 Computer Vision
* 自然语言处理 Natural Language Processing (NLP)
* 语音识别 Voice Recognition

以及更多...

## 经典模型

### 卷积神经网络 Convolutional Neural Networks (CNN)

* LeNet-5 http://yann.lecun.com/exdb/lenet/a35.html
* VGG-Net (Visual Geometry Group Network) https://baike.baidu.com/item/VGG%20模型
* GoogLeNet https://baike.baidu.com/item/GoogLeNet

### 循环神经网络 Recurrent Neural Network (RNN)

* SimpleRNN
* LSTM (Long Short-Term Memory, 长短期记忆网络) https://baike.baidu.com/item/LSTM
* GRU

### 目标检测

* R-CNN
* YOLO (You Only Look Once)

### 生成式深度学习

* AE (Auto Encoder, 自动编码机)
* RBM (Restricted Boltzmann Machine, 受限玻尔兹曼机)
* DBN (Deep Belief Network, 深度信念网络)
