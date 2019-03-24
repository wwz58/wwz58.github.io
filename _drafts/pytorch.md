---
title: pytorch
tags: pytorch
---
# pytorch:科学计算python包，目的：
- 替代numpy的多维array，可以利用起GPU
- 兼顾灵活和高效的深度学习框架
# Tensor
- 类似numpy array
- 操作：
    + torch.add(x,y,out=x)
    + x+y --> z
    + x.add(y) --> z
    + x.add_(y) inplace
- 与numpy array相互转换，但**共享存储**：
    + tensor.numpy()
    + torch.from_numpy(nparray)
    + 所有CPU上的tensor，除了Char Tensor都支持与numpy array相互转换
- CUDA Tensor
    + tensor使用to()移动到任意设备,默认创建在cpu（可修改）

    tensor.to(device, torch.double)#device可以是torch.device对象，也可以是字符串：'cuda','cpu','cuda:0'
# autograd
- autograde包，中心class：torch.Tensor和Function，动态创建计算图
- tensor的.grad_fn（创建该tensor的函数，用户自己创建的为None）和.requires_grad和.grad(累加)属性.requires_grad_(True)方法.detach()方法返回一个从计算图中detach的tensor，.backward()方法
# torch.nn package神经网络
- nn.Module定义网络的层，依赖于autograde包，需要forward（input）想象自己定义网络层，--》重用--》定义常用layers class
- nn.MSELoss
- torch.optim实现了各种更新方法SGD(params, )
# data
- Generally, when you have to deal with image, text, audio or video data,
you can use standard python packages that load data into a numpy array.
Then you can convert this array into a torch.*Tensor.
    + For images, packages such as Pillow, OpenCV are useful
    + For audio, packages such as scipy and librosa
    + For text, either raw Python or Cython based loading, or NLTK and SpaCy are useful
    + Specifically for vision：torchvision,
    that has data loaders for common datasets such as Imagenet, CIFAR10, MNIST, etc.
    and data transformers for images, viz.,
- torchvision.datasets__len__(),\__getitem__()
- torch.utils.data.DataLoader is an iterator 提供
    + Batching the data
    + Shuffling the data
    + Load the data in parallel using multiprocessing workers.
    + One parameter of interest is collate_fn定义sample是怎末batch起来的