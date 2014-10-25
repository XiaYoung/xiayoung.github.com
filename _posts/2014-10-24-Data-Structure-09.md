---
layout : post
category : mse
tags : [Data structure]
--- 
##第九章 查找 

### **第一节 查找的概念**  

####  一、查找表（Search Table）  

* 1）定义
	*  查找表是由同一类型的数据元素（或记录）构成的集合
	*  对查找表的操作：
		1. 查询某个“特定的”数据元素是否在查找表中；
		2. 检索某个“特定的”数据元素的各种属性；
		3. 在查找表中插入一个数据元素；
		4. 从查找表中删去某个数据元素 
* 2）分类
	* 静态查找表
		* 仅作查询和检索操作的查找表
	* 动态查找表
		* 在查找过程中同时插入查找表中不存在的数据元素，或者从查找表中删除已存在的某个数据元素  

####  二、关键字（Key）  

*  关键字是数据元素（记录）中某个数据项的值，用以标识（识别）一个数据元素（或记录）
*  主关键字：可以识别唯一的一个记录的关键字
*  次关键字：能识别若干记录的关键字

####  三、查找（Searching）  

*  查找是根据给定的某个值，在查找表中确定一个其关键字等于给定值的数据元素（或记录）
*   查找成功：在查找表中查到指定的记录
*  查找不成功：在查找表中没有找到指定记录

####  四、衡量查找算法的标准

*  时间复杂度
*  空间复杂度
*  平均查找长度ASL

####  五、平均查找长度（ASL）    

*  平均查找长度定义为确定记录在表中的位置所进行的和关键字比较的次数的平均值  
	$$ASL = \sum _{ i=1 }^{ n }{ P_ iC_i } $$  
*  n为查找表的长度，即表中所含元素的个数  
*  $$P_i$$ 为查找第i个元素的概率（$$\sum _{ }^{ }{ P_ i }=1 $$）
*  $$C_i$$是查找第i个元素时同给定值K比较的次数

---

### **第二节 静态查找表**  

####  一、顺序查找  

* 1）定义
	*  顺序查找算法是顺序表的查找方法
	*  在顺序查找算法中，以顺序表或线性链表表示静态查找表
* 2）顺序查找算法
	1. 从表中**最后一个记录**开始
	2. 逐个进行记录的关键字和给定值的比较
	3. 若某个记录比较相等，则查找成功
	4. 若直到第1个记录都比较不等，则查找不成功
* 3）顺序查找算法实现
	 
		int Search_Seq(SSTable ST, KeyType key){
			//若查找成功，返回位置
			ST.elem[0].key = key; //“哨兵“，
			for(i=ST.length; ST.elem[i].key != key; --i); //从后往前找
			return i;
		}// Search_Seq
	设置”哨兵“的目的是省略对下标越界的检查，提高算法执行速度
* 4）举例
<svg width="372" height="109" >
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_1" y2="60.83437" x2="4.16784" y1="27.83437" x1="4.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_3" y2="60.83437" x2="34.16784" y1="27.83437" x1="34.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_4" y2="60.83437" x2="64.16784" y1="27.83437" x1="64.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_5" y2="60.83437" x2="94.16784" y1="27.83437" x1="94.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_6" y2="60.83437" x2="124.16784" y1="27.83437" x1="124.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_7" y2="60.83437" x2="154.16784" y1="27.83437" x1="154.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_8" y2="60.83437" x2="184.16784" y1="27.83437" x1="184.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_9" y2="60.83437" x2="214.16784" y1="27.83437" x1="214.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_10" y2="60.83437" x2="244.16784" y1="27.83437" x1="244.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_11" y2="60.83437" x2="274.16784" y1="27.83437" x1="274.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_12" y2="60.83437" x2="304.16784" y1="27.83437" x1="304.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_13" y2="60.83437" x2="334.16784" y1="27.83437" x1="334.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_26" y2="60.83437" x2="364.16784" y1="27.83437" x1="364.16784" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_27" y="17.83437" x="12.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_28" y="17.83437" x="42.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_29" y="17.83437" x="72.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_30" y="17.83437" x="102.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_31" y="17.83437" x="132.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_32" y="17.83437" x="162.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_33" y="17.83437" x="192.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_34" y="17.83437" x="222.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">7</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_35" y="17.83437" x="252.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">8</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_36" y="17.83437" x="282.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">9</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_37" y="17.83437" x="312.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">10</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_38" y="17.83437" x="342.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">11</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_39" y="47.83437" x="12.16784" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f40909">64</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_40" y="47.83437" x="42.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_41" y="47.83437" x="72.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">13</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_42" y="47.83437" x="102.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">19</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_43" y="47.83437" x="132.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_44" y="47.83437" x="162.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">37</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_45" y="47.83437" x="192.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">56</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_46" y="47.83437" x="222.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">64</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_47" y="47.83437" x="252.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">75</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_48" y="47.83437" x="282.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">80</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_49" y="47.83437" x="312.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">88</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_50" y="47.83437" x="342.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">92</text>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_51" y2="28.33437" x2="365.88815" y1="28.33437" x1="3.66784" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_52" y2="61.00104" x2="365.88815" y1="61.00104" x1="3.66784" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_54" y="101.83438" x="222.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=7</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_55" y="101.83438" x="252.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=8</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_56" y="101.83438" x="282.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=9</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_57" y="101.83438" x="312.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=10</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_58" y="101.83438" x="342.16784" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=11</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_69" y="81.16591" x="224.83443" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_70" y="81.16591" x="254.83443" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_71" y="81.16591" x="284.83443" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_72" y="81.16591" x="314.83443" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_73" y="81.16591" x="344.83443" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
</svg>  
  
比较次数  
	查找第n个元素：1  
	查找第n-1个元素：2
	......  
	查找第1个元素：n
	查找第i个元素：n+1-i
	查找失败：n+1  

* 5）算法性能分析

*  

* 6）不等概率
* 7）特点

####  二、折半查找  

* 1）定义
* 2）算法
* 3）举例-成功
* 4）举例-不成功
* 5）判定树
* 6）算法性能分析
* 7）特点

####  三、分块查找（分块有序表）

* 1）定义
* 2）举例
* 3）性能分析

---

### **第三节 动态查找表**  

####  一、动态查找表  

####  二、二叉排序树  

* 1）定义
* 2）举例
* 3）查找
* 4）插入
* 5）生成
* 6）中序遍历
* 7）删除
* 8）性能分析
* 9）特性

####  三、平衡二叉树[AVL]

* 1）定义
* 2）平衡因子
* 3）平衡化旋转
* 4）平衡化单向旋转
* 5）平衡化双向旋转
* 6）单向右旋
* 7）单向左旋
* 8）先左后右双向旋转
* 9）先右后左双向旋转
* 10）例子
* 11）删除

---

### **第四节 哈希表**  

####  一、哈希表  

* 1）散列表
* 2）函数
* 3）查找
* 4）冲突
* 5）定义

####  二、哈希函数 

* 1）均匀性
* 2）要求
* 3）直接定址法
* 4）数字分析法
* 5）平方取中法
* 6）折叠法
* 7）除留余数法

####  三、处理冲突的方法

* 1）开发定址法
* 2）再哈希法
* 3）链地址法

####  四、哈希表的实现

* 1）定义
* 2）哈希函数 hash()
* 3）查找过程
* 4）查找函数 search()

####  五、哈希查找的性能分析

* 1）定义
* 2）哈希函数 hash()
* 3）查找过程
* 4）查找函数 search()

---
