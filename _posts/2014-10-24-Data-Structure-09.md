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
	* 判定树：描述查找过程的二叉树
	* 有n个结点的判定树的深度为$$(\log_{2}{n}) + 1$$  
	* 折半查找法在查找过程中进行的比较次数最多不超过$$(\log_{2}{n}) + 1$$  
	* 有11个元素的表的例子
	
<svg width="345" height="233" >
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
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.16761" y1="28.33437" x2="340.38793" y2="28.33437" id="svg_51" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.1679" y1="61.00104" x2="340.38793" y2="61.00104" id="svg_52" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <ellipse ry="10" rx="10" id="svg_19" cy="170.00006" cx="83.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_20" y="50.00023" x="261.49974" stroke-width="0" stroke="#0f0f00" fill="#000000">2</text>
  <ellipse ry="10" rx="10" id="svg_57" cy="78.00006" cx="168.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_59" y="83.50006" x="165" stroke-width="0" stroke="#0f0f00" fill="#000000">6</text>
  <ellipse ry="10" rx="10" id="svg_60" cy="107.00006" cx="267.5" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_61" y="112.50006" x="264" stroke-width="0" stroke="#0f0f00" fill="#000000">9</text>
  <ellipse ry="10" rx="10" id="svg_62" cy="108.00006" cx="85.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_63" y="50.00015" x="289.99971" stroke-width="0" stroke="#0f0f00" fill="#000000">3</text>
  <ellipse ry="10" rx="10" id="svg_64" cy="141.00006" cx="51.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_65" y="50.0002" x="168.99983" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <ellipse ry="10" rx="10" id="svg_66" cy="141.00006" cx="116.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_67" y="50.0002" x="321.49971" stroke-width="0" stroke="#0f0f00" fill="#000000">4</text>
  <ellipse ry="10" rx="10" id="svg_68" cy="140.00006" cx="231.5" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" stroke="#0f0f00" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_70" y="145.50006" x="228" stroke-width="0" fill="#000000">7</text>
  <ellipse ry="10" rx="10" id="svg_71" cy="142.00006" cx="299.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_72" y="147.50006" x="291.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">10</text>
  <ellipse ry="10" rx="10" id="svg_74" cy="172.00006" cx="326.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_75" y="177.50006" x="318.50001" stroke-width="0" stroke="#0f0f00" fill="#000000">11</text>
  <ellipse ry="10" rx="10" id="svg_76" cy="174.00006" cx="256.5" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_77" y="179.50006" x="253" stroke-width="0" stroke="#0f0f00" fill="#000000">8</text>
  <ellipse ry="10" rx="10" id="svg_78" cy="173.00006" cx="142.5" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_79" y="178.50006" x="139" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <text transform="matrix(1,0,0,1,0,0) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_80" y="50.00019" x="51.50009" stroke-width="0" stroke="#0f0f00" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_81" y="50.00015" x="22.00008" stroke-width="0" stroke="#0f0f00" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_82" y="50.00023" x="82.5" stroke-width="0" stroke="#0f0f00" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_83" y="50.0002" x="141.49996" stroke-width="0" stroke="#0f0f00" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_84" y="50.00015" x="111.49996" stroke-width="0" stroke="#0f0f00" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_85" y="50.00019" x="231.49983" stroke-width="0" stroke="#0f0f00" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_86" y="175.50006" x="80.5" stroke-width="0" stroke="#0f0f00" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_87" y="50.00015" x="202.49983" stroke-width="0" stroke="#0f0f00" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_88" y="146.50006" x="113" stroke-width="0" stroke="#0f0f00" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_89" y="146.50006" x="48" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_90" y="113.50006" x="82" stroke-width="0" stroke="#0f0f00" fill="#000000">3</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_91" y2="105.25004" x2="96.25011" y1="83.25007" x1="159.75002" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_92" y2="104.25004" x2="256.74988" y1="80.75008" x1="178.24999" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_93" y2="134.75" x2="239.74991" y1="115.25003" x1="260.74988" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_94" y2="133.75" x2="293.24983" y1="114.25003" x1="275.74985" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_95" y2="165.24996" x2="320.74979" y1="148.74998" x1="307.24981" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_96" y2="165.24996" x2="251.74989" y1="147.24998" x1="237.74991" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_97" y2="133.25" x2="57.25016" y1="114.75003" x1="78.25013" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_98" y2="132.25" x2="110.75009" y1="116.25003" x1="92.25011" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_99" y2="163.24996" x2="77.25013" y1="146.24998" x1="61.75016" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_100" y2="164.24996" x2="135.25005" y1="149.24998" x1="121.75007" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_101" height="29.99996" width="11.49998" y="193.99992" x="81.25013" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_102" height="29.99996" width="11.49998" y="162.99995" x="30.2502" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_103" height="29.99996" width="11.49998" y="162.99996" x="100.2501" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_104" height="29.99996" width="11.49998" y="162.99996" x="211.24995" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_105" height="29.99996" width="11.49998" y="162.99996" x="284.74984" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_106" height="29.99996" width="11.49998" y="193.99992" x="58.75016" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_107" height="29.99996" width="11.49998" y="193.99992" x="323.74979" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_108" height="29.99996" width="11.49998" y="193.99992" x="301.24982" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_109" height="29.99996" width="11.49998" y="193.99993" x="262.24987" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_110" height="29.99996" width="11.49998" y="193.99993" x="239.7499" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_111" height="29.99996" width="11.49998" y="193.99993" x="152.25003" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_112" height="29.99996" width="11.49998" y="193.99993" x="129.75006" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_113" y2="163.74996" x2="38.75019" y1="148.74998" x1="45.25018" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_114" y2="162.24996" x2="108.25009" y1="148.74998" x1="112.75008" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_115" y2="163.24996" x2="218.24994" y1="149.74998" x1="226.24992" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_116" y2="162.74996" x2="292.24983" y1="151.74998" x1="297.24982" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_117" y2="194.24992" x2="67.25015" y1="178.24994" x1="80.75013" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_118" y2="194.24992" x2="89.25012" y1="179.24994" x1="86.25012" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_119" y2="193.24992" x2="135.75005" y1="180.24994" x1="137.75005" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_120" y2="193.74992" x2="155.75002" y1="181.24993" x1="149.25003" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_121" y2="193.74992" x2="243.2499" y1="181.24993" x1="249.74989" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_122" y2="194.24992" x2="267.74987" y1="183.24993" x1="263.74987" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_123" y2="193.74992" x2="307.24981" y1="180.24994" x1="321.24979" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_124" y2="195.74991" x2="329.24978" y1="181.74993" x1="330.24978" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
</svg>
	
* 6）算法性能分析
	*	设有序表的长度$$n=2^h-1$$(即$$h=\log _2{(n+1)}$$)，则描述折半查找的判定树是深度为h的满二叉树
	*	树中层次为1的结点有1个，层次为2的结点有2个，层次为h的结点为$$2^{h-1}$$个 
	*	假设表中每个记录的查找概率相等，则查找成功时折半查找的平均查找长度  
	$$ASL_{bs} =\frac{1}{n}\sum_{i=1}^{n}{C_i} = \frac{1}{n}\left[ \sum_{j=1}^{h}{j*2^{j-1}} \right] = \frac{n+1}{n} \log_{2}{(n+1)} -1 $$    
* 7）特点
	* 折半查找的效率比顺序查找高（特别是在静态查找表的长度很长时）
	* 折半查找只能适用于有序表，并且以顺序存储结构存储

####  三、分块查找（分块有序表）

* 1）定义
	* 分块查找是一种索引顺序表（分块有序表）查找方法，是折半查找和顺序查找的简单结合
	* 索引顺序表（分块有序表）将整个表分成几块，块内无序，块间有序
	* 所谓块间有序是指后一块表中所有记录的关键字均大于前一块表中的最大关键字 
* 2）分块有序表
	* 主表：用数组存放待查记录，每个数据元素至少含有关键字域
	* 索引表：每个结点含有最大关键字域和指向本块第一个结点的指针 

<svg width="345" height="197">
  <line fill="none" stroke="#000" stroke-width="1.5" x1="8.66762" y1="154.83414" x2="8.66762" y2="187.83414" id="svg_3" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="38.66762" y1="154.83414" x2="38.66762" y2="187.83414" id="svg_4" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="68.66762" y1="154.83414" x2="68.66762" y2="187.83414" id="svg_5" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="98.66762" y1="154.83414" x2="98.66762" y2="187.83414" id="svg_6" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="128.66762" y1="154.83414" x2="128.66762" y2="187.83414" id="svg_7" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="158.66762" y1="154.83414" x2="158.66762" y2="187.83414" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="188.66762" y1="154.83414" x2="188.66762" y2="187.83414" id="svg_9" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="218.66762" y1="154.83414" x2="218.66762" y2="187.83414" id="svg_10" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="216.33435" y1="4.16774" x2="216.33435" y2="37.16774" id="svg_11" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="246.33435" y1="4.16774" x2="246.33435" y2="37.16774" id="svg_12" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="276.33435" y1="4.16774" x2="276.33435" y2="37.16774" id="svg_13" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="306.33435" y1="4.16774" x2="306.33435" y2="37.16774" id="svg_26" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="16.66762" y="144.83414" id="svg_28" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="46.66762" y="144.83414" id="svg_29" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="76.66762" y="144.83414" id="svg_30" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="106.66762" y="144.83414" id="svg_31" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="136.66762" y="144.83414" id="svg_32" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="166.66762" y="144.83414" id="svg_33" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="196.66762" y="144.83414" id="svg_34" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="226.66762" y="144.83414" id="svg_35" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">8</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="256.66762" y="144.83414" id="svg_36" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="286.66762" y="144.83414" id="svg_37" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="316.66762" y="144.83414" id="svg_38" font-size="16" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">11</text>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="216.50056" y1="4.66774" x2="308.05465" y2="4.66774" id="svg_51" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="216.83419" y1="37.33441" x2="308.05465" y2="37.33441" id="svg_52" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_20" y="26.00027" x="224.16648" stroke-width="0" stroke="#0f0f00" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_63" y="26.33352" x="254.66644" stroke-width="0" stroke="#0f0f00" fill="#000000">75</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_65" y="176.99997" x="166.6665" stroke-width="0" stroke="#0f0f00" fill="#000000">56</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_67" y="26.33357" x="284.49978" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_80" y="176.99996" x="46.50009" stroke-width="0" fill="#000000" stroke="#0f0f00">19</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_81" y="176.99992" x="22.00008" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_82" y="176.66666" x="76.5" stroke-width="0" stroke="#0f0f00" fill="#000000">13</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_83" y="176.99997" x="136.83329" stroke-width="0" stroke="#0f0f00" fill="#000000">75</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_84" y="176.66658" x="107.16663" stroke-width="0" stroke="#0f0f00" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_85" y="177.33329" x="226.49983" stroke-width="0" stroke="#0f0f00" fill="#000000">37</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_87" y="177.33325" x="197.1665" stroke-width="0" stroke="#0f0f00" fill="#000000">64</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="248.66762" y1="154.83414" x2="248.66762" y2="187.83414" id="svg_22" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="278.66762" y1="154.83414" x2="278.66762" y2="187.83414" id="svg_23" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="308.66762" y1="154.83414" x2="308.66762" y2="187.83414" id="svg_24" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="338.66762" y1="154.83414" x2="338.66762" y2="187.83414" id="svg_25" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.16761" y1="155.33414" x2="340.38793" y2="155.33414" id="svg_27" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="8.1679" y1="188.00081" x2="340.38793" y2="188.00081" id="svg_39" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_40" y="177" x="256.49974" stroke-width="0" stroke="#0f0f00" fill="#000000">88</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_41" y="177.66658" x="287.33304" stroke-width="0" stroke="#0f0f00" fill="#000000">80</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_42" y="177.66663" x="317.16638" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="216.33435" y1="37.83435" x2="216.33435" y2="70.83435" id="svg_53" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="246.33435" y1="37.83435" x2="246.33435" y2="70.83435" id="svg_54" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="276.33435" y1="37.83435" x2="276.33435" y2="70.83435" id="svg_55" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="306.33435" y1="37.83435" x2="306.33435" y2="70.83435" id="svg_56" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="216.83419" y1="71.00102" x2="308.05465" y2="71.00102" id="svg_57" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_58" y="60.00021" x="229.16647" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_59" y="60.00013" x="257.66644" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_60" y="60.00018" x="289.16644" stroke-width="0" stroke="#0f0f00" fill="#000000">9</text>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="264.66649" y1="71.33341" x2="264.66649" y2="103.54962" id="svg_61" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="143.33338" y1="104.66669" x2="265.33733" y2="104.66669" id="svg_62" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="270.33337" y1="111.00001" x2="270.33337" y2="134.70638" id="svg_64" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="276.00003" y1="130.99997" x2="271.6667" y2="135.66663" id="svg_66" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="264.66671" y1="131.66664" x2="271.33337" y2="135.99997" id="svg_68" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="231.99988" y1="71.33341" x2="231.99988" y2="97.88296" id="svg_69" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="19.66694" y1="99.00003" x2="232.67072" y2="99.00003" id="svg_70" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="19.66694" y1="99.6667" x2="19.66694" y2="129.03972" id="svg_71" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="25.00026" y1="125.33332" x2="20.66693" y2="129.99998" id="svg_72" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="13.66695" y1="125.99998" x2="20.3336" y2="130.33331" id="svg_73" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="144.00004" y1="104.66668" x2="144.00004" y2="128.37305" id="svg_74" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="149.6667" y1="124.66664" x2="145.33337" y2="129.3333" id="svg_75" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="138.33338" y1="125.33331" x2="145.00004" y2="129.66663" id="svg_76" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="270.00001" y1="112" x2="295.00223" y2="112" id="svg_77" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="293.33334" y1="112" x2="293.33334" y2="70.93366" id="svg_78" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_14" y="46" x="150" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">索引表</text>
</svg>
 
* 3）举例
	* 找64
	* 采用折半查找方法在索引表中找到块[第2块]
	* 用顺序查找方法在主表对应块中找到记录[第3记录]
* 4）性能分析
	* 若将长度为n的表分成b块，每块含s个记录，并设表中每个记录查找概率相等
	* 用折半查找方法在索引表中查找索引块，$$ASL_{块间} \approx \log_2{(n/s+1)}$$  
	* 用顺序查找法在主表对应块中查找记录，$$ ASL_{块内} = s/2 $$  
	*   $$ASL\approx \log_2{(n/s+1)} + s/2$$    

---

### **第三节 动态查找表**  

####  一、动态查找表  

*  表结构本身是在查找过程中动态生成的
*  若表中存在其关键字等于给定值key的记录，表明查找成功
*  否则插入关键字等于key的记录

####  二、二叉排序树  

* 1）定义
	* 空树或者是具有如下特征的二叉树：
	* (1). 若它的左子树不空，则左子树上所有结点的值均小于根结点的值
	* (2). 若它的右子树不空，则右子树上所有结点的值均大于根结点的值
	* (3). 它的左、右子树也都分别是二叉排序树
* 2）举例

<svg width="401" height="177" >
  <ellipse fill="none" stroke="#0f0f00" cx="277.5" cy="101.50006" id="svg_19" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="297" cy="11.50006" id="svg_57" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="289" y="16.50006" id="svg_59" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="336.5" cy="36.00006" id="svg_60" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="330.5" y="42.00006" id="svg_61" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <ellipse fill="none" stroke="#0f0f00" cx="261" cy="39.50006" id="svg_62" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="227" cy="72.50006" id="svg_64" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="292" cy="72.50006" id="svg_66" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="337" cy="132.00006" id="svg_68" rx="10" ry="10"/>
  <text fill="#000000" stroke-width="0" x="329.5" y="137.00006" id="svg_70" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#0f0f00">75</text>
  <ellipse fill="none" stroke="#0f0f00" cx="368.5" cy="71.00006" id="svg_71" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="360.00001" y="76.50006" id="svg_72" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <ellipse fill="none" stroke="#0f0f00" cx="359" cy="100.00006" id="svg_74" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="351.00001" y="105.50006" id="svg_75" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <ellipse fill="none" stroke="#0f0f00" cx="321" cy="98.50006" id="svg_76" rx="10" ry="10"/>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" x="312.5" y="104.50006" id="svg_77" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">60</text>
  <ellipse fill="none" stroke="#0f0f00" cx="268.5" cy="132.50006" id="svg_78" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="261" y="137.50006" id="svg_79" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="270.5" y="106.00006" id="svg_86" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="285" y="78.00006" id="svg_88" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">37</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="223" y="78.50006" id="svg_89" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="253" y="45.00006" id="svg_90" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">13</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="344.74985" y1="43.25003" x2="362.24983" y2="62.75" id="svg_94" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="367.24991" y1="105.24998" x2="381.24989" y2="123.24996" id="svg_96" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="253.75013" y1="46.25003" x2="232.75016" y2="64.75" id="svg_97" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="267.75011" y1="47.75003" x2="286.25009" y2="63.75" id="svg_98" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="288.25008" y1="80.24998" x2="283.75009" y2="93.74996" id="svg_114" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="277.24992" y1="109.74998" x2="269.24994" y2="123.24996" id="svg_115" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="366.24982" y1="80.74998" x2="361.24983" y2="91.74996" id="svg_116" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="353.74979" y1="108.24994" x2="339.74981" y2="121.74992" id="svg_123" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_3" y2="36.25" x2="268.75" y1="18.75" x1="290.75" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_4" y2="28.25" x2="330.75" y1="17.75" x1="306.25" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="64.5" cy="105.50006" id="svg_5" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="84" cy="15.50006" id="svg_6" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="76" y="20.50006" id="svg_7" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="123.5" cy="40.00006" id="svg_8" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="117.5" y="46.00006" id="svg_9" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <ellipse fill="none" stroke="#0f0f00" cx="48" cy="43.50006" id="svg_10" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="14" cy="76.50006" id="svg_11" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="79" cy="76.50006" id="svg_12" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="124" cy="136.00006" id="svg_13" rx="10" ry="10"/>
  <text fill="#000000" stroke-width="0" x="116.5" y="141.00006" id="svg_14" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#0f0f00">75</text>
  <ellipse fill="none" stroke="#0f0f00" cx="155.5" cy="75.00006" id="svg_15" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="147.00001" y="80.50006" id="svg_16" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <ellipse fill="none" stroke="#0f0f00" cx="146" cy="104.00006" id="svg_17" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="138.00001" y="109.50006" id="svg_18" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <ellipse fill="none" stroke="#0f0f00" cx="173" cy="136.00006" id="svg_20" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="166" y="140.50006" id="svg_21" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <ellipse fill="none" stroke="#0f0f00" cx="55.5" cy="136.50006" id="svg_22" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="48" y="141.50006" id="svg_23" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="57.5" y="110.00006" id="svg_24" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="72" y="82.00006" id="svg_25" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">37</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="10" y="82.50006" id="svg_26" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="40" y="49.00006" id="svg_27" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">13</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="131.74985" y1="47.25003" x2="149.24983" y2="66.75" id="svg_28" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="154.24991" y1="109.24998" x2="168.24989" y2="127.24996" id="svg_29" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="40.75013" y1="50.25003" x2="19.75016" y2="68.75" id="svg_30" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="54.75011" y1="51.75003" x2="73.25009" y2="67.75" id="svg_31" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="75.25008" y1="84.24998" x2="70.75009" y2="97.74996" id="svg_32" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="64.24992" y1="113.74998" x2="56.24994" y2="127.24996" id="svg_33" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="153.24982" y1="84.74998" x2="148.24983" y2="95.74996" id="svg_34" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="140.74979" y1="112.24994" x2="126.74981" y2="125.74992" id="svg_35" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_36" y2="40.25" x2="55.75" y1="22.75" x1="77.75" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_37" y2="32.25" x2="117.75" y1="21.75" x1="93.25" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_38" y2="91.25" x2="314.25" y1="76.75" x1="299.75" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="386" cy="132.00006" id="svg_39" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="379" y="136.50006" id="svg_40" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_42" y="171.25" x="71.25" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">二叉排序树</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_43" y="168.25" x="281.25" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">非二叉排序树</text>
</svg>

* 3）查找
	* 二叉排序树又称二叉查找树 
	* 查找算法 ：给定值与根结点比较：
		1.若相等，查找成功
		2.若小于，查找左子树
		3.若大于，查找右子树  
<svg width="190" height="190" >
  <ellipse ry="10" rx="10" id="svg_5" cy="105.50006" cx="64.5" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_6" cy="15.50006" cx="84" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_7" y="20.50006" x="76" stroke-width="0" stroke="#0f0f00" fill="#000000">56</text>
  <ellipse ry="10" rx="10" id="svg_8" cy="40.00006" cx="123.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_9" y="46.00006" x="117.5" stroke-width="0" stroke="#0f0f00" fill="#000000">64</text>
  <ellipse ry="10" rx="10" id="svg_10" cy="43.50006" cx="48" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_11" cy="76.50006" cx="14" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_12" cy="76.50006" cx="79" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_13" cy="136.00006" cx="124" stroke="#0f0f00" fill="none"/>
  <text stroke="#0f0f00" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_14" y="141.00006" x="116.5" stroke-width="0" fill="#000000">75</text>
  <ellipse ry="10" rx="10" id="svg_15" cy="75.00006" cx="155.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_16" y="80.50006" x="147.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <ellipse ry="10" rx="10" id="svg_17" cy="104.00006" cx="146" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_18" y="109.50006" x="138.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">80</text>
  <ellipse ry="10" rx="10" id="svg_20" cy="136.00006" cx="173" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_21" y="140.50006" x="166" stroke-width="0" stroke="#0f0f00" fill="#000000">88</text>
  <ellipse ry="10" rx="10" id="svg_22" cy="136.50006" cx="55.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_23" y="141.50006" x="48" stroke-width="0" stroke="#0f0f00" fill="#000000">19</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_24" y="110.00006" x="57.5" stroke-width="0" stroke="#0f0f00" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_25" y="82.00006" x="72" stroke-width="0" stroke="#0f0f00" fill="#000000">37</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_26" y="82.50006" x="10" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_27" y="49.00006" x="40" stroke-width="0" stroke="#0f0f00" fill="#000000">13</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_28" y2="66.75" x2="149.24983" y1="47.25003" x1="131.74985" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_29" y2="127.24996" x2="168.24989" y1="109.24998" x1="154.24991" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_30" y2="68.75" x2="19.75016" y1="50.25003" x1="40.75013" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="67.75" x2="73.25009" y1="51.75003" x1="54.75011" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="97.74996" x2="70.75009" y1="84.24998" x1="75.25008" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_33" y2="127.24996" x2="56.24994" y1="113.74998" x1="64.24992" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_34" y2="95.74996" x2="148.24983" y1="84.74998" x1="153.24982" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_35" y2="125.74992" x2="126.74981" y1="112.24994" x1="140.74979" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="77.75" y1="22.75" x2="55.75" y2="40.25" id="svg_36" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="93.25" y1="21.75" x2="117.75" y2="32.25" id="svg_37" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="26.91667" y="165.25" id="svg_42" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">在二叉排序树中查找</text>
  <text transform="rotate(47.82647705078125 175.00781250000006,84.98437499999996) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_2" y="89.83334" x="168.00001" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#00ff00">→</text>
  <text transform="rotate(23.003368377685547 109.3359375,21.65104103088379) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_41" y="26.50001" x="102.33334" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#00ff00">→</text>
  <text transform="rotate(51.319637298583984 144.9973907470703,52.651042938232436) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_44" y="57.50001" x="138.00001" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#00ff00">→</text>
  <text transform="rotate(52.790122985839844 158.66406249999997,120.984375) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_45" y="125.83334" x="151.66668" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">→</text>
  <text transform="rotate(140.38363647460938 63.66406249999999,25.986980438232425) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_46" y="30.83334" x="56.66668" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">→</text>
  <text transform="rotate(40.977115631103516 69.66406250000001,54.6484375) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_47" y="59.50001" x="62.66668" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">→</text>
  <text transform="rotate(24.305484771728516 104.00781249999999,30.648437500000018) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_48" y="35.50001" x="97.00001" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">→</text>
  <text transform="rotate(46.54911804199219 138.0078125,59.984375000000014) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_49" y="64.83334" x="131.00001" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">→</text>
  <text transform="rotate(111.48389434814453 145.6640625,88.6484375) " xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_50" y="93.50001" x="138.66668" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">→</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_51" y="183.83334" x="18.33334" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">关键字值等于</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_52" y="183.83334" x="105.66668" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">37</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_54" y="183.50001" x="122.66668" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#f41111">,88</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_55" y="183.83334" x="143.33334" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#00bf00">,94</text>
</svg>

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
