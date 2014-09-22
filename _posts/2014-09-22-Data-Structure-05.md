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

  
</svg>  

<svg width="400" height="400">
  <circle r="20" cx="200" cy="80" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="80"  fill="#000">A</text>

  <line x1="100" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="100" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="100" y="160" fill="#000">B</text>
  <line x1="200" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="200"  cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="160" fill="#000">C</text>
  <line x1="300" y1="160" x2="200" y2="80" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="300" cy="160" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="160" fill="#000">D</text>

  <line x1="70" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="70" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="70" y="240" fill="#000">E</text>
  <line x1="130" y1="240" x2="100" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="130" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="130" y="240" fill="#000">F</text>
  
  <line x1="200" y1="240" x2="200" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="200"  cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="200" y="240" fill="#000">G</text>
  
  <line x1="250" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="250" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="240" fill="#000">H</text>
  <line x1="300" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="300" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="300" y="240" fill="#000">I</text>
  <line x1="350" y1="240" x2="300" y2="160" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="350" cy="240" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="350" y="240" fill="#000">J</text>
  
  <line x1="40" y1="320" x2="70" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="40" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="40" y="320" fill="#000">K</text>
  <line x1="110" y1="320" x2="70" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="110" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="110" y="320" fill="#000">L</text>
  
  <line x1="250" y1="320" x2="250" y2="240" style ="stroke-width: 2; stroke: #00ff00;" /> 
  <circle r="20" cx="250" cy="320" stroke-width="2" stroke="#000" fill="red"/>
  <text font-size="16" x="250" y="320" fill="#000">M</text>
  
</svg>

####  二、树的基本术语  

### **第二节 二叉树**  

####  一、二叉树（Binary Tree）   

####  二、二叉树性质1    

####  三、二叉树性质2  

####  四、二叉树性质3  
        
####  五、满二叉树  

####  六、完全二叉树  

####  七、二叉树的顺序存储结构  

####  八、二叉树的链式存储结构  

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
 
  
