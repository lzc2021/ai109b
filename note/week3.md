# 第三周

## 遗传演算法

* 又稱基因演算法，模仿物競天擇，適者生存的演化機制

#### 自己的话

具有保存良好基因的特性，并且藉由下列公式不断改进，这个公式是交配机制所造成的效果：

良好基因（父）+良好基因（母）=更好的个体

简单来说就是由【物竞天择、适者生存】的淘汰机制，筛选好的个体，淘汰不好的个体。
遺傳演算法乃是透過優勝劣敗的生存法則所設計出來的一個競爭性演算法。

上述的公式不成立時，遺傳演算法也就失效了，因此该演算法也具有一定的局限性。

举例：比如key：101010 c1:011111 其中有两个数字相同

遗传算法前提是父母双方的结合会产生更好的个体，若父母双方结合产生的后代更劣等然而不如用爬山演算法进行计算

#### 概念表达
遗传演算法是根据大自然中生物体进化规律而设计提出的。是模拟达尔文生物进化论的自然选择和遗传学机理的生物进化过程的计算模型，是一种通过模拟自然进化过程搜索最优解的方法。该算法通过数学的方式,利用计算机仿真运算,将问题的求解过程转换成类似生物进化中的染色体基因的交叉、变异等过程。在求解较为复杂的组合优化问题时,相对一些常规的优化算法,通常能够较快地获得较好的优化结果。

#### 定义
遗传演算法主要特点是直接对结构对象进行操作，不存在求导和函数连续性的限定；具有内在的隐并行性和更好的全局寻优能力；采用概率化的寻优方法，不需要确定的规则就能自动获取和指导优化的搜索空间，自适应地调整搜索方向。

遗传算法以一种群体中的所有个体为对象，并利用随机化技术指导对一个被编码的参数空间进行高效搜索。其中，选择、交叉和变异构成了遗传算法的遗传操作；参数编码、初始群体的设定、适应度函数的设计、遗传操作设计、控制参数设定五个要素组成了遗传算法的核心内容。

#### 历史

遗传算法的起源可追溯到20世纪60年代初期。1967年,美国密歇根大学J. Holland教授的学生 Bagley在他的博士论文中首次提出了遗传算法这一术语,并讨论了遗传算法在博弈中的应用,但早期研究缺乏带有指导性的理论和计算工具的开拓。1975年, J. Holland等提出了对遗传算法理论研究极为重要的模式理论,出版了专著《自然系统和人工系统的适配》,在书中系统阐述了遗传算法的基本理论和方法,推动了遗传算法的发展。20世纪80年代后,遗传算法进入兴盛发展时期，被广泛应用于自动控制、生产计划、图像处理、机器人等研究领域。

#### 执行历史（部分）

```
PS F:\1文件\演算法\ai\ai\02-optimize\03-genetic> python keyGa.py > ga.out.text
============ generation 0 ===============
0 {'chromosome': '0111000001011101', 'fitness': 4}
1 {'chromosome': '1101110011011101', 'fitness': 5}
2 {'chromosome': '0100111110010101', 'fitness': 5}
3 {'chromosome': '1110000101010100', 'fitness': 5}
4 {'chromosome': '0100000111001100', 'fitness': 6}
5 {'chromosome': '0011001101010110', 'fitness': 6}
6 {'chromosome': '0100011110100101', 'fitness': 6}
7 {'chromosome': '0100010111101011', 'fitness': 7}
8 {'chromosome': '0110000000010000', 'fitness': 7}
9 {'chromosome': '0011101111010100', 'fitness': 7}
【省略】
```

## 加密技术

### 凯撒密码
* 字母位移法
#### 自己的话
通过改变每个原本字母位置的形式以达到隐藏原文的目的

#### 概念表达
在密码学中，恺撒密码（英语：Caesar cipher），或称恺撒加密、恺撒变换、变换加密，是一种最简单且最广为人知的加密技术。它是一种替换加密的技术，明文中的所有字母都在字母表上向后（或向前）按照一个固定数目进行偏移后被替换成密文。例如，当偏移量是3的时候，所有的字母A将被替换成D，B变成E，以此类推。这个加密方法是以罗马共和时期恺撒的名字命名的，当年恺撒曾用此方法与其将军们进行联系。

#### 历史
根据苏维托尼乌斯的记载，恺撒曾用此方法对重要的军事信息进行加密

同样，奥古斯都也使用过类似方式，只不过他是把字母向右移动一位，而且末尾不折回。每当他用密语写作时，他都用B代表A，C代表B，其余的字母也依同样的规则；他用A代表Z。

另外，有证据表明，恺撒曾经使用过更为复杂的密码系统：文法学家普罗布斯曾经写过一份独具创新的手稿，研究恺撒书信中包含有秘密信息的字母。

已经无法弄清恺撒密码在当时有多大的效果，但是有理由相信它是安全的。因为恺撒大部分敌人都是目不识丁的，而其余的则可能将这些消息当作是某个未知的外语。即使有某个敌人获取了恺撒的加密信息，根据现有的记载，当时也没有任何技术能够解决这一最基本、最简单的替换密码。
现存最早的破解方法记载在公元9世纪阿拉伯的阿尔·肯迪的有关发现频率分析的著作中。

### 维吉尼亚密码
* 凯撒密码的进化形态
#### 自己的话
将单一的数字位移改为一连串的位置，本质上没有超出凯撒密码的影子

#### 概念表达
维吉尼亚密码（又译维热纳尔密码）是使用一系列凯撒密码组成密码字母表的加密算法，属于多表密码的一种简单形式。

#### 历史
维吉尼亚密码曾多次被发明。该方法最早记录在吉奥万·巴蒂斯塔·贝拉索（ Giovan Battista Bellaso）于1553年所著的书《吉奥万·巴蒂斯塔·贝拉索先生的密码》（意大利语：La cifra del. Sig. Giovan Battista Bellaso）中。然而，后来在19世纪时被误传为是法国外交官布莱斯·德·维吉尼亚（Blaise De Vigenère）所创造，因此现在被称为“维吉尼亚密码”。


### XOR密码
* 逻辑运算之中，除了 AND 和 OR，还有一种 XOR 运算，中文称为"异或运算"。
#### 概念表达
异或是对两个运算元的一种逻辑分析类型，符号为XOR或EOR。与一般的逻辑或OR不同，当两两数值相同为否，而数值不同时为真。异或密码（simple XOR cipher）是密码学中一种简单的加密算法，是指对信息进行异或操作来达到加密和解密目的。按这种逻辑，文本串行的每个字符可以通过与给定的密钥进行按位异或运算来加密。如果要解密，只需要将加密后的结果与密钥再次进行按位异或运算即可。

```
true XOR true // false
false XOR false // false
true XOR false // true
true XOR false // true
```

![](https://github.com/lzc2021/ai109b/blob/main/image/%E5%9B%BE%E7%89%877.png)





> 参考资料：百度百科、简书、CSDN