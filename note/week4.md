# 第四周

## 线性规划和线性代数
* 线性是指量与量之间按比例、成直线的关系，在数学上可以理解为一阶导数为常数的函数。
#### 概念表达
线性规划（Linear programming,简称LP），是运筹学中研究较早、发展较快、应用广泛、方法较成熟的一个重要分支，它是辅助人们进行科学管理的一种数学方法。研究线性约束条件下线性目标函数的极值问题的数学理论和方法。英文缩写LP。

线性规划是运筹学的一个重要分支，广泛应用于军事作战、经济分析、经营管理和工程技术等方面。为合理地利用有限的人力、物力、财力等资源作出的最优决策，提供科学的依据。
#### 定义
线性规划(Linear Programming 简记 LP)是了运筹学中数学规划的一个重要分支。 在解决实际问题时，需要把问题归结成一个线性规划数学模型，关键及难点在于选适当的决策变量建立恰当的模型，这直接影响到问题的求解。

线性规划问题的目标函数及约束条件均为线性函数；约束条件记为 s.t.(即 subject to)。目标函数可以是求最大值，也可以是求最小值，约束条件的不等号可以 是小于号也可以是大于号。
#### 历史
自从 1947 年 G. B. Dantzig 提出 求解线性规划的单纯形法以来，线性规划在理论上趋向成熟，在实用中由于计算机能处理成千上万个约束条件和决策变量的线性规划问题之后，线性规划现代管理中经常采用的基本方法之一。

![image](https://github.com/lzc2021/ai109b/blob/main/image/%E5%9B%BE%E7%89%878.png)

## 单纯形法
#### 概念表达
单纯形法是求解线性规划问题最常用、最有效的算法之一。如果线性规划问题的最优解存在，则一定可以在其可行区域的顶点中找到。基于此，单纯形法的基本思路是：先找出可行域的一个顶点，据一定规则判断其是否最优；若否，则转换到与之相邻的另一顶点，并使目标函数值更优；如此下去，直到找到某最优解为止。
#### 定义
单纯形法的基本想法是从线性规划可行集的某一个顶点出发，沿着使目标函数值下降的方向寻求下一个顶点，面顶点个数是有限的，所以，只要这个线性规划有最优解，那么通过有限步迭代后，必可求出最优解 。
#### 历史
单纯形法最早由 George Dantzig于1947年提出，近70年来，虽有许多变形体已经开发，但却保持着同样的基本观念。
## Big O
* Big O，又稱為漸進符號，是用於描述函式漸近行為的數學符號。更確切地說，它是用另一個（通常更簡單的）函式來描述一個函式數量級的漸近上界。在數學中，它一般用來刻畫被截斷的無窮級數尤其是漸近級數的剩餘項；在電腦科學中，它在分析演算法複雜性的方面非常有用。
## 整数规划
#### 概念表达
整数规划是指规划中的变量（全部或部分）限制为整数，若在线性模型中，变量限制为整数，则称为整数线性规划。所流行的求解整数规划的方法往往只适用于整数线性规划。
一类要求问题的解中的全部或一部分变量为整数的数学规划。从约束条件的构成又可细分为线性，二次和非线性的整数规划。 
#### 定义
在线性规划问题中，有些最优解可能是分数或小数，但对于某些具体问题，常要求某些变量的解必须是整数。例如，当变量代表的是机器的台数，工作的人数或装货的车数等。为了满足整数的要求，初看起来似乎只要把已得的非整数解舍入化整就可以了。实际上化整后的数不见得是可行解和最优解，所以应该有特殊的方法来求解整数规划。在整数规划中，如果所有变量都限制为整数，则称为纯整数规划；如果仅一部分变量限制为整数，则称为混合整数规划。整数规划的一种特殊情形是01规划，它的变数仅限于0或1。不同于线性规划问题，整数和01规划问题至今尚未找到一般的多项式解法。
#### 历史
整数规划是从1958年由R.E.戈莫里提出割平面法之后形成独立分支的 ，30多年来发展出很多方法解决各种问题。解整数规划最典型的做法是逐步生成一个相关的问题，称它是原问题的衍生问题。对每个衍生问题又伴随一个比它更易于求解的松弛问题（衍生问题称为松弛问题的源问题）。

## NP完全
#### 概念表达
NP完全问题(NP-C问题)，是世界七大数学难题之一。 NP的英文全称是Non-deterministic Polynomial的问题，即多项式复杂程度的非确定性问题。简单的写法是 NP=P？，问题就在这个问号上，到底是NP等于P，还是NP不等于P。
#### 定义
NP完全或NP完备（NP-Complete，缩写为NP-C或NPC），是计算複杂度理论中，决定性问题的等级之一。NP完备是NP与NP困难的交集，是NP中最难的决定性问题，所有NP问题都可以被快速归化为NP完备问题。因此NP完备问题应该是最不可能被化简为P（多项式时间可决定）的决定性问题的集合。若任何NPC问题得到多项式时间的解法，那此解法就可应用在所有NP问题上。

#### 执行历史（部分）
```
PS F:\1文件\演算法\se\python\alg\00-complexity\bigO> python bubbleSort.py
sort([3, 8, 2, 1, 5]= [1, 2, 3, 5, 8]
PS F:\1文件\演算法\ai\ai\02-optimize\04-linearProgramming> pip install pulp
Collecting pulp
  Downloading PuLP-2.4-py3-none-any.whl (40.6 MB)
     |████████████████████████████████| 40.6 MB 1.3 MB/s 
Collecting amply>=0.1.2
  Downloading amply-0.1.4-py3-none-any.whl (16 kB)
Collecting docutils>=0.3
  Downloading docutils-0.16-py2.py3-none-any.whl (548 kB)
     |████████████████████████████████| 548 kB 656 kB/s 
Collecting pyparsing
  Downloading pyparsing-2.4.7-py2.py3-none-any.whl (67 kB)
     |████████████████████████████████| 67 kB 389 kB/s 
Installing collected packages: pyparsing, docutils, amply, pulp
Successfully installed amply-0.1.4 docutils-0.16 pulp-2.4 pyparsing-2.4.7
PS F:\1文件\演算法\ai\ai\02-optimize\04-linearProgramming> python linearProgramming1.py
Welcome to the CBC MILP Solver 
Version: 2.9.0
Build Date: Feb 12 2015
command line - C:\Users\asus1806\AppData\Local\Programs\Python\Python38\lib\site-packages\pulp\apis\..\solverdir\cbc\win\64\cbc.exe C:\Users\asus1806\AppData\Local\Temp\168fe62ca4f2442ab08980d5856db675-pulp.mps branch printingOptions all solution C:\Users\asus1806\AppData\Local\Temp\168fe62ca4f2442ab08980d5856db675-pulp.sol (default strategy 1)        
At line 2 NAME          MODEL
At line 3 ROWS
At line 8 COLUMNS
At line 18 RHS
At line 22 BOUNDS
At line 26 ENDATA
Problem MODEL has 3 rows, 3 columns and 6 elements
Coin0008I MODEL read with 0 errors
Presolve 1 (-2) rows, 2 (-1) columns and 2 (-4) elements
0  Obj 51.9 Primal inf 2.099999 (1)
1  Obj 54
Optimal - objective value 54
After Postsolve, objective 54, infeasibilities - dual 0 (0), primal 0 (0)
Optimal objective 54 - 1 iterations time 0.012, Presolve 0.01
Option for printingOptions changed from normal to all
Total time (CPU seconds):       0.02   (Wallclock seconds):       0.02
Status: Optimal
x = 4.0
y = -1.0
z = 6.0
objective= 54.0
PS F:\1文件\演算法\ai\ai\02-optimize\04-linearProgramming> python americanSteel.py
C:\Users\asus1806\AppData\Local\Programs\Python\Python38\lib\site-packages\pulp\pulp.py:1199: UserWarning: Spaces are 
not permitted in the name. Converted to '_'
  warnings.warn("Spaces are not permitted in the name. Converted to '_'")
Welcome to the CBC MILP Solver 
Version: 2.9.0 
Build Date: Feb 12 2015        

command line - C:\Users\asus1806\AppData\Local\Programs\Python\Python38\lib\site-packages\pulp\apis\..\solverdir\cbc\win\64\cbc.exe C:\Users\asus1806\AppData\Local\Temp\197dcf1578f04dbcbc3419741a2f7a92-pulp.mps branch printingOptions all solution C:\Users\asus1806\AppData\Local\Temp\197dcf1578f04dbcbc3419741a2f7a92-pulp.sol (default strategy 1)        
At line 2 NAME          MODEL
At line 3 ROWS
At line 14 COLUMNS
At line 85 RHS
At line 95 BOUNDS
At line 113 ENDATA
Problem MODEL has 9 rows, 14 columns and 28 elements
Coin0008I MODEL read with 0 errors
Continuous objective value is 15005 - 0.00 seconds
Cgl0003I 0 fixed, 1 tightened bounds, 0 strengthened rows, 0 substitutions
Cgl0004I processed model has 4 rows, 6 columns (6 integer (0 of which binary)) and 10 elements
Cutoff increment increased from 1e-005 to 0.024975
Cbc0012I Integer solution of 15005 found by DiveCoefficient after 0 iterations and 0 nodes (0.01 seconds)
Cbc0001I Search completed - best objective 15005, took 0 iterations and 0 nodes (0.01 seconds)
Cbc0035I Maximum depth 0, 0 variables fixed on reduced cost
Cuts at root node changed objective from 15005 to 15005
Probing was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)       
Gomory was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)        
Knapsack was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)      
Clique was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)        
MixedIntegerRounding2 was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)
FlowCover was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)     
TwoMirCuts was tried 0 times and created 0 cuts of which 0 were active after adding rounds of cuts (0.000 seconds)    

Result - Optimal solution found

Objective value:                15005.00000000
Enumerated nodes:               0
Total iterations:               0
Time (CPU seconds):             0.02
Time (Wallclock seconds):       0.02

Option for printingOptions changed from normal to all
Total time (CPU seconds):       0.03   (Wallclock seconds):       0.03

Status: Optimal
Route_('Chicago',_'Gary') = 4000.0
Route_('Chicago',_'Tempe') = 2000.0
Route_('Cincinatti',_'Albany') = 2000.0
Route_('Cincinatti',_'Houston') = 3000.0
Route_('Kansas_City',_'Houston') = 4000.0
Route_('Kansas_City',_'Tempe') = 2000.0
Route_('Pittsburgh',_'Chicago') = 3000.0
Route_('Pittsburgh',_'Cincinatti') = 2000.0
Route_('Pittsburgh',_'Gary') = 2000.0
Route_('Pittsburgh',_'Kansas_City') = 3000.0
Route_('Youngstown',_'Albany') = 1000.0
Route_('Youngstown',_'Chicago') = 3000.0
Route_('Youngstown',_'Cincinatti') = 3000.0
Route_('Youngstown',_'Kansas_City') = 3000.0
Total Cost of Transportation =  15005.0

PS F:\1文件\演算法\ai\ai\03-search\03-puzzle> python .\puzzleSearch.py
bfs:found= True
======= backtrace =========
[1, 2, 3]
[8, 0, 4]
[7, 6, 5]

[1, 0, 3]
[8, 2, 4]
[7, 6, 5]

[1, 3, 0]
[8, 2, 4]
[7, 6, 5]

[1, 3, 4]
[8, 2, 0]
[7, 6, 5]

[1, 3, 4]
[8, 2, 5]
[7, 6, 0]

[1, 3, 4]
[8, 2, 5]
[7, 0, 6]
```

> 参考资料：百度百科、CSDN

