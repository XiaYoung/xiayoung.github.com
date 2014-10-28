---
layout : post
category : mse
tags : [Data structure]
--- 
##第十章 内部排序 

### **第一节 排序**  

####  一、排序（Sorting）  

* 排序：将一个数据元素（或记录）的任意序列，重新排列成一个按关键字有序的序列
* 内部排序：在排序期间数据对象全部存放在内存的排序
* 外部排序：在排序期间全部对象个数太多，不能同时存放在内存，必须根据排序过程的要求，不断在内、外存之间移动的排序。


####  二、排序基本操作  

*  排序的基本操作包括：
	* 比较：比较两个关键字的大小
	* 移动：将记录从一个位置移动至另一个位置

####  三、排序时间复杂度

*  排序的时间复杂度可用算法执行中的记录关键字比较次数与记录移动次数来衡量

####  四、排序方法的稳定性

*  如果在记录序列中有两个记录r[i]和r[j]，它们的关键字 key[i] = key[j]，且在排序之前，记录r[i]排在r[j]前面
* 如果在排序之后，记录r[i]仍在记录r[j]的前面，则称这个排序方法是稳定的
* 否则称这个排序方法是不稳定的

---

### **第二节 插入排序**  

* 每步将一个待排序的对象，按其关键字大小，插入到前面已经排好序的有序表的适当位置上，直到对象全部插入为止。 

####  一、直接插入排序  

* 1）定义
	*  当插入第i(i≥1)个对象时，前面的r[0], r[1], ..., r[i-1]已经排好序。
	*  用r[i]的关键字与r[i-1], r[i-2], ...的关键字顺序进行比较（和顺序查找类似），如果小于，则将r[x]向后移动（插入位置后的记录向后顺移）
	*  找到插入位置即将r[i]插入  
* 2）举例
	* 已知待序的一组记录的初始化排列为： 21, 25, 49, 25*, 16, 08 

<svg width="690" height="470" >
  <rect stroke="#000" id="svg_1" height="46" width="29" y="49.5" x="37.5" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_2" y="78.5" x="41.5" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <rect id="svg_3" height="54" width="29" y="41.5" x="77.5" stroke-width="1.5" stroke="#000" fill="#999999"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_4" y="74.5" x="82.5" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <rect stroke="#000" id="svg_5" height="77" width="29" y="18.5" x="117.5" stroke-width="1.5" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_6" y="63.5" x="121.5" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect id="svg_7" height="54" width="29" y="41.5" x="157.5" stroke-width="1.5" stroke="#000" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_8" y="74.5" x="158.5" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <rect stroke="#000" id="svg_9" height="35" width="29" y="60.5" x="197.5" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_10" y="84.5" x="201.5" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <rect stroke="#000" id="svg_11" height="24" width="29" y="71.5" x="237.5" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_12" y="90.5" x="241.5" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <rect id="svg_13" height="54" width="29" y="41.5" x="297.5" stroke-width="1.5" stroke="#000" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_14" y="74.5" x="301.5" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_15" y="77.5" x="2.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_16" y="120.5" x="47.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_17" y="120.5" x="87.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_18" y="120.5" x="127.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_19" y="120.5" x="167.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_20" y="120.5" x="207.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_21" y="120.5" x="247.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_22" y="120.5" x="293.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">temp</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_23" y="144.03846" x="292.34615" stroke-width="0" fill="#007f3f">→</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_24" y2="147.30769" x2="108.65347" y1="147.30769" x1="307.11538" stroke="#ff0000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_25" y="151.92308" x="91.73077" stroke-width="0" stroke="#ff0000" fill="#ff0000">←</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_26" y2="139.61538" x2="94.80732" y1="139.61538" x1="293.26923" stroke="#007f3f" fill="none"/>
  <rect stroke="#000" id="svg_27" height="46" width="29" y="201.12556" x="37.5" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_28" y="230.12556" x="41.5" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <rect id="svg_29" height="54" width="29" y="193.12556" x="77.5" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_30" y="226.12556" x="82.5" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <rect stroke="#000" id="svg_31" height="77" width="29" y="170.12556" x="117.5" stroke-width="1.5" fill="#999999"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_32" y="215.12556" x="121.5" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect id="svg_33" height="54" width="29" y="193.12556" x="157.5" stroke-width="1.5" stroke="#000" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_34" y="226.12556" x="158.5" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <rect stroke="#000" id="svg_35" height="35" width="29" y="212.12557" x="197.5" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_36" y="236.12556" x="201.5" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <rect stroke="#000" id="svg_37" height="24" width="29" y="223.12556" x="237.5" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_38" y="242.12556" x="241.5" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_41" y="229.12556" x="2.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_42" y="272.12556" x="47.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_43" y="272.12556" x="87.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_44" y="272.12556" x="127.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_45" y="272.12556" x="167.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_46" y="272.12556" x="207.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_47" y="272.12556" x="247.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_48" y="272.12556" x="293.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">temp</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_49" y="295.66403" x="292.34615" stroke-width="0" fill="#007f3f">→</text>
  <line stroke="#ff0000" stroke-linecap="null" stroke-linejoin="null" id="svg_50" y2="298.93326" x2="148.73152" y1="298.93326" x1="308.02677" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_51" y="303.54864" x="131.80882" stroke-width="0" stroke="#ff0000" fill="#ff0000">←</text>
  <line stroke="#007f3f" stroke-linecap="null" stroke-linejoin="null" id="svg_52" y2="291.24095" x2="133.97398" y1="291.24095" x1="293.26923" fill="none"/>
  <rect stroke="#000" id="svg_55" height="77" width="29" y="170.12556" x="297.5" stroke-width="1.5" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_56" y="215.12556" x="301.5" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect stroke="#000" id="svg_57" height="46" width="29" y="351.12556" x="37.5" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_58" y="380.12556" x="41.5" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <rect id="svg_59" height="54" width="29" y="343.12556" x="77.5" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_60" y="376.12556" x="82.5" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <rect stroke="#000" id="svg_61" height="77" width="29" y="320.12556" x="117.5" stroke-width="1.5" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_62" y="365.12556" x="121.5" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect id="svg_63" height="54" width="29" y="343.12556" x="157.5" stroke-width="1.5" stroke="#000" fill="#999999"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_64" y="376.12556" x="158.5" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <rect stroke="#000" id="svg_65" height="35" width="29" y="362.12557" x="197.5" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_66" y="386.12556" x="201.5" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <rect stroke="#000" id="svg_67" height="24" width="29" y="373.12556" x="237.5" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_68" y="392.12556" x="241.5" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_69" y="379.12556" x="2.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_70" y="422.12556" x="47.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_71" y="422.12556" x="87.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_72" y="422.12556" x="127.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_73" y="422.12556" x="167.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_74" y="422.12556" x="207.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_75" y="422.12556" x="247.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_76" y="422.12556" x="293.5" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">temp</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_77" y="445.66403" x="292.34615" stroke-width="0" fill="#007f3f">→</text>
  <line stroke="#ff0000" stroke-linecap="null" stroke-linejoin="null" id="svg_78" y2="458.51657" x2="148.73152" y1="458.51657" x1="308.02677" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_79" y="463.13195" x="131.80882" stroke-width="0" stroke="#ff0000" fill="#ff0000">←</text>
  <line stroke="#007f3f" stroke-linecap="null" stroke-linejoin="null" id="svg_80" y2="441.24094" x2="174.80722" y1="441.24094" x1="293.26923" fill="none"/>
  <rect id="svg_83" height="54" width="29" y="343.12556" x="297.5" stroke-width="1.5" stroke="#000" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_84" y="376.12556" x="298.5" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_85" y="454.16891" x="156.76903" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_86" y2="449.15758" x2="135.64032" y1="449.15758" x1="157.85257" fill="none"/>
  <rect stroke="#000" id="svg_115" height="46" width="29" y="51.12556" x="388.29971" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_116" y="80.12556" x="392.29971" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <rect id="svg_117" height="54" width="29" y="43.12556" x="428.29971" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_118" y="76.12556" x="433.29971" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <rect stroke="#000" id="svg_119" height="77" width="29" y="20.12556" x="508.29971" stroke-width="1.5" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_120" y="65.12556" x="512.29971" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect id="svg_121" height="54" width="29" y="43.12556" x="468.29971" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_122" y="76.12556" x="469.29971" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <rect stroke="#000" id="svg_123" height="35" width="29" y="62.12557" x="548.29971" stroke-width="1.5" fill="#999999"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_124" y="86.12556" x="552.29971" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <rect stroke="#000" id="svg_125" height="24" width="29" y="73.12556" x="588.29971" stroke-width="1.5" fill="#aad4ff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_126" y="92.12556" x="592.29971" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_127" y="79.12556" x="353.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_128" y="122.12556" x="398.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_129" y="122.12556" x="438.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_130" y="122.12556" x="478.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_131" y="122.12556" x="518.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_132" y="122.12556" x="558.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_133" y="122.12556" x="598.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_134" y="122.12556" x="644.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">temp</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_135" y="145.66403" x="643.14587" stroke-width="0" fill="#007f3f">→</text>
  <line stroke="#ff0000" stroke-linecap="null" stroke-linejoin="null" id="svg_136" y2="158.51658" x2="418.30145" y1="158.51658" x1="657.59674" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_137" y="163.13195" x="401.37874" stroke-width="0" stroke="#ff0000" fill="#ff0000">←</text>
  <line stroke="#007f3f" stroke-linecap="null" stroke-linejoin="null" id="svg_138" y2="141.24094" x2="566.19519" y1="141.24094" x1="644.06894" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_141" y="153.76075" x="507.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_142" y2="149.15758" x2="486.44003" y1="149.15758" x1="508.65228" fill="none"/>
  <rect stroke="#000" id="svg_143" height="35" width="29" y="62.12557" x="648.29971" stroke-width="1.5" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_144" y="86.12556" x="652.29971" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="19" id="svg_145" y="153.96483" x="547.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_146" y2="149.15758" x2="526.44003" y1="149.15758" x1="548.65228" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_147" y="153.76075" x="467.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_148" y2="149.15758" x2="446.44003" y1="149.15758" x1="468.65228" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_149" y="153.76075" x="427.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_150" y2="149.15758" x2="406.44003" y1="149.15758" x1="428.65228" fill="none"/>
  <rect stroke="#000" id="svg_151" height="46" width="29" y="211.12556" x="428.29971" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_152" y="240.12556" x="432.29971" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <rect id="svg_153" height="54" width="29" y="203.12556" x="468.29971" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_154" y="236.12556" x="473.29971" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <rect stroke="#000" id="svg_155" height="77" width="29" y="180.12556" x="548.29971" stroke-width="1.5" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_156" y="225.12556" x="552.29971" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect id="svg_157" height="54" width="29" y="203.12556" x="508.29971" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_158" y="236.12556" x="509.29971" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <rect stroke="#000" id="svg_159" height="35" width="29" y="222.12557" x="388.29971" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_160" y="246.12556" x="392.29971" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <rect stroke="#000" id="svg_161" height="24" width="29" y="233.12556" x="588.29971" stroke-width="1.5" fill="#999999"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_162" y="252.12556" x="592.29971" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_163" y="239.12556" x="353.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_164" y="282.12556" x="398.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_165" y="282.12556" x="438.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_166" y="282.12556" x="478.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_167" y="282.12556" x="518.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_168" y="282.12556" x="558.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_169" y="282.12556" x="598.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_170" y="282.12556" x="644.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">temp</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_171" y="305.66403" x="643.14587" stroke-width="0" fill="#007f3f">→</text>
  <line stroke="#ff0000" stroke-linecap="null" stroke-linejoin="null" id="svg_172" y2="318.51658" x2="418.30145" y1="318.51658" x1="657.59674" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_173" y="323.13195" x="401.37874" stroke-width="0" stroke="#ff0000" fill="#ff0000">←</text>
  <line stroke="#007f3f" stroke-linecap="null" stroke-linejoin="null" id="svg_174" y2="301.24096" x2="604.69522" y1="301.24096" x1="644.06894" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_175" y="313.76075" x="507.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_176" y2="309.15758" x2="486.44003" y1="309.15758" x1="508.65228" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="19" id="svg_179" y="313.96483" x="547.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_180" y2="309.15758" x2="526.44003" y1="309.15758" x1="548.65228" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_181" y="313.76075" x="467.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_182" y2="309.15758" x2="446.44003" y1="309.15758" x1="468.65228" fill="none"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_183" y="313.76075" x="427.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_184" y2="309.15758" x2="406.44003" y1="309.15758" x1="428.65228" fill="none"/>
  <rect stroke="#000" id="svg_185" height="24" width="29" y="233.12556" x="648.29971" stroke-width="1.5" fill="#aad4ff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_186" y="252.12556" x="652.29971" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="19" id="svg_187" y="313.96483" x="587.56875" stroke-width="0" fill="#000000">→</text>
  <line stroke="#000000" stroke-linecap="null" stroke-linejoin="null" id="svg_188" y2="309.15758" x2="566.44003" y1="309.15758" x1="588.65228" fill="none"/>
  <rect stroke="#000" id="svg_189" height="46" width="29" y="371.12556" x="468.29971" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_190" y="400.12556" x="472.29971" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <rect id="svg_191" height="54" width="29" y="363.12556" x="508.29971" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_192" y="396.12556" x="513.29971" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <rect stroke="#000" id="svg_193" height="77" width="29" y="340.12556" x="588.29971" stroke-width="1.5" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_194" y="385.12556" x="592.29971" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <rect id="svg_195" height="54" width="29" y="363.12556" x="548.29971" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_196" y="396.12556" x="549.29971" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <rect stroke="#000" id="svg_197" height="35" width="29" y="382.12557" x="428.29971" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_198" y="406.12556" x="432.29971" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <rect stroke="#000" id="svg_199" height="24" width="29" y="393.12556" x="388.29971" stroke-width="1.5" fill="#007f00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_200" y="412.12556" x="392.29971" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_201" y="399.12556" x="353.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">i=6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_202" y="442.12556" x="398.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_203" y="442.12556" x="438.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_204" y="442.12556" x="478.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_205" y="442.12556" x="518.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_206" y="442.12556" x="558.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="18" id="svg_207" y="442.12556" x="598.29971" fill-opacity="null" stroke-opacity="null" stroke-width="0" fill="#000000">5</text>
</svg>

* 3）直接插入排序算法实现

		#define LISTLEN 6
		void InsertSort(){
			int r[LISTLEN] = {21, 25, 49, 25, 16, 8};
			int i, j, temp;
			for(i=1; i<LISTLEN; i++){
				if(r[i]<r[i-1]){
					temp = r[i];
					for(j=i-1; j>=0;j-=1)
						if(temp < r[j])
							r[j+1] = r[j];
						else 
							break;
					r[j+1] = temp;		
				}
			}
		}

* 4）直接插入排序算法分析
	* 关键字比较次数和记录移动次数与记录关键字的初始排列有关。
	* 最好情况下，排序前记录已按关键字从小到大有序，每趟只需与前面有序记录序列的最后一个记录比较1次，总的关键字比较次数为n-1
	* 最坏的情况下，第i趟时第i个记录必须与前面i个记录都做关键字比较，并且每做1次比较就要做1次数据移动。则总关键字比较次数KCN和记录移动次数RMN分别为  
	$$KCN = \sum_{i=1}^{n-1}{i} = n(n-1)/2 \approx n^2/2 $$  
	$$RMN = \sum_{i=1}^{n-1}{i+2} = (n+4)(n-1)/2 \approx n^2/2$$  
	*  在平均情况下的关键字比较次数和记录移动次数约为 $$n^2/4$$
	*  直接插入排序的时间复杂度为$$O(n^2)$$  
	*  直接插入排序是一种稳定的排序方法
	*  直接插入排序最大的优点是简单，在记录数较少时，是比较好的方法

####  二、折半插入排序

*  折半插入排序在查找记录插入位置时，采用折半查找算法
*  折半查找比顺序查找快，所以折半插入排序在查找上性能比直接插入排序好
* 但需要移动的记录数目与直接插入排序相同（为$$O(n^2)$$）  
* 折半插入排序的时间复杂度为$$O(n^2)$$  
*  折半插入排序是一种稳定的排序方法 

####  三、希尔排序
* 1）定义
	*  从直接插入排序可以看出，当待排序列为正序时，时间复杂度为O(n)
	*  若待排序列基本有序时，插入排序效率会提高
	*  希尔排序方法是先将待排序列分成若干子序列分别进行插入排序，待整个序列基本有序时，再对全体记录进行一次直接插入排序
	*  希尔排序又称为缩小增量排序
* 2）算法
	* 首先取一个整数gap < n (待排序记录数) 作为间隔，将全部记录分为 gap 个子序列，所有距离为gap 的记录放在同一个子序列中
	*  在每一个子序列中分别施行直接插入排序
	*  然后缩小间隔 gap, 例如取 gap = gap/2
	*  重复上述的子序列划分和排序工作，直到最后取gap = 1，将所有记录放在同一个个序列中排序为止
* 3）举例
	* 已知待排序的一组记录的初始排列为：21，25，49，25*，16，08

<svg width="457" height="400" >
  <ellipse ry="22" rx="22" id="svg_1" cy="67.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="75.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_5" cy="67.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="75.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_7" cy="67.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="75.64214" x="229.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_9" cy="67.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="75.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_11" cy="67.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="75.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_13" cy="67.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="75.64214" x="410.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_15" y="35.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="35.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_17" y="35.64214" x="230.52626" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="35.64214" x="290.52626" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_19" y="35.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_20" y="35.64214" x="410.52626" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <ellipse ry="22" rx="22" id="svg_21" cy="117.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#ff0000"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_22" y="125.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_23" cy="117.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#7f007f"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_24" y="125.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_25" cy="117.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_26" y="125.64214" x="229.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_27" cy="117.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#ff0000"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_28" y="125.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_29" cy="117.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#7f007f"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_30" y="125.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_31" cy="117.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_32" y="125.64214" x="410.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_39" y="122.5" x="9.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">Gap=3</text>
  <ellipse ry="22" rx="22" id="svg_40" cy="167.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#ff0000"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_41" y="175.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_42" cy="167.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#7f007f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_43" y="175.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_44" cy="167.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_45" y="175.64214" x="409.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_46" cy="167.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#ff0000"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_47" y="175.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_48" cy="167.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#7f007f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_49" y="175.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_50" cy="167.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#007f3f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_51" y="175.64214" x="230.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_64" y="222.5" x="9.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">Gap=2</text>
  <ellipse ry="22" rx="22" id="svg_65" cy="217.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#ffff00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_66" y="225.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_67" cy="217.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#ffff00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_68" y="225.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_69" cy="217.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#aaaaff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_70" y="225.64214" x="409.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_71" cy="217.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#aaaaff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_72" y="225.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_73" cy="217.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#aaaaff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_74" y="225.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_75" cy="217.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#ffff00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_76" y="225.64214" x="230.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <ellipse ry="22" rx="22" id="svg_77" cy="267.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#ffff00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_78" y="275.64214" x="230.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_79" cy="267.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#ffff00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_80" y="275.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_81" cy="267.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#aaaaff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_82" y="275.64214" x="409.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_83" cy="267.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#aaaaff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_84" y="275.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_85" cy="267.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#aaaaff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_86" y="275.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_87" cy="267.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#ffff00"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_88" y="275.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <ellipse ry="22" rx="22" id="svg_89" cy="317.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_90" y="325.64214" x="230.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_91" cy="317.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_92" y="325.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_93" cy="317.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_94" y="325.64214" x="409.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_95" cy="317.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_96" y="325.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_97" cy="317.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_98" y="325.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_99" cy="317.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_100" y="325.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <ellipse ry="22" rx="22" id="svg_101" cy="367.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_102" y="375.64214" x="230.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_103" cy="367.64214" cx="362.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_104" y="375.64214" x="350.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_105" cy="367.64214" cx="422.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_106" y="375.64214" x="409.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_107" cy="367.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_108" y="375.64214" x="287.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_109" cy="367.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_110" y="375.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_111" cy="367.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#7f7f7f"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_112" y="375.64214" x="110.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_113" y="322.5" x="9.5" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">Gap=1</text>
</svg>

