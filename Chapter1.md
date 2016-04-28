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
4. （另一种）
5. 
