# 第五周
## 八皇后问题
* 如何能夠在8×8的西洋棋棋盤上放置八個皇后，使得任何一個皇后都無法直接吃掉其他的皇后？為了達到此目的，任兩個皇后都不能處於同一條橫行、縱行或斜線上。
#### 概念表达
八皇后问题是回溯算法的典型案例。其问题表述为：在8×8格的国际象棋上摆放8个皇后，使其不能互相攻击，即任意两个皇后都不能处于同一行、同一列或同一斜线上，问有多少种摆法。高斯认为有76种方案。
#### 历史
八皇后问题（Eight queens），是由国际西洋棋棋手马克斯·贝瑟尔于1848年提出的问题。
1854年在柏林的象棋杂志上不同的作者发表了40种不同的解，后来有人用图论的方法解出92种结果。如果经过±90度、±180度旋转，和对角线对称变换的摆法看成一类，共有42类。计算机发明后，有多种计算机语言可以编程解决此问题。
#### 回溯算法思路
八皇后问题如果用穷举法需要尝试88=16,777,216种情况。每一列放一个皇后，可以放在第 1 行，第 2 行，……，直到第8行。穷举的时候从所有皇后都放在第1行的方案开始，检验皇后之间是否会相互攻击。如果会，把列H的皇后挪一格，验证下一个方案。移到底了就“进位”到列G的皇后挪一格，列H的皇后重新试过全部的8行。这种方法是非常低效率的，因为它并不是哪里有冲突就调整哪里，而是盲目地按既定顺序枚举所有的可能方案。

回溯算法优于穷举法。将列A的皇后放在第一行以后，列B的皇后放在第一行已经发生冲突。这时候不必继续放列C的皇后，而是调整列B的皇后到第二行，继续冲突放第三行，不冲突了才开始进入列C。如此可依次放下列A至E的皇后。将每个皇后往右边横向、斜向攻击的点位用叉标记，发现列F的皇后无处安身。这时回溯到列E的皇后，将其位置由第4行调整为第8行，进入列F，发现皇后依然无处安身，再次回溯列E。此时列E已经枚举完所有情况，回溯至列D，将其由第2行移至第7行，再进入列E继续。按此算法流程最终找到如图3所示的解，成功在棋盘里放下了8个“和平共处”的皇后。继续找完全部的解共92个。
回溯算法求解八皇后问题的原则是：有冲突解决冲突，没有冲突往前走，无路可走往回退，走到最后是答案。为了加快有无冲突的判断速度，可以给每行和两个方向的每条对角线是否有皇后占据建立标志数组。放下一个新皇后做标志，回溯时挪动一个旧皇后清除标志。

#### Code
```
def queen(n): # n 皇后主函數
	q = [] # q 代表已經排下去的皇后，一開始還沒排，所以是空的
	return queenNext(n, q) # 呼叫 queenNext 遞迴下去排出所有可能

# 思考：排到一半 q=[1,3] 繼續排下去
#      對 [1,3,0..], [1,3,1..], [1,3,2..], [1,3,3..] 全部試一遍
def queenNext(n, q): # 已經排好 q[0..y2-1], 繼續排下去 [y2...n-1]
	y2 = qlen = len(q)
	if qlen == n: # 全部排好了
		print(q)  # 印出盤面
		return
	# 還沒排滿，繼續排下去
	for x2 in range(n): # 對本列的每一個 x2 去嘗試
		isConflict = False
		for y in range(qlen): # 前面已經排下去的舊皇后，座標為 (x,y)
			x = q[y]
			if conflict(x,y,x2,y2): # 檢查新排的皇后(x2,y2)，和前面的有沒有衝突
				isConflict = True
		if not isConflict:  # 如果沒有衝突，就繼續排下去
			q.append(x2)    # 把 (x2,y2) 放進盤面
			queenNext(n, q) # 繼續遞迴尋找下一個皇后位置
			q.pop()         # 把 (x2,y2) 移出盤面
		
def conflict(x1,y1,x2,y2): # 判斷 (x1,y1), (x2,y2) 兩個位置有沒有衝突
	if x1==x2: return True
	if y1==y2: return True
	if x1+y1==x2+y2: return True
	if x1-y1==x2-y2: return True
	return False

queen(4) # 列出四皇后的解答
queen(8) # 列出八皇后的解答

```
