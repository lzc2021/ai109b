# 第十四周

## 人工智慧的方法
* 比對法
    * 紀錄問題與答案配對後，直接從表格內查出。
    * 例如:Elisa
* 推理法
    * 撰寫規則後，電腦根據規則推論。
    * 例如:專家系統
* 搜尋法
    * 對所有可能的結果進行系統式的列舉，然後看看有沒有答案。
    * 例如:深度優先、廣度優先、電腦下棋
* 統計法
    * 找出機率最大的解答。
    * 例如:利用電腦亂數驗證中央極限定理
* 優化法
    * 對每個可能的解答，都給一個分數及權重，找出總分最好的解答。
    * 例如:爬山演算法、遺傳演算法
## 深度学习的神经网络
#### 概念表达
深度学习(DL, Deep Learning)是机器学习(ML, Machine Learning)领域中一个新的研究方向，它被引入机器学习使其更接近于最初的目标——人工智能(AI, Artificial Intelligence)。

深度学习在搜索技术，数据挖掘，机器学习，机器翻译，自然语言处理，多媒体学习，语音，推荐和个性化技术，以及其他相关领域都取得了很多成果。深度学习使机器模仿视听和思考等人类的活动，解决了很多复杂的模式识别难题，使得人工智能相关技术取得了很大进步。

#### 定义
深度学习是学习样本数据的内在规律和表示层次，这些学习过程中获得的信息对诸如文字，图像和声音等数据的解释有很大的帮助。它的最终目标是让机器能够像人一样具有分析学习能力，能够识别文字、图像和声音等数据。 深度学习是一个复杂的机器学习算法，在语音和图像识别方面取得的效果，远远超过先前相关技术。

#### 学习方法
深度学习是一类模式分析方法的统称，就具体研究内容而言，主要涉及三类方法：
* 基于卷积运算的神经网络系统，即卷积神经网络(CNN)。 
* 基于多层神经元的自编码神经网络，包括自编码( Auto encoder)以及近年来受到广泛关注的稀疏编码两类( Sparse Coding)。
* 以多层自编码神经网络的方式进行预训练，进而结合鉴别信息进一步优化神经网络权值的深度置信网络(DBN)。 
通过多层处理，逐渐将初始的“低层”特征表示转化为“高层”特征表示后，用“简单模型”即可完成复杂的分类等学习任务。由此可将深度学习理解为进行“特征学习”（feature learning）或“表示学习”（representation learning）。 
以往在机器学习用于现实任务时，描述样本的特征通常需由人类专家来设计，这成为“特征工程”（feature engineering）。众所周知，特征的好坏对泛化性能有至关重要的影响，人类专家设计出好特征也并非易事；特征学习（表征学习）则通过机器学习技术自身来产生好特征，这使机器学习向“全自动数据分析”又前进了一步。 
近年来，研究人员也逐渐将这几类方法结合起来，如对原本是以有监督学习为基础的卷积神经网络结合自编码神经网络进行无监督的预训练，进而利用鉴别信息微调网络参数形成的卷积深度置信网络。与传统的学习方法相比，深度学习方法预设了更多的模型参数，因此模型训练难度更大，根据统计学习的一般规律知道，模型参数越多，需要参与训练的数据量也越大。
20世纪八九十年代由于计算机计算能力有限和相关技术的限制，可用于分析的数据量太小，深度学习在模式分析中并没有表现出优异的识别性能。自从2006年， Hinton等提出快速计算受限玻耳兹曼机(RBM)网络权值及偏差的CD-K算法以后，RBM就成了增加神经网络深度的有力工具，导致后面使用广泛的DBN(由 Hinton等开发并已被微软等公司用于语音识别中)等深度网络的出现。与此同时，稀疏编码等由于能自动从数据中提取特征也被应用于深度学习中。基于局部数据区域的卷积神经网络方法今年来也被大量研究。

## 卷积神经网络CNN
#### 概念表达
卷积神经网络（Convolutional Neural Networks, CNN）是一类包含卷积计算且具有深度结构的前馈神经网络（Feedforward Neural Networks），是深度学习（deep learning）的代表算法之一 [1-2]  。卷积神经网络具有表征学习（representation learning）能力，能够按其阶层结构对输入信息进行平移不变分类（shift-invariant classification），因此也被称为“平移不变人工神经网络（Shift-Invariant Artificial Neural Networks, SIANN）”
#### 定义
卷积神经网络的研究始于二十世纪80至90年代，时间延迟网络和LeNet-5是最早出现的卷积神经网络 [4]  ；在二十一世纪后，随着深度学习理论的提出和数值计算设备的改进，卷积神经网络得到了快速发展，并被应用于计算机视觉、自然语言处理等领域。
卷积神经网络仿造生物的视知觉（visual perception）机制构建，可以进行监督学习和非监督学习，其隐含层内的卷积核参数共享和层间连接的稀疏性使得卷积神经网络能够以较小的计算量对格点化（grid-like topology）特征，例如像素和音频进行学习、有稳定的效果且对数据没有额外的特征工程（feature engineering）要求
#### 历史
对卷积神经网络的研究可追溯至日本学者福岛邦彦（Kunihiko Fukushima）提出的neocognitron模型。在其1979和1980年发表的论文中，福岛仿造生物的视觉皮层（visual cortex）设计了以“neocognitron”命名的神经网络。neocognitron是一个具有深度结构的神经网络，并且是最早被提出的深度学习算法之一，其隐含层由S层（Simple-layer）和C层（Complex-layer）交替构成。其中S层单元在感受野（receptive field）内对图像特征进行提取，C层单元接收和响应不同感受野返回的相同特征。neocognitron的S层-C层组合能够进行特征提取和筛选，部分实现了卷积神经网络中卷积层（convolution layer）和池化层（pooling layer）的功能，被认为是启发了卷积神经网络的开创性研究。

## 循环神经网络RNN
#### 概念表达
循环神经网络（Recurrent Neural Network, RNN）是一类以序列（sequence）数据为输入，在序列的演进方向进行递归（recursion）且所有节点（循环单元）按链式连接的递归神经网络（recursive neural network）。
#### 定义
对循环神经网络的研究始于二十世纪80-90年代，并在二十一世纪初发展为深度学习（deep learning）算法之一，其中双向循环神经网络（Bidirectional RNN, Bi-RNN）和长短期记忆网络（Long Short-Term Memory networks，LSTM）是常见的循环神经网络。
循环神经网络具有记忆性、参数共享并且图灵完备（Turing completeness），因此在对序列的非线性特征进行学习时具有一定优势 [4]  。循环神经网络在自然语言处理（Natural Language Processing, NLP），例如语音识别、语言建模、机器翻译等领域有应用，也被用于各类时间序列预报。引入了卷积神经网络（Convolutional Neural Network,CNN）构筑的循环神经网络可以处理包含序列输入的计算机视觉问题。
#### 历史
1933年，西班牙神经生物学家Rafael Lorente de Nó发现大脑皮层（cerebral cortex）的解剖结构允许刺激在神经回路中循环传递，并由此提出反响回路假设（reverberating circuit hypothesis）。该假说在同时期的一系列研究中得到认可，被认为是生物拥有短期记忆的原因。随后神经生物学的进一步研究发现，反响回路的兴奋和抑制受大脑阿尔法节律（α-rhythm）调控，并在α-运动神经（α-motoneurones ）中形成循环反馈系统（recurrent feedback system）。在二十世纪70-80年代，为模拟循环反馈系统而建立的一些数学模型为RNN带来了启发。

> 参考资料：百度百科
