---
layout:     post
title:      Tensorflow Day 4
subtitle:   "Iris Classification"
date:       2018/10/12
author:     Duniang
header-img: "img/post-bg-2015.jpg"
tags:
    - Tensorflow
---
# Training
Training is the stage of machine learning when the model is gradually optimized, or the model learns the dataset. The goal is to learn enough about the structure of the training dataset to make predictions about unseen data. If you learn too much about the training dataset, then the predictions only work for the data it has seen and will not be generalizable. This problem is called overfitting—it's like memorizing the answers instead of understanding how to solve a problem.

The Iris classification problem is an example of supervised machine learning: the model is trained from examples that contain labels. In unsupervised machine learning, the examples don't contain labels. Instead, the model typically finds patterns among the features.
# ML at production scale
- [ ] Estimator guide()
- [ ] TF-Hub()
- census data 人口普查数据
- marital status 婚姻状况
- occupation 职业
## 第一个例子就是借助人口普查数据，包括年龄，教育，婚姻状况，职业特征，预测这个人是否年薪过5w美元(annual income of over 50,000 dollars)
- logistic regression model
- [tensorflow model repo](https://github.com/tensorflow/models/)
- [wide and deep model](https://github.com/tensorflow/models/tree/master/official/wide_deep/)
# 叹号表示交互式模式下执行命令，非命令行终端执行

```
! pip install  -q requests
! git clone --detpth 1 https://github.com/tensorflow/models
! head -n5 {tfe_virables}
! python -m official.wide_deep.census_main --help
```

## 构造自己的数据集时不懂的方法：
- if shuffle:
    
```
ds = ds.shuffle(10000)
ds = ds.batch(batch_size).repeat(num_epochs)
```
# 使用TensorFlow official model 
- https://github.com/tensorflow/models/tree/master/official#running-the-models
- [clone models to local path]

```
git config --global http.sslVerify false
git clone https://github.com/tensorflow/models.git
```
- windows 平台将models添加到python路径下
- 控制面板-...-系统环境变量-添加PYTHONPATH
# [Confusion matrix](https://www.tensorflow.org/hub/tutorials/text_classification_with_tf_hub)
可以画出热点图，区分错误分类的占比图


