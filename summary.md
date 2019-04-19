<!-- <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script> -->

## Zero-Shot Learning - A Comprehensive Evaluation of the Good, the Bad and the Ugly

### 写作背景及目的
#### 背景
因为目前零样本学习在对缺少标记的训练样本分类方面起着越来越重要的作用，所以越来越多的零样本学习方法被提出来了。

#### 目的
分析一下目前的零样本学习现状并且定义一个通用的评价基准

### 核心问题

目前零样本学习的现状主要存在以下几点问题：
1. 目前零样本学习没有一个一致公认的评价基准，导致很难评价新提出来的方法在之前的方法基础上有了多大的进步。
2. 数据集拆分标准不一，导致之前公布的方法所到达的效果也没法直接进行比较。而且如果有人在测试类别上进行预训练会对结果产生比较严重的影响。

### 现有状况
#### 常见的零样本学习方法类别
1. 线性方法(linear learning)
2. 非线性方法(nonlinear compatibility learning)
3. 独立分类器(independent classifier learning)

#### AWA1数据集
因为AWA1没有公开协议，目前不能直接获得原始图片，只能获得一些通过网络提取后的图像特征。

#### AWA2数据集
AWA2数据集具有公开协议协议，同时拥有和AWA1相同数量的图像类别和属性，且所有原始图片都是公开的，可以直接获取。

### 相关研究
#### 早期(Two Stage)
##### 通过属性(attribute)预测
步骤：

1. 预测出图像的一些属性
2. 搜寻具有这些相似的属性的类别

代表性方法:

1. Direct Attribute Prediction(DAP)
2. Indirect Attribute Prediction(IAP)

##### 通过词向量(word vector)预测

步骤:

1. 预测已知类别的后验概率
2. 将图像特征投影到词向量空间(Question)

代表性方法:

1. IAP
2. CONSE

#### 近期的研究
大多数近期的零样本学习方法采用了直接学习一个从图像特征空间到语义空间的映射的方式。

##### 1. SOC
SOC将图像特征映射进语义空间后，然后搜寻最相邻的类别向量。

##### 2. ALE
ALE使用ranking loss来学习图像与属性之间的双线性兼容(compatibility)函数

##### 3. DeViSE
DeViSE采用了一个更有效的ranking loss来学习一个图像与语义空间线性映射，并且在大型的ImageNet数据集上进行了评估

##### 4. SJE
SJE采用了SVM loss去学习双线性兼容函数

##### 5. ESZSL
ESZSL采用了square loss

##### 6. SAE
SAE采用了一种语义自动编码器(semantic auto encoder),通过强制将图像特征投影需要重新构建的语义空间来规范化模型

##### 7. LatEm
LatEm采用了多个线性映射将SJE的双线性兼容性模型扩展到了分段线性映射


##### 8. CMT
CMT采用了带有隐藏层的神经网络学习从图像特征到word2vec的非线性映射




### 作者所做的工作

### 方法创新点及局限性

### 实验验证

### 对自己的启发