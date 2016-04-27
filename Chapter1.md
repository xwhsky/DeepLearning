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

区别：区别于传统的0-1逻辑门，改用激活函数使得函数输出值为0~1区间的小数，
