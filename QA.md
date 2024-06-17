# Normalization 
把输入转化成均值为 0 方差为1的数据，在把数据送入激活函数之前进行归一化，因为我们不希望输入数据落在激活函数的饱和区，发生梯度消失的问题。
Batch Norm, Weight Norm, Layer Norm, Instance Norm, Group Norm

BN的主要思想是: 在每一层的每一批数据(一个batch里的同一通道)上进行归一化
LN的主要思想是:是在每一个样本(一个样本里的不同通道)上计算均值和方差，而不是 BN 那种在批方向计算均值和方差！
IN是针对于不同的batch, 不同的chennel进行归一化。还是把图像的尺寸表示为[N, C, H, W]的话，IN则是针对于[H,W]进行归一化。这种方式通常会用在风格迁移的训练中。
GN介乎于instance normal 和 layer normal 。也就是说当我们把所有的channel都放到同一个group中的时候就变成了layer normal， 如果我们把每个channel都归为一个不同的group，则变成了instance normal.
