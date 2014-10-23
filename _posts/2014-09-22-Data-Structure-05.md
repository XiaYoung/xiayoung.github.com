---
layout : post
category : mse
tags : [Data structure]
--- 
##第六章 树与二叉树 

### **第一节 树的概念与基本术语**  

####  一、树的定义（string）  

*  树是有n(n≥0)个结点的有限集合。
*  如果 n = 0, 称为空树；
*  如果 n>0,称为非空树，对于非空树，有且仅有一个特定的称为根（Root）的结点（无直接前驱）
*  如果n>1, 则除根以外的其它结点划分为m(m>0)个互不相交的有限集 T1，T2，..., Tm, 其中每个集合本身又是一棵树， 并且称为根的子树（SubTree）.
*  每个结点都有唯一的直接前驱，但可能有多个后继
* 例子  

<svg width="200" height="200">
  <circle r="20" cy="100" cx="100" stroke-width="2" stroke="#000" fill="red"/>
  <text x="100" y="100" font-size="16" fill="#000">A</text>
  <text x="20" y="150" font-size="16" fill="#000">只有根节点的树</text>
  
</svg>  

<svg width="400" height="400">

  <line x1="100" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="200" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="300" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="70" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="130" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="200" y1="240" x2="200" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="250" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" />  
  <line x1="300" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="350" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="40" y1="320" x2="70" y2="240" style ="stroke-width: 2; stroke: #00ff00;" />   
  <line x1="110" y1="320" x2="70" y2="240" style ="stroke-width: 2; stroke: #00ff00;" />   
  <line x1="250" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <circle r="20" cx="200" cy="80" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="80"  fill="#000">A</text>

  <circle r="20" cx="100" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="100" y="160" fill="#000">B</text>
  <circle r="20" cx="200"  cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="160" fill="#000">C</text>
  <circle r="20" cx="300" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="160" fill="#000">D</text>

  <circle r="20" cx="70" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="70" y="240" fill="#000">E</text>
  <circle r="20" cx="130" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="130" y="240" fill="#000">F</text>
  <circle r="20" cx="200"  cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="240" fill="#000">G</text>
  <circle r="20" cx="250" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="240" fill="#000">H</text>
  <circle r="20" cx="300" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="240" fill="#000">I</text>
  <circle r="20" cx="350" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="350" y="240" fill="#000">J</text>
 
  <circle r="20" cx="40" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="40" y="320" fill="#000">K</text>
  <circle r="20" cx="110" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="110" y="320" fill="#000">L</text>
  <circle r="20" cx="250" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="320" fill="#000">M</text>
  <text font-size="16" x="270" y="320" fill="#000">有13个结点的树</text>
  
</svg>  

*  其中：A是根；其余结点分成三个互不相交的子集
* T1 ={B, E, F, K, L}; T2={C, G}; T3={D, H, I, J,M}
* T1 T2 T3都是跟A的子树，且本身也是一棵树

####  二、树的基本术语  

*  **结点**：包含一个数据元素及若干指向其子树的分支
* **结点的度**：结点拥有的子树数
* **叶节点**：度为0的结点[没有子树的结点]
* **分支结点**： 度不为0的结点[包括根结点]，也称为非终端结点。除根外称为内部结点
* **孩子**：结点的子树的根[直接后继，可能有多个]
* **双亲**：孩子的直接前驱[最多只能有一个] 
* **兄弟**：同一双亲的孩子
* **子孙**：以某结点为根的树中的所有节点
* **祖先**：从根到该结点所经分支上的所有结点
* **层次**：根节点为第一层，其孩子为第二层，依次类推
* **深度**：树中结点的最大层次
* **森林**：互不相交的树的集合。对树中每个结点而言，其子树的集合即为森林

### **第二节 二叉树**  

####  一、二叉树（Binary Tree）   

*  每个节点最多有2棵子树
*  二叉树的子树有左右之分
* 种类
	* 空树
	* 只有根
	* 只有左子树
	* 只有右子树
	* 有左右子树

####  二、二叉树性质    

*  性质1
	*  在二叉树的第i层上至多有$$2^{i-1}$$个结点
	*  证明：
	1. i = 1, 只有一个根节点，因此$$2^{i-1} = 2^0 = 1$$  
	2. 设第i-1层上，以上性质成立，即第i-1层至多有$$2^{(i-1)-1}$$结点。由二叉树的定义可知，任何结点的度小于2，因此，第i层上的结点数最多为第i-1层上的两倍，即$$2*2^{i-2} = 2^{i-1}$$  
	
* 性质2  

	*  深度为k的二叉树至多有$$2^k-1$$个结点 
	*  证明：
		1. 由性质1，已知第i层上的结点数最多为$$2^{i-1}$$ 
		2. $$\sum_{i=1}^{k}{2^{i-1}}=2^k-1$$

* 性质3  
  
	*  如果二叉树终端结点数为$$n_0$$，度为2的结点数为$$n_2$$，则$$n_0=n_2+1$$  
	*  证明：
		1. 设$$n_1$$为度为1的结点，则总结点数$$n=n_0+n_1+n_2$$  
		2. 设B为二叉树的分支数，除根结点外，每个结点有且只有一个（上游）分支，因此	总结点数n = B+1
		3. 每个分支皆有度为1或2的结点发出，$$B = n_1+2n_2$$  
		4. $$n = B+1 = (n_1+2n_2)+1 = n_0+n_1+n_2$$, 因此 $$n_0=+n_2+1$$  

####  三、满二叉树  

*  一个深度为k且有$$2^{k-1}$$个结点的二叉树 
*  每层上的结点数都是最大数
*  可以自上而下，自左至右连续编号

<svg width="400" height="400">

  <line x1="100" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="300" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="50" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="150" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="250" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="350" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" />  
  
  <line x1="25" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
   <line x1="75" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" />   
  
  <line x1="125" y1="320" x2="150" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="175" y1="320" x2="150" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
      
  <line x1="225" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="275" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 

  <line x1="325" y1="320" x2="350" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="375" y1="320" x2="350" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
     
  <circle r="20" cx="200" cy="80" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="80"  fill="#000">1</text>

  <circle r="20" cx="100" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="100" y="160" fill="#000">2</text>
  <circle r="20" cx="300"  cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="160" fill="#000">3</text>

  <circle r="20" cx="50" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="50" y="240" fill="#000">4</text>
  <circle r="20" cx="150" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="150" y="240" fill="#000">5</text>
  
  <circle r="20" cx="250"  cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="240" fill="#000">6</text>
  <circle r="20" cx="350" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="350" y="240" fill="#000">7</text>
  
  <circle r="20" cx="25" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="25" y="320" fill="#000">8</text>
  <circle r="20" cx="75" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="75" y="320" fill="#000">9</text>
  
   <circle r="20" cx="125" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="125" y="320" fill="#000">10</text>
  <circle r="20" cx="175" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="175" y="320" fill="#000">11</text>

  <circle r="20" cx="225" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="225" y="320" fill="#000">12</text>
  <circle r="20" cx="275" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="275" y="320" fill="#000">13</text>
  
   <circle r="20" cx="325" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="325" y="320" fill="#000">14</text>
  <circle r="20" cx="375" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="375" y="320" fill="#000">15</text>
  
</svg>  


####  四、完全二叉树  

*  当且仅当每一个结点都与深度相同的满二叉树中编号从1到n的结点一一对应的二叉树
* 叶子结点只在最大的两层上出现
* 左子树深度与右子树深度相等或大1

<svg width="400" height="400">

  <line x1="100" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="300" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="50" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="150" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="250" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="350" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" />  
  
  <line x1="25" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
   <line x1="75" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" />   
  
  <line x1="125" y1="320" x2="150" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="175" y1="320" x2="150" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
      
  <line x1="225" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 

  <circle r="20" cx="200" cy="80" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="80"  fill="#000">1</text>

  <circle r="20" cx="100" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="100" y="160" fill="#000">2</text>
  <circle r="20" cx="300"  cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="160" fill="#000">3</text>

  <circle r="20" cx="50" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="50" y="240" fill="#000">4</text>
  <circle r="20" cx="150" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="150" y="240" fill="#000">5</text>
  
  <circle r="20" cx="250"  cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="240" fill="#000">6</text>
  <circle r="20" cx="350" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="350" y="240" fill="#000">7</text>
  
  <circle r="20" cx="25" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="25" y="320" fill="#000">8</text>
  <circle r="20" cx="75" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="75" y="320" fill="#000">9</text>
  
   <circle r="20" cx="125" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="125" y="320" fill="#000">10</text>
  <circle r="20" cx="175" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="175" y="320" fill="#000">11</text>

  <circle r="20" cx="225" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="225" y="320" fill="#000">12</text>
  
</svg>  

#### 五、完全二叉树性质

*  性质 4 
	*  具有n个结点的完全二叉树，其深度为$$log_2n + 1$$  
	*  设k为深度， 由二叉树性质2，已知  
	$$2^{k-1}-1 < n \le 2^k -1$$    
	即 $$2^{k-1}\le n < 2^k $$  
	$$k-1 \le log_2n <k$$  
	$$k = log_2n + 1$$   
*  性质 5
	*  在完全二叉树中，结点i的双亲为i/2
	*  结点i的左孩子LCHILD(i) = 2i
	*  结点i的右孩子RCHILD(i) = 2i+1

####  六、二叉树的顺序存储结构  

* 用一组连续的存储单元依次自上而下，自左而右存储结点

<svg width="400" height="400">

  <line x1="100" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="300" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="50" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="150" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="250" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="350" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" />  
  
  <line x1="25" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
   <line x1="75" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" />   
  
  <line x1="125" y1="320" x2="150" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 


  <circle r="20" cx="200" cy="80" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="80"  fill="#000">1</text>

  <circle r="20" cx="100" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="100" y="160" fill="#000">2</text>
  <circle r="20" cx="300"  cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="160" fill="#000">3</text>

  <circle r="20" cx="50" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="50" y="240" fill="#000">4</text>
  <circle r="20" cx="150" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="150" y="240" fill="#000">5</text>
  
  <circle r="20" cx="250"  cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="240" fill="#000">6</text>
  <circle r="20" cx="350" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="350" y="240" fill="#000">7</text>
  
  <circle r="20" cx="25" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="25" y="320" fill="#000">8</text>
  <circle r="20" cx="75" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="75" y="320" fill="#000">9</text>
  
   <circle r="20" cx="125" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="125" y="320" fill="#000">10</text>
  
</svg>  

完全二叉树的顺序表示  
1 2 3 4 5 6 7 8 9 10  

<svg width="400" height="400">

  <line x1="100" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="300" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  
  <line x1="50" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
    
  <line x1="250" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="350" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" />  
  
  <line x1="25" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
   <line x1="75" y1="320" x2="50" y2="240" style ="stroke-width: 2; stroke: #00ff00;" />   
 
  <line x1="225" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <line x1="275" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 

  <circle r="20" cx="200" cy="80" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="80"  fill="#000">1</text>

  <circle r="20" cx="100" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="100" y="160" fill="#000">2</text>
  <circle r="20" cx="300"  cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="160" fill="#000">3</text>

  <circle r="20" cx="50" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="50" y="240" fill="#000">4</text>
  
  <circle r="20" cx="250"  cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="240" fill="#000">5</text>
  <circle r="20" cx="350" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="350" y="240" fill="#000">6</text>
  
  <circle r="20" cx="25" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="25" y="320" fill="#000">7</text>
  <circle r="20" cx="75" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="75" y="320" fill="#000">8</text>

  <circle r="20" cx="225" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="225" y="320" fill="#000">9</text>
  <circle r="20" cx="275" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="275" y="320" fill="#000">10</text>
  

  
</svg>  

一般二叉树的顺序表示

1 2 3 4  **0** 5 6 7 8 **0** **0** 9 10


####  七、二叉树的链式存储结构  

*   二叉链表 
	* 采用数据域加上左、右孩子指针
	* 定义：
	二叉链表结点由一个数据域和两个指针域组成
		
			typedef struct BiTNode 
			{
				TElemType data;
				struct BiTNode *lChild, *rChild;
			} BiTNode, *BiTree;
	*  例子：  
	
<svg width="580" height="400">
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_11" y2="287.5" x2="197.5" y1="170.5" x1="117.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="19" rx="22" id="svg_1" cy="272.5" cx="198" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_10" y2="207.5" x2="87.5" y1="111.5" x1="142.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="19" rx="22" id="svg_2" cy="102.5" cx="143" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19" rx="22" id="svg_3" cy="156.5" cx="114" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19" rx="22" id="svg_4" cy="213.5" cx="86" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_12" y2="275.5" x2="112.5" y1="213.5" x1="153.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="19" rx="22" id="svg_5" cy="213.5" cx="155" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19" rx="22" id="svg_6" cy="272.5" cx="116" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_7" height="24" width="33" y="256.5" x="523.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_8" height="24" width="33" y="256.5" x="457.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_9" height="24" width="33" y="256.5" x="490.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_16" height="24" width="33" y="88.5" x="407.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_17" height="24" width="33" y="88.5" x="341.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_18" height="24" width="33" y="88.5" x="374.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_19" height="24" width="33" y="144.5" x="375.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_20" height="24" width="33" y="144.5" x="309.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_21" height="24" width="33" y="144.5" x="342.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_22" height="24" width="33" y="197.5" x="339.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_23" height="24" width="33" y="197.5" x="273.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_24" height="24" width="33" y="197.5" x="306.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_25" height="24" width="33" y="198.5" x="457.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_26" height="24" width="33" y="198.5" x="391.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_27" height="24" width="33" y="198.5" x="424.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_28" height="24" width="33" y="256.5" x="399.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_29" height="24" width="33" y="256.5" x="333.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <rect id="svg_30" height="24" width="33" y="256.5" x="366.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_31" y="107.5" x="383.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">A</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_32" y="164.5" x="351.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_33" y="220.5" x="311.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_34" y="219.5" x="432.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">D</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_35" y="279.5" x="377.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">E</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_36" y="276.5" x="498.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">F</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_37" y="104.5" x="131.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">A</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_38" y="162.5" x="106.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_39" y="215.5" x="79.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_40" y="221.5" x="147.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">D</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_41" y="279.5" x="105.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">E</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_42" y="280.5" x="186.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">F</text>
  <text stroke="#000" transform="rotate(47.90452194213867 492.4684753417971,234.28985595703116) matrix(2.191050555739371,0,0,1,-348.6545940732784,52.55037055154315) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_43" y="190.26057" x="371.85695" stroke-opacity="null" stroke-width="0" fill="#729C62">→</text>
  <text stroke="#000" transform="rotate(129.0565185546875 339.7568359375,125.55036926269533) matrix(1.9175889492034905,0,0,1,-252.01412006989466,52.55037055154315) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_44" y="81.5" x="296.5" stroke-opacity="null" stroke-width="0" fill="#729C62">→</text>
  <text stroke="#000" transform="rotate(129.0565185546875 310.701171875,182.4039001464844) matrix(1.9175889492034905,0,0,1,-252.01412006989466,52.55037055154315) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_45" y="138.5" x="281.37684" stroke-opacity="null" stroke-width="0" fill="#729C62">→</text>
  <text stroke="#000" transform="rotate(129.0565185546875 398.1529846191406,237.7916107177734) matrix(2.2545899241177088,0,0,1,-370.428720728341,52.55037055154315) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_46" y="193.74125" x="328.79511" stroke-opacity="null" stroke-width="0" fill="#729C62">→</text>
  <text stroke="#000" transform="rotate(47.90452194213867 419.48315429687506,178.2925720214843) matrix(2.191050555739371,0,0,1,-348.6545940732784,52.55037055154315) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_47" y="134.26057" x="338.5396" stroke-opacity="null" stroke-width="0" fill="#729C62">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_48" y="278.5" x="537.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_49" y="111.5" x="419.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_50" y="224.5" x="283.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_51" y="223.5" x="354.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_52" y="281.5" x="345.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_53" y="281.5" x="412.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_54" y="282.5" x="468.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
</svg>    


*  三叉链表   

### **第三节 遍历二叉树**  

####  一、遍历二叉树   

*  树的遍历就是按某种次序访问树中的结点，要求每个结点访问一次且仅访问一次
*  一个二叉树由根节点与左子树和右子树组成
*  设访问根结点用D表示，遍历左、右子树用L、R表示
*  如果规定**先左子树后右子树**，则共有三种组合
	* DLR 先序遍历 先根遍历
	* LDR 中序遍历 中根遍历 
	* LRD 后序遍历 后根遍历
*  举例
<svg width="230" height="230">
  <ellipse ry="19.5" rx="19.5" id="svg_3" cy="79" cx="208" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19.5" rx="19.5" id="svg_4" cy="24" cx="132" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19.5" rx="19.5" id="svg_5" cy="78" cx="76" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19.5" rx="19.5" id="svg_6" cy="138" cx="24" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19.5" rx="19.5" id="svg_7" cy="196" cx="79" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19.5" rx="19.5" id="svg_8" cy="137" cx="176" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="19.5" rx="19.5" id="svg_9" cy="138" cx="117" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="84.5" x="68.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_11" y="30.5" x="124.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">A</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="145.5" x="167.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">F</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_13" y="146.5" x="15.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">D</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="147.5" x="107.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">E</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_15" y="205.5" x="70.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">G</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="88.5" x="199.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">C</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_17" y2="67.5" x2="94.5" y1="40.5" x1="122.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_18" y2="125.5" x2="39.5" y1="95.5" x1="64.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_19" y2="67.5" x2="191.5" y1="41.5" x1="147.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_20" y2="119.5" x2="187.5" y1="99.5" x1="200.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_21" y2="124.5" x2="110.5" y1="95.5" x1="89.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_22" y2="179.5" x2="93.5" y1="155.5" x1="110.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
</svg>

	*  先序遍历  ABDEGCF
	*  中序遍历 DBGEAFC
	*  后序遍历 DGEBFCA


#### 二、先序遍历二叉树  

*  算法
	1. 若二叉树为空，则返回；否则：
	2. 访问根节点(D)
	3. 先序遍历左子树(L)
	4. 先序遍历右子树(R)

*  C语言实现

		void PreOrderTraverse ( BinTree T) {
			if (T) {
				cout << T->data;
				PreOrderTraverse ( T->lChild );
				PreOrderTraverse ( T->rChild );
			}
		}
*  特性
	*  先序遍历中，第一个输出节点必为根节点
	*  先序遍历序列，由
		* 根 + 左子树先序遍历序列 + 右子树先序遍历序列

#### 三、中序遍历二叉树  

*  算法
	1. 若二叉树为空，则返回；否则：
	2. 中序遍历左子树(L)
	3. 访问根节点(D)
	4. 中序遍历右子树(R)
*  C语言实现

		void InOrderTraverse ( BinTree T) {
			if (T) {
				InOrderTraverse ( T->lChild );
				cout << T->data;
				InOrderTraverse ( T->rChild );
			}
		}
*  特性
	*  中序遍历中，先于根节点D输出的节点为左子树L的节点，后于根节点D输出的节点为右子树R的节点
	*  先序遍历序列，由
		* 左子树中序遍历序列 + 根 +  右子树中序遍历序列

#### 四、后序遍历二叉树  

*  算法
	1. 若二叉树为空，则返回；否则：
	2. 后序序遍历左子树(L)
	3. 后序遍历右子树(R)
	4. 访问根节点(D)

*  C语言实现

		void PostOrderTraverse ( BinTree T) {
			if (T) {
				PostOrderTraverse ( T->lChild );
				PostOrderTraverse ( T->rChild );
				cout << T->data;
			}
		}
*  特性
	*  先序遍历中，最后一个输出节点必为根节点
	*  先序遍历序列，由
		* 左子树后序遍历序列 + 右子树后序遍历序列 + 根  

#### 五、根据先、中序遍历求序列二叉树

*  如果已知一棵二叉树的先序遍历和中序遍历序列，则可以惟一确定这棵二叉树
*  算法：
	1. 在先序遍历序列中，第一个节点为根节点D，之后跟左子树先序遍历序列 + 右子树先序遍历序列
	2. 在中序遍历序列中，根节点D左边的节点归为左子树L，根节点D右边的节点归为右子树R
	3. 对每个子树反复使用1，2两步，直到确定二叉树

#### 六、根据后、中序遍历求序列二叉树  

*  如果已知一棵二叉树的后序遍历和中序遍历序列，则可以惟一确定这棵二叉树
*  算法：
	1. 在后序遍历序列中，最后一个节点为根节点D，前为左子树先序遍历序列 + 右子树先序遍历序列
	2. 在中序遍历序列中，根节点D左边的节点归为左子树L，根节点D右边的节点归为右子树R
	3. 对每个子树反复使用1，2两步，直到确定二叉树

### **第四节 线索二叉树**  

####  一、增加新指针  

*  最简单的方法是在每个结点中，增加前驱(fwd)和后继(bkwd)指针
	* fwd lChild data rChild bkwd
*  在做二叉树遍历（前、中、后序），将每个结点的前驱和后继信息添入fwd和bkwd域中

####  二、利用空指针  

*  在有n个结点的二叉树中，必定存在n+1个空链域
*  因为每个结点有两个链域（左、右孩子指针），因此共有2n个链域
*  除根结点外（根节点没有）、每个结点都有且仅有一个分支相连（在它们头顶上，别的结点连到它们），即n-1个链域被使用
*  在结点中增加两个标记位（LTag , RTag）
	*  LTag lChild data rChild RTag
	* LTag = 0, lChild 域指示结点的左孩子  
	  LTag = 1, lChild 域指示结点的前驱结点
	* RTag = 0, rChild 域指示结点的左孩子  
	  RTag = 1, rChild 域指示结点的后继结点

### **第五节 树与森林**  

####  一、树的存储结构  

<svg width="240" height="170">
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="208" cy="79" id="svg_3" rx="19.5" ry="19.5"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="132" cy="24" id="svg_4" rx="19.5" ry="19.5"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="76" cy="78" id="svg_5" rx="19.5" ry="19.5"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="24" cy="138" id="svg_6" rx="19.5" ry="19.5"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="143" cy="80" id="svg_7" rx="19.5" ry="19.5"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="176" cy="137" id="svg_8" rx="19.5" ry="19.5"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="117" cy="138" id="svg_9" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="68.5" y="84.5" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="124.5" y="30.5" id="svg_11" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="110.5" y="145.5" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">F</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="200.5" y="88.5" id="svg_13" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">D</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="15.5" y="146.5" id="svg_14" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">E</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="168.5" y="144.5" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">G</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="134.5" y="88.5" id="svg_16" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="122.5" y1="40.5" x2="94.5" y2="67.5" id="svg_17" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="64.5" y1="95.5" x2="39.5" y2="125.5" id="svg_18" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="147.5" y1="41.5" x2="191.5" y2="67.5" id="svg_19" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="200.5" y1="99.5" x2="187.5" y2="119.5" id="svg_20" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="89.5" y1="95.5" x2="110.5" y2="124.5" id="svg_21" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_2" y2="59.5" x2="141.5" y1="42.5" x1="129.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
</svg>

*  双亲表示法
	* 采用一组连续的存储空间
	* 由于每个结点只有一个双亲，只需要一个指针
	
	|0|1|2|3|4|5|6|7|
	|-
	||A|B|C|D|E|F|G|
	||0|1|1|1|2|2|4
	
*  孩子表示法[多链表]
	* 可以采用多重链表，即每个结点有多个指针
	
		|data|child1|child2|child3|......|childd|
		|-
	* 最大缺点是空链域太多 
		* [(d-1)n+1个]
*  孩子表示法[单链表]
	* 将每个结点的孩子排列起来，用单链表表示
	* 将每个结点排列成一个线性表  
<svg width="411" height="223" xmlns="http://www.w3.org/2000/svg">
 <!-- Created with Method Draw - http://github.com/duopixel/Method-Draw/ -->

 <g>
  <title>background</title>
  <rect x="-1" y="-1" width="207.50317" height="113.50172" id="canvas_background" fill="#fff"/>
  <g id="canvasGrid" display="none">
   <rect id="svg_27" width="100%" height="100%" x="0" y="0" stroke-width="0" fill="url(#gridpattern)"/>
  </g>
 </g>
 <g>
  <title>Layer 1</title>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="186.49884" width="72" height="28" id="svg_1"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="186.49884" x2="74.99956" y2="214.51669" id="svg_2" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="131.99956" y="96.49884" width="72" height="28" id="svg_3"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="174.99956" y1="96.49884" x2="174.99956" y2="124.51669" id="svg_4" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="36.49884" width="72" height="28" id="svg_5"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="36.49884" x2="74.99956" y2="64.51669" id="svg_6" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="66.49884" width="72" height="28" id="svg_7"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="66.49884" x2="74.99956" y2="94.51669" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="96.49884" width="72" height="28" id="svg_9"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="96.49884" x2="74.99956" y2="124.51669" id="svg_10" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="126.49884" width="72" height="28" id="svg_11"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="126.49884" x2="74.99956" y2="154.51669" id="svg_12" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="156.49884" width="72" height="28" id="svg_13"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="156.49884" x2="74.99956" y2="184.51669" id="svg_14" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="31.99956" y="6.49884" width="72" height="28" id="svg_15"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="74.99956" y1="6.49884" x2="74.99956" y2="34.51669" id="svg_16" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="131.99956" y="46.49884" width="72" height="28" id="svg_17"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="174.99956" y1="46.49884" x2="174.99956" y2="74.51669" id="svg_18" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="231.99956" y="46.49884" width="72" height="28" id="svg_19"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="274.99956" y1="46.49884" x2="274.99956" y2="74.51669" id="svg_20" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="131.99956" y="6.49884" width="72" height="28" id="svg_21"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="174.99956" y1="6.49884" x2="174.99956" y2="34.51669" id="svg_22" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="231.99956" y="6.49884" width="72" height="28" id="svg_23"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="274.99956" y1="6.49884" x2="274.99956" y2="34.51669" id="svg_24" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="331.99956" y="6.49884" width="72" height="28" id="svg_25"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="374.99956" y1="6.49884" x2="374.99956" y2="34.51669" id="svg_26" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="97.90228" y1="110.49809" x2="131.21002" y2="110.49809" id="svg_34" stroke-linejoin="null" stroke-linecap="null" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="123.47326" y1="102.73211" x2="131.57179" y2="110.83065" id="svg_35" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="131.54343" y1="110.83153" x2="123.99728" y2="118.37767" id="svg_36" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="98.42858" y1="19.7093" x2="131.73633" y2="19.7093" id="svg_127" stroke-linejoin="null" stroke-linecap="null" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="123.99956" y1="11.94332" x2="132.0981" y2="20.04186" id="svg_128" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="132.06974" y1="20.04274" x2="124.52359" y2="27.58888" id="svg_129" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="196.8489" y1="20.23561" x2="230.15664" y2="20.23561" id="svg_130" stroke-linejoin="null" stroke-linecap="null" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="222.41988" y1="12.46963" x2="230.51842" y2="20.56817" id="svg_131" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="230.49005" y1="20.56905" x2="222.9439" y2="28.1152" id="svg_132" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="297.63761" y1="19.7093" x2="330.94536" y2="19.7093" id="svg_133" stroke-linejoin="null" stroke-linecap="null" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="323.20859" y1="11.94332" x2="331.30713" y2="20.04186" id="svg_134" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="331.27876" y1="20.04274" x2="323.73261" y2="27.58888" id="svg_135" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="197.37521" y1="59.709" x2="230.68295" y2="59.709" id="svg_136" stroke-linejoin="null" stroke-linecap="null" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="222.94619" y1="51.94302" x2="231.04473" y2="60.04156" id="svg_137" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="231.01636" y1="60.04243" x2="223.47021" y2="67.58858" id="svg_138" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="99.21806" y1="56.81428" x2="132.5258" y2="56.81428" id="svg_139" stroke-linejoin="null" stroke-linecap="null" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="124.78904" y1="49.0483" x2="132.88757" y2="57.14684" id="svg_140" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="132.85921" y1="57.14772" x2="125.31306" y2="64.69387" id="svg_141" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="147.24781" y="118.74873" id="svg_142" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="148.24782" y="28.24734" id="svg_144" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="251.24942" y="27.74733" id="svg_145" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="348.75093" y="29.24735" id="svg_146" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="145.74778" y="68.24795" id="svg_147" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="251.74942" y="67.74795" id="svg_148" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="48.24627" y="207.25011" id="svg_149" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">G</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.74622" y="28.74735" id="svg_150" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="45.74624" y="58.74781" id="svg_151" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.24624" y="88.24827" id="svg_152" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.24624" y="118.74874" id="svg_153" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">D</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="47.24626" y="149.24921" id="svg_154" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">E</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="47.74627" y="179.24967" id="svg_155" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">F</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="7.74565" y="29.24736" id="svg_156" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="183.24837" y="120.74876" id="svg_162" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="383.25147" y="28.74734" id="svg_165" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="284.74994" y="71.248" id="svg_166" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="8.74567" y="59.24782" id="svg_167" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="9.24568" y="88.74828" id="svg_168" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="9.24568" y="119.24875" id="svg_169" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="9.24568" y="149.74922" id="svg_170" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="10.7457" y="179.74968" id="svg_171" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="11.24571" y="207.75011" id="svg_172" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
 </g>
</svg>

* 孩子兄弟表示法
	* 采用二叉链表
	|data|firstChild|nextSibling|
	|-
	
	* 左边指针指向第一个孩子，右边指针指向兄弟   
<svg width="411" height="223" xmlns="http://www.w3.org/2000/svg">
 <!-- Created with Method Draw - http://github.com/duopixel/Method-Draw/ -->

 <g>
  <title>background</title>
  <rect x="-1" y="-1" width="413.00067" height="225.00037" id="canvas_background" fill="#fff"/>
  <g id="canvasGrid" display="none">
   <rect id="svg_27" width="100%" height="100%" x="0" y="0" stroke-width="0" fill="url(#gridpattern)"/>
  </g>
 </g>
 <g>
  <title>Layer 1</title>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="234.99818" y="188.83216" width="87" height="28" id="svg_1"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="297.33138" y1="188.16549" x2="297.33138" y2="216.18334" id="svg_2" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="81.33256" y="53.49872" width="87" height="28" id="svg_5"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="143.66576" y1="52.83206" x2="143.66576" y2="80.84991" id="svg_6" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="188.66516" y="94.83198" width="87" height="28" id="svg_7"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="250.99836" y1="94.16532" x2="250.99836" y2="122.18317" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="317.66427" y="142.49853" width="87" height="28" id="svg_9"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="379.99748" y1="141.83186" x2="379.99748" y2="169.84971" id="svg_10" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="13.33302" y="95.49905" width="87" height="28" id="svg_11"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="75.66622" y1="94.83239" x2="75.66622" y2="122.85024" id="svg_12" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="83.66587" y="146.49891" width="87" height="28" id="svg_13"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="145.99907" y1="145.83225" x2="145.99907" y2="173.8501" id="svg_14" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" x="152.6654" y="5.83218" width="87" height="28" id="svg_15"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="214.9986" y1="5.16552" x2="214.9986" y2="33.18337" id="svg_16" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="272.91141" y="210.25009" id="svg_149" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">G</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="187.07858" y="28.74735" id="svg_150" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="116.74575" y="76.41436" id="svg_151" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="224.57836" y="117.24807" id="svg_152" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="353.57747" y="165.41509" id="svg_153" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">D</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="50.24624" y="118.91608" id="svg_154" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">E</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="121.0791" y="169.9164" id="svg_155" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">F</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="260.33163" y1="188.83216" x2="260.33163" y2="216.85001" id="svg_22" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="106.66601" y1="53.49872" x2="106.66601" y2="81.51657" id="svg_23" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="213.99862" y1="94.83198" x2="213.99862" y2="122.84983" id="svg_24" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="342.99773" y1="142.49853" x2="342.99773" y2="170.51638" id="svg_25" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="38.66648" y1="95.49905" x2="38.66648" y2="123.5169" id="svg_26" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="108.99933" y1="146.49891" x2="108.99933" y2="174.51676" id="svg_28" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="177.99885" y1="5.83218" x2="177.99885" y2="33.85003" id="svg_29" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="328.42841" y1="162.47587" x2="293.42829" y2="193.47598" id="svg_30" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="293.57144" y1="194" x2="296.42858" y2="187.80952" id="svg_31" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="294.28572" y1="193.76191" x2="299.52382" y2="190.66667" id="svg_32" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="161.99983" y1="21.99968" x2="126.99971" y2="52.99979" id="svg_33" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="127.14286" y1="53.52381" x2="130" y2="47.33333" id="svg_34" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="127.85715" y1="53.28572" x2="133.09524" y2="50.19048" id="svg_35" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="93.4284" y1="64.85682" x2="58.42828" y2="95.85693" id="svg_36" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="58.57143" y1="96.38095" x2="61.42857" y2="90.19048" id="svg_37" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="59.28572" y1="96.14286" x2="64.52381" y2="93.04762" id="svg_38" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="79.76192" y1="115.42857" x2="143.80954" y2="142.09524" id="svg_42" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="143.57144" y1="141.61905" x2="139.52382" y2="136.85714" id="svg_43" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="143.09525" y1="141.38095" x2="136.90477" y2="142.09524" id="svg_44" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="161.90477" y1="65.90476" x2="225.95239" y2="92.57143" id="svg_45" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="225.71429" y1="92.09524" x2="221.66667" y2="87.33334" id="svg_46" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="225.2381" y1="91.85715" x2="219.04763" y2="92.57143" id="svg_47" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="266.42858" y1="112.80953" x2="330.4762" y2="139.47619" id="svg_48" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="330.23811" y1="139" x2="326.19049" y2="134.2381" id="svg_49" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="329.76192" y1="138.76191" x2="323.57144" y2="139.47619" id="svg_50" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_3" y="215" x="307" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="34" x="221" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_17" y="121" x="21" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="122" x="196" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_19" y="173" x="91" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_20" y="174" x="153" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_21" y="166" x="387" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_39" y="216" x="241" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">^</text>
 </g>
</svg>

####  二、树与二叉树的对应关系  

*  树与二叉树都可以采用二叉链表作存储结构 （孩子兄弟）
*  任意给定一棵树，可以找到一个唯一的二叉树（没有右子树）

####  三、森林与二叉树的对应关系  

*  如果把森林中的第二棵树的根结点看作是第一棵树的根结点的兄弟，则可找到一个唯一的二叉树与之对应

####  四、树的遍历    

*  对树的遍历主要有两种
	* 先根（次序）遍历
		* 当树非空时
			* 访问根结点
			* 依次先根遍历根的各棵子树 
	* 后根（次序）遍历
		* 当树非空时
			* 依次后根遍历根的各棵子树 
			* 访问根结点
*  与二叉树遍历的关系
	* 当采用孩子兄弟表示法表示树时
	* 树的先根遍历，与树对应的二叉树的先根遍历完全相同
	* 树的后根遍历，与树对应的二叉树的中根遍历完全相同

### **第六节 霍夫曼树及其应用**  

####  一、最优二叉树  

*  路径：从树中一个结点到另一个结点之间的分支构成这两个结点之间的路径
*  路径长度：路径上的分支数目
*  树的路径长度：从树根到每个结点的路径长度之和
*  带权路径长度：从结点到树根之间的路径长度与结点上权的乘积
*  树的带权路径长度（WPL）：树中所有**叶子结点**的带权路径长度之和
*  最优二叉树：假设二叉树有n个叶子，其每个叶子结点带权 wi，则带权路径长度wpl最小的二叉树称为最优二叉树
*  赫夫曼Huffman树就是一棵最优二叉树

####  二、Huffman树

##### 构造  

*  在Huffman树中，权值最大的结点离根最近
*  权值最小的结点离根最远

##### 算法  

1. 根据给定的n个权值$$(w_1, w_2, ..., w_n)$$ 构成n棵二叉树的集合$$F= \{T_1, T_2, ..., T_n\}$$, 其中每棵二叉树$$T_i$$中只有一个权值为 $$w_i$$ 的根节点
2. 在F中选取两棵根结点的权值最小的树作为左右子树构造一棵新的二叉树，且置其根结点的权值为其左右子树权值之和
3. 在F中删除这两棵树，同时将新得到的二叉树加入F中
4. 重复2，3，直到F只含一棵树为止  

##### 举例   
 
 <svg width="533" height="289" xmlns="http://www.w3.org/2000/svg">
 <!-- Created with Method Draw - http://github.com/duopixel/Method-Draw/ -->
 <g>
  <title>background</title>
  <rect fill="#fff" id="canvas_background" height="291" width="535" y="-1" x="-1"/>
  <g display="none" overflow="visible" y="0" x="0" height="100%" width="100%" id="canvasGrid">
   <rect fill="url(#gridpattern)" stroke-width="0" y="0" x="0" height="100%" width="100%"/>
  </g>
 </g>
 <g>
  <title>Layer 1</title>
  <rect id="svg_1" height="29" width="43" y="254.5" x="459.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="276.5" x="474.5" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_3" height="29" width="43" y="254.5" x="406.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="276.5" x="421.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <rect id="svg_5" height="29" width="43" y="206.5" x="352.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="228.5" x="367.5" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <rect id="svg_7" height="29" width="43" y="161.5" x="302.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="183.5" x="317.5" stroke-width="0" stroke="#000" fill="#000000">7</text>
  <rect id="svg_9" height="29" width="43" y="16.5" x="184.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="38.5" x="199.5" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_11" height="29" width="43" y="16.5" x="131.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="38.5" x="146.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <rect id="svg_13" height="29" width="43" y="16.5" x="77.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="38.5" x="92.5" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <rect id="svg_15" height="29" width="43" y="16.5" x="24.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="38.5" x="39.5" stroke-width="0" stroke="#000" fill="#000000">7</text>
  <ellipse ry="15.5" rx="26" id="svg_17" cy="135" cx="370.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="143.5" x="356.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">18</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_19" y2="255.5" x2="435.5" y1="235.5" x1="442.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_20" y2="254.5" x2="480.5" y1="236.5" x1="467.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_21" height="29" width="43" y="65.5" x="453.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_22" y="87.5" x="468.5" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_23" height="29" width="43" y="65.5" x="400.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_24" y="87.5" x="415.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <rect id="svg_25" height="29" width="43" y="17.5" x="346.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_26" y="39.5" x="361.5" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <rect id="svg_27" height="29" width="43" y="17.5" x="293.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_28" y="39.5" x="308.5" stroke-width="0" stroke="#000" fill="#000000">7</text>
  <ellipse ry="15.5" rx="26" id="svg_29" cy="33" cx="446.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_30" y="40.5" x="438.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="66.5" x2="429.5" y1="46.5" x1="436.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="65.5" x2="474.5" y1="47.5" x1="461.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="15.5" rx="26" id="svg_33" cy="222" cx="452.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_34" y="229.5" x="444.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_35" y2="186.5" x2="400.5" y1="207.5" x1="381.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_36" y2="183.5" x2="424.5" y1="208.5" x1="447.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_37" height="29" width="43" y="214.5" x="187.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_38" y="236.5" x="202.5" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_39" height="29" width="43" y="214.5" x="134.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_40" y="236.5" x="149.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <rect id="svg_41" height="29" width="43" y="166.5" x="80.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_42" y="188.5" x="95.5" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <rect id="svg_43" height="29" width="43" y="121.5" x="30.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_44" y="143.5" x="45.5" stroke-width="0" stroke="#000" fill="#000000">7</text>
  <ellipse ry="15.5" rx="26" id="svg_45" cy="135" cx="139.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_46" y="142.5" x="125.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">11</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_47" y2="215.5" x2="163.5" y1="195.5" x1="170.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_48" y2="214.5" x2="208.5" y1="196.5" x1="195.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="15.5" rx="26" id="svg_49" cy="182" cx="180.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_50" y="189.5" x="172.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_51" y2="146.5" x2="128.5" y1="167.5" x1="109.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_52" y2="143.5" x2="152.5" y1="168.5" x1="175.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="15.5" rx="26" id="svg_55" cy="175" cx="411.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_56" y="182.5" x="397.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">11</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_57" y2="163" x2="335.5" y1="144" x1="349.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_58" y2="161" x2="403.5" y1="147" x1="387.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
 </g>
</svg>
  
##### Huffman编码

*  设给出一段报文： GOOD_GOOD_GOOD_GOOOOOOOO_OFF
*  字符集合是{O, G, _, D, F}, 各个字符出现的频度（次数）是 w = {15, 4, 4, 3, 2}.
*  若给每个字符以等长编码
	* O : 000  
	* G : 001 
	* _ : 010 
	* D : 011
	* F : 100
	*  则总编码长度为 (15+4+4+3+2) * 3 = 84   
*  若按各个字符出现的概率不同而给予不等长编码，可望减少总编码长度。
	* 各字符{O, G, _, D, F},出现概率为{15/28, 4/28, 3/28, 2/28 }, 化整为{ 15, 4, 4, 3, 2 }
	* 如果规定，Huffman树的左子树小于右子树，则可构成下图所示Huffman树
 <svg width="231" height="205" xmlns="http://www.w3.org/2000/svg">
 <!-- Created with Method Draw - http://github.com/duopixel/Method-Draw/ -->

 <g>
  <title>background</title>
  <rect fill="#fff" id="canvas_background" height="207" width="233" y="-1" x="-1"/>
  <g display="none" id="canvasGrid">
   <rect fill="url(#gridpattern)" stroke-width="0" y="0" x="0" height="100%" width="100%" id="svg_53"/>
  </g>
 </g>
 <g>
  <title>Layer 1</title>
  <rect id="svg_1" height="29" width="43" y="143.5" x="173.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="165.5" x="188.5" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_3" height="29" width="43" y="143.5" x="120.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="165.5" x="135.5" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_7" height="29" width="43" y="51.5" x="162.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="73.5" x="171.5" stroke-width="0" stroke="#000" fill="#000000">15</text>
  <ellipse ry="15.5" rx="26" id="svg_17" cy="24" cx="143.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_19" y2="144.5" x2="149.5" y1="124.5" x1="156.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_20" y2="143.5" x2="194.5" y1="125.5" x1="181.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_21" height="29" width="43" y="144.5" x="64.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_22" y="166.5" x="79.5" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <rect id="svg_23" height="29" width="43" y="144.5" x="11.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_24" y="165.5" x="27.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <ellipse ry="15.5" rx="26" id="svg_29" cy="112" cx="57.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_30" y="119.5" x="49.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="145.5" x2="40.5" y1="125.5" x1="47.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="144.5" x2="85.5" y1="126.5" x1="72.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="15.5" rx="26" id="svg_33" cy="111" cx="166.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_34" y="118.5" x="158.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">8</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_35" y2="78.5" x2="95.5" y1="99.5" x1="76.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_36" y2="75.5" x2="119.5" y1="100.5" x1="142.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="15.5" rx="26" id="svg_55" cy="67" cx="106.5" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_56" y="74.5" x="92.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">13</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_57" y2="52" x2="108.5" y1="33" x1="122.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_58" y2="50" x2="176.5" y1="36" x1="160.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_5" y="131.5" x="123" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ed1a1a">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="125" x="89" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#6D97AB">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_9" y="40.5" x="91" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ed1a1a">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="87.5" x="59" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ed1a1a">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_11" y="131.5" x="15" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ed1a1a">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="42.5" x="180" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#6D97AB">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_13" y="91.5" x="140" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#6D97AB">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="134.5" x="195" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#6D97AB">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="101" x="189" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#C97A86">O</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="195" x="29" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#C97A86">F</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_25" y="195" x="76" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#C97A86">D</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_26" y="196" x="135" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#C97A86">G</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_27" y="191" x="186" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#C97A86">_</text>
 </g>
</svg>

	*  令左孩分支为编码0, 右孩子分支为编码1
	*  将根结点到叶子结点路径上的分支编码，组合起来，作为该字符的Huffman码，则可得到
		*  O : 1
		* _ : 011
		* G : 010
		* D : 001
		* F : 000 
	*  则总编码长度为 15*1+(2+3+4+4)*3 = 54<84
	* Huffman是一种前缀编码，解码时不会混淆
	* 如 GOOD 编码为 01011001 
 
