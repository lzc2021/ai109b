# 第二周

## 爬山演算法

![image](https://github.com/lzc2021/ai109b/blob/main/image/%E5%9B%BE%E7%89%875.png)
* hillClimbing2rpy

隨機取一萬次，如果都失敗則停止執行；
取最高位子移過去

#### 自己的话

Uniform 均等分布，设一段长度-h到h，这其中的每一点都是均等分布的
最平均的分布，应该是如一个圆中均匀的分布的众多点，但是在方形中并不是平均的，因为在对角线方向上分布的点会更多

![image](https://github.com/lzc2021/ai109b/blob/main/image/图片6.png)

能量最低点，与之前的寻找最高点互成相反函数

## 模擬退火法

* 將爬山演算法加上溫度控制，模仿打鐵退火機制
#### 概念表达

模拟退火算法（Simulate Anneal Arithmetic，SAA）是一种通用概率演算法，用来在一个大的搜寻空间内找寻命题的最优解。

#### 定义

模拟退火来自冶金学的专有名词退火。退火是将材料加热后再经特定速率冷却，目的是增大晶粒的体积，并且减少晶格中的缺陷。材料中的原子原来会停留在使内能有局部最小值的位置，加热使能量变大，原子会离开原来位置，而随机在其他位置中移动。退火冷却时速度较慢，使得原子有较多可能可以找到内能比原先更低的位置。

#### 历史

模拟退火是S.Kirkpatrick, C.D.Gelatt和M.P.Vecchi在1983年所发明。而V.Čern&yacute;在1985年也独立发明此演算法。模拟退火算法是解决TSP问题的有效方法之一。

#### 执行历史（部分）
```
PS F:\1文件\演算法\ai\ai\02-optimize\01-hillclimbing\03-var2> python hillClimbing2r.py
x=0.000 y=-0.002 f(x,y)=8.000
x=0.009 y=0.002 f(x,y)=8.005 
x=0.014 y=0.001 f(x,y)=8.013 
x=0.012 y=-0.007 f(x,y)=8.025
x=0.008 y=-0.016 f(x,y)=8.038
x=0.017 y=-0.011 f(x,y)=8.049
x=0.022 y=-0.014 f(x,y)=8.056
x=0.020 y=-0.018 f(x,y)=8.071
x=0.028 y=-0.018 f(x,y)=8.074
x=0.038 y=-0.024 f(x,y)=8.091
x=0.040 y=-0.034 f(x,y)=8.122
x=0.043 y=-0.033 f(x,y)=8.145
【省略】
PS F:\1文件\演算法\ai\ai\02-optimize\01-hillclimbing\04-framework> python hillClimbingNumber.py
start:  energy(0.000)=4.000
0 : energy(0.010)=4.000 
2 : energy(0.020)=4.000 
4 : energy(0.030)=3.999 
6 : energy(0.040)=3.998 
9 : energy(0.050)=3.998 
【省略】
PS F:\1文件\演算法\ai\ai\02-optimize\01-hillclimbing\04-framework> python .\annealingEquation.py
Traceback (most recent call last):
  File ".\annealingEquation.py", line 2, in <module>
    from solutionEquation import SolutionEquation # 引入平方根解答類別
  File "F:\1文件\演算法\ai\ai\02-optimize\01-hillclimbing\04-framework\solutionEquation.py", line 12, in <module>   
    import numpy as np
ModuleNotFoundError: No module named 'numpy'
PS F:\1文件\演算法\ai\ai\02-optimize\01-hillclimbing\04-framework> pip install numpy
Collecting numpy
  Downloading numpy-1.20.1-cp38-cp38-win_amd64.whl (13.7 MB)
     |████████████████████████████████| 13.7 MB 409 kB/s 
Installing collected packages: numpy
Successfully installed numpy-1.20.1
WARNING: You are using pip version 20.2.3; however, version 21.0.1 is available.
You should consider upgrading via the 'c:\users\asus1806\appdata\local\programs\python\python38\python.exe -m pip install --upgrade pip' command.
PS F:\1文件\演算法\ai\ai\02-optimize\01-hillclimbing\04-framework> python .\annealingEquation.py
0 T=99.50000 energy([[ 0.00696836  0.         -0.00777608]])=2.460413
1 T=99.00250 energy([[ 0.00736438  0.         -0.00777608]])=2.459753
2 T=98.50749 energy([[ 0.00231886  0.         -0.00112026]])=2.448906
3 T=98.01495 energy([[ 0.00231886 -0.00195379 -0.00697472]])=2.469154
4 T=97.52488 energy([[ 0.00231886  0.01452531 -0.00661412]])=2.440908
5 T=97.03725 energy([[ 0.00231886  0.01667271 -0.00181125]])=2.424099
【省略】
```
> 参考资料：百度百科、CSDN

