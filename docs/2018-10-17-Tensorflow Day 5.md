---
layout:     post
title:      Tensorflow Day 5
subtitle:   "Generative Model"
date:       2018/10/17
author:     Duniang
header-img: "img/post-bg-2015.jpg"
tags:
    - Tensorflow
---

# 翻译 Attention Model
[西班牙到英语](https://github.com/tensorflow/tensorflow/blob/r1.11/tensorflow/contrib/eager/python/examples/nmt_with_attention/nmt_with_attention.ipynb)
## [数据集](http://www.manythings.org/anki/)
此数据集包含很多语言翻译对:_翻译后 翻译前_（May I borrow this book?    ¿Puedo tomar prestado este libro?）
## 预处理数据集
1.Add a start and end token to each sentence.
2.Clean the sentences by removing special characters.
3.Create a word index and reverse word index (dictionaries mapping from word → id and id → word).
4.Pad each sentence to a maximum length.
## 下载文件
- `os.path.dirname(file)` # 返回的是当前文件所在目录，是不包含此文件名词的
- `unicodedata.normalize('NFD', s)` #按照'NFD'方式标准化字符
- create_dataset(path, num_examples) # 返回的是一个num_examples*2的一个二维列表[[english, spanish],[english2, spanish2]]
- LanguageIndex()类是将输入的语言，比如西班牙，去重排序，建立word2idx, idx2word的字典和词汇表，并且第一个索引是‘<pad>’
- max_length()函数找到最长的一个tensor，即最长的一个序列，一个句子。也就是维度
- padding 'post'方式：在序列的结尾补0，‘pre’在序列的起始补0
## `难点`write the encoder and decoder model
tf.keras.layers.Embedding(vocab_size, embedding_dim)
attention
### encoder

```
class Encoder(tf.keras.Model):
    def __init__(self, vocab_size, embedding_dim, enc_units, batch_sz):
        super(Encoder, self).__init__()
        self.batch_sz = batch_sz
        self.enc_units = enc_units
        self.embedding = tf.keras.layers.Embedding(vocab_size, embedding_dim)
        self.gru = gru(self.enc_units)
        
    def call(self, x, hidden):
        x = self.embedding(x)
        output, state = self.gru(x, initial_state = hidden)        
        return output, state
    
    def initialize_hidden_state(self):
        return tf.zeros((self.batch_sz, self.enc_units))`
```
decoder
# 第二个是image caption（给图像生成简单的文字说明）
Our goal is generate a caption, such as "a surfer riding on a wave". Here, we'll use an attention based model. This enables us to see which parts of the image the model focuses on as it generates a caption.
