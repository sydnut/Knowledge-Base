### What is Linear Regression?
> [**线性回归**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#linear-regression)是一种用于查找变量之间关系的统计技术。在机器学习背景下，线性回归用于查找[**特征**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#feature)与[**标签**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#label)之间的关系

我们可以用线性回归方程表对统计数据进行建模（类似高中数学的统计学）。其中
在机器学习中，线性回归模型的方程式如下所示：

$$
y' = b + w_1x_1
$$
其中：
- $y'$ 是预测标签（输出）。
- $b$ 是模型的**偏差**。
  偏差与直线代数方程式中的 y 轴截距概念相同。
  在机器学习中，偏差有时称为 $w_0$。
  偏差是模型的**形参**，在训练期间计算得出。
- $w_1$ 是特征的**权重**。
  权重与线性代数方程式中的斜率 $m$ 的概念相同。
  权重是模型的**形参**，在训练期间计算得出。
- $x_1$ 是一个**特征**，即输入。

### 损失函数 Loss

> [损失](https://developers.google.com/machine-learning/glossary?hl=zh-cn#loss)是一种数值指标，用于描述模型的[**预测**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#prediction)与实际情况的偏差程度。损失用于衡量模型预测与实际标签之间的距离。训练模型的目标是尽可能降低损失，使其达到最低值

![](file://)
![Loss Lines](resources/ML/loss-lines.png)
#### 损失类型
![](resources/ML/损失类型.png)

### 梯度下降法 Gradient descent

> [**梯度下降法**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#gradient-descent)是一种数学技巧，可迭代地找到能使模型产生最低损失的权重和偏差。梯度下降法通过重复以下过程（迭代次数由用户定义）来找到最佳权重和偏差。

模型开始训练时，权重和偏差会随机化为接近于零的值，然后重复执行以下步骤：

1. 使用当前权重和偏差计算损失。

2. 确定可减少损失的权重和偏差移动方向。

3. 将权重和偏差值沿可减少损失的方向移动少量距离。

4. 返回到第 1 步，重复此过程，直到模型无法进一步减少损失为止。

**有点类似站在一个山坡，往各个方向伸脚确定下落方向和高度**

### 超参数 Hyperparameters

> **超参数**是控制训练不同方面的变量。常见有以下三种：
> - **学习速率**
> - **批次大小**
> - **周期**

#### 学习速率

> 学习速率是一个设置的**浮点数**，用于影响模型的收敛速度

有点类似梯度下降移动的“**步伐**”

一般来说，旧模型参数与新模型参数之间的差异与损失函数的斜率成正比。例如，如果斜率较大，模型会采取较大的步长（快速收敛）。如果较小，则采取较小的步长（稳步下降）
**理想**
![理想](resources/ML/理想学习速率.png)
**过小**
![630](resources/ML/small-lr.png)
**过大**
![](resources/ML/high-lr.png)
#### 批次大小
> [**批次大小**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#batch-size)是一种超参数，指的是模型在更新权重和偏差之前处理的[**示例**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#example)数量

模型在更新权重和偏差前需要**预估出平均梯度**，但计算上百万数据是不实际的，所以一般有以下两种方法：
- **随机梯度下降法 (SGD)**：：随机梯度下降法在每次迭代中仅使用一个示例（批次大小为 1）。在迭代次数足够多的情况下，SGD 可以正常运行，但噪声非常大。
- **小批次随机梯度下降法（小批次 SGD）**：小批次随机梯度下降法是全批次和 SGD 之间的折衷方案。对于 N 个数据点，批次大小可以是大于 1 且小于 N 的任意数字。模型会随机选择每个批次中包含的示例，对它们的梯度求平均值，然后在每次迭代中更新一次权重和偏差

#### 周期数

**周期**：
> 在训练期间，一个[**周期**](https://developers.google.com/machine-learning/glossary?hl=zh-cn#epoch)是指模型已处理训练集中的**每个示例**一次。
> 例如，如果训练集包含 1,000 个示例，而小批次大小为 100 个示例，则模型需要 10 次[迭代](https://developers.google.com/machine-learning/glossary?hl=zh-cn#iteration)才能完成一个周期

周期数是一种超参数，您需要在模型开始训练之前设置该参数。在许多情况下，您需要通过实验来确定模型收敛所需的周期数。**一般来说，训练周期数越多，模型效果越好，但训练时间也越长。**

