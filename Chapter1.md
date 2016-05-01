##感知（Perceptrons）


##Sigmoid神经元(Sigmoid neurons)
###引出
一个实际的问题--->>可转化为一系列的电路单元组合后的逻辑电路结构---->>转化为对应的神经元组合的神经网络<p>
神经网络中需要学习的参数：<p>
>各网络权重(Weight)<p>
各节点的偏置项(阈值Threshold)<p>

###参数学习中遇到的问题：
>诸多参数的微调，对最终输出结果的影响忽大忽小，无法控制<p>
需要找到一个可以逐渐微调权重、偏置值以保证不断向理想输出值靠近的方法

###Sigmoid神经元
特点：small changes in their weights and bias cause only a small change in their output. That's the crucial fact which will allow a network of sigmoid neurons to learn.

区别：区别于传统的0-1逻辑门，改用激活函数使得函数输出值为0~1区间的小数，<p>
从本质上看，它是阶梯函数的平滑版本（微分到每一段都可以理解为一段一段的分段函数的组合）<p>
激活值在0~1区间，具有类似模糊函数的优点

上述情况能保证，我在改变较小参数的时候，整体改变也较小

选用不同激活函数的原因：The main thing that changes when we use a different activation function is that the particular values for the partial derivatives in Equation (5) change.

###练习
1. 假如神经网络中所有的权重和偏置统一乘以一个倍数(C>0)，证明神经网络的作用不变
2. 


###神经网络的架构

![logo](http://neuralnetworksanddeeplearning.com/images/tikz11.png)


一般的神经网路都是前向反馈，没有循环的，但有特例：[recurrent neural networks](https://en.wikipedia.org/wiki/Recurrent_neural_network)
其原理：Todo
其缺陷：现有RNN的效果还没有前向反馈神经网络效果好，但是它更加符合人脑的思维，是以后的应用前景

###一个识别手写数字的简单神经网络
解决思路：
1. 将一串数字分割成单个数字的图片集合
一种解决思路：
不断分割图像，并对分割后的结果参照the individual digit classifier进行评分。每个分割片段得分高低取决于.....
2. 识别每一个分割的数字图片值

【实战】假设识别的网络结构图如下：
![logo](http://neuralnetworksanddeeplearning.com/images/tikz12.png)

1. 输入图像统一像素大小28-28，输入层节点=28*28=784个节点
2. 隐含层就一层，暂定节点个数n=15，后期做实验再对比效果优化
3. 输出层节点为10，从上到下依次认为是0,1,2...9。通过比对一幅输入图像在输出节点中最高的值来判断它属于哪个数字。<p>
（另一种思路换做二进制的话4个输出节点就够[0~2^4=16],缺陷：它包含超过了10种情况，且实测效果没有10个节点的好【[为什么呢？](http://neuralnetworksanddeeplearning.com/chap1.html)：从图像认知的角度去考虑问题，分成10种情况，如针对0的识别可以通过对0的图像进行分解而得到，具有一定的实际意义可以参考，但是分成4中的情况就不太好处理。具体详见链接】）

###练习


###梯度下降算法学习
训练数据：[MNIST data set](http://yann.lecun.com/exdb/mnist/)-上万个手写数字图片、以及它对应的数字结果
MNIST data：60000个训练图片（250个人的样本），10000个测试图片（250个人的样本）

学习方式：训练->测试->应用

代价函数： C(w,b)=  <p>
有点像均方根误差（MSE）：目标是使代价函数达到最小，
为什么用这个代价函数来表示？
1. 为什么用这种公式
2. 为什么选择这个平滑的二次函数来表示

梯度下降算法原理：
1. 由于C(w,b)包含各个神经元的所有输入、权重、偏置等，这里进行简化理解，改为C(v)，且v只有两个参数v1,v2。<p>
2. ![graduate](http://read.html5.qq.com/image?src=forum&q=5&r=0&imgflag=7&imageUrl=http://mmbiz.qpic.cn/mmbiz/58FUuNaBUjqmFnpiaugfukXTylgau1kOBFo4MELHoew2OHpbfK7OoDEpFZtgaRYITcGicxkKibH2NmpjuokU9AsCg/0?wx_fmt=png)
3. 从图上，我们能很直观的看到当v1，v2在哪个位置的时候整个公式是最小值。同样如果参数很多的话，也应该有类似的极小值出现。它是一个凸函数（？？对不对）
4. 从理论上解决:一种是利用偏导数的方式，但是变量太多，会极大地影响运算效率。另一种：首先把我们的函数想象成一个山谷。我们想象又一个小球从山谷的斜坡滚落下来。是我们的日常经验告诉我们这个球终会达到谷底。也许我们可以用这种思想来解决函数最小值的问题？我们随机地为小球选取一个起点，然后开始模拟小球滚落到谷底的运动。我们可以简单的通过计算C的导数（或者二阶导数）来模拟-这些导数将会告诉我们关于山谷“地形”的一切，这会引导我们的小球该如何下落。
5. 

梯度下降法的缺点：需要大量的求解二阶偏导，计算量也很大
η：学习速率（小球下滚的速率）
SGD：随机梯度下降
mini-batch：利用随机的几个变量平均值代替整个变化的值




