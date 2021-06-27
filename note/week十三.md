# 第十三周
## 反传递演算法
* 反向传播是「误差反向传播」的简称，是一种与最优化方法（如梯度下降法）结合使用的，用来训练人工神经网络的常见方法。该方法对网络中所有权重计算损失函数的梯度。这个梯度会反馈给最优化方法，用来更新权值以最小化损失函数。

* 反向传播要求有对每个输入值想得到的已知输出，来计算损失函数梯度。因此，它通常被认为是一种监督式学习方法，虽然它也用在一些无监督网络（如自动编码器）中。它是多层前馈网络的Delta规则的推广，可以用链式法则对每层叠代计算梯度。反向传播要求人工神经元（或「节点」）的激励函数可微。



#### code
* net1.py
```
net.forward()= 10
net.backwward()
x= v:1 g:2 y= v:3 g:6 o= v:10 g:1
gfx = x.g/o.g =  2.0 gfy = y.g/o.g= 6.0
```
* net2.py
```
0  =>  10
1  =>  9.216
2  =>  8.4934656
.
.
.
98  =>  0.003350901606872675
99  =>  0.003088190920893857
x= 0.01687031935884968 y= 0.050610958076549
```
## pytorch
PyTorch是一个开源的Python机器学习库，基于Torch，底层由C++实现，应用于人工智慧领域，如自然语言处理。它最初由Facebook的人工智慧研究团队开发，并且被用于Uber的概率编程软体Pyro。

PyTorch主要有两大特徵:

* 类似于NumPy的张量计算，可使用GPU加速；

* 基于带自动微分系统的深度神经网路。

### code

* autograd0.py
```
tensor(2.)
tensor(6.)
10.0   
```

* autograd1.py
```
tensor(2.)
tensor(6.)
10.0
```

* autograd2.py
```
f= 10.0
x.grad= tensor([2., 6.])
```

* torchGd1.py
```
99 x= 0.05263785645365715 loss= 3.792219400405884
199 x= 0.4059540331363678 loss= 2.540982484817505
299 x= 0.6951667666435242 loss= 1.702589750289917
.
.
.
4899 x= 1.999867558479309 loss= 0.0       
4999 x= 1.9998914003372192 loss= 0.0      
Result: x = 1.9998916387557983 loss=0.0 
```

* torchGd2.py
```
99 parameters= [tensor(0.3926, requires_grad=True)] loss= 2.583590269088745
199 parameters= [tensor(0.6843, requires_grad=True)] loss= 1.7311391830444336       
299 parameters= [tensor(0.9230, requires_grad=True)] loss= 1.1599531173706055  
.
.
.
4899 parameters= [tensor(1.9999, requires_grad=True)] loss= 0.0
4999 parameters= [tensor(1.9999, requires_grad=True)] loss= 0.0
Result: parameters = [tensor(1.9999, requires_grad=True)] loss=0.0
```

* torchGd3.py
```
x= tensor([-0.0018, -0.0035], requires_grad=True)
```
