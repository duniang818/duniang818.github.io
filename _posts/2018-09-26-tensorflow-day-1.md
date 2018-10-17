---
layout:     post
title:      Tensorflow Day 1
subtitle:   ""
date:       2018/09/26
author:     Duniang
header-img: "img/post-bg-2015.jpg"
tags:
    - Tensorflow
---
# 对tensorflow的生态系统有个整体的认识
意义：能够明白TensorFlow能做哪些事情，你可以对哪些部分感兴趣并对其深入研究，又或有哪些是前人已经有的学习成果
(https://www.tensorflow.org/ecosystem/)
- tensorflow hub,TensorFlow Hub 是一个库，有助于发布、发现和使用机器学习模型中可重复使用的部分。
- TensorFlow Extended (TFX)
TensorFlow Extended (TFX) 是一个端到端的机器学习平台，涵盖了数据获取、训练和生产级服务等功能。
- TensorFlow Probability
TensorFlow Probability 是一个用于概率推理和统计分析的库。
- 模型
使用 TensorFlow 构建的官方模型和示例。在 GITHUB 上查看
- Magenta
Magenta 是一个研究项目，旨在探索机器学习在艺术和音乐创作过程中的作用。
- TensorFlow.js
采用 WebGL 加速技术且基于浏览器的 JavaScript 库，用于训练和部署机器学习模型。
- TensorFlow Lite
TensorFlow 针对移动设备和嵌入式设备提供的精简解决方案。
- Swift for TensorFlow
我们认为，机器学习非常重要，理应获得一流的语言和编译器支持，Swift for TensorFlow 正是在这一信念的基础上开发出来的。
# develop(https://www.tensorflow.org/tutorials/keras/basic_classification)
# google 机器学习速成课程(https://developers.google.com/machine-learning/crash-course/)
# 基本使用 
- 使用 TensorFlow, 你必须明白 TensorFlow:
- 使用图 (graph) 来表示计算任务.
- 在被称之为 会话 (Session) 的上下文 (context) 中执行图.
- 使用 tensor 表示数据.
- 通过 变量 (Variable) 维护状态.
- 使用 feed 和 fetch 可以为任意的操作(arbitrary operation) 赋值或者从其中获取数据.
# [tensor rank, shape, type](http://www.tensorfly.cn/tfdoc/resources/dims_types.html)
每一个张量有维数，有阶数，而这两者组合起来又构成了一个张量的形状。
你可以认为一个二阶张量就是我们平常所说的矩阵，一阶张量可以认为是一个向量.对于一个二阶张量你可以用语句t[i, j]来访问其中的任何元素.而对于三阶张量你可以用't[i, j, k]'来访问其中的任何元素.
比如：
- s = 483，纯量 (只有大小)，0阶
- v = [1.1, 2.2, 3.3]，向量(大小和方向)，1阶
- m = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]，矩阵(数据表)，2阶
- t = [[[2], [4], [6]], [[8], [10], [12]], [[14], [16], [18]]]，3阶张量 (数据立体)，3阶
- n阶 (自己想想看)
- type:是数据的类型
- feed 使用一个 tensor 值临时替换一个操作的输出结果. 
# 关于更多的pycharm-python-file template(https://www.jetbrains.com/help/pycharm/using-file-and-code-templates.html)
