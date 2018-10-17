---
layout:     post
title:      Tensorflow Day 2
subtitle:   ""
date:       2018/10/08
author:     Duniang
header-img: "img/post-bg-2015.jpg"
tags:
    - Tensorflow
---
- [tensorflow 中文指南](https://www.tensorflow.org/programmers_guide/eager?hl=zh-cn)
- [tensorflow 英文指南](https://www.tensorflow.org/tutorials/eager/eager_basics)
# regression
predict the output of a continuous value rather than a discrete label like a classification problem
# numpy.argsort()

```
>>> import numpy
>>> help(numpy.argsort)
Help on function argsort in module numpy.core.fromnumeric:
argsort(a, axis=-1, kind='quicksort', order=None)
    Returns the indices that would sort an array.
    
    Perform an indirect sort along the given axis using the algorithm specified
    by the `kind` keyword. It returns an array of indices of the same shape as
    `a` that index data along the given axis in sorted order.
从中可以看出argsort函数返回的是数组值从小到大的索引值
Examples
    --------
    One dimensional array:一维数组
    
    >>> x = np.array([3, 1, 2])
    >>> np.argsort(x)
    array([1, 2, 0])
    
    Two-dimensional array:二维数组
    
    >>> x = np.array([[0, 3], [2, 2]])
    >>> x
    array([[0, 3],
           [2, 2]])
    
    >>> np.argsort(x, axis=0) #按列排序
    array([[0, 1],
           [1, 0]])
    
    >>> np.argsort(x, axis=1) #按行排序
    array([[0, 1],
           [0, 1]])
#######################################
例1：
>>> x = np.array([3, 1, 2])
>>> np.argsort(x) #按升序排列
array([1, 2, 0])
>>> np.argsort(-x) #按降序排列
array([0, 2, 1])
>>> x[np.argsort(x)] #通过索引值排序后的数组
array([1, 2, 3])
>>> x[np.argsort(-x)]
array([3, 2, 1])
另一种方式实现按降序排序：
>>> a = x[np.argsort(x)]
>>> a
array([1, 2, 3])
>>> a[::-1]
array([3, 2, 1])
```
# normalize features
## 标准差（Standard Deviation） ，中文环境中又常称均方差，是离均差平方的算术平均数的平方根，用σ表示。标准差是方差的算术平方根。标准差能反映一个数据集的离散程度。平均数相同的两组数据，标准差未必相同。
⒈方差s^2=[（x1-x）^2+（x2-x）^2+......（xn-x）^2]/（n）（x为平均数）
⒉标准差=方差的算术平方根errorbar。在实验中单次测量总是难免会产生误差，为此我们经常测量多次，然后用测量值的平均值表示测量的量，并用误差条来表征数据的分布，其中误差条的高度为±标准误。这里即标准差。
简要步骤：
- 构建模型，build  model
- 输入数据多个特征进行归一化处理，normalize, 减少复杂度
- 训练模型，fit model
- 验证模型，evaluate model
- 预测模型，predict model
- 如果数据比较少，不要构建太多层，以及减少隐藏单元，防止过拟合
# IMDB 数据集说明
IMDB Movie reviews sentiment classification
Dataset of 25,000 movies reviews from IMDB, labeled by sentiment (positive/negative). Reviews have been preprocessed, and each review is encoded as a sequence of word indexes (integers). For convenience, words are indexed by overall frequency in the dataset, so that for instance the integer "3" encodes the 3rd most frequent word in the data. This allows for quick filtering operations such as: "only consider the top 10,000 most common words, but eliminate the top 20 most common words".

As a convention, "0" does not stand for a specific word, but instead is used to encode any unknown word.
# history这个类的属性
# plt.plot()返回值的属性
# 解决过拟合和欠拟合策略
L1, L2, dropout

```
To recap: here the most common ways to prevent overfitting in neural networks:

Get more training data.
Reduce the capacity of the network.
Add weight regularization.
Add dropout.
And two important approaches not covered in this guide are data-augmentation and batch normalization.
```

# create source dataset using apply transformations
Apply transformations
Use the transformations functions like [map](https://www.tensorflow.org/api_docs/python/tf/data/Dataset#map), [batch](https://www.tensorflow.org/api_docs/python/tf/data/Dataset#batch), [shuffle] etc. to apply transformations to the records of the dataset. See the API documentation for tf.data.Dataset for details.
# [eager execution](https://www.tensorflow.org/programmers_guide/eager?hl=zh-cn)