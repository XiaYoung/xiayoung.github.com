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
	* 二叉排序树是一种动态查找表
	* 当树中不存在查找的结点时，作插入操作
	* 新插入的结点一定是叶子结点（只需改动一个结点的指针）
	* 该叶子结点是查找不成功时路径上访问的最后一个结点的左孩子或右孩子（新结点值小于或大于该结点值）
* 5）生成
	* 画出在初始为空的二叉排序树中依次插入56,64,92,80.88,75时该树的生长全过程

<svg width="390" height="160" >
  <ellipse fill="none" stroke="#0f0f00" cx="23.66683" cy="21.16671" id="svg_6" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="15.66683" y="26.16671" id="svg_7" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="93.50008" cy="46.00004" id="svg_8" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="87.50008" y="52.00004" id="svg_9" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_37" y2="38.24998" x2="87.75008" y1="27.74998" x1="63.25008" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="286.33279" cy="19.50005" id="svg_59" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="278.33279" y="24.50005" id="svg_60" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="325.83279" cy="44.00005" id="svg_61" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="319.83279" y="50.00005" id="svg_62" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <ellipse fill="none" stroke="#0f0f00" cx="326.33279" cy="140.00005" id="svg_63" rx="10" ry="10"/>
  <text fill="#000000" stroke-width="0" x="318.83279" y="145.00005" id="svg_64" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#0f0f00">75</text>
  <ellipse fill="none" stroke="#0f0f00" cx="357.83279" cy="79.00005" id="svg_65" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="349.3328" y="84.50005" id="svg_66" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <ellipse fill="none" stroke="#0f0f00" cx="348.33279" cy="108.00005" id="svg_67" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="340.3328" y="113.50005" id="svg_68" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <ellipse fill="none" stroke="#0f0f00" cx="375.33279" cy="140.00005" id="svg_69" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="368.33279" y="144.50005" id="svg_70" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="334.08264" y1="51.25002" x2="351.58262" y2="70.74999" id="svg_71" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="356.5827" y1="113.24997" x2="370.58268" y2="131.24995" id="svg_72" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="355.58261" y1="88.74997" x2="350.58262" y2="99.74995" id="svg_73" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="343.08258" y1="116.24993" x2="329.0826" y2="129.74991" id="svg_74" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_75" y2="36.24999" x2="320.08279" y1="25.74999" x1="295.58279" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="211.99966" cy="20.16671" id="svg_90" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="203.99966" y="25.16671" id="svg_91" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="251.49966" cy="44.66671" id="svg_92" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="245.49966" y="50.66671" id="svg_93" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <ellipse fill="none" stroke="#0f0f00" cx="280.833" cy="80.66671" id="svg_94" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="272.33301" y="86.16671" id="svg_95" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <ellipse fill="none" stroke="#0f0f00" cx="271.333" cy="109.66671" id="svg_96" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="263.33301" y="115.16671" id="svg_97" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <ellipse fill="none" stroke="#0f0f00" cx="298.333" cy="141.66671" id="svg_98" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="291.333" y="146.16671" id="svg_99" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">88</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="259.74951" y1="51.91668" x2="277.24949" y2="71.41665" id="svg_100" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="279.58291" y1="114.91663" x2="293.58289" y2="132.91661" id="svg_101" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="278.58282" y1="90.41663" x2="273.58283" y2="101.41661" id="svg_102" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_103" y2="36.91665" x2="245.74966" y1="26.41665" x1="221.24966" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="156.33314" cy="21.50004" id="svg_104" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="148.33314" y="26.50004" id="svg_105" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="196.49981" cy="45.00004" id="svg_106" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="190.49981" y="51.00004" id="svg_107" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <ellipse fill="none" stroke="#0f0f00" cx="228.49981" cy="80.00004" id="svg_108" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="219.99982" y="85.50004" id="svg_109" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <ellipse fill="none" stroke="#0f0f00" cx="218.99981" cy="109.00004" id="svg_110" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="210.99982" y="114.50004" id="svg_111" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">80</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="204.74966" y1="52.25001" x2="222.24964" y2="71.74998" id="svg_112" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="226.24963" y1="89.74996" x2="221.24964" y2="100.74994" id="svg_113" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_114" y2="38.24998" x2="190.08314" y1="27.74998" x1="165.58314" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="103.66661" cy="22.16671" id="svg_115" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="95.33328" y="27.50004" id="svg_116" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
  <ellipse fill="none" stroke="#0f0f00" cx="142.49995" cy="44.66672" id="svg_117" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="136.49995" y="50.66672" id="svg_118" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">64</text>
  <ellipse fill="none" stroke="#0f0f00" cx="174.49995" cy="79.66672" id="svg_119" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="165.99996" y="85.16672" id="svg_120" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">92</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="150.7498" y1="51.91669" x2="168.24978" y2="71.41666" id="svg_121" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_122" y2="36.91666" x2="136.74995" y1="26.41666" x1="112.24995" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="none" stroke="#0f0f00" cx="54.00008" cy="21.50004" id="svg_128" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="46.00008" y="26.50004" id="svg_129" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">56</text>
</svg>  

* 6）中序遍历
	* 中序遍历二叉排序树，可得到一个关键字的有序序列，
	 如5, 13, 19, 21, 37, 56, 64, 92, 75, 80, 88
* 7）删除
	* 删除二叉排序树中的一个结点后，必须保持二叉排序树的特性（左子树的所有结点值小于根结点，右子树的所有结点值大于根结点）
	* 也即保持中序遍历后，输出为有序序列  
	* 被删除结点具有以下三种情况：
	1. 是叶子结点
		* 直接删除结点，并让其父结点指向该结点的指针变为空
	2. 只有左子树或右子树
		* 删除结点，让其父结点指向该结点的指针指向其左子树（或右子树），即用孩子结点替代被删除结点即可  
	3. 同时有左、右子树
		* 以中序遍历时的直接前驱s替代被删除结点p，然后再删除该直接前驱（只可能有左孩子）
* 8）性能分析
	* 在最好的情况下，二叉排序树为一近似完全二叉树时，其查找深度为$$log_2n$$量级，即其时间复杂性为$$O(\log_2n)$$  
	* 在最坏的情况下，二叉排序树为近似线性表时（如以升序或降序输入结点时），其查找深度为n量级，即其时间复杂性为O(n)
	
<svg width="116" height="218" >
  <ellipse ry="10" rx="10" id="svg_65" cy="14.20006" cx="104.23281" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_66" y="19.70006" x="96.53282" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <ellipse ry="10" rx="10" id="svg_69" cy="110.00005" cx="13.33282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_70" y="115.70005" x="9.53282" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <ellipse ry="10" rx="10" id="svg_2" cy="34.40006" cx="86.13282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_3" y="38.90006" x="78.73282" stroke-width="0" stroke="#0f0f00" fill="#000000">88</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_5" y2="26.70001" x2="93.60001" y1="21.50001" x1="98.00001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_10" y2="103.10001" x2="20.00002" y1="97.90001" x1="25.20002" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_11" cy="54.40006" cx="68.53282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_12" y="58.90006" x="61.53282" stroke-width="0" stroke="#0f0f00" fill="#000000">80</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_13" y2="47.50001" x2="75.20001" y1="42.30001" x1="80.40001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_14" cy="73.60006" cx="49.73282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_15" y="78.50006" x="42.33282" stroke-width="0" stroke="#0f0f00" fill="#000000">75</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_16" y2="66.70001" x2="56.40001" y1="61.50001" x1="61.60001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_17" cy="91.60005" cx="31.73282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_18" y="96.50005" x="24.33282" stroke-width="0" stroke="#0f0f00" fill="#000000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_19" y2="84.70001" x2="38.40002" y1="79.50001" x1="43.60001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_34" cy="205.06208" cx="104.23281" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_35" y="210.56208" x="96.53282" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <ellipse ry="10" rx="10" id="svg_36" cy="186.2737" cx="86.13282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_37" y="190.7737" x="78.73282" stroke-width="0" stroke="#0f0f00" fill="#000000">88</text>
  <ellipse ry="10" rx="10" id="svg_39" cy="165.20005" cx="69.73282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_40" y="169.70005" x="62.73282" stroke-width="0" stroke="#0f0f00" fill="#000000">80</text>
  <ellipse ry="10" rx="10" id="svg_42" cy="146.80005" cx="49.73282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_43" y="151.70005" x="42.33282" stroke-width="0" stroke="#0f0f00" fill="#000000">75</text>
  <ellipse ry="10" rx="10" id="svg_45" cy="126.40005" cx="31.73282" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_46" y="131.30005" x="24.33282" stroke-width="0" stroke="#0f0f00" fill="#000000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_50" y2="120.3" x2="24.80001" y1="115.5" x1="20.40001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_51" y2="198.3" x2="97.20001" y1="193.5" x1="92.80001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_52" y2="139.1" x2="43.60001" y1="134.3" x1="39.20001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_53" y2="158.7" x2="61.20001" y1="153.9" x1="56.80001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_54" y2="178.3" x2="80.00001" y1="173.5" x1="75.60001" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
</svg>  

* 9）特性
*  一个无序序列可以通过构造一棵二叉排序树而变成一个有序序列（通过中序遍历）
*  插入新纪录时，只需要改变一个结点的指针，相当于在有序序列中插入一个记录而不需要移动其它记录
*  二叉排序树既拥有类似于折半查找的特性，又采用了链表作存储结构  
*  但当插入记录的次序不当时（如升序或降序），则二叉排序树深度很深（n），增加了查找的时间

####  三、平衡二叉树[AVL]

* 1）定义
	*	平衡二叉树是二叉排序（查找）树的另一种形式
	*	平衡二叉树又称AVL树（Adelsen-Velskii and Landis）
	*	其特点为：树中每个结点的左、右子树深度之差的绝对值不大于1, 即$$|h_L-h_R|\le 1$$  

<svg width="412" height="183" >
  <ellipse ry="10" rx="10" id="svg_19" cy="101.50006" cx="277.5" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_57" cy="11.50006" cx="297" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_59" y="16.50006" x="289" stroke-width="0" stroke="#0f0f00" fill="#000000">56</text>
  <ellipse ry="10" rx="10" id="svg_60" cy="36.00006" cx="336.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_61" y="42.00006" x="330.5" stroke-width="0" stroke="#0f0f00" fill="#000000">64</text>
  <ellipse ry="10" rx="10" id="svg_62" cy="39.50006" cx="261" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_64" cy="72.50006" cx="227" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_66" cy="72.50006" cx="292" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_68" cy="132.00006" cx="337" stroke="#0f0f00" fill="none"/>
  <text stroke="#0f0f00" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_70" y="137.00006" x="329.5" stroke-width="0" fill="#000000">75</text>
  <ellipse ry="10" rx="10" id="svg_71" cy="71.00006" cx="368.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_72" y="76.50006" x="360.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <ellipse ry="10" rx="10" id="svg_74" cy="100.00006" cx="359" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_75" y="105.50006" x="351.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">80</text>
  <ellipse ry="10" rx="10" id="svg_78" cy="132.50006" cx="268.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_79" y="137.50006" x="261" stroke-width="0" stroke="#0f0f00" fill="#000000">19</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_86" y="106.00006" x="270.5" stroke-width="0" stroke="#0f0f00" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_88" y="78.00006" x="285" stroke-width="0" stroke="#0f0f00" fill="#000000">37</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_89" y="78.50006" x="223" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_90" y="45.00006" x="253" stroke-width="0" stroke="#0f0f00" fill="#000000">13</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_94" y2="62.75" x2="362.24983" y1="43.25003" x1="344.74985" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_96" y2="123.24996" x2="381.24989" y1="105.24998" x1="367.24991" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_97" y2="64.75" x2="232.75016" y1="46.25003" x1="253.75013" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_98" y2="63.75" x2="286.25009" y1="47.75003" x1="267.75011" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_114" y2="93.74996" x2="283.75009" y1="80.24998" x1="288.25008" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_115" y2="123.24996" x2="269.24994" y1="109.74998" x1="277.24992" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_116" y2="91.74996" x2="361.24983" y1="80.74998" x1="366.24982" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_123" y2="121.74992" x2="339.74981" y1="108.24994" x1="353.74979" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="290.75" y1="18.75" x2="268.75" y2="36.25" id="svg_3" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="306.25" y1="17.75" x2="330.75" y2="28.25" id="svg_4" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse ry="10" rx="10" id="svg_5" cy="81.50006" cx="66.5" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_6" cy="15.50006" cx="84" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_7" y="20.50006" x="76" stroke-width="0" stroke="#0f0f00" fill="#000000">56</text>
  <ellipse ry="10" rx="10" id="svg_8" cy="78.00006" cx="106.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_9" y="84.00006" x="100.5" stroke-width="0" stroke="#0f0f00" fill="#000000">64</text>
  <ellipse ry="10" rx="10" id="svg_10" cy="43.50006" cx="48" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_11" cy="76.50006" cx="14" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_12" cy="112.50006" cx="80" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_13" cy="112.00006" cx="120" stroke="#0f0f00" fill="none"/>
  <text stroke="#0f0f00" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_14" y="117.00006" x="112.5" stroke-width="0" fill="#000000">75</text>
  <ellipse ry="10" rx="10" id="svg_15" cy="80.00006" cx="159.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_16" y="85.50006" x="151.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">92</text>
  <ellipse ry="10" rx="10" id="svg_17" cy="39.00006" cx="126" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_18" y="44.50006" x="118.00001" stroke-width="0" stroke="#0f0f00" fill="#000000">80</text>
  <ellipse ry="10" rx="10" id="svg_20" cy="111.00006" cx="146" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_21" y="115.50006" x="139" stroke-width="0" stroke="#0f0f00" fill="#000000">88</text>
  <ellipse ry="10" rx="10" id="svg_22" cy="112.50006" cx="49.5" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_23" y="117.50006" x="42" stroke-width="0" stroke="#0f0f00" fill="#000000">19</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_24" y="86.00006" x="59.5" stroke-width="0" stroke="#0f0f00" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_25" y="118.00006" x="73" stroke-width="0" stroke="#0f0f00" fill="#000000">37</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_26" y="82.50006" x="10" stroke-width="0" stroke="#0f0f00" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_27" y="49.00006" x="40" stroke-width="0" stroke="#0f0f00" fill="#000000">13</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_30" y2="68.75" x2="19.75016" y1="50.25003" x1="40.75013" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="102.74996" x2="54.75009" y1="89.24998" x1="59.25008" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_34" y2="100.74996" x2="152.24983" y1="89.74998" x1="157.24982" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="77.75" y1="22.75" x2="55.75" y2="40.25" id="svg_36" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="93.25" y1="21.75" x2="117.75" y2="32.25" id="svg_37" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse ry="10" rx="10" id="svg_39" cy="132.00006" cx="386" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_40" y="136.50006" x="379" stroke-width="0" stroke="#0f0f00" fill="#000000">88</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="71.25" y="171.25" id="svg_42" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">AVL树</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="281.25" y="168.25" id="svg_43" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">非AVL树</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_2" y2="103.5" x2="78.5" y1="89.5" x1="70.5" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="76.5" x2="67.5" y1="52.5" x1="54.5" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_33" y2="71.5" x2="154.5" y1="47.5" x1="134.5" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_35" y2="68.5" x2="111.5" y1="49.5" x1="122.5" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_38" y2="102.5" x2="116.5" y1="87.5" x1="103.5" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
</svg>  

* 2）平衡因子
	* 每个结点附加一个数字，给出该结点左子树的高度减去右子树的高度所得的高度差，这个数字即为结点的平衡因子balance
	* AVL树任一结点平衡因子只能取 -1, 0, 1	
	
<svg width="184" height="135">
  <ellipse fill="none" stroke="#0f0f00" cx="65.78571" cy="85.07149" id="svg_5" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="83.28571" cy="19.07149" id="svg_6" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="105.78571" cy="81.57149" id="svg_8" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="47.28571" cy="47.07149" id="svg_10" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="13.28571" cy="80.07149" id="svg_11" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="79.28571" cy="116.07149" id="svg_12" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="119.28571" cy="115.57149" id="svg_13" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="158.78571" cy="83.57149" id="svg_15" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="125.28571" cy="42.57149" id="svg_17" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="145.28571" cy="114.57149" id="svg_20" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="48.78571" cy="116.07149" id="svg_22" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="42.14285" y="52.50006" id="svg_26" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="40.03584" y1="53.82146" x2="19.03587" y2="72.32143" id="svg_30" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="58.53579" y1="92.82141" x2="54.0358" y2="106.32139" id="svg_32" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="156.53553" y1="93.32141" x2="151.53554" y2="104.32139" id="svg_34" stroke-linejoin="null" stroke-linecap="null"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_36" y2="43.82143" x2="55.03571" y1="26.32143" x1="77.03571" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_37" y2="35.82143" x2="117.03571" y1="25.32143" x1="92.53571" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="69.78571" y1="93.07143" x2="77.78571" y2="107.07143" id="svg_2" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="53.78571" y1="56.07143" x2="66.78571" y2="80.07143" id="svg_31" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="133.78571" y1="51.07143" x2="153.78571" y2="75.07143" id="svg_33" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="121.78571" y1="53.07143" x2="110.78571" y2="72.07143" id="svg_35" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="102.78571" y1="91.07143" x2="115.78571" y2="106.07143" id="svg_38" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="80" y="23.21435" id="svg_69" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="123.57142" y="49.64292" id="svg_70" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="62.85714" y="92.50006" id="svg_71" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="74.28571" y="121.07148" id="svg_72" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="8.57142" y="85.3572" id="svg_73" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="114.99999" y="121.78577" id="svg_74" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="140.71427" y="121.07148" id="svg_75" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="154.2857" y="89.64291" id="svg_76" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="99.28571" y="86.07149" id="svg_77" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="45.71428" y="120.3572" id="svg_78" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
</svg>  

* 3）平衡化旋转
	*  如果在一棵平衡的二叉查找树中插入一个新的结点，造成了不平衡。此时必须调整树的结构，使之平衡化。
	* 平衡化旋转（处理）有两类：
		1. 单向旋转（单向右旋和单向左旋）
		2. 双向旋转（先左后右旋转和先右后左旋转） 
	*  每插入一个新结点时，AVL树中相关结点的平衡状态可能会发生改变。
	*  在插入一个新结点后，需要从插入位置沿通向根的路径回溯，检查各结点的平衡因子
	*  如果在某一结点发现高度不平衡，停止回溯
	*  从发生不平衡的结点起，沿刚才回溯的路径取直接下两层的结点 
* 4）平衡化单向旋转
	* 如果这三个结点处于一条直线上（“/”型或“\”型），则采用单向旋转进行平衡化[A>B>C]
	* 单向旋转分为单向右旋（“/”型）和单向左旋("\"型)

<svg width="312" height="135">
  <ellipse ry="10" rx="10" id="svg_6" cy="81.07159" cx="299.28802" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_10" cy="49.73816" cx="272.28803" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_11" cy="82.40483" cx="249.28805" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_26" y="55.16673" x="267.14517" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_69" y="86.21445" x="294.33564" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_73" y="87.69054" x="244.57376" stroke-width="0" stroke="#0f0f00" fill="#000000">C</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_2" y2="74.33335" x2="255.83556" y1="57.66665" x1="267.16891" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_4" cy="83.47011" cx="214.61926" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_5" cy="48.07149" cx="192.95261" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_7" cy="14.69682" cx="169.95263" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_8" y="53.50006" x="187.80975" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_9" y="88.61297" x="209.66688" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_12" y="19.98253" x="165.23834" stroke-width="0" stroke="#0f0f00" fill="#000000">C</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_15" y2="72.00001" x2="292.50228" y1="57.66666" x1="279.16893" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <path stroke="#0f0f00" id="svg_16" d="m229.03168,67.64844c-0.82716,-0.45802 -0.71869,-0.73541 1.29242,-3.30229c1.01543,-1.29604 1.84618,-2.39426 1.84618,-2.44027c0,-0.046 -2.80397,-0.08356 -6.23129,-0.08356l-6.23122,0l0,-2.42776l0,-2.42749l6.28064,0c4.84274,0 6.22652,-0.07313 6.04462,-0.31925c-0.12982,-0.17574 -1.01573,-1.34162 -1.96858,-2.59065c-1.79611,-2.35477 -1.79552,-2.98616 0.00272,-3.18195c0.895,-0.0973 14.82838,7.38668 15.3073,8.22211c-4.64105,2.98272 -10.18867,6.1047 -15.29907,8.85754c-0.26944,0 -0.73911,-0.13799 -1.0437,-0.30643z" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_17" cy="80.40492" cx="142.6211" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_18" cy="49.07149" cx="115.62111" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_19" cy="81.73816" cx="92.62113" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_20" y="54.50006" x="110.47825" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_21" y="85.54778" x="137.66872" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_22" y="87.02387" x="87.90684" stroke-width="0" stroke="#0f0f00" fill="#000000">C</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_23" y2="73.66668" x2="99.16864" y1="56.99999" x1="110.50199" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_24" cy="13.73815" cx="57.95234" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_25" cy="47.40482" cx="36.28569" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_27" cy="80.07149" cx="13.28571" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_28" y="52.83339" x="31.14283" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_29" y="18.88101" x="52.99996" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_30" y="85.3572" x="8.57142" stroke-width="0" stroke="#0f0f00" fill="#000000">C</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="72.00001" x2="19.83322" y1="55.33332" x1="31.16657" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="38.33329" x2="42.16659" y1="21.6666" x1="53.49994" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_33" y2="71.33334" x2="135.83536" y1="56.99999" x1="122.50201" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <path stroke="#0f0f00" id="svg_34" d="m72.36475,66.98177c-0.82716,-0.45802 -0.7187,-0.73542 1.29242,-3.3023c1.01543,-1.29604 1.84618,-2.39426 1.84618,-2.44027c0,-0.04599 -2.80397,-0.08356 -6.23129,-0.08356l-6.23123,0l0,-2.42775l0,-2.42749l6.28064,0c4.84276,0 6.22652,-0.07312 6.04462,-0.31925c-0.12983,-0.17574 -1.01572,-1.34162 -1.96859,-2.59065c-1.7961,-2.35476 -1.79551,-2.98616 0.00272,-3.18195c0.895,-0.0973 14.82839,7.38667 15.3073,8.22211c-4.64106,2.98271 -10.18867,6.10469 -15.29908,8.85753c-0.26942,0 -0.7391,-0.13799 -1.04369,-0.30642z" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_35" y2="38.99996" x2="187.50005" y1="23.33327" x1="176.1667" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_36" y2="74.00002" x2="210.16675" y1="56.66665" x1="198.50007" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_38" y="118.00008" x="46.83316" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">单向右旋</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_39" y="117.33342" x="215.83343" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">单向左旋</text>
</svg>

* 5）平衡化双向旋转
	* 如果这三个结点处于一条折线上("<"型或">"型)，则采用双向旋转进行平衡化[A>B>C]。
	* 双旋转分为先左后右("<"型)和先右后左(">"型)

<svg width="450" height="135">
  <ellipse fill="none" stroke="#0f0f00" cx="435.19384" cy="81.07159" id="svg_6" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="408.19385" cy="49.73816" id="svg_10" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="385.19387" cy="82.40483" id="svg_11" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="403.05099" y="55.16673" id="svg_26" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="430.24146" y="86.21445" id="svg_69" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="380.47958" y="87.69054" id="svg_73" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="403.07473" y1="57.66665" x2="391.74138" y2="74.33335" id="svg_2" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="none" stroke="#0f0f00" cx="350.52508" cy="83.47011" id="svg_4" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="328.85843" cy="48.07149" id="svg_5" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="305.85845" cy="14.69682" id="svg_7" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="323.71557" y="53.50006" id="svg_8" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="345.5727" y="88.61297" id="svg_9" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="301.14416" y="19.98253" id="svg_12" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="415.07475" y1="57.66666" x2="428.4081" y2="72.00001" id="svg_15" stroke-linejoin="null" stroke-linecap="null"/>
  <path fill="none" stroke-width="null" stroke-opacity="null" fill-opacity="null" d="m364.93784,67.6484c-0.827,-0.458 -0.71902,-0.7354 1.29199,-3.3022c1.01599,-1.2961 1.84601,-2.3943 1.84601,-2.4403c0,-0.046 -2.80402,-0.0836 -6.23102,-0.0836l-6.23099,0l0,-2.4277l0,-2.4275l6.28,0c4.84299,0 6.22699,-0.0732 6.04501,-0.3193c-0.13,-0.1757 -1.01602,-1.3416 -1.96902,-2.5906c-1.79599,-2.3548 -1.79501,-2.9862 0.00302,-3.182c0.89499,-0.0973 14.82898,7.3867 15.30698,8.2221c-4.64099,2.9828 -10.18799,6.1047 -15.29898,8.8576c-0.26901,0 -0.73901,-0.138 -1.043,-0.3065l0,0z" id="svg_16" stroke="#0f0f00"/>
  <ellipse fill="none" stroke="#0f0f00" cx="205.03548" cy="80.40492" id="svg_17" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="178.03549" cy="49.07149" id="svg_18" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="155.03551" cy="81.73816" id="svg_19" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="172.89263" y="54.50006" id="svg_20" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="200.0831" y="85.54778" id="svg_21" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="150.32122" y="87.02387" id="svg_22" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="172.91637" y1="56.99999" x2="161.58302" y2="73.66668" id="svg_23" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="none" stroke="#0f0f00" cx="44.84948" cy="13.39332" id="svg_24" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="23.18283" cy="47.05999" id="svg_25" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="86.04492" cy="80.07149" id="svg_27" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="18.03997" y="52.48856" id="svg_28" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="39.8971" y="18.53618" id="svg_29" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="81.33063" y="85.3572" id="svg_30" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="103.92578" y1="55.33332" x2="92.59243" y2="72.00001" id="svg_31" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="40.39708" y1="21.32177" x2="29.06373" y2="37.98846" id="svg_32" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="184.91639" y1="56.99999" x2="198.24974" y2="71.33334" id="svg_33" stroke-linejoin="null" stroke-linecap="null"/>
  <path fill="none" stroke-width="null" stroke-opacity="null" fill-opacity="null" d="m305.46884,71.11971c-0.82715,-0.45802 -0.71869,-0.73542 1.29242,-3.30231c1.01544,-1.29604 1.84616,-2.39426 1.84616,-2.44027c0,-0.04599 -2.80396,-0.08356 -6.23129,-0.08356l-6.2312,0l0,-2.42775l0,-2.42749l6.28064,0c4.84274,0 6.2265,-0.07312 6.04462,-0.31925c-0.12985,-0.17574 -1.01572,-1.34162 -1.9686,-2.59065c-1.79611,-2.35476 -1.7955,-2.98616 0.00272,-3.18195c0.89502,-0.0973 14.8284,7.38666 15.30731,8.22211c-4.64108,2.98272 -10.18869,6.10469 -15.2991,8.85754c-0.26941,0 -0.73907,-0.13799 -1.04367,-0.30642z" id="svg_34" stroke="#0f0f00"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="312.07252" y1="23.33327" x2="323.40587" y2="38.99996" id="svg_35" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="29.57829" y1="56.66665" x2="41.24497" y2="74.00002" id="svg_36" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="89.24754" y="119.37939" id="svg_38" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">先左后右旋转</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="315.53236" y="119.40239" id="svg_39" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">先右后左旋转</text>
  <ellipse fill="none" stroke="#0f0f00" cx="130.71155" cy="13.73815" id="svg_3" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="47.32076" cy="81.54275" id="svg_13" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="42.1779" y="86.97132" id="svg_14" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="125.75917" y="18.88101" id="svg_37" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="126.25915" y1="21.6666" x2="114.9258" y2="38.33329" id="svg_40" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="334.40589" y1="56.66665" x2="346.07257" y2="74.00002" id="svg_41" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="none" stroke="#0f0f00" cx="109.0449" cy="47.40482" id="svg_42" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="103.90204" y="52.83339" id="svg_43" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <path fill="none" stroke-width="null" stroke-opacity="null" fill-opacity="null" d="m134.77867,66.98177c-0.82716,-0.45802 -0.7187,-0.73542 1.2924,-3.3023c1.01544,-1.29604 1.84618,-2.39426 1.84618,-2.44027c0,-0.04599 -2.80396,-0.08356 -6.23129,-0.08356l-6.23122,0l0,-2.42775l0,-2.42749l6.28064,0c4.84276,0 6.22652,-0.07312 6.04462,-0.31925c-0.12984,-0.17574 -1.01572,-1.34162 -1.96858,-2.59065c-1.79611,-2.35476 -1.79552,-2.98616 0.00272,-3.18195c0.895,-0.0973 14.82838,7.38667 15.3073,8.22211c-4.64107,2.98271 -10.18867,6.10469 -15.29909,8.85753c-0.26941,0 -0.73909,-0.13799 -1.04367,-0.30642z" id="svg_44" stroke="#0f0f00"/>
  <ellipse fill="none" stroke="#0f0f00" cx="283.68602" cy="48.07149" id="svg_50" rx="10" ry="10"/>
  <ellipse fill="none" stroke="#0f0f00" cx="260.68604" cy="14.69682" id="svg_51" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="278.54316" y="53.50006" id="svg_52" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="255.97175" y="19.98253" id="svg_53" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="266.90011" y1="23.33327" x2="278.23346" y2="38.99996" id="svg_54" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="none" stroke="#0f0f00" cx="264.66195" cy="80.07149" id="svg_55" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" x="259.94766" y="85.3572" id="svg_56" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="282.54281" y1="55.33332" x2="271.20946" y2="72.00001" id="svg_57" stroke-linejoin="null" stroke-linecap="null"/>
  <path fill="none" stroke-width="null" stroke-opacity="null" fill-opacity="null" d="m63.05505,64.91281c-0.82716,-0.45802 -0.7187,-0.73542 1.29241,-3.30231c1.01544,-1.29604 1.84617,-2.39425 1.84617,-2.44027c0,-0.04599 -2.80395,-0.08355 -6.23129,-0.08355l-6.23122,0l0,-2.42775l0,-2.42749l6.28064,0c4.84276,0 6.22652,-0.07312 6.04462,-0.31925c-0.12984,-0.17575 -1.01572,-1.34162 -1.96858,-2.59066c-1.79611,-2.35476 -1.79552,-2.98616 0.00272,-3.18194c0.895,-0.0973 14.82838,7.38666 15.30729,8.2221c-4.64108,2.98272 -10.18867,6.10469 -15.2991,8.85754c-0.2694,0 -0.73909,-0.13799 -1.04367,-0.30642z" id="svg_58" stroke="#0f0f00"/>
</svg>

* 6）单向右旋
	* 在B子树$$B_L$$上插入新结点使其高度增1，导致结点A的平衡因子增加到 +2，造成不平衡。
	* 为了使树恢复平衡，从A沿插入路径连续取3个结点A、B和$$B_L$$  （“/”型）
	* 以结点B为旋转轴，将结点A顺时针（右）旋转。
	
<svg width="342" height="142">
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="54.96297" x2="254.81465" y1="38.29628" x1="266.148" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_33" y2="52.44445" x2="291.95344" y1="38.1111" x1="278.62009" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_3" cy="60.03444" cx="298.85969" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_37" y="57.7699" x="312.7962" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_40" y2="84.62958" x2="283.07394" y1="67.96289" x1="294.40729" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_42" cy="30.36778" cx="271.26712" stroke="#0f0f00" fill="#00ff7f"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_43" y="83.20376" x="320.93907" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_2" height="28.51852" width="16.2963" y="85.83333" x="272.09258" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <rect id="svg_4" height="28.51852" width="16.2963" y="86.2037" x="312.09258" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <rect stroke="#0f0f00" id="svg_5" height="44.44445" width="16.2963" y="55.83333" x="246.90739" stroke-opacity="null" fill="#005fbf"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_7" y="25.42598" x="251.67982" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_8" y="85.59259" x="329.16666" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_9" y="50.98154" x="238.34648" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_10" y="53.37037" x="246.57407" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_11" y="75.96296" x="250.64815" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_12" y="106.33333" x="316.20371" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_13" y="106.7037" x="276.2037" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_14" y="80.98153" x="267.97611" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_15" y="83.37037" x="276.2037" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_16" y="16.33333" x="267.31481" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_17" y="43.74074" x="296.57407" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_18" y2="85.33334" x2="25.18502" y1="68.66665" x1="36.51837" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_19" y2="51.70371" x2="82.69418" y1="37.37036" x1="69.36083" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_20" cy="27.07148" cx="63.30414" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_21" y="22.21434" x="41.31472" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_22" y2="51.66662" x2="47.51839" y1="34.99993" x1="58.85174" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_23" cy="60.73815" cx="41.63749" stroke="#0f0f00" fill="#00ff7f"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_24" y="50.98154" x="93.90204" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_25" height="28.51852" width="16.2963" y="86.2037" x="50.6111" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <rect id="svg_26" height="28.51852" width="16.2963" y="56.2037" x="77.64814" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <rect id="svg_27" height="28.51852" width="16.2963" y="86.2037" x="17.27777" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_28" y2="86.33333" x2="58.7963" y1="70.03704" x1="47.31482" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_29" y="55.79635" x="22.05019" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_30" y="53.37037" x="102.12963" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_32" y="81.35191" x="8.71685" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_34" y="83.74074" x="16.94445" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_35" y="106.33333" x="21.01852" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_36" y="76.33333" x="81.75926" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_38" y="107.07407" x="54.35185" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_39" y="81.72228" x="59.08722" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_41" y="84.11111" x="67.31482" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_44" y="46.7037" x="37.68519" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_45" y="10.77778" x="61.01852" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">+1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_46" y="85.59259" x="251.75926" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">+</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_47" y="95.22222" x="251.75926" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_48" y2="86.07408" x2="135.92576" y1="69.40739" x1="147.25911" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_49" y2="52.44445" x2="193.43492" y1="38.1111" x1="180.10157" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_50" cy="27.81222" cx="174.04488" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_51" y="22.95508" x="152.05546" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_52" y2="52.40736" x2="158.25913" y1="35.74067" x1="169.59248" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_53" cy="61.47889" cx="152.37823" stroke="#0f0f00" fill="#00ff7f"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_54" y="51.72228" x="204.64278" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_55" height="28.51852" width="16.2963" y="86.94444" x="161.35184" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <rect id="svg_56" height="28.51852" width="16.2963" y="56.94444" x="188.38888" stroke-opacity="null" stroke="#0f0f00" fill="#00ff7f"/>
  <rect stroke="#0f0f00" id="svg_57" height="44.44445" width="16.2963" y="86.94444" x="128.0185" stroke-opacity="null" fill="#005fbf"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_58" y2="87.07407" x2="169.53704" y1="70.77778" x1="158.05555" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_59" y="56.53709" x="132.79093" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_60" y="54.11111" x="212.87037" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_61" y="82.09265" x="119.45759" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_62" y="84.48148" x="127.68518" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_63" y="107.07407" x="131.75926" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_64" y="77.07407" x="192.5" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_65" y="107.81481" x="165.09259" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_66" y="82.46302" x="169.82796" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_67" y="84.85185" x="178.05555" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_68" y="47.44444" x="148.42592" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">+1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_69" y="11.51852" x="171.75926" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">+2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_70" y="116.7037" x="132.87037" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">+</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_71" y="126.33333" x="132.87037" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_72" y2="84.66667" x2="318.24974" y1="70.33332" x1="304.91639" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
</svg>
	
* 7）单向左旋
	* 在B右子树$$B_R$$中插入新结点，该子树高度增1导致结点A的平衡因子变成-2，出现不平衡。
	*  沿插入路径检查三个结点A、B和$$B_R$$("\"型)
	*  以结点B为旋转轴，让结点A反时针（左）旋转
	
<svg width="342" height="138" >
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="77.98179" y1="70.13006" x2="66.64844" y2="86.79675" id="svg_18" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="69.36083" y1="37.37036" x2="82.69418" y2="51.70371" id="svg_19" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="63.30414" cy="27.07148" id="svg_20" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="41.31472" y="22.21434" id="svg_21" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="58.85174" y1="34.99993" x2="47.51839" y2="51.66662" id="svg_22" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="83.10091" cy="62.20156" id="svg_23" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="23.90204" y="48.05471" id="svg_24" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="92.07452" y="87.66711" width="16.2963" height="28.51852" id="svg_25"/>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="35.94082" y="52.54516" width="16.2963" height="28.51852" id="svg_26"/>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="58.74119" y="87.66711" width="16.2963" height="28.51852" id="svg_27"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="88.77824" y1="71.50045" x2="100.25972" y2="87.79674" id="svg_28" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="93.26971" y="55.79635" id="svg_29" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="32.12963" y="50.44354" id="svg_30" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="54.32661" y="83.30313" id="svg_32" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="62.55421" y="85.69196" id="svg_34" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="62.48194" y="107.79674" id="svg_35" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="40.05194" y="72.67479" id="svg_36" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="95.81527" y="108.53748" id="svg_38" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="98.35552" y="82.21008" id="svg_39" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="106.58312" y="84.59891" id="svg_41" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="82.80714" y="47.1915" id="svg_44" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="61.01852" y="10.77778" id="svg_45" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <rect fill="#005fbf" stroke-opacity="null" x="197.28679" y="88.16395" width="16.2963" height="44.44445" id="svg_57" stroke="#0f0f00"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="201.02755" y="108.29358" id="svg_63" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="202.13866" y="117.92321" id="svg_70" font-size="12" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="202.13866" y="127.55284" id="svg_71" font-size="12" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="182.61594" y1="70.13006" x2="171.28259" y2="86.79675" id="svg_6" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="173.99498" y1="37.37036" x2="187.32833" y2="51.70371" id="svg_73" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="167.93829" cy="27.07148" id="svg_74" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="145.94887" y="22.21434" id="svg_75" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="163.48589" y1="34.99993" x2="152.15254" y2="51.66662" id="svg_76" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="187.73506" cy="62.20156" id="svg_77" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="128.53619" y="48.05471" id="svg_78" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="140.57497" y="52.54516" width="16.2963" height="28.51852" id="svg_80"/>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="163.37534" y="87.66711" width="16.2963" height="28.51852" id="svg_81"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="193.41239" y1="71.50045" x2="204.89387" y2="87.79674" id="svg_82" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="197.90385" y="55.79635" id="svg_83" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="136.76378" y="50.44354" id="svg_84" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="158.96076" y="83.30313" id="svg_85" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="167.18836" y="85.69196" id="svg_86" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="167.11609" y="107.79674" id="svg_87" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="144.68609" y="72.67479" id="svg_88" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="202.98966" y="82.21008" id="svg_90" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="211.21726" y="84.59891" id="svg_91" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="187.44129" y="47.1915" id="svg_92" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="165.65267" y="10.77778" id="svg_93" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-2</text>
  <rect fill="#005fbf" stroke-opacity="null" x="305.82338" y="56.21273" width="16.2963" height="44.44445" id="svg_94" stroke="#0f0f00"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="309.56414" y="76.34236" id="svg_95" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="310.67525" y="85.97199" id="svg_96" font-size="12" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="310.67525" y="95.60162" id="svg_97" font-size="12" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="291.15252" y1="38.17884" x2="279.81917" y2="54.84553" id="svg_98" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="278.14132" y1="72.49232" x2="291.47467" y2="86.82567" id="svg_99" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="273.79195" cy="63.41294" id="svg_100" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="251.80253" y="58.5558" id="svg_101" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="269.33955" y1="71.34139" x2="258.0062" y2="88.00808" id="svg_102" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="296.27164" cy="30.25034" id="svg_103" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="234.38985" y="84.39618" id="svg_104" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="246.42863" y="88.88663" width="16.2963" height="28.51852" id="svg_105"/>
  <rect fill="#00ff7f" stroke="#0f0f00" stroke-opacity="null" x="283.37534" y="87.42321" width="16.2963" height="28.51852" id="svg_106"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="301.94897" y1="39.54923" x2="313.43045" y2="55.84552" id="svg_107" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="270.83069" y="22.86952" id="svg_108" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text style="cursor: move;" fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="242.61744" y="86.78501" id="svg_109" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="289.93637" y="81.59581" id="svg_110" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="298.16397" y="83.98464" id="svg_111" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="287.11609" y="107.55284" id="svg_112" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="250.53975" y="109.01626" id="svg_113" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="311.52625" y="50.25886" id="svg_114" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="319.75385" y="52.64769" id="svg_115" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="295.97788" y="15.24028" id="svg_116" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="271.50633" y="47.11924" id="svg_117" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
</svg>  

* 8）先左后右双向旋转
	*  在C的子树$$C_L$$或$$C_R$$中插入新结点，该子树的高度增1.结点A的平衡因子变为+2，发生了不平衡
	*  从结点A起沿插入路径选取3个结点A、B和C（“<”型）
	*  以结点C为旋转轴，先做单向左旋
	*  再以结点C为旋转轴，做单向右旋

<svg width="580" height="196" >
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="36.51837" y1="68.66665" x2="25.18502" y2="85.33334" id="svg_17" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="72.12767" cy="26.48324" id="svg_19" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="50.13825" y="21.6261" id="svg_22" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="41.63749" cy="60.73815" id="svg_25" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="119.78439" y="48.6286" id="svg_31" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="103.53049" y="53.85076" width="16.2963" height="50.87146" id="svg_33"/>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="17.27777" y="86.2037" width="16.2963" height="63.2244" id="svg_37"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="53.78541" y1="68.27233" x2="65.26689" y2="84.56862" id="svg_38" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="22.05019" y="55.79635" id="svg_40" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="128.01198" y="51.01743" id="svg_41" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="8.71685" y="81.35191" id="svg_42" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="16.94445" y="83.74074" id="svg_43" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="21.01852" y="106.33333" id="svg_46" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="107.64161" y="73.98039" id="svg_47" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="80.85192" y="83.37386" id="svg_48" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="65.33224" y="79.64487" id="svg_49" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="69.84205" y="10.18954" id="svg_50" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+1</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="67.1066" y1="100.90647" x2="55.77325" y2="117.57316" id="svg_51" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="72.22572" cy="92.97797" id="svg_52" rx="10" ry="10"/>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="81.98364" y="119.03175" width="16.2963" height="40.87146" id="svg_54"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="77.90305" y1="102.27686" x2="89.38453" y2="118.57315" id="svg_55" stroke-linejoin="null" stroke-linecap="null"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="45.18743" y="113.59173" id="svg_56" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="53.41503" y="115.98056" id="svg_57" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="78.07733" y="146.2202" id="svg_58" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="89.67545" y="113.9621" id="svg_60" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="97.90305" y="116.35093" id="svg_61" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_62" y2="55.00003" x2="102.64709" y1="33.82356" x1="82.6471" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_63" y2="53.82356" x2="49.11769" y1="33.82356" x1="63.82357" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <text fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="37.68519" y="46.7037" id="svg_64" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_66" y="144.95476" x="97.3756" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_67" y="144.95476" x="89.14031" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">-</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="47.866" y="118.44351" width="16.2963" height="40.87146" id="svg_69"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="43.95969" y="145.63197" id="svg_70" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_71" y="143.98191" x="63.25796" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_72" y="143.98191" x="55.02267" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">-</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="173.96718" y1="68.66665" x2="162.63383" y2="85.33334" id="svg_73" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="209.57648" cy="26.48324" id="svg_74" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="187.58706" y="21.6261" id="svg_75" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="179.0863" cy="60.73815" id="svg_76" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="257.2332" y="48.6286" id="svg_77" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="240.9793" y="53.85076" width="16.2963" height="50.87146" id="svg_78"/>
  <rect stroke="#0f0f00" fill="#007fff" stroke-opacity="null" x="185.59615" y="118.37762" width="16.2963" height="63.2244" id="svg_79"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="191.23422" y1="68.27233" x2="202.7157" y2="84.56862" id="svg_80" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="159.499" y="55.79635" id="svg_81" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="265.46079" y="51.01743" id="svg_82" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="146.16566" y="81.35191" id="svg_83" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="154.39326" y="83.74074" id="svg_84" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="189.3369" y="138.50724" id="svg_85" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="245.09042" y="73.98039" id="svg_86" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="218.30073" y="83.37386" id="svg_87" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="202.78105" y="79.64487" id="svg_88" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+1</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="207.29086" y="10.62433" id="svg_89" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+2</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="204.55541" y1="100.90647" x2="193.22206" y2="117.57316" id="svg_90" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#ffaaaa" stroke="#0f0f00" cx="209.67453" cy="92.97797" id="svg_91" rx="10" ry="10"/>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="219.43245" y="119.03175" width="16.2963" height="40.87146" id="svg_92"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="215.35186" y1="102.27686" x2="226.83334" y2="118.57315" id="svg_93" stroke-linejoin="null" stroke-linecap="null"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="182.63624" y="113.59173" id="svg_94" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="190.86384" y="115.98056" id="svg_95" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="215.52614" y="146.2202" id="svg_96" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="227.12426" y="113.9621" id="svg_97" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="235.35186" y="116.35093" id="svg_98" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_99" y2="55.00003" x2="240.0959" y1="33.82356" x1="220.09591" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_100" y2="53.82356" x2="186.5665" y1="33.82356" x1="201.27238" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="175.134" y="46.7037" id="svg_101" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_102" y="144.95476" x="234.82441" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_103" y="144.95476" x="226.58912" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">-</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="154.72658" y="86.2037" width="16.2963" height="63.2244" id="svg_108"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="158.46733" y="106.33333" id="svg_109" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="315.46936" y1="106.05795" x2="304.13601" y2="122.72464" id="svg_110" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="362.81779" cy="26.48324" id="svg_111" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="340.82837" y="21.6261" id="svg_112" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="320.58848" cy="98.12945" id="svg_113" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="395.25711" y="47.32425" id="svg_114" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="386.39452" y="56.02467" width="16.2963" height="50.87146" id="svg_115"/>
  <rect stroke="#0f0f00" fill="#007fff" stroke-opacity="null" x="329.70702" y="124.89935" width="16.2963" height="63.2244" id="svg_116"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="326.64944" y1="106.96798" x2="338.13092" y2="123.26427" id="svg_117" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="287.85488" y="119.2746" id="svg_118" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="403.4847" y="49.71308" id="svg_119" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="295.89544" y="121.13204" id="svg_120" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="333.44777" y="145.02898" id="svg_121" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="390.50564" y="76.1543" id="svg_122" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="347.62899" y="54.24343" id="svg_123" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="332.10932" y="50.51444" id="svg_124" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+2</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="360.53217" y="10.62433" id="svg_125" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+2</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="333.88367" y1="71.77603" x2="322.55032" y2="88.44272" id="svg_126" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#ffaaaa" stroke="#0f0f00" cx="339.00279" cy="63.84753" id="svg_127" rx="10" ry="10"/>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="354.41289" y="83.81436" width="16.2963" height="40.87146" id="svg_128"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="350.3323" y1="67.05946" x2="361.81378" y2="83.35575" id="svg_129" stroke-linejoin="null" stroke-linecap="null"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="338.92103" y="119.67868" id="svg_130" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="347.14863" y="122.06751" id="svg_131" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="350.50658" y="111.00281" id="svg_132" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="362.1047" y="78.7447" id="svg_133" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="370.3323" y="81.13353" id="svg_134" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_135" y2="55.00003" x2="393.33721" y1="33.82356" x1="373.33721" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_136" y2="53.82356" x2="339.80781" y1="33.82356" x1="354.51369" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="316.63618" y="84.095" id="svg_137" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_138" y="109.73737" x="369.80485" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_139" y="109.73737" x="361.56956" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">-</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="296.22876" y="123.595" width="16.2963" height="63.2244" id="svg_140"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="299.96951" y="143.72463" id="svg_141" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="455.19799" y1="72.1449" x2="443.86464" y2="88.81159" id="svg_142" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#56ffaa" stroke="#0f0f00" cx="520.37251" cy="63.43976" id="svg_143" rx="10" ry="10"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" x="530.99178" y="51.19132" id="svg_144" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <ellipse fill="#00ff7f" stroke="#0f0f00" cx="460.31711" cy="64.2164" id="svg_145" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="545.85531" y="85.15034" id="svg_146" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">A</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="536.99272" y="93.85076" width="16.2963" height="50.87146" id="svg_147"/>
  <rect stroke="#0f0f00" fill="#007fff" stroke-opacity="null" x="469.43565" y="90.98631" width="16.2963" height="63.2244" id="svg_148"/>
  <line fill="none" stroke="#0f0f00" stroke-opacity="null" x1="466.37807" y1="73.05494" x2="477.85955" y2="89.35123" id="svg_149" stroke-linejoin="null" stroke-linecap="null"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="428.12112" y="84.49199" id="svg_150" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="554.0829" y="87.53917" id="svg_151" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="435.62407" y="87.21899" id="svg_152" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="473.1764" y="111.11594" id="svg_153" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="541.10384" y="113.98039" id="svg_154" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="487.35763" y="20.33039" id="svg_155" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="471.83795" y="16.60139" id="svg_156" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="518.08689" y="47.58085" id="svg_157" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="473.61231" y1="37.86299" x2="462.27896" y2="54.52968" id="svg_158" stroke-linejoin="null" stroke-linecap="null"/>
  <ellipse fill="#ffaaaa" stroke="#0f0f00" cx="478.73143" cy="29.93449" id="svg_159" rx="10" ry="10"/>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="497.18501" y="92.94479" width="16.2963" height="40.87146" id="svg_160"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="478.64966" y="85.76564" id="svg_162" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="486.87726" y="88.15447" id="svg_163" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">L</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="493.2787" y="120.13325" id="svg_164" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <text style="cursor: move;" stroke="#0f0f00" fill="#000000" stroke-width="0" x="494.87681" y="84.39688" id="svg_165" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">C</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="503.10441" y="86.78571" id="svg_166" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">R</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_167" y2="58.0435" x2="509.58758" y1="36.86704" x1="489.58759" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_168" y2="92.95399" x2="502.57992" y1="72.954" x1="517.2858" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <text style="cursor: move;" fill="#ff0000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="456.36481" y="50.18195" id="svg_169" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_170" y="118.8678" x="512.57696" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_171" y="118.8678" x="504.34167" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">-</text>
  <rect stroke="#0f0f00" fill="#00ff7f" stroke-opacity="null" x="435.95739" y="89.68196" width="16.2963" height="63.2244" id="svg_172"/>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="439.69814" y="109.81158" id="svg_173" font-size="17" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">h</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_174" y2="92.82611" x2="543.93541" y1="71.64964" x1="523.93541" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="440.72981" y="59.2746" id="svg_175" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
  <text stroke="#0f0f00" fill="#000000" stroke-width="0" x="301.00118" y="93.18765" id="svg_176" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">B</text>
</svg>

* 9）先右后左双向旋转
	*  在C的子树$$C_L$$或$$C_R$$中插入新结点，该子树的高度增1.结点A的平衡因子变为-2，发生了不平衡
	*  从结点A起沿插入路径选取3个结点A、B和C（“<”型）
	*  以结点C为旋转轴，先做单向右旋
	*  再以结点C为旋转轴，做单向左旋

<svg width="580" height="199">
  <rect id="svg_79" height="63.2244" width="16.2963" y="126.27255" x="212.154" stroke-opacity="null" fill="#007fff" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_85" y="146.40217" x="215.89475" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <ellipse ry="10" rx="10" id="svg_3" cy="32.6144" cx="62.0685" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_4" y="27.75726" x="40.07908" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <ellipse ry="10" rx="10" id="svg_5" cy="71.65401" cx="93.77931" stroke="#0f0f00" fill="#00ff7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_6" y="54.2813" x="8.94375" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_7" height="50.87146" width="16.2963" y="59.98192" x="14.04543" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <rect id="svg_8" height="63.2244" width="16.2963" y="91.8564" x="110.08947" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_10" y="61.44905" x="102.90016" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_11" y="56.67013" x="17.17134" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_12" y="87.00461" x="116.83956" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_13" y="89.39344" x="125.06716" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_14" y="111.98603" x="113.83022" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_15" y="80.11155" x="18.15655" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_16" y="91.89737" x="42.56307" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_18" y="85.77603" x="55.27307" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_20" y="16.3207" x="59.78288" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">-1</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_21" y2="123.70432" x2="45.71408" y1="107.03763" x1="57.04743" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_23" cy="99.10913" cx="62.16655" stroke="#0f0f00" fill="#00ff7f"/>
  <rect id="svg_24" height="40.87146" width="16.2963" y="125.16291" x="71.92447" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_26" y2="91.21147" x2="115.21054" y1="74.91518" x1="103.72906" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_27" y="119.72289" x="35.12826" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_28" y="122.11172" x="43.35586" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_29" y="152.35136" x="68.01816" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_30" y="120.09326" x="79.61628" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_32" y="122.48209" x="87.84388" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="72.58793" y1="39.95472" x2="92.58792" y2="61.13119" id="svg_34" stroke-linejoin="null" stroke-linecap="null"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_36" y="57.61956" x="89.82701" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="87.31643" y="151.08592" id="svg_39" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="79.08114" y="151.08592" id="svg_44" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-</text>
  <rect id="svg_45" height="40.87146" width="16.2963" y="124.57467" x="37.80683" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_53" y="151.76313" x="33.90052" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="53.19879" y="150.11307" id="svg_59" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.9635" y="150.11307" id="svg_65" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-</text>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_68" y2="93.33393" x2="69.88653" y1="78.77306" x1="85.41813" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_105" y2="124.70431" x2="79.32536" y1="108.40802" x1="67.84388" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_106" y2="58.29995" x2="29.46222" y1="36.76884" x1="52.42874" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_210" cy="32.6144" cx="203.38804" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_211" y="27.75726" x="181.39862" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <ellipse ry="10" rx="10" id="svg_212" cy="71.65401" cx="235.09885" stroke="#0f0f00" fill="#00ff7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_213" y="54.2813" x="150.26329" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_214" height="50.87146" width="16.2963" y="59.98192" x="155.36497" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <rect id="svg_215" height="63.2244" width="16.2963" y="91.8564" x="251.40901" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_216" y="61.44905" x="244.2197" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_217" y="56.67013" x="158.49088" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_218" y="87.00461" x="258.15911" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_219" y="89.39344" x="266.38671" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_220" y="111.98603" x="255.14976" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_221" y="80.11155" x="159.47609" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_222" y="91.89737" x="183.88261" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_223" y="85.77603" x="196.59261" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">-1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_224" y="16.3207" x="201.10242" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">-2</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_225" y2="123.70432" x2="187.03362" y1="107.03763" x1="198.36697" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse ry="10" rx="10" id="svg_226" cy="99.10913" cx="203.48609" stroke="#0f0f00" fill="#ffaaaa"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_228" y2="91.21147" x2="256.53009" y1="74.91518" x1="245.04861" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_229" y="119.72289" x="176.4478" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_230" y="122.11172" x="184.6754" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_232" y="120.09326" x="220.93582" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_233" y="122.48209" x="229.16342" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <line fill="none" stroke="#0f0f00" stroke-width="null" stroke-opacity="null" fill-opacity="null" x1="210.35717" y1="41.13816" x2="230.35716" y2="62.31463" id="svg_234" stroke-linejoin="null" stroke-linecap="null"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_235" y="57.61956" x="231.14655" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">+1</text>
  <rect id="svg_238" height="40.87146" width="16.2963" y="124.57467" x="179.12637" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_239" y="151.76313" x="175.22006" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="194.51833" y="150.11307" id="svg_240" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="186.28304" y="150.11307" id="svg_241" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-</text>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_242" y2="93.33393" x2="211.20607" y1="78.77306" x1="226.73767" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_243" y2="124.70431" x2="220.6449" y1="108.40802" x1="209.16342" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_244" y2="58.29995" x2="170.78177" y1="36.76884" x1="193.74829" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_247" height="63.2244" width="16.2963" y="117.98853" x="358.30785" stroke-opacity="null" fill="#007fff" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_248" y="138.11815" x="362.0486" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <ellipse ry="10" rx="10" id="svg_249" cy="32.6144" cx="340.07444" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_250" y="27.75726" x="318.08502" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <ellipse ry="10" rx="10" id="svg_251" cy="96.50608" cx="382.43614" stroke="#0f0f00" fill="#00ff7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_252" y="54.2813" x="286.94969" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_253" height="50.87146" width="16.2963" y="59.98192" x="292.05137" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <rect id="svg_254" height="63.2244" width="16.2963" y="116.70847" x="398.7463" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_255" y="86.30112" x="391.55699" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_256" y="56.67013" x="295.17728" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_257" y="111.85668" x="405.4964" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_258" y="114.24551" x="413.724" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_259" y="136.8381" x="402.48705" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_260" y="80.11155" x="296.16249" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_261" y="55.8027" x="374.41517" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_262" y="49.68136" x="356.94765" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">-2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_263" y="16.3207" x="337.78882" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">-2</text>
  <ellipse ry="10" rx="10" id="svg_265" cy="63.01446" cx="363.84113" stroke="#0f0f00" fill="#ffaaaa"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_266" y2="116.06354" x2="403.86738" y1="99.76725" x1="392.3859" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_267" y="88.36195" x="324.37681" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_268" y="90.75078" x="332.60441" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_269" y="111.21753" x="350.52163" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_270" y="113.60636" x="358.74923" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_272" y="82.47163" x="378.48384" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <rect id="svg_273" height="40.87146" width="16.2963" y="93.21373" x="327.05538" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_274" y="120.40219" x="323.14907" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="342.44734" y="118.75213" id="svg_275" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="334.21205" y="118.75213" id="svg_276" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-</text>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_277" y2="119.36944" x2="359.72679" y1="104.80857" x1="375.25839" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_278" y2="86.24278" x2="379.2248" y1="69.94649" x1="367.74332" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_280" y2="59.93635" x2="306.27219" y1="40.40972" x1="330.53255" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_281" y2="92.48073" x2="340.59172" y1="69.99552" x1="357.15977" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_282" y2="54.01919" x2="357.15977" y1="39.22629" x1="345.32545" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <rect id="svg_283" height="63.2244" width="16.2963" y="87.21929" x="505.07282" stroke-opacity="null" fill="#007fff" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_284" y="107.34891" x="508.81357" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <ellipse ry="10" rx="10" id="svg_285" cy="58.64991" cx="466.72106" stroke="#0f0f00" fill="#56ffaa"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_286" y="53.79277" x="444.73164" stroke-width="0" stroke="#0f0f00" fill="#000000">A</text>
  <ellipse ry="10" rx="10" id="svg_287" cy="65.73684" cx="529.20111" stroke="#0f0f00" fill="#00ff7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_288" y="80.3168" x="432.53123" stroke-width="0" fill="#000000" stroke="#0f0f00">A</text>
  <rect id="svg_289" height="50.87146" width="16.2963" y="86.01743" x="437.63291" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <rect id="svg_290" height="63.2244" width="16.2963" y="85.93923" x="545.51127" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_291" y="55.53188" x="538.32196" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_292" y="82.70563" x="440.75882" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_293" y="81.08744" x="552.26136" stroke-width="0" fill="#000000" stroke="#0f0f00">B</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_294" y="83.47627" x="560.48896" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_295" y="106.06886" x="549.25202" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_296" y="106.14706" x="441.74403" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_297" y="25.03346" x="521.18013" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_298" y="19.50384" x="503.1209" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <text style="cursor: move;" stroke="#0f0f00" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_299" y="42.35621" x="464.43544" stroke-opacity="null" stroke-width="0" fill="#ff0000">+1</text>
  <ellipse ry="10" rx="10" id="svg_300" cy="32.24523" cx="510.6061" stroke="#0f0f00" fill="#ffaaaa"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_301" y2="85.29431" x2="550.63234" y1="68.99802" x1="539.15086" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_302" y="83.0365" x="484.15952" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_303" y="85.42533" x="492.38712" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">L</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_304" y="80.44829" x="497.2866" stroke-width="0" fill="#000000" stroke="#0f0f00">C</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_305" y="82.83712" x="505.5142" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">R</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_306" y="51.70239" x="525.24881" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">0</text>
  <rect id="svg_307" height="40.87146" width="16.2963" y="86.70485" x="470.86176" stroke-opacity="null" fill="#00ff7f" stroke="#0f0f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="17" id="svg_308" y="113.89331" x="466.95545" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">h</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="486.25372" y="112.24325" id="svg_309" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="478.01843" y="112.24325" id="svg_310" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-</text>
  <line stroke="#0f0f00" stroke-linecap="null" stroke-linejoin="null" id="svg_311" y2="88.60021" x2="506.49176" y1="74.03933" x1="522.02336" fill-opacity="null" stroke-opacity="null" stroke-width="null" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_312" y2="55.47355" x2="525.98976" y1="39.17726" x1="514.50828" stroke-opacity="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_316" y2="86.56357" x2="448.28403" y1="68.81208" x1="459.52664" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_317" y2="87.15528" x2="480.2367" y1="67.62865" x1="470.76924" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_318" y2="53.42747" x2="473.72782" y1="38.04285" x1="503.90534" fill-opacity="null" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
</svg>  

* 10）例子
	* 画出在初始为空的AVL树中依次插入65，5，13，21，19，80，75，37，56时该树的生长过程，并在有旋转时说出旋转的类型。

<svg width="540" height="387" >
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="25.8161" cy="32.6144" id="svg_3" rx="10" ry="10"/>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="23.53048" y="18.40403" id="svg_20" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_2" y="37.625" x="17.70593" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="64.59913" cy="55.53107" id="svg_7" rx="10" ry="10"/>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="62.31351" y="41.3207" id="svg_8" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_9" y="60.54167" x="60.65562" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="83.76579" cy="32.6144" id="svg_12" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="79.39684" y="18.40403" id="svg_13" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_14" y="37.625" x="75.65562" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_15" y2="40.54167" x2="77.84348" y1="48.45833" x1="70.76014" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="141.40419" cy="79.69773" id="svg_16" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="139.11857" y="65.48737" id="svg_17" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_18" y="84.29167" x="132.87735" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="140.98753" cy="32.6144" id="svg_19" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="136.61857" y="18.40403" id="svg_21" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">+2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_22" y="37.625" x="132.87735" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_23" y2="40.54167" x2="135.06521" y1="48.45833" x1="127.98188" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="121.82086" cy="55.53107" id="svg_24" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="119.53524" y="41.3207" id="svg_25" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_26" y="60.54167" x="117.87735" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_27" y2="71.79167" x2="135.12531" y1="63.04167" x1="127.62531" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="238.54352" cy="56.78107" id="svg_28" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="236.2579" y="42.5707" id="svg_29" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="217.71019" cy="32.6144" id="svg_31" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="213.34124" y="18.40403" id="svg_32" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_33" y="61.79167" x="231.68335" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_34" y2="40.54167" x2="211.78787" y1="48.45833" x1="204.70454" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="198.54352" cy="55.53107" id="svg_35" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="196.2579" y="41.3207" id="svg_36" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_37" y="60.54167" x="194.60002" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_38" y2="48.875" x2="232.26464" y1="40.125" x1="224.76464" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_30" y="38.04167" x="209.18335" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <path id="svg_41" d="m167.45308,58.83655c-0.88623,-0.32214 -0.77042,-0.51718 1.38474,-2.32293c1.08765,-0.91171 1.97791,-1.68421 1.97791,-1.71663c0,-0.03238 -3.00412,-0.05885 -6.67694,-0.05885l-6.67593,0l0,-1.7077l0,-1.70763l6.72931,0c5.18848,0 6.67191,-0.05144 6.47653,-0.22468c-0.13898,-0.12357 -1.08865,-0.94364 -2.10883,-1.82235c-1.92453,-1.65641 -1.92453,-2.10068 0.00302,-2.2383c0.95874,-0.06858 15.88635,5.19612 16.39996,5.78376c-4.97296,2.09821 -10.91641,4.29451 -16.39191,6.23098c-0.28802,0 -0.79156,-0.09709 -1.11786,-0.21568z" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="317.34752" cy="56.78107" id="svg_42" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="315.0619" y="42.5707" id="svg_43" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="296.51418" cy="32.6144" id="svg_44" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="292.14523" y="18.40403" id="svg_45" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_46" y="61.79167" x="310.48735" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_47" y2="64.29167" x2="311.84187" y1="72.20833" x1="304.75853" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="277.34752" cy="55.53107" id="svg_48" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="275.0619" y="41.3207" id="svg_49" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_50" y="60.54167" x="273.40401" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_51" y2="48.875" x2="311.06863" y1="40.125" x1="303.56863" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_52" y="38.04167" x="287.98734" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="296.51418" cy="80.13085" id="svg_53" rx="10" ry="10"/>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="292.14523" y="65.92048" id="svg_54" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_55" y="85.55811" x="287.98734" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_56" y2="40.54167" x2="290.59187" y1="48.45833" x1="283.50853" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_57" y="44.29167" x="153.95833" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">左右双旋</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="396.93085" cy="56.78107" id="svg_58" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="394.64523" y="42.5707" id="svg_59" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="376.09752" cy="32.6144" id="svg_60" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="371.72857" y="18.40403" id="svg_61" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_62" y="61.79167" x="390.07068" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_63" y2="64.29167" x2="391.4252" y1="72.20833" x1="384.34187" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="356.93085" cy="55.53107" id="svg_64" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="354.64523" y="41.3207" id="svg_65" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_66" y="60.54167" x="352.98735" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_67" y2="48.875" x2="390.65197" y1="40.125" x1="383.15197" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_68" y="38.04167" x="367.57068" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="376.09752" cy="80.13085" id="svg_69" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="371.72857" y="65.92048" id="svg_70" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_71" y="85.55811" x="367.57068" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_72" y2="40.54167" x2="370.1752" y1="48.45833" x1="363.09187" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="356.93085" cy="101.5534" id="svg_73" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="354.64523" y="87.34304" id="svg_74" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_75" y="106.564" x="348.40401" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_76" y2="86.56401" x2="370.1752" y1="94.48067" x1="363.09187" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="493.8902" cy="56.78107" id="svg_77" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="491.60458" y="42.5707" id="svg_78" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="473.05687" cy="32.6144" id="svg_79" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="468.68792" y="18.40403" id="svg_80" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_82" y2="64.29167" x2="488.38455" y1="72.20833" x1="481.30122" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="453.8902" cy="55.53107" id="svg_83" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="451.60458" y="41.3207" id="svg_84" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_85" y="60.54167" x="449.9467" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_86" y2="72.20833" x2="510.11132" y1="63.45833" x1="502.61132" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_87" y="38.04167" x="464.53003" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="473.05687" cy="80.13085" id="svg_88" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="468.68792" y="65.92048" id="svg_89" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_90" y="61.39145" x="486.61336" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_91" y2="40.54167" x2="467.13455" y1="48.45833" x1="460.05122" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="515.97353" cy="79.47007" id="svg_92" rx="10" ry="10"/>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="514.10458" y="66.92637" id="svg_93" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_94" y="85.314" x="464.11336" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_97" y2="48.875" x2="487.61132" y1="40.125" x1="480.11132" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_81" y="85.125" x="508.6967" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <path id="svg_98" d="m423.26233,58.83655c-0.88623,-0.32215 -0.77042,-0.51718 1.38474,-2.32293c1.08765,-0.91171 1.97787,-1.68421 1.97787,-1.71663c0,-0.03237 -3.00409,-0.05885 -6.67691,-0.05885l-6.67593,0l0,-1.7077l0,-1.70763l6.72931,0c5.18848,0 6.67188,-0.05144 6.47653,-0.22468c-0.13901,-0.12357 -1.08865,-0.94364 -2.10886,-1.82235c-1.92453,-1.6564 -1.92453,-2.10067 0.00305,-2.2383c0.95874,-0.06858 15.88632,5.19612 16.39993,5.78377c-4.97293,2.09821 -10.91641,4.29451 -16.39188,6.23098c-0.28802,0 -0.7916,-0.09709 -1.11786,-0.21568z" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_99" y="44.29167" x="414.76756" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">右旋</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="55.97164" cy="167.80699" id="svg_100" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="53.68602" y="153.59663" id="svg_101" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="35.13831" cy="143.64033" id="svg_102" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="30.76935" y="129.42996" id="svg_103" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-2</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_104" y2="175.3176" x2="50.46599" y1="183.23426" x1="43.38266" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="15.97164" cy="166.55699" id="svg_105" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="13.68602" y="152.34663" id="svg_106" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_107" y="171.56759" x="12.02813" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_108" y2="207.01028" x2="92.21877" y1="198.26028" x1="84.71877" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_109" y="149.06759" x="26.61146" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="35.13831" cy="191.15677" id="svg_110" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="30.76935" y="176.94641" id="svg_111" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_112" y="172.41737" x="48.6948" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_113" y2="151.5676" x2="29.21599" y1="159.48426" x1="22.13266" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="98.08099" cy="214.27201" id="svg_114" rx="10" ry="10"/>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="96.21203" y="201.72832" id="svg_115" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_116" y="196.33993" x="26.1948" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_117" y2="159.90093" x2="49.69275" y1="151.15093" x1="42.19275" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_118" y="219.92694" x="90.80415" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_119" y2="183.23426" x2="72.19276" y1="174.48426" x1="64.69276" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="78.05497" cy="190.496" id="svg_120" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="76.18602" y="177.9523" id="svg_121" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_122" y="196.15093" x="70.77813" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="158.9566" cy="140.5193" id="svg_146" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="156.67098" y="126.30894" id="svg_147" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="144.39151" cy="164.89033" id="svg_148" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="140.02256" y="150.67996" id="svg_149" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_150" y2="148.0299" x2="153.45095" y1="155.94657" x1="146.36762" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="125.22485" cy="187.807" id="svg_151" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="122.93923" y="173.59663" id="svg_152" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_153" y="192.81759" x="121.28134" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_154" y2="179.72259" x2="195.20373" y1="170.97259" x1="187.70373" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_155" y="170.3176" x="135.86467" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="162.20242" cy="189.28575" id="svg_156" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="157.83346" y="175.07538" id="svg_157" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_158" y="145.12968" x="151.67976" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_159" y2="172.8176" x2="138.4692" y1="180.73426" x1="131.38586" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="201.06595" cy="186.98432" id="svg_160" rx="10" ry="10"/>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="199.197" y="174.44063" id="svg_161" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_162" y="194.46891" x="153.25891" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_163" y2="181.15093" x2="158.94596" y1="172.40093" x1="151.44596" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_164" y="192.63925" x="193.78911" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_165" y2="155.94657" x2="175.17772" y1="147.19657" x1="167.67772" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="181.03993" cy="163.20831" id="svg_166" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="179.17098" y="150.66461" id="svg_167" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_168" y="168.86324" x="173.76309" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <path id="svg_169" d="m96.61974,171.52914c-0.88623,-0.32214 -0.77042,-0.51718 1.38474,-2.32294c1.08765,-0.9117 1.97791,-1.6842 1.97791,-1.71661c0,-0.03238 -3.00412,-0.05885 -6.67694,-0.05885l-6.67593,0l0,-1.7077l0,-1.70763l6.72931,0c5.18848,0 6.67191,-0.05145 6.47653,-0.22469c-0.13898,-0.12357 -1.08865,-0.94363 -2.10883,-1.82234c-1.92453,-1.6564 -1.92453,-2.10068 0.00302,-2.23831c0.95874,-0.06857 15.88635,5.19612 16.39996,5.78377c-4.97296,2.09822 -10.91641,4.29451 -16.39191,6.23099c-0.28802,0 -0.79156,-0.09709 -1.11786,-0.21568z" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_170" y="156.98426" x="83.12499" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">左旋</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="283.46815" cy="140.5193" id="svg_171" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="281.18253" y="126.30894" id="svg_172" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="268.90306" cy="164.89033" id="svg_173" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="264.53411" y="150.67996" id="svg_174" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_175" y2="148.0299" x2="277.9625" y1="155.94657" x1="270.87917" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="249.7364" cy="187.807" id="svg_176" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="247.45078" y="173.59663" id="svg_177" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_178" y="192.81759" x="245.79289" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_179" y2="179.72259" x2="319.71528" y1="170.97259" x1="312.21528" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_180" y="170.3176" x="260.37622" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="286.71397" cy="189.28575" id="svg_181" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="282.34501" y="175.07538" id="svg_182" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_183" y="145.12968" x="276.19131" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_184" y2="194.90093" x2="320.89742" y1="202.8176" x1="313.81408" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="325.5775" cy="186.98432" id="svg_185" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="323.70855" y="174.44063" id="svg_186" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_187" y="194.46891" x="277.77046" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_188" y2="181.15093" x2="283.45751" y1="172.40093" x1="275.95751" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_189" y="192.63925" x="318.30066" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_190" y2="155.94657" x2="299.68927" y1="147.19657" x1="292.18927" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="305.55148" cy="163.20831" id="svg_191" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="303.26587" y="150.66461" id="svg_192" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_193" y="168.86324" x="298.27465" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="305.55148" cy="211.17025" id="svg_195" rx="10" ry="10"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_197" y="216.82517" x="298.27465" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">75</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_198" y2="172.8176" x2="262.98075" y1="180.73426" x1="255.89741" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="398.47118" cy="140.5193" id="svg_199" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="396.18556" y="126.30894" id="svg_200" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="383.90609" cy="164.89033" id="svg_201" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="379.53714" y="150.67996" id="svg_202" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_203" y2="148.0299" x2="392.96553" y1="155.94657" x1="385.8822" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="364.73943" cy="187.807" id="svg_204" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="362.45381" y="173.59663" id="svg_205" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_206" y="192.81759" x="360.79592" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_207" y2="179.72259" x2="434.71831" y1="170.97259" x1="427.21831" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_208" y="170.3176" x="375.37925" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="389.599" cy="189.28575" id="svg_209" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="405.26471" y="175.07538" id="svg_210" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_211" y="145.12968" x="391.19434" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_212" y2="171.5676" x2="420.48378" y1="179.48426" x1="413.40044" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="440.58053" cy="186.98432" id="svg_213" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_215" y="194.46891" x="380.65549" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_216" y2="181.15093" x2="398.46054" y1="172.40093" x1="390.96054" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_217" y="192.63925" x="433.30369" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_218" y2="155.94657" x2="414.6923" y1="147.19657" x1="407.1923" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="420.55451" cy="163.20831" id="svg_219" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="418.26889" y="150.66461" id="svg_220" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="415.13785" cy="189.08691" id="svg_222" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_223" y="168.07517" x="412.44434" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">75</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_224" y2="172.8176" x2="377.98378" y1="180.73426" x1="370.90044" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_221" y="193.44657" x="407.02767" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="397.34804" y="175.07538" id="svg_225" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="440.26471" y="175.49205" id="svg_227" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <path id="svg_228" d="m343.28644,169.66989c-0.88623,-0.32214 -0.77045,-0.51718 1.3847,-2.32294c1.08765,-0.9117 1.97794,-1.6842 1.97794,-1.71661c0,-0.03238 -3.00412,-0.05885 -6.67694,-0.05885l-6.67593,0l0,-1.7077l0,-1.70763l6.72931,0c5.18848,0 6.67191,-0.05145 6.4765,-0.22469c-0.13898,-0.12357 -1.08862,-0.94363 -2.10883,-1.82234c-1.9245,-1.6564 -1.9245,-2.10068 0.00305,-2.23831c0.95874,-0.06857 15.88635,5.19612 16.39993,5.78378c-4.97293,2.09821 -10.91641,4.29451 -16.39188,6.23097c-0.28806,0 -0.79156,-0.09709 -1.11786,-0.21568z" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_229" y="155.12501" x="329.79167" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">右左双旋</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="55.56178" cy="269.68597" id="svg_230" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="53.27616" y="255.47561" id="svg_231" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="40.9967" cy="294.057" id="svg_232" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="36.62774" y="279.84663" id="svg_233" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_234" y2="277.19657" x2="50.05613" y1="285.11324" x1="42.9728" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="57.66336" cy="343.22367" id="svg_235" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="55.37774" y="329.0133" id="svg_236" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_237" y="348.65093" x="51.63652" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">37</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_238" y2="308.88926" x2="91.80892" y1="300.13926" x1="84.30892" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_239" y="299.48427" x="32.46986" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="46.6896" cy="318.45242" id="svg_240" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="62.35531" y="304.24205" id="svg_241" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_242" y="274.29635" x="48.28494" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_243" y2="300.73427" x2="77.57438" y1="308.65093" x1="70.49105" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="97.67113" cy="316.15099" id="svg_244" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_245" y="323.63558" x="37.7461" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_246" y2="310.3176" x2="55.55115" y1="301.5676" x1="48.05115" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_247" y="321.80592" x="90.39429" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_248" y2="285.11324" x2="71.7829" y1="276.36324" x1="64.2829" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="77.64512" cy="292.37498" id="svg_249" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="75.3595" y="279.83128" id="svg_250" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="72.22845" cy="318.25358" id="svg_251" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_252" y="297.24184" x="69.53495" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">75</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_253" y2="328.23427" x2="70.90771" y1="336.15093" x1="63.82438" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_254" y="322.61324" x="64.11828" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="54.43865" y="304.24205" id="svg_255" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="97.35531" y="304.65872" id="svg_256" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="21.83003" cy="316.97366" id="svg_257" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="19.54441" y="302.7633" id="svg_258" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_259" y="321.98426" x="17.88652" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_260" y2="301.98427" x2="35.07438" y1="309.90093" x1="27.99105" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="173.91273" cy="269.68597" id="svg_261" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="171.21044" y="255.47561" id="svg_262" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-2</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="159.34764" cy="294.057" id="svg_263" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="154.97869" y="279.84663" id="svg_264" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_265" y2="277.19657" x2="168.40708" y1="285.11324" x1="161.32375" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="176.01431" cy="343.22367" id="svg_266" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="174.56202" y="331.09663" id="svg_267" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_268" y="348.65093" x="169.98747" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">37</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_269" y2="356.38926" x2="190.99319" y1="347.63926" x1="183.49319" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_270" y="299.48427" x="150.8208" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="165.04055" cy="318.45242" id="svg_271" rx="10" ry="10"/>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="183.20626" y="306.74205" id="svg_272" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_273" y="274.29635" x="166.63589" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_274" y2="300.73427" x2="195.92532" y1="308.65093" x1="188.84199" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="196.85541" cy="363.65099" id="svg_275" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_276" y="323.63558" x="156.09704" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_277" y2="310.3176" x2="173.90209" y1="301.5676" x1="166.40209" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_278" y="369.30592" x="189.1619" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">56</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_279" y2="285.11324" x2="190.13385" y1="276.36324" x1="182.63385" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="195.99606" cy="292.37498" id="svg_280" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="193.71044" y="279.83128" id="svg_281" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="190.57939" cy="318.25358" id="svg_282" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_283" y="297.24184" x="187.88589" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">75</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_284" y2="328.23427" x2="189.25866" y1="336.15093" x1="182.17533" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_285" y="322.61324" x="182.46922" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="172.78959" y="304.24205" id="svg_286" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="196.53959" y="352.15872" id="svg_287" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="140.18097" cy="316.97366" id="svg_288" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="137.89535" y="302.7633" id="svg_289" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_290" y="321.98426" x="136.23747" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_291" y2="301.98427" x2="153.42532" y1="309.90093" x1="146.34199" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_292" y2="308.88926" x2="210.15986" y1="300.13926" x1="202.65986" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="216.02208" cy="316.15099" id="svg_293" rx="10" ry="10"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_294" y="321.80592" x="208.74524" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="215.70626" y="304.65872" id="svg_295" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="321.11111" cy="269.68597" id="svg_296" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="318.40882" y="255.47561" id="svg_297" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">-1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="306.54602" cy="294.057" id="svg_298" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="302.17707" y="279.84663" id="svg_299" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_300" y2="277.19657" x2="315.60546" y1="285.11324" x1="308.52213" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="323.21269" cy="343.22367" id="svg_301" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="321.7604" y="331.09663" id="svg_302" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_303" y="348.65093" x="315.10251" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">37</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_304" y2="337.22259" x2="349.85824" y1="328.47259" x1="342.35824" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_305" y="299.48427" x="298.01918" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">13</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="312.23893" cy="318.45242" id="svg_306" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="330.40464" y="306.74205" id="svg_307" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_308" y="274.29635" x="313.83427" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">21</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_309" y2="300.73427" x2="343.1237" y1="308.65093" x1="336.04037" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="355.72045" cy="344.48433" id="svg_310" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_311" y="323.63558" x="303.29542" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">19</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_312" y2="310.3176" x2="321.10047" y1="301.5676" x1="313.60047" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_314" y2="285.11324" x2="337.33223" y1="276.36324" x1="329.83223" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="343.19444" cy="292.37498" id="svg_315" rx="10" ry="10"/>
  <text style="cursor: move;" stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="340.90882" y="279.83128" id="svg_316" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="337.77777" cy="318.25358" id="svg_317" rx="10" ry="10"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_318" y="297.24184" x="335.08427" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">75</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_319" y2="328.23427" x2="336.45704" y1="336.15093" x1="329.3737" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_320" y="348.86324" x="348.4176" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">64</text>
  <text fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="319.98797" y="304.24205" id="svg_321" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="355.40464" y="332.99205" id="svg_322" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="287.37935" cy="316.97366" id="svg_323" rx="10" ry="10"/>
  <text style="cursor: move;" fill="#007f00" stroke="#0f0f00" stroke-width="0" stroke-opacity="null" x="285.09373" y="302.7633" id="svg_324" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_325" y="321.98426" x="283.43585" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_326" y2="301.98427" x2="300.6237" y1="309.90093" x1="293.54037" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_327" y2="308.88926" x2="357.35824" y1="300.13926" x1="349.85824" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <ellipse fill="#ffff56" stroke="#0f0f00" cx="363.22046" cy="316.15099" id="svg_328" rx="10" ry="10"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_329" y="321.80592" x="355.94362" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">80</text>
  <text stroke="#0f0f00" fill="#007f00" stroke-width="0" stroke-opacity="null" x="362.90464" y="304.65872" id="svg_330" font-size="9" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_313" y="323.05592" x="330.11028" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#ff0000">56</text>
  <path id="svg_331" d="m249.95308,321.75323c-0.88623,-0.32214 -0.77042,-0.51718 1.38474,-2.32294c1.08765,-0.91171 1.97791,-1.6842 1.97791,-1.71661c0,-0.03238 -3.00412,-0.05887 -6.67694,-0.05887l-6.67593,0l0,-1.70767l0,-1.70764l6.72931,0c5.18848,0 6.67191,-0.05145 6.47653,-0.22467c-0.13898,-0.1236 -1.08865,-0.94366 -2.10883,-1.82236c-1.92453,-1.6564 -1.92453,-2.10068 0.00302,-2.23831c0.95874,-0.06857 15.88634,5.19614 16.39995,5.78378c-4.97293,2.09821 -10.91638,4.29449 -16.39189,6.23099c-0.28802,0 -0.79156,-0.09711 -1.11786,-0.2157z" stroke-opacity="null" stroke-width="null" stroke="#0f0f00" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="9" id="svg_332" y="307.20835" x="236.45833" stroke-opacity="null" stroke-width="0" stroke="#0f0f00" fill="#000000">左右双旋</text>
</svg>

* 11）删除
	*	如果被删除结点A没有孩子，则直接删除之，并作平衡化处理
	*	如果被删除结点A最多只有一个孩子，那么将结点A从树中删去，并将其双亲指向它的指针指向它的唯一孩子，并作平衡化处理
	*	如果被删除结点A有两个子女，则用该结点的直接前驱S替代被删结点，然后对直接前驱S作删除处理（S只有一个孩子或没有孩子）	

---

### **第四节 哈希表**  

####  一、哈希表  

* 1）散列表
	* 哈希（Hash）表又称散列表
	* 散列表是一种直接计算记录存放地址的方法，它在关键码与存储位置之间直接建立了映像
* 2）函数
	* 哈希函数是从关键字空间存储地址空间的一种映像
	* 哈希函数在记录的关键字与记录的存储地址之间建立起一种对应关系。可写成：  
	$$addr(a_i) = H(key_i)$$ 
	* H(·)为哈希函数
	* $$Key_i$$是表中元素$$a_i$$关键字，$$addr(a_i)$$是存储地址   
* 3）查找
	* 哈希差值也叫散列查找，是利用哈希函数进行查找的过程
	* 首先利用哈希函数及记录的关键字计算出记录的存储地址
	* 然后直接到指定地址进行查找  
	* 不需要经过比较，一次存取就能得到所查元素  
* 4）冲突
	* 不同的记录，其关键字通过哈希函数的计算，可能得到相同的地址
	* 把不同的记录映射到同一个散列地址上，这种现象称为冲突
* 5）定义
	* 根据设定的哈希函数H(key)和所选中的处理冲突的方法
	* 将一组关键字映象到一个有限的、地址连续的地址集（区间）上
	* 并以关键字在地址集中的“象”作为相应记录在表中的存储位置
	* 如此构造所得的查找表称之为“哈希表”  

####  二、哈希函数 

* 1）均匀性
	* 哈希函数实现的一般是从一个大的集合（部分元素，空间位置上一般不连续）到一个小的集合（空间连续）的映射
	* 一个好的哈希函数，对于记录中的任何关键字，将其映射到地址集合中任何一个地址的概率应该是相等的
	* 即关键字经过哈希函数得到一个“随机的地址”
* 2）要求
	* 哈希函数应是简单的，能在较短的时间内计算出结果
	* 哈希函数的定义域必须包括需要存储的全部关键字，如果散列表允许有m个地址时，其值域必须在0到m-1之间
	* 散列函数计算出来的地址应能均匀分布在整个地址空间中 
* 3）直接定址法
	* 在直接定址法中，哈希函数取关键字的线性函数  
	H(key) = a*key + b  
	其中a和b为常数  
	*  例子 
	H(key) = key - 2009150000    
	
	|004|2009150004|麦伟杰|男|计算机学院 02
	|-
	|005|2009150005|张喆|男|计算机学院 05
	|006|2009150006|赖少琪|女|计算机学院 01
	|011|2009150011|冯文松|男|计算机学院 02
	|014|2009150014|赵慧敏|女|计算机学院 02
	|020|2009150020|冯冠翔|男|计算机学院 02
	|024|2009150024|张芙铭|男|计算机学院 03  

	* 特性
		* 直接定址法仅适合于地址集合的大小与关键字集合的大小相等的情况
		* 当a=1时，H(key) = key，即用关键字做地址
		* 在实际应用中能使用这种哈希函数的情况很少
* 4）数字分析法
	* 假设关键字集合中的每个关键字都是由s位数字组成($$u_1, u_2, ..., u_s$$)  
	* 分析关键字集中的全体  
	* 从中提取分布均匀的若干位或它们的组合作为地址。
	* 例子1
		* 有80个记录，关键字为10位十进制数，哈希地址为3位十进制数  

		|1|2|3|4|5|6|7|8|9|10|-
		|-
		|2|0|0|8|1|3|0|0|4|0|方舒庭
		|2|0|0|8|1|3|0|1|7|4|朱子超
		|2|0|0|8|1|3|0|4|3|7|李智达
		|2|0|0|8|1|3|0|4|6|7|任哲
		|2|0|0|8|1|3|0|4|7|7|钟志明
		|2|0|0|8|1|5|0|0|9|3|吾拉木
		|2|0|0|8|1|5|0|0|9|9|张凯
		|2|0|0|8|1|6|0|1|2|5|梁振杰
		|2|0|0|8|1|3|0|3|9|3|陈曦
		|2|0|0|9|1|5|0|0|0|4|麦俊杰
		|2|0|0|9|1|5|0|0|0|5|张喆  
		
		 *  分析：
			 * 1列只取2
			 * 23列只取0
			 * 4列只取8，9
			 * 57列只取1，0
			 * 6列只取3，5，6
			 * 8910数字分布近乎随机
		 * 所以：取8910三位作为哈希地址
		 
	* 例子2
		* 有80个记录，关键字为8位十进制数，哈希地址为2位十进制数  

		|1|2|3|4|5|6|7|8|
		|-
		|8|1|3|4|6|5|3|2
		|8|1|3|7|2|2|4|2
		|8|1|3|8|7|4|2|2
		|8|1|3|0|1|3|6|7
		|8|1|3|2|2|8|1|7
		|8|1|3|3|8|9|6|7
		|8|1|3|6|8|5|3|7
		|8|1|4|1|9|3|5|5

		 *  分析：
			 * 1列只取8
			 * 2列只取1
			 * 3列只取3，4
			 * 8列只取2，7，5
			 * 4567数字分布近乎随机
		 * 所以：取4567任意两位 或 两位与另两位的叠加 作为哈希地址
	* 特性
		* 数字分析发仅使用于事先明确直到表中所有关键码每一位数值的分布情况
		* 数字分析法完全依赖于关键码集合
		* 如果换一个关键码集合，选择哪几位要重新决定   
* 5）平方取中法
	* 以关键字的平方值的中间几位作为存储地址。
	* 求"关键字的平方值"的目的是“扩大差别”
	* 同时平方值的中间各位又能收到整个关键字中各位的影响
	* 此方法在词典处理中使用十分广泛。
	* 它先计算构成关键码的标识符的内码的平方，然后按照散列表的大小取中间的若干为作为散列地址。
	* 例子
		
		|标识符|内码|内码的平方|散列地址
		|-
		|A|01|01|001
		|A1|0134|20420|042
		|B|02|4|004
		|DMAX|04150130|21526443617100|443
		|DMAX1|0415013034|5264473522151420|352
		|AMAX|01150130|135423617100|236
		|AMAX1|0115013034|3454246522151420|652
	*  特性
		* 平方取中法是较常用的构造哈希函数的方法
		* 适合于关键字中的每一位都有某些数字重复出现且频度很高的情况  
		* 中间所取的位数，由哈希表长决定  
		
* 6）折叠法
	* 将关键字分割称位数相同的若干部分（最后部分的位数可以不同），然后取它们的叠加和（舍去进位）为哈希地址
	* 移位叠加：将分割后的几部分低位对齐相加
	* 间界叠加：从一端沿分割界来回折叠，然后对齐相加
	* 例子：关键字为: 0442205864 哈希地址数为4  
$$\frac { \begin{matrix}  & 5 & 8 & 6 & 4 \\  & 4 & 2 & 2 & 0 \\  &  &  & 0 & 4 \end{matrix} }{ \begin{matrix} 1 & 0 & 0 & 8 & 8 \end{matrix} } $$ $$\frac { \begin{matrix}  & 5 & 8 & 6 & 4 \\  & 0 & 2 & 2 & 4 \\  &  &  & 0 & 4 \end{matrix} }{ \begin{matrix}  & 6 & 0 & 9 & 2 \end{matrix} }   $$

	* 特性
		* 折叠法适合于关键字的数字位数特别多，而且每一位上数字分布大致均匀的情况 	

* 7）除留余数法
	* 去关键字被某个不大于哈希表长m的数p除后所得余数为哈希地址  
	H(key) = key MOD p （p≤m）
	* m为表长 
	* p为不大于m的素数或是不含20以下的质因子  	
		* 给定一组关键字为： 12，39，18，24，33，21，若取p =9，则他们对应的哈希函数值将为：3，3，0，6，6，3
		* 可见，若p中含质因子3，则所有含质因子3的关键字均映射到“3的倍数“的地址上，从而增加了”冲突“的可能
	* 特性
		* 除留余数法是一种最简单、最常用的构造哈希函数的方法
		* 不但可以对关键字直接取模（MOD），也可在折叠、平方取中等运算之后取模 

####  三、处理冲突的方法

*  ”处理冲突“的实际含义是：为产生冲突的地址寻找下一个哈希地址。
* 1）开放定址法
	* 为产生冲突的地址H(key)求得一个地址序列：  
	$$H_0, H_1, H_2, ..., H_s, 1\le s \le m-1$$  
	$$H_i = [H(key) + d_i] MOD m$$  i=1,2,..., s  
	* H(key)为哈希函数
	* m为哈希表长   
	* 线性探测
		*  当$$d_i取1,2,3,...m-1时，称这种开放定址法为线性探测再散列$$  
		*  例如：给定关键字集合{19,01,23,14,55,68,11,82,36}，设定哈希函数H(key)=key MOD 11(表长=11)
		
		|地址|0|1|2|3|4|5|6|7|8|9|10|
		|-
		|关键字|55|01|23|14|68|11|82|36|19|||
		|冲突次数|0|0|1|0|2|5|1|4|0|||
	* 二次探测  
		*  当$$d_i取1^2,2^2,3^2,...时，称这种开放定址法为二次探测再散列$$  
		*  例如：给定关键字集合{19,01,23,14,55,68,11,82,36}，设定哈希函数H(key)=key MOD 11(表长=11)
		
		|地址|0|1|2|3|4|5|6|7|8|9|10|
		|-
		|关键字|55|01|23|14|11|82|68|36|19|||
		|冲突次数|0|0|1|0|2|0|2|2|0|||
	*  特性
		* 优点：只要哈希表中有空位置，总能找到一个不发生冲突的地址
		* 缺点：易产生”二次聚集“，即在处理同义词的冲突过程中，又添加了非同义词的冲突，对查找不利
* 2）再哈希法
	* 构造若干个哈希函数，当发生冲突时，计算下一个哈希地址，直到冲突不再发生，即：$$H_i = Rh_i(key)$$  i=1, 2, ... k  
	* $$Rh_i $$——不同的哈希函数  
	* 特点： 不易产生聚集，但增加计算时间  
* 3）链地址法
	* 将所有哈希地址相同的记录都链接在同一链表中
	* [表后插入]  查找不成功，再插入新结点时，用表后插入方式较好
	* [表头插入]  给定关键字集合，逐步生成哈希表时，用表头插入方法较好
			
		<svg width="580" height="400" >
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="39.2647" x2="111.63825" y2="39.2647" id="svg_2" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="69.2647" x2="111.63825" y2="69.2647" id="svg_5" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="99.2647" x2="111.63825" y2="99.2647" id="svg_6" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="129.2647" x2="111.63825" y2="129.2647" id="svg_7" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="159.2647" x2="111.63825" y2="159.2647" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="189.2647" x2="111.63825" y2="189.2647" id="svg_9" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="219.2647" x2="111.63825" y2="219.2647" id="svg_10" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="249.2647" x2="111.63825" y2="249.2647" id="svg_11" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="279.2647" x2="111.63825" y2="279.2647" id="svg_12" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="309.2647" x2="111.63825" y2="309.2647" id="svg_13" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="339.2647" x2="111.63825" y2="339.2647" id="svg_14" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="63.2647" y1="369.2647" x2="111.63825" y2="369.2647" id="svg_15" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="112.2647" y1="37.2647" x2="112.2647" y2="371.27817" id="svg_16" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="63.2647" y1="38.2647" x2="63.2647" y2="372.27817" id="svg_17" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="138.5035" y="45.00007" width="55.29409" height="20.58823" id="svg_18"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="173.7976" y1="45.58831" x2="173.7976" y2="66.20521" id="svg_19" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="270.29412" y="153.82355" id="svg_38" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="127.73941" y="41.39683" id="svg_40" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="96.75843" y="40.95551" id="svg_41" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="138.5035" y="75.00007" width="55.29409" height="20.58823" id="svg_42"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="173.7976" y1="75.58831" x2="173.7976" y2="96.20521" id="svg_43" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="127.73941" y="52.65037" id="svg_44" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="96.75843" y="52.20905" id="svg_45" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="138.5035" y="105.00007" width="55.29409" height="20.58823" id="svg_46"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="173.7976" y1="105.58831" x2="173.7976" y2="126.20521" id="svg_47" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="96.75843" y="63.4626" id="svg_49" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="138.5035" y="135.00007" width="55.29409" height="20.58823" id="svg_50"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="173.7976" y1="135.58831" x2="173.7976" y2="156.20521" id="svg_51" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="127.73941" y="75.15745" id="svg_52" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="96.75843" y="74.71614" id="svg_53" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="138.5035" y="195.00007" width="55.29409" height="20.58823" id="svg_54"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="173.7976" y1="195.58831" x2="173.7976" y2="216.20521" id="svg_55" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="96.75843" y="97.22322" id="svg_57" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="138.5035" y="285.00007" width="55.29409" height="20.58823" id="svg_58"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="173.7976" y1="285.58831" x2="173.7976" y2="306.20521" id="svg_59" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="96.75843" y="130.98385" id="svg_61" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="228.5035" y="45.00007" width="55.29409" height="20.58823" id="svg_62"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="263.7976" y1="45.58831" x2="263.7976" y2="66.20521" id="svg_63" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="228.5035" y="75.00007" width="55.29409" height="20.58823" id="svg_66"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="263.7976" y1="75.58831" x2="263.7976" y2="96.20521" id="svg_67" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="227.32703" y="135.00007" width="55.29409" height="20.58823" id="svg_70"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="263.7976" y1="135.58831" x2="263.7976" y2="156.20521" id="svg_71" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="270.88235" y="62.64712" id="svg_73" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="270.88235" y="92.05887" id="svg_74" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="83.8236" y="181.4706" id="svg_75" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="180.29415" y="122.6471" id="svg_76" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="179.11768" y="210.88235" id="svg_77" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="181.47062" y="303.82349" id="svg_78" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="85.58831" y="327.94112" id="svg_79" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="86.17655" y="362.64699" id="svg_80" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="85.58831" y="273.23527" id="svg_81" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="85.00008" y="240.88234" id="svg_82" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="59.70595" id="svg_83" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="89.70595" id="svg_84" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="119.70595" id="svg_85" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="149.70595" id="svg_86" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="179.70595" id="svg_87" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="209.70595" id="svg_88" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="239.70595" id="svg_89" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="269.70595" id="svg_90" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="299.70595" id="svg_91" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">8</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="44.41187" y="329.70595" id="svg_92" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="40.88246" y="359.70595" id="svg_93" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="152.64711" y="58.52948" id="svg_94" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">55</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="152.64711" y="88.52948" id="svg_95" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">01</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="152.64711" y="119.70595" id="svg_96" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">68</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="152.64711" y="149.70595" id="svg_97" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">14</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="152.64711" y="209.70595" id="svg_98" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">82</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="152.64711" y="299.70595" id="svg_99" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="242.64707" y="58.52948" id="svg_100" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">11</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="242.64707" y="87.94125" id="svg_101" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">23</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="242.64707" y="149.70595" id="svg_102" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">36</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="39.2647" x2="371.58023" y2="39.2647" id="svg_175" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="69.2647" x2="371.58023" y2="69.2647" id="svg_176" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="99.2647" x2="371.58023" y2="99.2647" id="svg_177" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="129.2647" x2="371.58023" y2="129.2647" id="svg_178" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="159.2647" x2="371.58023" y2="159.2647" id="svg_179" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="189.2647" x2="371.58023" y2="189.2647" id="svg_180" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="219.2647" x2="371.58023" y2="219.2647" id="svg_181" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="249.2647" x2="371.58023" y2="249.2647" id="svg_182" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="279.2647" x2="371.58023" y2="279.2647" id="svg_183" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="309.2647" x2="371.58023" y2="309.2647" id="svg_184" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="339.2647" x2="371.58023" y2="339.2647" id="svg_185" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="323.20669" y1="369.2647" x2="371.58023" y2="369.2647" id="svg_186" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="372.20669" y1="37.2647" x2="372.20669" y2="371.27817" id="svg_187" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="323.20669" y1="38.2647" x2="323.20669" y2="372.27817" id="svg_188" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="398.44549" y="45.00007" width="55.29409" height="20.58823" id="svg_189"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="433.73959" y1="45.58831" x2="433.73959" y2="66.20521" id="svg_190" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="530.2361" y="153.82355" id="svg_191" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="222.15698" y="41.39683" id="svg_192" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="191.17599" y="40.95551" id="svg_193" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="398.44549" y="75.00007" width="55.29409" height="20.58823" id="svg_194"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="433.73959" y1="75.58831" x2="433.73959" y2="96.20521" id="svg_195" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="222.15698" y="52.65037" id="svg_196" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="191.17599" y="52.20905" id="svg_197" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="398.44549" y="105.00007" width="55.29409" height="20.58823" id="svg_198"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="433.73959" y1="105.58831" x2="433.73959" y2="126.20521" id="svg_199" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="191.17599" y="63.4626" id="svg_200" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="398.44549" y="135.00007" width="55.29409" height="20.58823" id="svg_201"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="433.73959" y1="135.58831" x2="433.73959" y2="156.20521" id="svg_202" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="222.15698" y="75.15745" id="svg_203" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="191.17599" y="74.71614" id="svg_204" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="398.44549" y="195.00007" width="55.29409" height="20.58823" id="svg_205"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="433.73959" y1="195.58831" x2="433.73959" y2="216.20521" id="svg_206" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="191.17599" y="97.22322" id="svg_207" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="398.44549" y="285.00007" width="55.29409" height="20.58823" id="svg_208"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="433.73959" y1="285.58831" x2="433.73959" y2="306.20521" id="svg_209" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="191.17599" y="130.98385" id="svg_210" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="matrix(2.753110520213511,0,0,2.665827313870153,-166.5889089994656,-45.84564252114434) " stroke="#000">→</text>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="488.44549" y="45.00007" width="55.29409" height="20.58823" id="svg_211"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="523.73959" y1="45.58831" x2="523.73959" y2="66.20521" id="svg_212" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="488.44549" y="75.00007" width="55.29409" height="20.58823" id="svg_213"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="523.73959" y1="75.58831" x2="523.73959" y2="96.20521" id="svg_214" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <rect fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="487.26902" y="135.00007" width="55.29409" height="20.58823" id="svg_215"/>
  <line fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="523.73959" y1="135.58831" x2="523.73959" y2="156.20521" id="svg_216" stroke-linejoin="undefined" stroke-linecap="undefined" stroke="#000"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="530.82434" y="62.64712" id="svg_217" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="530.82434" y="92.05887" id="svg_218" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="343.76559" y="181.4706" id="svg_219" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="440.23614" y="122.6471" id="svg_220" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="439.05967" y="210.88235" id="svg_221" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="441.41261" y="303.82349" id="svg_222" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="345.5303" y="327.94112" id="svg_223" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="346.11853" y="362.64699" id="svg_224" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="345.5303" y="273.23527" id="svg_225" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="344.94206" y="240.88234" id="svg_226" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="59.70595" id="svg_227" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="89.70595" id="svg_228" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="119.70595" id="svg_229" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="149.70595" id="svg_230" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="179.70595" id="svg_231" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="209.70595" id="svg_232" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="239.70595" id="svg_233" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="269.70595" id="svg_234" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="299.70595" id="svg_235" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">8</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="304.35385" y="329.70595" id="svg_236" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="300.82444" y="359.70595" id="svg_237" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="499.05965" y="59.70595" id="svg_238" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">55</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="499.05965" y="90.88242" id="svg_239" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">01</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="412.5891" y="119.70595" id="svg_240" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">68</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="497.29494" y="150.88242" id="svg_241" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">14</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="412.5891" y="209.70595" id="svg_242" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">82</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="412.5891" y="299.70595" id="svg_243" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">19</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="409.05968" y="59.11772" id="svg_244" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">11</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="409.64792" y="90.29419" id="svg_245" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">23</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="410.23616" y="150.29419" id="svg_246" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">36</text>
		</svg>  

####  四、哈希表的实现

* 1）结构
	* 假设哈希函数为关键字求模运算，哈希表用拉链法解决冲突，其结构可以定义如下：

			#define LEN  31   // 表长LEN最好为质数
			typedef struct node {
				int data;
				struct node *next;
			} node;
			struct node HashTab[LEN];
		
* 2）哈希函数 hash()
	* 返回值为哈希表地址 	
				
			int hash(int key){
			retAddr = key MOD LEN;
			return(retAddr);
			} 
	
* 3）查找过程
	*  对于给定值key，计算哈希地址 p=hash(Key)
	*  若HashTab[p].next= NULL，则查找不成功
	*  若HashTab[p].next.data = key, 则查找成功
	* 否则“求下一地址”，再进行比较  

```flow
st=>start: Start
op1=>operation: 给定k值
op2=>operation: 计算hash(key)    
cond1=>condition: 此地址不为空    
cond2=>condition: 关键字!=key
op3=>operation: 查找失败返回或插入新结点
op4=>operation: 查找成功
op5=>operation: 按处理冲突方法计算下一地址

st->op1->op2->cond1
cond1(yes)->cond2
cond1(no)->op3
cond2(yes)->op5
cond2(no)->op4
op5->cond1
```   

* 4）查找函数 search()
	*   若找到key，返回其结点指针；否则将其插入表中再返回其结点指针[链地址法解决冲突，表头插入]
	
			node *search(int  key) {
				i = hash(key);
				p = HashTab[i].next;
				while(p!=NULL){
					if (p.data == key) 
						return(p);
					p = p.next;	
				}
				q = malloc(sizeof(node)); //表头插入
				q.data = key;
				q.next = HashTab[i],next;
				HashTab[i].next = q;
				return(q);
			}

####  五、哈希查找的性能分析

* 虽然哈希表在关键字与记录的存储位置之间建立了直接映像，但由于“冲突”的产生，使得哈希表的查找过程仍然是一个给定值和关键字进行比较的过程
* 因此，仍须以平均查找长度ASL作为衡量哈希表的查找效率的量度
* 1）线性探测再散列，如前例
	* 假设每个关键字的查找概率相同，则：
	* ASL = (1/9)(0*4+1*2+2*1+4*1+5*1) + 1 = 22/9
* 2）二次探测再散列，如前例
	* 假设每个关键字的查找概率相同，则：
	* ASL = (1/9)(0*5+1*1+2*3) + 1 = 16/9
* 3）链地址法，如前例
	* 假设每个关键字的查找概率相同，则：
	* ASL = (1/9)(1*6+2*3)  = 12/9
*  决定哈希表查找的ASL的因素
	1. 选用的哈希函数
	2. 选用的处理冲突的方法
	3. 哈希表的装填因子  
*  装填因子
	* 哈希表的装填因子是哈希表中填入的记录数与哈希表的长度的比值，即：
	 α = 哈希表中填入的记录数/哈希表的长度  
	* 装填因子α标志哈希表的装满程度
	* 直观来看：
		* 装填因子α越小，发生冲突的可能性就越小
		* 装填因子α越大，发生冲突的可能性就越大 
	* 评价ASL
		* 线性探测再散列的哈希表查找成功时：
			* ASL ≈ (1/2)(1+1/(1-α))  
		* 二次探测再散列的哈希表查找成功时：
			* ASL ≈ -(1/α)ln(1-α)
		* 链地址法处理冲突的哈希表查找成功时： 
			* ASL ≈ (1 + α/2)

---
