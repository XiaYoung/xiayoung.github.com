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

* 4）算法实现
	
		#define LISTLEN 6
		void InsertSort(){
		    int r[LISTLEN] = {21, 25, 49, 25, 16, 8};
		    int i, j, gap, temp;
		    for(gap=(int)(LISTLEN / 2); gap>0;gap / =2){
			    for(i=gap; i<LISTLEN; i++){
			        if(r[i]<r[i-gap]){
			            temp = r[i];
			            for(j=i-gap; j>=0;j-=gap)
			                if(temp < r[j])
			                    r[j+gap] = r[j];
			                else 
			                    break;
			            r[j+gap] = temp;      
			        }
			    }
			}
		}
* 5）算法分析
	* 开始时 gap的值较大， 子序列中的记录较少，排序速度较快，而且记录一次移动的间隔较大
	* 随着排序进展，gap值逐渐变小，子序列中记录个数逐渐变多，由于前面大多数记录已基本有序，所以排序速度仍然很快。
	* Gap的取法有多种。shell提出取gap=[n/2], gap = [gap/2], 直到gap = 1
	* 希尔排序的性能分析是一个复杂的问题
	* 只对特定的待排序记录序列，可以准确地估算关键字的比较次数和记录移动次数
	*  希尔排序所需的比较次数和移动次数约为$$n^{1.3}$$  
	*  希尔排序的时间复杂度约为O(n*(\log_2n)^2)  
	*  希尔排序是一种不稳定的排序方法  

---

### **第三节 快速排序**

####  一、起泡排序   

*  设待排序记录序列中的记录个数为n
*  一般地，第i趟起泡排序从1到n-i+1
*  依次比较相邻两个记录的关键字，如果发生逆序，则交换之
*  其结果是这n-i+1个记录中，关键字最大的记录被交换到第n-i+1的位置上，最多作n-1趟
*  i = 1时，为第一趟排序，关键字最大的记录将被交换到最后一个位置
*  i = 2时，为第二趟排序，关键字次大的记录将被交换到最后第二个位置
*  关键字小的记录不断上浮（起泡），关键字大的记录不断下沉（每趟排序最大的一直沉到底）

<svg width="430" height="315" >
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="37.64214" id="svg_1" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="45.64214" id="svg_2" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="87.64214" id="svg_5" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="95.64214" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="137.64214" id="svg_7" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="29.52626" y="145.64214" id="svg_8" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="187.64214" id="svg_9" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="27.52626" y="195.64214" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="237.64214" id="svg_11" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="245.64214" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="287.64214" id="svg_13" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="295.64214" id="svg_14" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="112.52626" cy="37.64214" id="svg_4" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="100.52626" y="45.64214" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="112.52626" cy="87.64214" id="svg_16" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="100.52626" y="95.64214" id="svg_17" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="112.52626" cy="287.64214" id="svg_18" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="99.52626" y="295.64214" id="svg_19" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="112.52626" cy="137.64214" id="svg_20" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="97.52626" y="145.64214" id="svg_21" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="112.52626" cy="187.64214" id="svg_22" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="100.52626" y="195.64214" id="svg_23" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="112.52626" cy="237.64214" id="svg_24" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="100.52626" y="245.64214" id="svg_25" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="37.64214" id="svg_26" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="45.64214" id="svg_27" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="87.64214" id="svg_28" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="95.64214" id="svg_29" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="287.64214" id="svg_30" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="169.52626" y="295.64214" id="svg_31" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="237.64214" id="svg_32" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="167.52626" y="245.64214" id="svg_33" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="137.64214" id="svg_34" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="145.64214" id="svg_35" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="187.64214" id="svg_36" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="195.64214" id="svg_37" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="252.52626" cy="37.64214" id="svg_38" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="240.52626" y="45.64214" id="svg_39" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="252.52626" cy="187.64214" id="svg_40" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="240.52626" y="195.64214" id="svg_41" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="252.52626" cy="287.64214" id="svg_42" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="239.52626" y="295.64214" id="svg_43" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="252.52626" cy="237.64214" id="svg_44" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="237.52626" y="245.64214" id="svg_45" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="252.52626" cy="87.64214" id="svg_46" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="240.52626" y="95.64214" id="svg_47" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="252.52626" cy="137.64214" id="svg_48" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="240.52626" y="145.64214" id="svg_49" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="322.52626" cy="137.64214" id="svg_50" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="310.52626" y="145.64214" id="svg_51" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="322.52626" cy="187.64214" id="svg_52" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="310.52626" y="195.64214" id="svg_53" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="322.52626" cy="287.64214" id="svg_54" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="309.52626" y="295.64214" id="svg_55" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="322.52626" cy="237.64214" id="svg_56" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="307.52626" y="245.64214" id="svg_57" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="322.52626" cy="37.64214" id="svg_58" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="310.52626" y="45.64214" id="svg_59" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="322.52626" cy="87.64214" id="svg_60" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="310.52626" y="95.64214" id="svg_61" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="392.52626" cy="137.64214" id="svg_62" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="380.52626" y="145.64214" id="svg_63" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="392.52626" cy="187.64214" id="svg_64" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="380.52626" y="195.64214" id="svg_65" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="392.52626" cy="287.64214" id="svg_66" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="379.52626" y="295.64214" id="svg_67" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="392.52626" cy="237.64214" id="svg_68" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="377.52626" y="245.64214" id="svg_69" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="392.52626" cy="87.64214" id="svg_70" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="380.52626" y="95.64214" id="svg_71" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="392.52626" cy="37.64214" id="svg_72" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="380.52626" y="45.64214" id="svg_73" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_74" y2="60" x2="393" y1="265" x1="111" stroke-width="1.5" stroke="#ff0000" fill="none"/>
</svg>

*  性能分析
	* 最坏情况：执行n-1趟起泡，第i趟做n-i次关键字比较，执行n-1次记录交换，共计：
	$$KCN = \sum_{i = 1}^{n-1}{(n - i)} = \frac{1}{2}n(n-1) $$  
	$$RMN = 3\sum_{i = 1}^{n-1}{(n - i)} = \frac{3}{2}n(n-1) $$  
	*   起泡排序的时间复杂度为O(n^2)  
	*  起泡排序是一种稳定的排序方法  


####  二、快速排序   

* 1）定义 
	*  任取待排序记录序列中的某个记录（例如取第一个记录）作为基准（枢），按照该记录的关键字大小，将整个记录序列划分为左右两个子序列：
		* 左侧子序列中所有记录的关键字都小于或等于基准记录的关键字
		* 右侧子序列中所有记录的关键字都大于基准记录的关键字
	*  基准记录则排在这两个子序列中间（这也是该记录最终应安放的位置）。
	* 然后分别对这两个子序列重复施行上述方法，直到所有的记录都排在相应位置上为止。
	* 基准记录也称为枢轴（或支点）记录。 
* 2 ）算法
	* 取序列第一个记录为枢轴记录，其关键字为PrivotKey
	* 指针low指向序列第一个记录位置
	* 指针high指向序列最后一个记录位置
	* 一趟排序（某个子序列）过程
		1. 从high指向的记录开始，向前找到第一个关键字的值小于Pivotkey的记录，将其放到Low指向的位置，low + 1
		2. 从low指向的记录开始，向后找到第一个关键字的值大于pivotKey的记录，将其放到high指向的位置，high -1
		3. 重复1，2，直到low=high，将枢轴记录放在low(high)指向的位置 
	 * 对枢轴记录前后两个子序列执行相同的操作，直到每个子序列都只有一个记录为止。
* 3）例子

<svg width="457" height="698" >
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="37.64214" id="svg_1" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="45.64214" id="svg_2" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="37.64214" id="svg_5" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="45.64214" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="222.52626" cy="37.64214" id="svg_7" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="45.64214" id="svg_8" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="37.64214" id="svg_9" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="45.64214" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="37.64214" id="svg_11" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="45.64214" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="37.64214" id="svg_13" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="390.52626" y="45.64214" id="svg_14" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="97.5" y="77.52631" id="svg_4" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="79.47365" y="81.97367" id="svg_15" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="395.41525" y="77.52631" id="svg_18" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="407.93337" y="81.97367" id="svg_19" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="32.52626" cy="127.64214" id="svg_20" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="20.52626" y="135.64214" id="svg_21" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="207.64214" id="svg_22" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="215.64214" id="svg_23" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="222.52626" cy="207.64214" id="svg_24" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="215.64214" id="svg_25" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="207.64214" id="svg_26" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="215.64214" id="svg_27" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="207.64214" id="svg_28" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="215.64214" id="svg_29" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="207.64214" id="svg_30" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="215.64214" id="svg_31" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="157.5" y="247.52631" id="svg_32" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="139.47365" y="251.97367" id="svg_33" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="395.41525" y="247.52631" id="svg_34" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="407.93337" y="251.97367" id="svg_35" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <rect fill="#007f3f" stroke="#000000" stroke-width="0" x="379.47372" y="188.28946" width="40.52632" height="37.36843" id="svg_36"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="297.64214" id="svg_37" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="390.52626" y="305.64214" id="svg_38" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="222.52626" cy="297.64214" id="svg_39" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="305.64214" id="svg_40" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="297.64214" id="svg_41" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="305.64214" id="svg_42" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="297.64214" id="svg_43" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="305.64214" id="svg_44" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="297.64214" id="svg_45" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="305.64214" id="svg_46" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="157.5" y="337.52631" id="svg_47" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="139.47365" y="341.97367" id="svg_48" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="335.41525" y="337.52631" id="svg_49" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="347.93337" y="341.97367" id="svg_50" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <rect fill="#007f3f" stroke="#000000" stroke-width="0" x="139.47372" y="278.28946" width="40.52632" height="37.36843" id="svg_51"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="387.64214" id="svg_52" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="390.52626" y="395.64214" id="svg_53" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="222.52626" cy="387.64214" id="svg_54" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="395.64214" id="svg_55" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="387.64214" id="svg_56" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="395.64214" id="svg_57" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="387.64214" id="svg_58" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="395.64214" id="svg_59" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="387.64214" id="svg_60" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="395.64214" id="svg_61" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="217.5" y="427.52631" id="svg_62" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="199.47365" y="431.97367" id="svg_63" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="335.41525" y="427.52631" id="svg_64" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="347.93337" y="431.97367" id="svg_65" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <rect fill="#007f3f" stroke="#000000" stroke-width="0" x="319.47372" y="368.28946" width="40.52632" height="37.36843" id="svg_66"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="127.64214" id="svg_84" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="135.64214" id="svg_85" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="222.52626" cy="127.64214" id="svg_86" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="135.64214" id="svg_87" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="127.64214" id="svg_88" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="135.64214" id="svg_89" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="127.64214" id="svg_90" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="135.64214" id="svg_91" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="127.64214" id="svg_92" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="390.52626" y="135.64214" id="svg_93" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="97.5" y="167.52631" id="svg_94" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="79.47365" y="171.97367" id="svg_95" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="395.41525" y="167.52631" id="svg_96" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="407.93337" y="171.97367" id="svg_97" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <rect fill="#007f3f" stroke="#000000" stroke-width="0" x="79.47372" y="108.28946" width="40.52632" height="37.36843" id="svg_98"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="477.64214" id="svg_99" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="390.52626" y="485.64214" id="svg_100" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="477.64214" id="svg_101" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="329.52626" y="485.64214" id="svg_102" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="477.64214" id="svg_103" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="485.64214" id="svg_104" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="477.64214" id="svg_105" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="485.64214" id="svg_106" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="477.64214" id="svg_107" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="485.64214" id="svg_108" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="217.5" y="517.52631" id="svg_109" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="199.47365" y="521.97367" id="svg_110" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="275.41525" y="517.52631" id="svg_111" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="287.93337" y="521.97367" id="svg_112" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <rect fill="#007f3f" stroke="#000000" stroke-width="0" x="199.47372" y="458.28946" width="40.52632" height="37.36843" id="svg_113"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="557.64214" id="svg_114" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="390.52626" y="565.64214" id="svg_115" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="557.64214" id="svg_116" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="329.52626" y="565.64214" id="svg_117" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="557.64214" id="svg_118" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="565.64214" id="svg_119" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="557.64214" id="svg_120" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="565.64214" id="svg_121" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="557.64214" id="svg_122" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="565.64214" id="svg_123" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="207.5" y="597.52631" id="svg_124" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="189.47365" y="601.97367" id="svg_125" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">low</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="225.41525" y="597.52631" id="svg_126" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">↑</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="237.93337" y="601.97367" id="svg_127" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">high</text>
  <ellipse fill="#007f3f" stroke="#000000" stroke-width="1.5" cx="222.52626" cy="557.64214" id="svg_129" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="210.52626" y="565.64214" id="svg_130" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000000" stroke-width="0" x="4.54525" y="93.63615" id="svg_131" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">pivotkey</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_16" y2="607.5" x2="425.52319" y1="607.5" x1="80.5" fill-opacity="null" stroke-opacity="null" stroke="#000000" fill="none"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="657.64214" id="svg_78" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="665.64214" id="svg_79" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="402.52626" cy="657.64214" id="svg_80" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="389.52626" y="665.64214" id="svg_81" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#005fbf" stroke="#000" stroke-width="1.5" cx="282.52626" cy="657.64214" id="svg_82" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="665.64214" id="svg_83" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="657.64214" id="svg_128" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="665.64214" id="svg_132" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="657.64214" id="svg_133" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="665.64214" id="svg_134" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#007f3f" stroke="#000000" stroke-width="1.5" cx="222.52626" cy="657.64214" id="svg_135" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="210.52626" y="665.64214" id="svg_136" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
</svg>


* 4）性能分析

	*  快速排序是一个递归过程，其递归树如图所示

	<svg width="303" height="190" >
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_4" y2="142.5" x2="256" y1="41.5" x1="112" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="22" rx="22" id="svg_1" cy="27.64214" cx="92.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="35.64214" x="80.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_5" cy="67.64214" cx="152.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="75.64214" x="140.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_7" cy="157.64214" cx="272.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="165.64214" x="259.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_9" cy="107.64214" cx="212.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="115.64214" x="197.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_11" cy="107.64214" cx="82.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="115.64214" x="70.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_13" cy="67.64214" cx="32.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="75.64214" x="20.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_15" y2="54.5" x2="53" y1="39.5" x1="74" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_16" y2="80.5" x2="50" y1="97.5" x1="67" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
	</svg>

	*  利用序列第一个记录作为基准，将整个序列划分为左右两个子序列。只要是关键字小于基准记录关键字的记录都移到序列左侧
	* 快速排序的趟数取决于递归树的高度。
	* 如果每次划分对一个记录定位后，该记录的左侧子序列与右侧子序列的长度相同，则下一步将是对两个长度减半的子序列进行排序，这是最理想的情况。
		* 在n个元素的序列中，对一个记录定位所需时间为O(n)。若设t(n)是对n个元素的序列进行排序所需的时间，而且每次对一个记录正确定位后，正好把序列划分为长度相等的两个子序列，此时，总的计算时间为：
	$$T(n)\le cn + 2T(n/2)$$  
	$$T(n)\le cn + 2(cn/2 + 2T(n/4)) = 2cn + 4T(n/4)$$  
	$$T(n)\le 2cn + 4(cn/4 + 2T(n/8)) = 3cn + 8T(n/8)$$   
	$$......$$  
	$$T(n)\le cn \log_2n + nT(1)) = O(n \log_2n)$$    

		*  可以证明，快速排序的平均计算时间也是$$O(nlog_2n)$$
		*  实验结果表明：就平均计算时间而言，快速排序是所有内排序方法中最好的一个。
		*  但快速排序是一种不稳定的排序方法 
	*  在最坏情况下，即待排序记录序列已经按其关键字从小到大排好序，其递归树成为单支树。
		* 每次划分只得到一个比上一次少一个记录的子序列
		* 必须经过n-1趟才能把所有记录定位
		* 而且第i趟需要经过n-i次关键字比较才能找到第i个记录的安放位置，总的关键字比较次数将达到
	$$\sum_{i=1}^{n-1}{n-i}=\frac{1}{2}n(n-1) \approx \frac{n^2}{2}$$   
* 5 )改进 	
	* 枢轴记录取low、high、(low+high)/2 三者指向记录关键字居中的记录  

---

### **第四节 选择排序**

####  一、简单选择排序   

*  每一趟（例如第i趟，i=1, 2, ..., n-1）在后面n-i+1个待排序记录中通过n-i次比较，选出关键字最小的记录，与第i个记录交换
*  例子
	<svg width="580" height="469" >
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="122.52626" cy="67.64214" id="svg_1" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="75.64214" id="svg_2" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="67.64214" id="svg_5" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="75.64214" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="242.52626" cy="67.64214" id="svg_7" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="229.52626" y="75.64214" id="svg_8" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="302.52626" cy="67.64214" id="svg_9" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="75.64214" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="362.52626" cy="67.64214" id="svg_11" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="75.64214" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="422.52626" cy="67.64214" id="svg_13" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="410.52626" y="75.64214" id="svg_14" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="35.64214" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="35.64214" id="svg_16" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="230.52626" y="35.64214" id="svg_17" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="290.52626" y="35.64214" id="svg_18" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="35.64214" id="svg_19" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="410.52626" y="35.64214" id="svg_20" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text stroke="#000" fill="#000000" stroke-width="0" stroke-opacity="null" x="37.5" y="148.5" id="svg_39" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">i=1</text>
  <ellipse fill="#ffff00" stroke="#000" stroke-width="1.5" cx="122.52626" cy="137.64214" id="svg_4" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="145.64214" id="svg_21" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="182.52626" cy="137.64214" id="svg_22" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="145.64214" id="svg_23" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="242.52626" cy="137.64214" id="svg_24" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="229.52626" y="145.64214" id="svg_25" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="302.52626" cy="137.64214" id="svg_26" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="145.64214" id="svg_27" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="362.52626" cy="137.64214" id="svg_28" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="145.64214" id="svg_29" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#005fbf" stroke="#000" stroke-width="1.5" cx="422.52626" cy="137.64214" id="svg_30" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="410.52626" y="145.64214" id="svg_31" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="422.52626" cy="197.64214" id="svg_32" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="410.52626" y="205.64214" id="svg_33" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#ffff00" stroke="#000" stroke-width="1.5" cx="182.52626" cy="197.64214" id="svg_34" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="205.64214" id="svg_35" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="242.52626" cy="197.64214" id="svg_36" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="229.52626" y="205.64214" id="svg_37" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="302.52626" cy="197.64214" id="svg_38" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="205.64214" id="svg_40" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#005fbf" stroke="#000" stroke-width="1.5" cx="362.52626" cy="197.64214" id="svg_41" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="205.64214" id="svg_42" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="122.52626" cy="197.64214" id="svg_43" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="205.64214" id="svg_44" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#005fbf" stroke="#000" stroke-width="1.5" cx="422.52626" cy="257.64214" id="svg_45" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="410.52626" y="265.64214" id="svg_46" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="362.52626" cy="257.64214" id="svg_47" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="265.64214" id="svg_48" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#ffff00" stroke="#000" stroke-width="1.5" cx="242.52626" cy="257.64214" id="svg_49" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="229.52626" y="265.64214" id="svg_50" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="302.52626" cy="257.64214" id="svg_51" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="265.64214" id="svg_52" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="182.52626" cy="257.64214" id="svg_53" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="265.64214" id="svg_54" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="122.52626" cy="257.64214" id="svg_55" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="265.64214" id="svg_56" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="242.52626" cy="317.64214" id="svg_57" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="230.52626" y="325.64214" id="svg_58" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="362.52626" cy="317.64214" id="svg_59" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="325.64214" id="svg_60" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="422.52626" cy="317.64214" id="svg_61" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="409.52626" y="325.64214" id="svg_62" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#005fbf" stroke="#000" stroke-width="1.5" cx="302.52626" cy="317.64214" id="svg_63" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="325.64214" id="svg_65" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="182.52626" cy="317.64214" id="svg_66" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="325.64214" id="svg_67" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="122.52626" cy="317.64214" id="svg_68" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="325.64214" id="svg_69" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="242.52626" cy="377.64214" id="svg_70" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="230.52626" y="385.64214" id="svg_71" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#005fbf" stroke="#000" stroke-width="1.5" cx="362.52626" cy="377.64214" id="svg_72" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="385.64214" id="svg_73" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="422.52626" cy="377.64214" id="svg_74" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="409.52626" y="385.64214" id="svg_75" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="302.52626" cy="377.64214" id="svg_76" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="385.64214" id="svg_77" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="182.52626" cy="377.64214" id="svg_78" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="385.64214" id="svg_79" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="122.52626" cy="377.64214" id="svg_80" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="385.64214" id="svg_81" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="242.52626" cy="437.64214" id="svg_82" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="230.52626" y="445.64214" id="svg_83" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="362.52626" cy="437.64214" id="svg_84" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="350.52626" y="445.64214" id="svg_85" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="422.52626" cy="437.64214" id="svg_86" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="409.52626" y="445.64214" id="svg_87" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="302.52626" cy="437.64214" id="svg_88" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="287.52626" y="445.64214" id="svg_89" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="182.52626" cy="437.64214" id="svg_90" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="170.52626" y="445.64214" id="svg_91" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#007f00" stroke="#000" stroke-width="1.5" cx="122.52626" cy="437.64214" id="svg_92" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="110.52626" y="445.64214" id="svg_93" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text style="cursor: move;" stroke="#000" fill="#000000" stroke-width="0" stroke-opacity="null" x="37.5" y="208.5" id="svg_94" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">i=2</text>
  <text style="cursor: move;" stroke="#000" fill="#000000" stroke-width="0" stroke-opacity="null" x="37.5" y="268.5" id="svg_95" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">i=3</text>
  <text style="cursor: move;" stroke="#000" fill="#000000" stroke-width="0" stroke-opacity="null" x="37.5" y="328.5" id="svg_96" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">i=4</text>
  <text style="cursor: move;" stroke="#000" fill="#000000" stroke-width="0" stroke-opacity="null" x="37.5" y="388.5" id="svg_97" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">i=5</text>
  <text stroke="#000" fill="#000000" stroke-width="0" stroke-opacity="null" x="37.5" y="448.5" id="svg_98" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">i=6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_99" y="132" x="477.5" stroke-width="0" stroke="#000" fill="#000000">min = 08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_100" y="147" x="475.5" stroke-width="0" stroke="#000" fill="#000000">swap 21 08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_101" y="182" x="477.5" stroke-width="0" stroke="#000" fill="#000000">min =16</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_102" y="197" x="475.5" stroke-width="0" stroke="#000" fill="#000000">swap 25 16</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_103" y="242" x="477.5" stroke-width="0" stroke="#000" fill="#000000">min = 21</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_104" y="257" x="475.5" stroke-width="0" stroke="#000" fill="#000000">swap 49 21</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_105" y="312" x="477.5" stroke-width="0" stroke="#000" fill="#000000">min =25*</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_106" y="327" x="475.5" stroke-width="0" stroke="#000" fill="#000000">no swap</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_107" y="372" x="477.5" stroke-width="0" stroke="#000" fill="#000000">min = 25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_108" y="387" x="475.5" stroke-width="0" stroke="#000" fill="#000000">no swap</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_109" y="442" x="477.5" stroke-width="0" stroke="#000" fill="#000000">finish</text>
	</svg>

*  性能分析 
	* 直接选择排序的关键字比较次数KCN与记录的初始排列无关
	* 设整个待排序记录序列有n个记录，则第i趟选择最小关键字记录所需的比较次数总是n-i次。总的关键字比较次数为：  
	$$KCN = \sum_{i=1}^{n-1}{(n-i)} = n(n-1)/2$$  
	*  记录的移动次数与记录序列的初始排列有关。当这组记录的初始状态是按其关键字从下到大有序的时候。记录的移动次数RMN=0，达到最少  
	*  最坏情况是每一趟都要进行交换，总的记录移动次数为RMN =3(n-1)  
	*  直接选择排序时间复杂度为O(n^2)  
	*  直接选择排序是一种不稳定的排序方法  
