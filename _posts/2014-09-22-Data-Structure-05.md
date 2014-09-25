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

* 三叉链表  

### **第三节 遍历二叉树**  

####  一、遍历二叉树   

#### 二、先序遍历二叉树  

#### 三、中序遍历二叉树  

#### 四、后序遍历二叉树  

#### 五、根据先、中序遍历求序列二叉树

#### 六、根据后、中序遍历求序列二叉树  

### **第四节 线索二叉树**  

####  一、增加新指针  

####  二、利用空指针  

### **第五节 树与森林**  

####  一、树的存储结构  

####  二、树与二叉树的对应关系  

####  三、森林与二叉树的对应关系  

####  四、树的遍历    

### **第六节 霍夫曼树及其应用**  

####  一、最优二叉树  

####  二、Huffman树

##### 构造  

##### 算法  
  
##### 举例   
  
##### 编码     
 
  
