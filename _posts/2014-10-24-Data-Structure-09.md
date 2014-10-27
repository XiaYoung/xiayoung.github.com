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

	*  对顺序表而言，$$C_i = n-i+1$$  
	*  在等概率查找的情况下，$$P_i = 1/n$$  
	*  $$ASL =n*p_1 +(n-1)P_2+...+ 2P_{n-1} +P_n = (n+1)/2$$      

* 6）不等概率
	* 如果被查找的记录概率不等时，取
	$$P_n\ge  P_{n-1}\ge ...\ge P_2\ge P_1$$  
	* 若查找概率无法事先测定，则查找过程采取的改进办法是，在每次查找之后，将刚刚查找到的记录直接移至表尾的位置上
* 7）特点
	* 优点
		* 简单
		* 适应面广（对表的结构无任何要求）
	* 缺点 
		* 平均查找长度较大
		* 特别是当n很大时，查找效率很低 

####  二、折半查找  

* 1）定义
	* 折半查找算法是有序表的查找方法
	* 在折半查找算法中，静态查找表按关键字大小的次序，有序存放在顺序表中
	* 折半查找的原理是：
	1. 先确定待查记录所在的范围（前部分或后部分）
	2. 逐步缩小（一半）范围直到找（不）到该记录为止
* 2）算法
	1. n个对象从小到大存放在有序顺序表ST中，k为给定值
	2. 设low、high指向待查元素所在区间的下界、上界，即low=1, high=n
	3. 设mid指向待查区间的中点，即mid=(low+high)/2
	4. 让k与mid指向的记录比较  
	若k=ST[mid].key，查找成功，结束  
	若k<ST[mid].key，则high=mid-1 [上半区间]  
	若k>ST[mid].key，则low=mid+1 [下半区间]
	5. 重复3,4操作，直至low>high时，查找失败。
* 3）举例-成功 
	* 找64

<svg width="370" height="285" >
  <line fill="none" stroke="#000" stroke-width="1.5" x1="8.66762" y1="27.83437" x2="8.66762" y2="60.83437" id="svg_3" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="38.66762" y1="27.83437" x2="38.66762" y2="60.83437" id="svg_4" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="68.66762" y1="27.83437" x2="68.66762" y2="60.83437" id="svg_5" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="98.66762" y1="27.83437" x2="98.66762" y2="60.83437" id="svg_6" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="128.66762" y1="27.83437" x2="128.66762" y2="60.83437" id="svg_7" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="158.66762" y1="27.83437" x2="158.66762" y2="60.83437" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="188.66762" y1="27.83437" x2="188.66762" y2="60.83437" id="svg_9" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="218.66762" y1="27.83437" x2="218.66762" y2="60.83437" id="svg_10" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="248.66762" y1="27.83437" x2="248.66762" y2="60.83437" id="svg_11" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="278.66762" y1="27.83437" x2="278.66762" y2="60.83437" id="svg_12" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="308.66762" y1="27.83437" x2="308.66762" y2="60.83437" id="svg_13" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="338.66762" y1="27.83437" x2="338.66762" y2="60.83437" id="svg_26" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="17.83437" id="svg_28" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="17.83437" id="svg_29" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="17.83437" id="svg_30" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="17.83437" id="svg_31" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="17.83437" id="svg_32" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="17.83437" id="svg_33" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="196.66762" y="17.83437" id="svg_34" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="17.83437" id="svg_35" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">8</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="17.83437" id="svg_36" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="17.83437" id="svg_37" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="17.83437" id="svg_38" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">11</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="47.83437" id="svg_40" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="47.83437" id="svg_41" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">13</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="47.83437" id="svg_42" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="47.83437" id="svg_43" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="47.83437" id="svg_44" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">37</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="47.83437" id="svg_45" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <text fill="#f70909" stroke="#000" stroke-width="0" stroke-opacity="null" x="196.66762" y="47.83437" id="svg_46" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="47.83437" id="svg_47" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">75</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="47.83437" id="svg_48" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="47.83437" id="svg_49" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="47.83437" id="svg_50" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.16761" y1="28.33437" x2="340.38793" y2="28.33437" id="svg_51" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.1679" y1="61.00104" x2="340.38793" y2="61.00104" id="svg_52" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text style="cursor: move;" fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="6.16754" y="89.33427" id="svg_54" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low=1</text>
  <text style="cursor: move;" fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="157.66754" y="89.83427" id="svg_55" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">mid=6</text>
  <text fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="308.16754" y="88.83427" id="svg_58" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">High=11</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="17.33421" y="74.16585" id="svg_69" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="169.33421" y="74.16585" id="svg_70" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="319.33421" y="74.16585" id="svg_73" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="8.66762" y1="119.83518" x2="8.66762" y2="152.83518" id="svg_149" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="38.66762" y1="119.83518" x2="38.66762" y2="152.83518" id="svg_150" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="68.66762" y1="119.83518" x2="68.66762" y2="152.83518" id="svg_151" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="98.66762" y1="119.83518" x2="98.66762" y2="152.83518" id="svg_152" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="128.66762" y1="119.83518" x2="128.66762" y2="152.83518" id="svg_153" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="158.66762" y1="119.83518" x2="158.66762" y2="152.83518" id="svg_154" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="188.66762" y1="119.83518" x2="188.66762" y2="152.83518" id="svg_155" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="218.66762" y1="119.83518" x2="218.66762" y2="152.83518" id="svg_156" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="248.66762" y1="119.83518" x2="248.66762" y2="152.83518" id="svg_157" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="278.66762" y1="119.83518" x2="278.66762" y2="152.83518" id="svg_158" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="308.66762" y1="119.83518" x2="308.66762" y2="152.83518" id="svg_159" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="338.66762" y1="119.83518" x2="338.66762" y2="152.83518" id="svg_160" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="109.83518" id="svg_161" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="109.83518" id="svg_162" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="109.83518" id="svg_163" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="109.83518" id="svg_164" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="109.83518" id="svg_165" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="109.83518" id="svg_166" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="196.66762" y="109.83518" id="svg_167" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="109.83518" id="svg_168" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">8</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="109.83518" id="svg_169" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="109.83518" id="svg_170" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="109.83518" id="svg_171" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">11</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="139.83518" id="svg_172" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="139.83518" id="svg_173" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">13</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="139.83518" id="svg_174" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="139.83518" id="svg_175" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="139.83518" id="svg_176" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">37</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="139.83518" id="svg_177" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <text fill="#f70909" stroke="#000" stroke-width="0" stroke-opacity="null" x="196.66762" y="139.83518" id="svg_178" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="139.83518" id="svg_179" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">75</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="139.83518" id="svg_180" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="139.83518" id="svg_181" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="139.83518" id="svg_182" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.16761" y1="120.33518" x2="340.38793" y2="120.33518" id="svg_183" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.1679" y1="153.00185" x2="340.38793" y2="153.00185" id="svg_184" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="188.66915" y="181.33508" id="svg_185" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low=7</text>
  <text style="cursor: move;" fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="249.66835" y="180.83508" id="svg_186" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">mid=9</text>
  <text fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="308.16754" y="180.83508" id="svg_187" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">High=11</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="199.83581" y="166.16666" id="svg_188" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="260.83501" y="166.16666" id="svg_189" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="319.33421" y="166.16666" id="svg_190" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="8.66762" y1="215.83603" x2="8.66762" y2="248.83603" id="svg_191" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="38.66762" y1="215.83603" x2="38.66762" y2="248.83603" id="svg_192" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="68.66762" y1="215.83603" x2="68.66762" y2="248.83603" id="svg_193" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="98.66762" y1="215.83603" x2="98.66762" y2="248.83603" id="svg_194" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="128.66762" y1="215.83603" x2="128.66762" y2="248.83603" id="svg_195" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="158.66762" y1="215.83603" x2="158.66762" y2="248.83603" id="svg_196" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="188.66762" y1="215.83603" x2="188.66762" y2="248.83603" id="svg_197" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="218.66762" y1="215.83603" x2="218.66762" y2="248.83603" id="svg_198" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="248.66762" y1="215.83603" x2="248.66762" y2="248.83603" id="svg_199" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="278.66762" y1="215.83603" x2="278.66762" y2="248.83603" id="svg_200" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="308.66762" y1="215.83603" x2="308.66762" y2="248.83603" id="svg_201" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="338.66762" y1="215.83603" x2="338.66762" y2="248.83603" id="svg_202" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="205.83603" id="svg_203" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="205.83603" id="svg_204" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="205.83603" id="svg_205" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="205.83603" id="svg_206" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="205.83603" id="svg_207" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="205.83603" id="svg_208" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="196.66762" y="205.83603" id="svg_209" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="205.83603" id="svg_210" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">8</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="205.83603" id="svg_211" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="205.83603" id="svg_212" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="205.83603" id="svg_213" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">11</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="235.83603" id="svg_214" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="235.83603" id="svg_215" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">13</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="235.83603" id="svg_216" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="235.83603" id="svg_217" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="235.83603" id="svg_218" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">37</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="235.83603" id="svg_219" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <text fill="#f70909" stroke="#000" stroke-width="0" stroke-opacity="null" x="196.66762" y="235.83603" id="svg_220" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="235.83603" id="svg_221" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">75</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="235.83603" id="svg_222" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="235.83603" id="svg_223" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="235.83603" id="svg_224" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.16761" y1="216.33603" x2="340.38793" y2="216.33603" id="svg_225" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.1679" y1="249.0027" x2="340.38793" y2="249.0027" id="svg_226" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="162.66892" y="277.33593" id="svg_227" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low=7</text>
  <text fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="200.66791" y="276.83592" id="svg_228" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">mid=7</text>
  <text fill="#00ff00" stroke="#000" stroke-width="0" stroke-opacity="null" x="240.66694" y="276.83592" id="svg_229" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">High=8</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="189.33572" y="262.16751" id="svg_230" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="200.83448" y="262.16751" id="svg_231" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="239.8335" y="262.16751" id="svg_232" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
</svg>

* 4）举例-不成功
	* 找59   
<svg width="348" height="99" >
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_3" y2="60.83437" x2="8.66762" y1="27.83437" x1="8.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_4" y2="60.83437" x2="38.66762" y1="27.83437" x1="38.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_5" y2="60.83437" x2="68.66762" y1="27.83437" x1="68.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_6" y2="60.83437" x2="98.66762" y1="27.83437" x1="98.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_7" y2="60.83437" x2="128.66762" y1="27.83437" x1="128.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_8" y2="60.83437" x2="158.66762" y1="27.83437" x1="158.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_9" y2="60.83437" x2="188.66762" y1="27.83437" x1="188.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_10" y2="60.83437" x2="218.66762" y1="27.83437" x1="218.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_11" y2="60.83437" x2="248.66762" y1="27.83437" x1="248.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_12" y2="60.83437" x2="278.66762" y1="27.83437" x1="278.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_13" y2="60.83437" x2="308.66762" y1="27.83437" x1="308.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_26" y2="60.83437" x2="338.66762" y1="27.83437" x1="338.66762" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_28" y="17.83437" x="16.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_29" y="17.83437" x="46.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_30" y="17.83437" x="76.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_31" y="17.83437" x="106.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_32" y="17.83437" x="136.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_33" y="17.83437" x="166.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_34" y="17.83437" x="196.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">7</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_35" y="17.83437" x="226.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">8</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_36" y="17.83437" x="256.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">9</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_37" y="17.83437" x="286.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">10</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_38" y="17.83437" x="316.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">11</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_40" y="47.83437" x="16.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_41" y="47.83437" x="46.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">13</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_42" y="47.83437" x="76.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">19</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_43" y="47.83437" x="106.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_44" y="47.83437" x="136.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">37</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_45" y="47.83437" x="166.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">56</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_46" y="47.83437" x="196.66762" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">64</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_47" y="47.83437" x="226.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">75</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_48" y="47.83437" x="256.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">80</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_49" y="47.83437" x="286.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">88</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_50" y="47.83437" x="316.66762" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">92</text>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_51" y2="28.33437" x2="340.38793" y1="28.33437" x1="8.16761" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none" stroke="#000"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_52" y2="61.00104" x2="340.38793" y1="61.00104" x1="8.1679" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none" stroke="#000"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_54" y="88.00094" x="191.50078" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#00ff00">low=7</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_58" y="89" x="133.50096" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#00ff00">High=6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_69" y="72.83252" x="202.66745" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="16" id="svg_73" y="72.83252" x="171.33429" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">↑</text>
</svg>
	
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
