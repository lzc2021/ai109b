# 第十五周

## colab
Colaboratory（也称为Colab）是一个免费的Jupyter Notebook环境，它在云端中运行，并将笔记本存储在Google云端端硬碟上。Colaboratory最初是Jupyter专案的一部分，但最终被Google接管。截止到2018年9月，Colaboratory只支援Python 2和Python 3核心，不支援其他Jupyter核心，比如Julia和R。
* 优点
  * 使用云端空间，不用自己的电脑空间。
  * 可免费用 Colab 的 GPU 算力，执行深度学习速度有感。
  * 可以跳过 Mac 、 Win 的各种坑，设定省心。
  * 手机平板也可以执行，但建议只用来看成果，因为容易断线且优化待加强。
* 缺点
  * 佔用 Google 云端硬碟容量。
  * 部分功能及服务需付费。
  * 云端服务一定要有网路。

## RNN
RNN是為了對序列數據進行建模而產生的。文本，是字母和詞彙的序列；語音，是音節的序列；視頻，是圖像的序列；氣象觀測數據，股票交易數據等等，也都是序列數據。

RNN背後的核心理念是利用序列的信息。傳統的神經網絡常常假設輸入（輸出）是獨立於彼此的，這對於某些應用來說是不可行的。
以下是RNN的典型結構：

![image](https://user-images.githubusercontent.com/47874872/123468955-091d9600-d625-11eb-88df-38f2eec15516.png)

## one-hot
  * One-hot在数位电路中被用来表示一种特殊的位元组合，该位元组里，仅容许单一位元爲1，其他位元都必须爲0。之所以称爲one-hot就是因爲只能有一个1（hot）。若情况相反，只有一个0，其馀爲1，则称爲one-cold。在机器学习里，也有one-hot向量（英语：one-hot vector）的概念。在一任意维度的向量中，仅有一个维度的值是1，其馀爲0。

#### 概念表达
One-Hot编码，又称为一位有效编码，主要是采用N位状态寄存器来对N个状态进行编码，每个状态都由他独立的寄存器位，并且在任意时候只有一位有效。

One-Hot编码是分类变量作为二进制向量的表示。这首先要求将分类值映射到整数值。然后，每个整数值被表示为二进制向量，除了整数的索引之外，它都是零值，它被标记为1。

#### 编码过程

1.确定要编码的对象--hello world，

2.确定分类变量--h  e  l  l  o  空格  w  o  r  l  d，共27种类别（26个小写字母 + 空格，）；

3.以上问题就相当于，有11个样本，每个样本有27个特征，将其转化为二进制向量表示，

这里有一个前提，特征排列的顺序不同，对应的二进制向量亦不同（比如我把空格放在第一列和a放第一列，one-hot编码结果肯定是不同的）

因此我们必须要事先约定特征排列的顺序：

1.、27种特征首先进行整数编码：a--0，b--1，c--2，......，z--25，空格--26

2、27种特征按照整数编码的大小从前往后排列

* 应用
* 自然语言
* 在自然语言处理中，若有个字典或字库里有{\displaystyle N}N个单字，则每个单字可以被一个{\displaystyle N}N维的one-hot向量代表。譬如若字库里仅有apple（苹果），banana（香蕉），以及pineapple（凤梨）这三个单字，则他们各自的one-hot向量

> 参考资料：慕课网、博客园
