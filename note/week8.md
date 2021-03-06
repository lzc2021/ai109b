# 第八周

## 电脑下棋
* 五子棋，该名词来源于日本，日文亦有连五子、五子连、串珠、五目、五目碰、五格、五石、五法、五联、京棋等多种称谓；英文则称之为FIR（Five In A Row的缩写）
* 16年阿尔法go击败职业选手
* 围棋是对电脑难度最高的棋

### 电脑下棋的方法
有两个关键方式
* 《盘面评估函数》
* 《搜寻很多层对局》寻找最不容易被打败的下法
下棋的可能性最多有
标准围棋棋盘是19*19=361
225*224*...*1=255！
* 太阳系中太阳的质量占了98%，而太阳几乎都是由氢原子构成，根据太阳的阿伏伽德罗常数，太阳系的原子数约为10^60
而2^225的数量远远超过太阳系的原子数

### MiniMax算法
#### 概念表达
MiniMax算法常用于棋类等由两方较量的游戏和程序。该算法是一个零总和算法，即一方要在可选的选项中选择将其优势最大化的选择，另一方则选择令对手优势最小化的方法。而开始的时候总和为0。很多棋类游戏可以採取此算法，例如圈圈叉叉。

在下棋的时候，如果要打败对手，必须考量让自己得分最多，且让对手得分最少，Min-Max 正是根据这样的想法而设计出来的。 必须注意的是，当电脑要下一子之前，当然会下让自己得分最多的那一格，但是这很容易会落入对手的陷阱，因为得分最多的那一格很可能接下来失分更多。 于是、一个合理的想法是将所有层次分为「敌我双方」两类，我方下的那层得分越多越好，而对方下的那层失分越少越好。 而且、我们不能假设对方是个笨蛋，因此在每一层上，我们都必须认为「对方可能会下出让我们失分最多的一步」，而我们必须尽可能选择「最大失分最小化」的策略，这种想法就导出了「Min-Max 对局搜寻法」

![image](https://github.com/lzc2021/ai109b/blob/main/image/%E5%9B%BE%E7%89%879.png)

## Alpha-Beta 修剪法
Alpha-Beta 剪枝是 Minimax 对局搜寻法的一个修改版，主要是在 Minimax 当中加入了 α 与 β 两个纪录值，用来做为是否要修剪的参考标准。两个参数以交错的方式传递给下层的子树。

* 在最大层取最大值的时候，若发现了一个大于等于β 的值，就不用再对其它分枝进行搜寻，这就是所谓的 β 剪枝。
* 在最小层取最小值的时候，发现了一个小于等于α 的值，也不用再对其它分枝进行搜寻，这就是所谓的α 剪枝。
### Alpha-Beta 剪枝结论
* α-β剪枝真正关注的是(α, β)区间内的估值。对于区间之外的估值，则会引发剪枝
* Alpha-beta剪枝不会影响Minimax搜寻法的结果
* 修剪法并不保证能将对局树修剪得非常小，而且树的大小会与拜访的顺序有关，但通常应用上我们可以做到接近最佳情况(O(bm/2))。

## 恐怖谷理论
* 恐怖谷理论是一个关于人类对机器人和非人类物体的感觉的假设，在1970年被日本机器人专家森昌弘提出。其中， “恐怖谷”一词由Ernst Jentsch于1906年的论文《恐怖谷心理学》中提出，而他的观点被弗洛伊德在1919年的论文《恐怖谷》中阐述，因而成为著名理论。
* 森政弘的假设指出：由于机器人与人类在外表、动作上相似，所以人类亦会对机器人产生正面的情感；而当机器人与人类的相似程度达到一个特定程度的时候，人类对他们的反应便会突然变得极其负面和反感，哪怕机器人与人类只有一点点的差别，都会显得非常显眼刺目，从而整个机器人有非常僵硬恐怖的感觉，犹如面对行尸走肉；当机器人和人类的相似度继续上升，相当于普通人之间的相似度的时候，人类对他们的情感反应会再度回到正面，产生人类与人类之间的移情作用。

![image](https://github.com/lzc2021/ai109b/blob/main/image/%E5%9B%BE%E7%89%8710.png)

