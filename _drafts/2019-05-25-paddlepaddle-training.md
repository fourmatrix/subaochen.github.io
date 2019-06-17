时间：2019-05-25

主讲人：王浩（百度）

# 小组建设

本组组名：皮皮鲁

口号：不仅AI，要深AI

# 机器学习入门

##  机器学习的定义

## 机器学习的一般过程

模型->策略（评价，损失函数的选择）->算法（调参，最优化）

#　机器学习的方法
* 有监督学习（supervised leanring）：分类和回归
* 无监督学习（unsupervised learning）：聚类
* 半监督学习（Semi-supervised learning）
* 强化学习
* 多任务学习

# 机器学习面临的困难和挑战
* 数据稀疏性
* 模型抽象困难
* 模型评估困难
* 寻找最优解困难
* 速度
* scalability
* onlien learning

# 机器学习准备
## 鸢尾花问题
###　数据预处理
* 数据清洗
* 数据采样：过采样，欠采样，打破数据不均衡
* 数据集划分：留出法，ｋ－折交叉验证

### 特征工程
* 特征选择：剔除不需要的特征
* 特征降维：主成分分析（PCA），线性判别
* 特征编码：one-hot编码
* 语义编码：word2vec

### 规范化
* 标准化
* 归一化

# 机器学习方法
## 分类问题
### 决策树：ID3，C4.5, CART算法
### 贝叶斯分类
1. 计算先验概率
2. 计算每个属性的概率
3. 计算后验概率

### SVM（支持向量机）
什么是支持向量？
支持向量间的距离最大化
核函数的作用？更好的核函数？

### 逻辑回归

最大熵模型
熵力：喜欢变乱的力量

### 集成学习
三个臭皮匠赛过诸葛亮
竞赛时几乎都使用了集成学习
bagging
boosting
## 回归问题
### 线性回归
线性回归扩展，多项式拟合
岭回归：解决过拟合
losso回归：套索？
## 聚类问题
### k-means
### 高斯混合
### 隐马尔科夫模型
### 条件随机场
### LDA主题模型

# 机器学习模型评估
## 模型选择
泛化误差，经验误差
## 性能评价指标-分类
准确率
召回率

# 深度学习入门（自然语言处理方向）
## 深度学习概述
<2012年，深度学习被SVM打的落花流水。2012年Hiton说，这是一个里程碑（ImageNet）
## 为什么深度学习
### 传统方法：人工特征提取+分类器
三个空间的转换：（测量空间-》特征空间(核心任务)-》类别空间）

### 深度学习：
特征空间的人工提取：取消了！

深度学习的不可认知性：存在吗？

深度学习：仿造了人脑的视觉机理
生物学上的实验如何证明神经学习？快速闪过的图片，验证认知的过程：边缘特征到细节


## 如何使用深度学习
 * 目标：寻找一个合适的函数
 * 函数集合：数学模型，机器针对模型尝试不同的参数，挑出最好的参数拟合

## 全连接神经网络
为什么叫做激活函数？起什么作用？基于实验的
### 建立模型
前馈神经网络
层数是经验决定的？resnet:152层,3.57%
softmax不是概率，但是可以相当于概率

####  手写数字识别
多少层？
多少节点？
是否选择其他网络结构（RNN，CNN）？

### 损失函数
损失函数现在是一个选择或者组合问题？论文中一般没有给出如何选择
MSE的适用场合：回归
交叉熵的适用场合：分类问题

### 参数学习
最笨的办法：穷举法（不现实，参数爆炸）
目前普遍采用（随机）梯度下降
如何跳出局部最优解:多次迭代随机跳出；如何在梯度变化慢的时候加快迭代？变步长的优化策略。

### 反向传播算法
快速求导，没有重复计算的一个算法而已，图形方式理解链式法则

### 模型回顾
FC的问题：结构不灵活，参数太多->CNN

## CNN
### 局部连接
### 权重共享
使用同一个神经元完成窗口滑动
### 下采样

把FC看做CNN如何解释？很有意思！

### 建立模型
#### 卷积核
相当于全连接的参数，在CNN中就是共享的权重
步长：滑动的格数
如果input map=kernel则为全连接
从全连接的角度理解CNN有意思，跳过的输入节点是CNN的特点

参数太少，会导致模型太简单？如何解决？
每一个kernel是一组待训练的参数，多个kernel就是多组待训练的参数
一个卷积核可以提取图像的一种特征:这是认为的理解，还是机器的理解？
多通道卷积：卷积核为立方体而已，还是线性操作，输出和单层的shape一样
#### pooling层（下采样）
目的：减少feature map的尺寸
max pooling，要解释清楚操作的效果和意义
下采样时的参数个数如何确定？

### 经典模型LeNet-5
弄清楚其中的维度变化

questions:

1. fluid是什么意思？
1. pooling层的参数个数？
1. CNN最后的全连接层的shape？
1. default_startup_program和default_main_program分别有什么作用？为什么
需要两个？
1. 训练中出现很多accuracy=1.0000，是不是出了啥问题？如何调整？

3层：97.2%
batch_size=32, accuracy=97.6
