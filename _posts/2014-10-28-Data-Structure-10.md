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

####  二、堆排序   

* 1）定义
	*	设有一个关键字集合，按完全二叉树的顺序存储方式存放在一个一维数组中。对它们从根开始，自顶向下，同一层自左向右，从1开始连续编号。若满足： 
	$$K_i \ge K_{2i} \&\& k_i \ge k_{2i+1}  $$  
	则称该关键字集合构成一个堆（最大堆）
* 2）举例

<svg width="460" height="268" >
  <ellipse ry="22" rx="22" id="svg_1" cy="127.64214" cx="302.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="135.64214" x="290.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_5" cy="127.64214" cx="182.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="135.64214" x="170.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_7" cy="67.64214" cx="242.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="75.64214" x="229.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_9" cy="197.64214" cx="122.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="205.64214" x="107.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_11" cy="197.64214" cx="212.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="205.64214" x="200.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_13" cy="197.64214" cx="272.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="205.64214" x="260.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_15" y="168.64214" x="246.52626" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="51.64214" x="204.52626" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_17" y="99.64214" x="159.52626" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="97.64214" x="295.52626" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_19" y="172.64214" x="94.52626" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_20" y="167.64214" x="218.52626" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_4" y2="112" x2="198.5" y1="83" x1="225.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_21" y2="172" x2="138.5" y1="143" x1="165.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_22" y2="172" x2="268.5" y1="143" x1="295.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_23" y2="112" x2="287.5" y1="84" x1="260.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_24" y2="172" x2="217.5" y1="144" x1="190.5" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
</svg>

* 3）主要要解决两个问题
	1. 如何根据给定的序列建初始堆
	2. 任何在交换掉根结点后，将剩下的结点调整为新的堆（筛选）
* 4）筛选
	* 输出根结点
	* 用最后结点代替根结点值
	* 比较根结点与两个子结点的值，如果小于其中一个子结点，则选择大的子结点与根结点交换
	* 继续将交换的结点与其子结点比较
	* 直到叶子结点或者根结点值大于两个子结点 

<svg width="700" height="214" >
  <ellipse ry="22" rx="22" id="svg_1" cy="109.64214" cx="211.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="117.64214" x="199.51922" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_5" cy="109.64214" cx="91.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="117.64214" x="79.51922" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_7" cy="179.64214" cx="181.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="187.64214" x="168.51922" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_9" cy="179.64214" cx="31.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="187.64214" x="16.51922" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_11" cy="179.64214" cx="121.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="187.64214" x="109.51922" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_13" cy="49.64214" cx="151.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="57.64214" x="139.51922" stroke-width="0" stroke="#000" fill="#ff0000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_15" y="150.64214" x="155.51922" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="33.64214" x="113.51922" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_17" y="81.64214" x="68.51922" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="79.64214" x="204.51922" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_19" y="154.64214" x="3.51922" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_20" y="149.64214" x="127.51922" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_4" y2="94" x2="107.49296" y1="65" x1="134.49296" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_21" y2="154" x2="47.49296" y1="125" x1="74.49296" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_23" y2="94" x2="196.49296" y1="66" x1="169.49296" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_24" y2="154" x2="126.49296" y1="126" x1="99.49296" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="22" rx="22" id="svg_48" cy="109.64214" cx="446.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_49" y="117.64214" x="434.51922" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_50" cy="49.64214" cx="386.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_51" y="57.64214" x="374.51922" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_52" cy="179.64214" cx="416.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_53" y="187.64214" x="403.51922" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_54" cy="179.64214" cx="266.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_55" y="187.64214" x="251.51922" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_56" cy="179.64214" cx="356.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_57" y="187.64214" x="344.51922" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_58" cy="109.64214" cx="326.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_59" y="117.64214" x="314.51922" stroke-width="0" stroke="#000" fill="#ff0000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_60" y="150.64214" x="390.51922" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_61" y="33.64214" x="348.51922" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_62" y="81.64214" x="303.51922" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_63" y="79.64214" x="439.51922" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_64" y="154.64214" x="238.51922" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_65" y="149.64214" x="362.51922" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_66" y2="94" x2="342.49296" y1="65" x1="369.49296" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_67" y2="154" x2="282.49296" y1="125" x1="309.49296" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_68" y2="94" x2="431.49296" y1="66" x1="404.49296" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_69" y2="154" x2="361.49296" y1="126" x1="334.49296" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <ellipse ry="22" rx="22" id="svg_70" cy="109.64214" cx="674.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_71" y="117.64214" x="662.51922" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_72" cy="49.64214" cx="614.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_73" y="57.64214" x="602.51922" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_74" cy="179.64214" cx="644.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_75" y="187.64214" x="631.51922" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_76" cy="109.64214" cx="554.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_77" y="117.64214" x="539.51922" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_78" cy="179.64214" cx="584.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_79" y="187.64214" x="572.51922" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_80" cy="179.64214" cx="504.51922" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_81" y="187.64214" x="492.51922" stroke-width="0" stroke="#000" fill="#ff0000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_82" y="150.64214" x="618.51922" stroke-width="0" stroke="#000" fill="#000000">6</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_83" y="33.64214" x="576.51922" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_84" y="81.64214" x="531.51922" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_85" y="79.64214" x="667.51922" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_86" y="154.64214" x="466.51922" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_87" y="149.64214" x="590.51922" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_88" y2="94" x2="570.49296" y1="65" x1="597.49296" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_89" y2="154" x2="510.49296" y1="125" x1="537.49296" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_90" y2="94" x2="659.49296" y1="66" x1="632.49296" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_91" y2="154" x2="589.49296" y1="126" x1="562.49296" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line fill="none" stroke="#ff0000" stroke-width="1.5" x1="278.33319" y1="146.71427" x2="298.80938" y2="124.80952" id="svg_93" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#ff0000" stroke-width="1.5" x1="106.6666" y1="82.42859" x2="127.14278" y2="60.52383" id="svg_94" stroke-linejoin="null" stroke-linecap="null"/>
</svg>

* 5）创建初始堆
	*	根据给定的序列，从1至n按顺序创建一个完全二叉树
	*	由最后一个非终端结点（第n/2个结点）开始至第1个结点。逐步做筛选（向叶子方向操作）
	*	例子： 已知待排序的一组记录的初始排列为：21, 25, 49, 25*, 16, 08 

<svg width="539" height="520" >
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="231.51922" cy="127.64214" id="svg_1" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="111.51922" cy="127.64214" id="svg_5" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="99.51922" y="135.64214" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="201.51922" cy="197.64214" id="svg_7" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="219.51922" y="137.64214" id="svg_8" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="51.51922" cy="197.64214" id="svg_9" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="36.51922" y="205.64214" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="141.51922" cy="197.64214" id="svg_11" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="129.51922" y="205.64214" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="171.51922" cy="67.64214" id="svg_13" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="188.51922" y="205.64214" id="svg_14" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="175.51922" y="168.64214" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="133.51922" y="51.64214" id="svg_16" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="88.51922" y="99.64214" id="svg_17" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="224.51922" y="97.64214" id="svg_18" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="23.51922" y="172.64214" id="svg_19" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="147.51922" y="167.64214" id="svg_20" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="154.49296" y1="83" x2="127.49296" y2="112" id="svg_4" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="224.49296" y1="149" x2="197.49296" y2="178" id="svg_21" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="189.49296" y1="84" x2="216.49296" y2="112" id="svg_23" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="119.49296" y1="144" x2="146.49296" y2="172" id="svg_24" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="94.49296" y1="143" x2="67.49296" y2="172" id="svg_22" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="158.51922" y="75.64214" id="svg_2" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#ff0000" stroke-width="0" stroke-opacity="null" x="263.34211" y="85.28948" id="svg_25" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">i=3</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="246.5" y="109.5" id="svg_26" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="rotate(114.08781433105469 258.5,101) ">→</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="484.53085" cy="127.64214" id="svg_27" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="364.53085" cy="127.64214" id="svg_28" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="352.53085" y="135.64214" id="svg_29" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="454.53085" cy="197.64214" id="svg_30" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="472.53085" y="137.64214" id="svg_31" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="304.53085" cy="197.64214" id="svg_32" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="289.53085" y="205.64214" id="svg_33" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="394.53085" cy="197.64214" id="svg_34" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="382.53085" y="205.64214" id="svg_35" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="424.53085" cy="67.64214" id="svg_36" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="441.53085" y="205.64214" id="svg_37" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="428.53085" y="168.64214" id="svg_38" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="386.53085" y="51.64214" id="svg_39" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="341.53085" y="99.64214" id="svg_40" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="477.53085" y="97.64214" id="svg_41" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="276.53085" y="172.64214" id="svg_42" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="400.53085" y="167.64214" id="svg_43" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="407.50459" y1="83" x2="380.50459" y2="112" id="svg_44" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="477.50459" y1="149" x2="450.50459" y2="178" id="svg_45" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="442.50459" y1="84" x2="469.50459" y2="112" id="svg_46" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="372.50459" y1="144" x2="399.50459" y2="172" id="svg_47" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="347.50459" y1="143" x2="320.50459" y2="172" id="svg_48" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="411.53085" y="75.64214" id="svg_49" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#ff0000" stroke-width="0" stroke-opacity="null" x="353.62646" y="75.28947" id="svg_50" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">i=2</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="352.2389" y="98.59091" id="svg_51" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="rotate(74.365234375 364.2336730957031,90.40625000000003) ">→</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="231.40269" cy="374.07155" id="svg_52" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="111.40269" cy="374.07155" id="svg_53" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="99.40269" y="382.07155" id="svg_54" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="201.40269" cy="444.07155" id="svg_55" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="219.40269" y="384.07155" id="svg_56" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="51.40269" cy="444.07155" id="svg_57" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="36.40269" y="452.07155" id="svg_58" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="141.40269" cy="444.07155" id="svg_59" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="129.40269" y="452.07155" id="svg_60" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="171.40269" cy="314.07155" id="svg_61" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="188.40269" y="452.07155" id="svg_62" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="175.40269" y="415.07155" id="svg_63" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="133.40269" y="298.07155" id="svg_64" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="88.40269" y="346.07155" id="svg_65" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="224.40269" y="344.07155" id="svg_66" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="23.40269" y="419.07155" id="svg_67" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="147.40269" y="414.07155" id="svg_68" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="154.37643" y1="329.42941" x2="127.37643" y2="358.42941" id="svg_69" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="224.37643" y1="395.42941" x2="197.37643" y2="424.42941" id="svg_70" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="189.37643" y1="330.42941" x2="216.37643" y2="358.42941" id="svg_71" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="119.37643" y1="390.42941" x2="146.37643" y2="418.42941" id="svg_72" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="94.37643" y1="389.42941" x2="67.37643" y2="418.42941" id="svg_73" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="158.40269" y="322.07155" id="svg_74" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#ff0000" stroke-width="0" stroke-opacity="null" x="213.22558" y="281.71888" id="svg_75" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">i=1</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="191.83802" y="305.92941" id="svg_76" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="rotate(117.68938446044922 203.83566284179688,297.7447509765625) ">→</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="484.36532" cy="374.07155" id="svg_77" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="364.36532" cy="374.07155" id="svg_78" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="352.36532" y="382.07155" id="svg_79" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="454.36532" cy="444.07155" id="svg_80" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="304.36532" cy="444.07155" id="svg_82" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="289.36532" y="452.07155" id="svg_83" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="394.36532" cy="444.07155" id="svg_84" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="382.36532" y="452.07155" id="svg_85" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="424.36532" cy="314.07155" id="svg_86" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="441.36532" y="452.07155" id="svg_87" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="428.36532" y="415.07155" id="svg_88" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="386.36532" y="298.07155" id="svg_89" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="341.36532" y="346.07155" id="svg_90" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="477.36532" y="344.07155" id="svg_91" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="276.36532" y="419.07155" id="svg_92" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="400.36532" y="414.07155" id="svg_93" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="407.33906" y1="329.42941" x2="380.33906" y2="358.42941" id="svg_94" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="477.33906" y1="395.42941" x2="450.33906" y2="424.42941" id="svg_95" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="442.33906" y1="330.42941" x2="469.33906" y2="358.42941" id="svg_96" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="372.33906" y1="390.42941" x2="399.33906" y2="418.42941" id="svg_97" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="347.33906" y1="389.42941" x2="320.33906" y2="418.42941" id="svg_98" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="471.36533" y="383.88974" id="svg_99" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="446.61883" y="339.56577" id="svg_101" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="rotate(-134.2577362060547 458.6119689941407,331.38253784179693) ">→</text>
  <text fill="#ff0000" stroke="#000" stroke-width="0" stroke-opacity="null" x="459.3461" y="331.38395" id="svg_103" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" transform="rotate(45.70512390136719 471.34280395507824,323.2021484374999) ">→</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="411.45622" y="323.16245" id="svg_81" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="113.5909" y="257.5909" id="svg_104" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">初始</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="303.5" y="253.5" id="svg_105" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">不需要调整</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="60.11555" y="506.11122" id="svg_106" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">不需要调整</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="345.57012" y="503.29304" id="svg_107" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">调整</text>
</svg>

* 6) 排序举例	 

<svg width="531" height="1581">
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="229.36211" cy="127.64214" id="svg_77" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="109.36211" cy="127.64214" id="svg_78" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="97.36211" y="135.64214" id="svg_79" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="199.36211" cy="197.64214" id="svg_80" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="49.36211" cy="197.64214" id="svg_82" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="34.36211" y="205.64214" id="svg_83" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="139.36211" cy="197.64214" id="svg_84" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="127.36211" y="205.64214" id="svg_85" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="169.36211" cy="67.64214" id="svg_86" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="186.36211" y="205.64214" id="svg_87" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="173.36211" y="168.64214" id="svg_88" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="131.36211" y="51.64214" id="svg_89" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="86.36211" y="99.64214" id="svg_90" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="222.36211" y="97.64214" id="svg_91" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="21.36211" y="172.64214" id="svg_92" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="145.36211" y="167.64214" id="svg_93" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="152.33585" y1="83" x2="125.33585" y2="112" id="svg_94" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="222.33585" y1="149" x2="195.33585" y2="178" id="svg_95" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="187.33585" y1="84" x2="214.33585" y2="112" id="svg_96" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="117.33585" y1="144" x2="144.33585" y2="172" id="svg_97" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="92.33585" y1="143" x2="65.33585" y2="172" id="svg_98" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="216.36212" y="137.46033" id="svg_99" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="156.45301" y="76.73304" id="svg_81" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="121.71589" y="298.09403" id="svg_104" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">初始</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="338.87493" y="296.50313" id="svg_105" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">交换1号与6号记录，</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="77.51962" y="605.72391" id="svg_107" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">从1号到5号</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_26" y2="275.30584" x2="58" y1="244.5" x1="58" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_27" y2="275.30584" x2="88" y1="244.5" x1="88" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_28" y2="275.30584" x2="118" y1="244.5" x1="118" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_29" y2="275.30584" x2="148" y1="244.5" x1="148" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_30" y2="275.30584" x2="178" y1="244.5" x1="178" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="275.30584" x2="208" y1="244.5" x1="208" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="275.30584" x2="238" y1="244.5" x1="238" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_33" y2="245.5" x2="236.01117" y1="245.5" x1="57" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_34" y2="275.5" x2="236.01117" y1="275.5" x1="57" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_35" y="264.5" x="67" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_36" y="264.5" x="97" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_37" y="264.5" x="127" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_38" y="264.5" x="157" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_39" y="264.5" x="187" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_40" y="264.5" x="217" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="489.36211" cy="127.64214" id="svg_41" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="369.36211" cy="127.64214" id="svg_42" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="357.36211" y="135.64214" id="svg_43" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="459.36211" cy="197.64214" id="svg_44" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="309.36211" cy="197.64214" id="svg_45" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="294.36211" y="205.64214" id="svg_46" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="399.36211" cy="197.64214" id="svg_47" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="387.36211" y="205.64214" id="svg_48" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="429.36211" cy="67.64214" id="svg_49" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="415.11214" y="76.26725" id="svg_50" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="433.36211" y="168.64214" id="svg_51" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="391.36211" y="51.64214" id="svg_52" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="346.36211" y="99.64214" id="svg_53" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="482.36211" y="97.64214" id="svg_54" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="281.36211" y="172.64214" id="svg_55" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="405.36211" y="167.64214" id="svg_56" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="412.33585" y1="83" x2="385.33585" y2="112" id="svg_57" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="482.33585" y1="149" x2="455.33585" y2="178" id="svg_58" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="447.33585" y1="84" x2="474.33585" y2="112" id="svg_59" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="377.33585" y1="144" x2="404.33585" y2="172" id="svg_60" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="352.33585" y1="143" x2="325.33585" y2="172" id="svg_61" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="476.36212" y="137.46033" id="svg_62" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="445.82799" y="205.48293" id="svg_63" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_64" y2="275.30584" x2="318" y1="244.5" x1="318" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_65" y2="275.30584" x2="348" y1="244.5" x1="348" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_66" y2="275.30584" x2="378" y1="244.5" x1="378" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_67" y2="275.30584" x2="408" y1="244.5" x1="408" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_68" y2="275.30584" x2="438" y1="244.5" x1="438" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_69" y2="275.30584" x2="468" y1="244.5" x1="468" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_70" y2="275.30584" x2="498" y1="244.5" x1="498" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_71" y2="245.5" x2="496.01117" y1="245.5" x1="317" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_72" y2="275.5" x2="496.01117" y1="275.5" x1="317" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_73" y="264.5" x="477" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_74" y="264.5" x="357" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_75" y="264.5" x="387" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_76" y="264.5" x="417" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_100" y="264.5" x="447" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_101" y="264.5" x="327" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="230.79064" cy="435.49929" id="svg_102" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="110.79064" cy="435.49929" id="svg_103" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="200.79064" cy="505.49929" id="svg_109" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="50.79064" cy="505.49929" id="svg_110" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="94.54059" y="442.24935" id="svg_111" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="140.79064" cy="505.49929" id="svg_112" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="128.79064" y="513.49929" id="svg_113" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="none" stroke="#000" stroke-width="1.5" cx="170.79064" cy="375.49929" id="svg_114" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="35.29078" y="512.87428" id="svg_115" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="174.79064" y="476.49929" id="svg_116" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="132.79064" y="359.49929" id="svg_117" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="87.79064" y="407.49929" id="svg_118" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="223.79064" y="405.49929" id="svg_119" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="22.79064" y="480.49929" id="svg_120" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="146.79064" y="475.49929" id="svg_121" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="153.76438" y1="390.85715" x2="126.76438" y2="419.85715" id="svg_122" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="223.76438" y1="456.85715" x2="196.76438" y2="485.85715" id="svg_123" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="188.76438" y1="391.85715" x2="215.76438" y2="419.85715" id="svg_124" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="118.76438" y1="451.85715" x2="145.76438" y2="479.85715" id="svg_125" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="93.76438" y1="450.85715" x2="66.76438" y2="479.85715" id="svg_126" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="217.79065" y="445.31748" id="svg_127" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="187.25652" y="513.34007" id="svg_128" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_129" y2="583.16299" x2="59.42853" y1="552.35715" x1="59.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_130" y2="583.16299" x2="89.42853" y1="552.35715" x1="89.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_131" y2="583.16299" x2="119.42853" y1="552.35715" x1="119.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_132" y2="583.16299" x2="149.42853" y1="552.35715" x1="149.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_133" y2="583.16299" x2="179.42853" y1="552.35715" x1="179.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_134" y2="583.16299" x2="209.42853" y1="552.35715" x1="209.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_135" y2="583.16299" x2="239.42853" y1="552.35715" x1="239.42853" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_136" y2="553.35715" x2="237.4397" y1="553.35715" x1="58.42853" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_137" y2="583.35715" x2="237.4397" y1="583.35715" x1="58.42853" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_138" y="572.35715" x="218.42853" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_139" y="572.35715" x="67.17855" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_140" y="572.35715" x="128.42853" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_141" y="572.98215" x="96.55358" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_142" y="572.35715" x="188.42853" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_143" y="572.98215" x="157.80345" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="158.79059" y="383.49934" id="svg_108" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="496.89409" cy="434.07073" id="svg_144" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="376.89409" cy="434.07073" id="svg_145" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="466.89409" cy="504.07073" id="svg_146" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="316.89409" cy="504.07073" id="svg_147" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="360.64404" y="440.82079" id="svg_148" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="406.89409" cy="504.07073" id="svg_149" rx="22" ry="22"/>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="436.89409" cy="374.07073" id="svg_151" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="301.39423" y="511.44572" id="svg_152" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="440.89409" y="475.07073" id="svg_153" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="398.89409" y="358.07073" id="svg_154" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="353.89409" y="406.07073" id="svg_155" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="489.89409" y="404.07073" id="svg_156" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="288.89409" y="479.07073" id="svg_157" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="412.89409" y="474.07073" id="svg_158" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="419.86783" y1="389.42859" x2="392.86783" y2="418.42859" id="svg_159" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="489.86783" y1="455.42859" x2="462.86783" y2="484.42859" id="svg_160" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="454.86783" y1="390.42859" x2="481.86783" y2="418.42859" id="svg_161" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="384.86783" y1="450.42859" x2="411.86783" y2="478.42859" id="svg_162" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="359.86783" y1="449.42859" x2="332.86783" y2="478.42859" id="svg_163" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="483.8941" y="443.88892" id="svg_164" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="453.35997" y="511.91151" id="svg_165" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="393.01907" y="512.69567" id="svg_181" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="423.01907" y="381.44585" id="svg_150" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_182" y2="581.73443" x2="322.62335" y1="550.92859" x1="322.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_183" y2="581.73443" x2="352.62335" y1="550.92859" x1="352.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_184" y2="581.73443" x2="382.62335" y1="550.92859" x1="382.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_185" y2="581.73443" x2="412.62335" y1="550.92859" x1="412.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_186" y2="581.73443" x2="442.62335" y1="550.92859" x1="442.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_187" y2="581.73443" x2="472.62335" y1="550.92859" x1="472.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_188" y2="581.73443" x2="502.62335" y1="550.92859" x1="502.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_189" y2="551.92859" x2="500.63452" y1="551.92859" x1="321.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_190" y2="581.92859" x2="500.63452" y1="581.92859" x1="321.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_191" y="570.92859" x="481.62335" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_192" y="572.17859" x="450.99827" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_193" y="570.92859" x="391.62335" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_194" y="571.55359" x="359.7484" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_195" y="571.55359" x="327.24846" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_196" y="571.55359" x="420.99827" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="81.269" y="626.57615" id="svg_197" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">重新调整为最大堆</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="343.59071" y="319.969" id="svg_198" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6号就位</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="323.49828" y="602.93172" id="svg_199" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">交换1号与5号记录，</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="328.21406" y="626.39759" id="svg_200" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5号就位</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="236.89409" cy="750.4993" id="svg_201" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="116.89409" cy="750.4993" id="svg_202" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="206.89409" cy="820.4993" id="svg_203" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="56.89409" cy="820.4993" id="svg_204" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="146.89409" cy="820.4993" id="svg_206" rx="22" ry="22"/>
  <ellipse fill="none" stroke="#000" stroke-width="1.5" cx="176.89409" cy="690.4993" id="svg_207" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="41.39423" y="827.8743" id="svg_208" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="180.89409" y="791.4993" id="svg_209" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="138.89409" y="674.4993" id="svg_210" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="93.89409" y="722.4993" id="svg_211" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="229.89409" y="720.4993" id="svg_212" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="28.89409" y="795.4993" id="svg_213" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="152.89409" y="790.4993" id="svg_214" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="159.86783" y1="705.85716" x2="132.86783" y2="734.85716" id="svg_215" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="229.86783" y1="771.85716" x2="202.86783" y2="800.85716" id="svg_216" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="194.86783" y1="706.85716" x2="221.86783" y2="734.85716" id="svg_217" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="124.86783" y1="766.85716" x2="151.86783" y2="794.85716" id="svg_218" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="99.86783" y1="765.85716" x2="72.86783" y2="794.85716" id="svg_219" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="223.8941" y="760.31749" id="svg_220" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="193.35997" y="828.34009" id="svg_221" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="133.01907" y="829.12424" id="svg_222" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="100.87621" y="759.30299" id="svg_223" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_224" y2="898.163" x2="62.62335" y1="867.35716" x1="62.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_225" y2="898.163" x2="92.62335" y1="867.35716" x1="92.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_226" y2="898.163" x2="122.62335" y1="867.35716" x1="122.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_227" y2="898.163" x2="152.62335" y1="867.35716" x1="152.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_228" y2="898.163" x2="182.62335" y1="867.35716" x1="182.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_229" y2="898.163" x2="212.62335" y1="867.35716" x1="212.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_230" y2="898.163" x2="242.62335" y1="867.35716" x1="242.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_231" y2="868.35716" x2="240.63452" y1="868.35716" x1="61.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_232" y2="898.35716" x2="240.63452" y1="898.35716" x1="61.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_233" y="889.50002" x="219.48049" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_234" y="888.60716" x="190.99827" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_235" y="887.35716" x="131.62335" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_236" y="888.69645" x="69.03411" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_237" y="888.69645" x="99.39132" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_238" y="887.98216" x="160.99827" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="343.49828" y="920.07458" id="svg_239" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">交换1号与4号记录，</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="348.21406" y="943.54045" id="svg_240" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4号就位</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="159.92976" y="697.96365" id="svg_205" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="496.89409" cy="750.4993" id="svg_280" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="376.89409" cy="750.4993" id="svg_281" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="466.89409" cy="820.4993" id="svg_282" rx="22" ry="22"/>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="316.89409" cy="820.4993" id="svg_283" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="406.89409" cy="820.4993" id="svg_284" rx="22" ry="22"/>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="436.89409" cy="690.4993" id="svg_285" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="422.8228" y="699.30285" id="svg_286" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="440.89409" y="791.4993" id="svg_287" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="398.89409" y="674.4993" id="svg_288" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="353.89409" y="722.4993" id="svg_289" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="489.89409" y="720.4993" id="svg_290" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="288.89409" y="795.4993" id="svg_291" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="412.89409" y="790.4993" id="svg_292" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="419.86783" y1="705.85716" x2="392.86783" y2="734.85716" id="svg_293" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="489.86783" y1="771.85716" x2="462.86783" y2="800.85716" id="svg_294" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="454.86783" y1="706.85716" x2="481.86783" y2="734.85716" id="svg_295" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="384.86783" y1="766.85716" x2="411.86783" y2="794.85716" id="svg_296" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="359.86783" y1="765.85716" x2="332.86783" y2="794.85716" id="svg_297" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="483.8941" y="760.31749" id="svg_298" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="453.35997" y="828.34009" id="svg_299" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="393.01907" y="829.12424" id="svg_300" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="360.87621" y="759.30299" id="svg_301" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_302" y2="898.163" x2="322.62335" y1="867.35716" x1="322.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_303" y2="898.163" x2="352.62335" y1="867.35716" x1="352.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_304" y2="898.163" x2="382.62335" y1="867.35716" x1="382.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_305" y2="898.163" x2="412.62335" y1="867.35716" x1="412.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_306" y2="898.163" x2="442.62335" y1="867.35716" x1="442.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_307" y2="898.163" x2="472.62335" y1="867.35716" x1="472.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_308" y2="898.163" x2="502.62335" y1="867.35716" x1="502.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_309" y2="868.35716" x2="500.63452" y1="868.35716" x1="321.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_310" y2="898.35716" x2="500.63452" y1="898.35716" x1="321.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_311" y="888.78573" x="480.19478" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_312" y="888.60716" x="450.99827" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_313" y="887.35716" x="391.62335" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_314" y="887.98216" x="420.46269" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_315" y="888.69645" x="359.39132" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_316" y="887.98216" x="330.28398" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="300.64403" y="830.1065" id="svg_317" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="76.09105" y="920.00964" id="svg_318" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">从1号到4号</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="79.84043" y="940.86189" id="svg_319" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">重新调整为最大堆</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="236.89409" cy="1061.22905" id="svg_320" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="116.89409" cy="1061.22905" id="svg_321" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="206.89409" cy="1131.22905" id="svg_322" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="56.89409" cy="1131.22905" id="svg_323" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="146.89409" cy="1131.22905" id="svg_324" rx="22" ry="22"/>
  <ellipse fill="none" stroke="#000" stroke-width="1.5" cx="176.89409" cy="1001.22905" id="svg_325" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="224.25138" y="1069.31833" id="svg_326" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="180.89409" y="1102.22905" id="svg_327" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="138.89409" y="985.22905" id="svg_328" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="93.89409" y="1033.22905" id="svg_329" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="229.89409" y="1031.22905" id="svg_330" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="28.89409" y="1106.22905" id="svg_331" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="152.89409" y="1101.22905" id="svg_332" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="159.86783" y1="1016.58691" x2="132.86783" y2="1045.58691" id="svg_333" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="229.86783" y1="1082.58691" x2="202.86783" y2="1111.58691" id="svg_334" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="194.86783" y1="1017.58691" x2="221.86783" y2="1045.58691" id="svg_335" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="124.86783" y1="1077.58691" x2="151.86783" y2="1105.58691" id="svg_336" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="99.86783" y1="1076.58691" x2="72.86783" y2="1105.58691" id="svg_337" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="163.17982" y="1010.33295" id="svg_338" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="193.35997" y="1139.06984" id="svg_339" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="133.01907" y="1139.85399" id="svg_340" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="100.87621" y="1070.03274" id="svg_341" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_342" y2="1208.89276" x2="62.62335" y1="1178.08691" x1="62.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_343" y2="1208.89276" x2="92.62335" y1="1178.08691" x1="92.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_344" y2="1208.89276" x2="122.62335" y1="1178.08691" x1="122.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_345" y2="1208.89276" x2="152.62335" y1="1178.08691" x1="152.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_346" y2="1208.89276" x2="182.62335" y1="1178.08691" x1="182.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_347" y2="1208.89276" x2="212.62335" y1="1178.08691" x1="212.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_348" y2="1208.89276" x2="242.62335" y1="1178.08691" x1="242.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_349" y2="1179.08691" x2="240.63452" y1="1179.08691" x1="61.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_350" y2="1209.08691" x2="240.63452" y1="1209.08691" x1="61.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_351" y="1200.22977" x="219.48049" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_352" y="1199.33691" x="190.99827" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_353" y="1200.22977" x="70.19478" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_354" y="1199.4262" x="158.31984" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_355" y="1199.4262" x="99.39132" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_356" y="1199.4262" x="129.5697" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="343.49828" y="1230.80433" id="svg_357" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">交换1号与3号记录，</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="348.21406" y="1254.2702" id="svg_358" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3号就位</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="40.64404" y="1140.12198" id="svg_359" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="496.89409" cy="1061.22905" id="svg_360" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="376.89409" cy="1061.22905" id="svg_361" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="466.89409" cy="1131.22905" id="svg_362" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="316.89409" cy="1131.22905" id="svg_363" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="406.89409" cy="1131.22905" id="svg_364" rx="22" ry="22"/>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="436.89409" cy="1001.22905" id="svg_365" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="422.8228" y="1010.03261" id="svg_366" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="440.89409" y="1102.22905" id="svg_367" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="398.89409" y="985.22905" id="svg_368" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="353.89409" y="1033.22905" id="svg_369" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="489.89409" y="1031.22905" id="svg_370" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="288.89409" y="1106.22905" id="svg_371" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="412.89409" y="1101.22905" id="svg_372" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="419.86783" y1="1016.58691" x2="392.86783" y2="1045.58691" id="svg_373" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="489.86783" y1="1082.58691" x2="462.86783" y2="1111.58691" id="svg_374" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="454.86783" y1="1017.58691" x2="481.86783" y2="1045.58691" id="svg_375" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="384.86783" y1="1077.58691" x2="411.86783" y2="1105.58691" id="svg_376" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="359.86783" y1="1076.58691" x2="332.86783" y2="1105.58691" id="svg_377" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="483.8941" y="1071.04724" id="svg_378" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="453.35997" y="1139.06984" id="svg_379" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="393.01907" y="1139.85399" id="svg_380" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="360.87621" y="1070.03274" id="svg_381" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_382" y2="1208.89276" x2="322.62335" y1="1178.08691" x1="322.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_383" y2="1208.89276" x2="352.62335" y1="1178.08691" x1="352.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_384" y2="1208.89276" x2="382.62335" y1="1178.08691" x1="382.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_385" y2="1208.89276" x2="412.62335" y1="1178.08691" x1="412.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_386" y2="1208.89276" x2="442.62335" y1="1178.08691" x1="442.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_387" y2="1208.89276" x2="472.62335" y1="1178.08691" x1="472.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_388" y2="1208.89276" x2="502.62335" y1="1178.08691" x1="502.62335" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_389" y2="1179.08691" x2="500.63452" y1="1179.08691" x1="321.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_390" y2="1209.08691" x2="500.63452" y1="1209.08691" x1="321.62335" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_391" y="1199.51548" x="480.19478" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_392" y="1199.33691" x="450.99827" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_393" y="1199.51548" x="390.19478" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_394" y="1198.71191" x="420.46269" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_395" y="1199.4262" x="359.39132" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_396" y="1198.71191" x="330.28398" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="300.64403" y="1140.83625" id="svg_397" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="76.09105" y="1230.73939" id="svg_398" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">从1号到3号</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="79.84043" y="1251.59164" id="svg_399" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">重新调整为最大堆</text>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="224.75124" cy="1378.04624" id="svg_480" rx="22" ry="22"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="104.75124" cy="1378.04624" id="svg_481" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="194.75124" cy="1448.04624" id="svg_482" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="44.75124" cy="1448.04624" id="svg_483" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="134.75124" cy="1448.04624" id="svg_484" rx="22" ry="22"/>
  <ellipse fill="none" stroke="#000" stroke-width="1.5" cx="164.75124" cy="1318.04624" id="svg_485" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="89.25137" y="1386.13551" id="svg_486" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="168.75124" y="1419.04624" id="svg_487" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="126.75124" y="1302.04624" id="svg_488" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="81.75124" y="1350.04624" id="svg_489" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="217.75124" y="1348.04624" id="svg_490" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="16.75124" y="1423.04624" id="svg_491" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="140.75124" y="1418.04624" id="svg_492" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="147.72498" y1="1333.4041" x2="120.72498" y2="1362.4041" id="svg_493" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="217.72498" y1="1399.4041" x2="190.72498" y2="1428.4041" id="svg_494" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="182.72498" y1="1334.4041" x2="209.72498" y2="1362.4041" id="svg_495" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="112.72498" y1="1394.4041" x2="139.72498" y2="1422.4041" id="svg_496" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="87.72498" y1="1393.4041" x2="60.72498" y2="1422.4041" id="svg_497" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="212.46553" y="1387.86443" id="svg_498" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="181.21711" y="1455.88703" id="svg_499" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="120.87621" y="1456.67118" id="svg_500" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="149.44764" y="1322.56421" id="svg_501" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_502" y2="1525.70994" x2="50.48049" y1="1494.9041" x1="50.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_503" y2="1525.70994" x2="80.48049" y1="1494.9041" x1="80.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_504" y2="1525.70994" x2="110.48049" y1="1494.9041" x1="110.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_505" y2="1525.70994" x2="140.48049" y1="1494.9041" x1="140.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_506" y2="1525.70994" x2="170.48049" y1="1494.9041" x1="170.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_507" y2="1525.70994" x2="200.48049" y1="1494.9041" x1="200.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_508" y2="1525.70994" x2="230.48049" y1="1494.9041" x1="230.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_509" y2="1495.9041" x2="228.49167" y1="1495.9041" x1="49.48049" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_510" y2="1525.9041" x2="228.49167" y1="1525.9041" x1="49.48049" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_511" y="1517.04696" x="207.33764" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_512" y="1516.1541" x="178.85541" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_513" y="1514.9041" x="120.90906" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_514" y="1516.24339" x="146.17698" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_515" y="1516.24339" x="57.96274" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_516" y="1516.95767" x="87.42684" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="331.35542" y="1547.62152" id="svg_517" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">交换1号与2号记录，</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="336.0712" y="1571.08739" id="svg_518" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">所有记录就位</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="28.50119" y="1456.93916" id="svg_519" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="484.75124" cy="1378.04624" id="svg_520" rx="22" ry="22"/>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="364.75124" cy="1378.04624" id="svg_521" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="454.75124" cy="1448.04624" id="svg_522" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="304.75124" cy="1448.04624" id="svg_523" rx="22" ry="22"/>
  <ellipse fill="#bfbf00" stroke="#000" stroke-width="1.5" cx="394.75124" cy="1448.04624" id="svg_524" rx="22" ry="22"/>
  <ellipse fill="#aad4ff" stroke="#000" stroke-width="1.5" cx="424.75124" cy="1318.04624" id="svg_525" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="410.67995" y="1326.84979" id="svg_526" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="428.75124" y="1419.04624" id="svg_527" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="386.75124" y="1302.04624" id="svg_528" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="341.75124" y="1350.04624" id="svg_529" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="477.75124" y="1348.04624" id="svg_530" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="276.75124" y="1423.04624" id="svg_531" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="400.75124" y="1418.04624" id="svg_532" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="407.72498" y1="1333.4041" x2="380.72498" y2="1362.4041" id="svg_533" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="477.72498" y1="1399.4041" x2="450.72498" y2="1428.4041" id="svg_534" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="442.72498" y1="1334.4041" x2="469.72498" y2="1362.4041" id="svg_535" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="372.72498" y1="1394.4041" x2="399.72498" y2="1422.4041" id="svg_536" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" x1="347.72498" y1="1393.4041" x2="320.72498" y2="1422.4041" id="svg_537" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="471.75125" y="1387.86443" id="svg_538" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="441.21711" y="1455.88703" id="svg_539" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="380.87621" y="1456.67118" id="svg_540" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="348.01907" y="1386.84993" id="svg_541" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_542" y2="1525.70994" x2="310.48049" y1="1494.9041" x1="310.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_543" y2="1525.70994" x2="340.48049" y1="1494.9041" x1="340.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_544" y2="1525.70994" x2="370.48049" y1="1494.9041" x1="370.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_545" y2="1525.70994" x2="400.48049" y1="1494.9041" x1="400.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_546" y2="1525.70994" x2="430.48049" y1="1494.9041" x1="430.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_547" y2="1525.70994" x2="460.48049" y1="1494.9041" x1="460.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_548" y2="1525.70994" x2="490.48049" y1="1494.9041" x1="490.48049" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_549" y2="1495.9041" x2="488.49167" y1="1495.9041" x1="309.48049" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_550" y2="1525.9041" x2="488.49167" y1="1525.9041" x1="309.48049" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_551" y="1516.33267" x="468.05192" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_552" y="1516.1541" x="438.85541" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_553" y="1516.33267" x="378.05192" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">21</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_554" y="1515.5291" x="408.31983" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff0000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_555" y="1516.24339" x="347.24846" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff5656">16</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_556" y="1515.5291" x="318.14113" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#ff5656">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="288.50117" y="1457.65344" id="svg_557" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <text style="cursor: move;" fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="63.94819" y="1547.55658" id="svg_558" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">从1号到2号</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" x="67.69757" y="1568.40883" id="svg_559" font-size="14" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">重新调整为最大堆</text>
</svg>

* 7) 性能分析
	* 对于长度为n的序列，其对应的完全二叉树的深度为$$k(2^{k-1}\le n\le2^k)(即：k = log_2n)$$  
	* 对深度为k的堆，筛选算法中进行的关键比较次数至多为2(k-1)次
	* 堆排序时间主要耗费在建初始堆和调整建新堆（筛选）上
	* 建初始堆最多做n/2次筛选
	* 对长度为n的序列，排序最多需要做n-1次调整建新堆（筛选）。建初始堆时，需要n/2次筛选
	* 因此共需要O(n*k)量级的时间
	* $$k = log_2n$$
	* 堆排序时间复杂度为$$O(n\log_2n)$$  
	* 堆排序是一种不稳定的排序方法 

---

### **第五节 归并排序**

####  一、归并   

*  归并是将两个或两个以上的有序表合并成一个新的有序表的操作过程。

####  二、两路归并  
 
	typedef int SortData;
	void merge(SortData InitList[], SortData mergedList[], int  left,int mid, int right){
		int i = left,j=mid+1,k=left;
		while(i<=mid && j<= right)  //两两比较将较小的并入
			if(InitList[i] <= InitList[j]){megedList[k] = InitList[i];i++;k++;}
			else {mergedList[k] =InitList[j];j++;k++;}
		while(i<=mid){mergedList[k] = InitList[i];i++;k++;}//将mid前剩余的并入
		while(j<=mid){mergedList[k] = InitList[j];j++;k++;}//将mid后剩余的并入
	}

*  性能分析
	* 假设待归并的两个有序表长度分别为m和L，则两路归并后，新的有序表长度为m+L
	* 两路归并操作至多只需要m+L次移位和m+L次比较
	* 因此两路归并的时间复杂度为O(m+L)

####  三、2路——归并排序  

*  将n个记录堪称是n个有序序列
* 将前后相邻的两个有序序列归并为一个有序序列（两路归并）
* 重复做两路归并操作，直到只有一个有序序列为止
* 例子

<svg width="383" height="282" >
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="42.52626" cy="67.64214" id="svg_1" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="75.64214" id="svg_2" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="102.52626" cy="67.64214" id="svg_5" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="75.64214" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="162.52626" cy="67.64214" id="svg_7" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="149.52626" y="75.64214" id="svg_8" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="222.52626" cy="67.64214" id="svg_9" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="207.52626" y="75.64214" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="67.64214" id="svg_11" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="270.52626" y="75.64214" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="67.64214" id="svg_13" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="75.64214" id="svg_14" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="35.64214" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="35.64214" id="svg_16" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="35.64214" id="svg_17" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="210.52626" y="35.64214" id="svg_18" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="270.52626" y="35.64214" id="svg_19" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="35.64214" id="svg_20" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="42.52626" cy="127.64214" id="svg_32" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="135.64214" id="svg_33" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="102.52626" cy="127.64214" id="svg_34" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="135.64214" id="svg_35" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#7fff00" stroke="#000" stroke-width="1.5" cx="162.52626" cy="127.64214" id="svg_36" rx="22" ry="22"/>
  <ellipse fill="#7fff00" stroke="#000" stroke-width="1.5" cx="222.52626" cy="127.64214" id="svg_38" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="147.52626" y="135.64214" id="svg_40" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#007fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="127.64214" id="svg_41" rx="22" ry="22"/>
  <ellipse fill="#007fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="127.64214" id="svg_43" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="270.52626" y="135.64214" id="svg_44" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="135.64214" id="svg_37" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="135.64214" id="svg_42" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="42.52626" cy="187.64214" id="svg_45" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="195.64214" id="svg_46" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="102.52626" cy="187.64214" id="svg_47" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="195.64214" id="svg_48" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="162.52626" cy="187.64214" id="svg_49" rx="22" ry="22"/>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="222.52626" cy="187.64214" id="svg_50" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="147.52626" y="195.64214" id="svg_51" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#007fff" stroke="#000" stroke-width="1.5" cx="282.52626" cy="187.64214" id="svg_52" rx="22" ry="22"/>
  <ellipse fill="#007fff" stroke="#000" stroke-width="1.5" cx="342.52626" cy="187.64214" id="svg_53" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="270.52626" y="195.64214" id="svg_54" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="209.52626" y="195.64214" id="svg_55" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="330.52626" y="195.64214" id="svg_56" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="162.52626" cy="247.64214" id="svg_57" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="150.52626" y="255.64214" id="svg_58" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">21</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="222.52626" cy="247.64214" id="svg_59" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="210.52626" y="255.64214" id="svg_60" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="282.52626" cy="247.64214" id="svg_61" rx="22" ry="22"/>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="342.52626" cy="247.64214" id="svg_62" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="267.52626" y="255.64214" id="svg_63" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">25*</text>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="42.52626" cy="247.64214" id="svg_65" rx="22" ry="22"/>
  <ellipse fill="#ff0000" stroke="#000" stroke-width="1.5" cx="102.52626" cy="247.64214" id="svg_66" rx="22" ry="22"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.52626" y="255.64214" id="svg_67" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">08</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="329.52626" y="255.64214" id="svg_68" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">49</text>
  <text fill="#000000" stroke="#000" stroke-width="0" x="90.52626" y="255.64214" id="svg_69" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">16</text>
</svg>

*  性能分析
	* 如果待排序的记录为n个，则需要做$$log_2n$$趟两路归并排序  
	* 每趟两路归并排序的时间复杂度为O(n) 
	* 因此2路——归并排序的时间复杂度为$$O(n\log_2n)$$
	* 归并排序是一种稳定的排序方法

---

### **第六节 基数排序**

####  一、多关键字的排序   

*  例:对52张扑克牌按以下次序排序：
♣2<♣3<......<♣A<♢2<♢3<......<♢A<♥2<♥3<......<♥A<♤2<♤3<......<♤A
* 两个关键字：
	* 花色（♣<♢<♥<♤）
	* 面值 （2<3<...<A）
* 并且“花色”地位高于“面值”  
*  最低位优先法LSD
	* 从最低位关键字kd起进行排序，
	* 然后再对高一位的关键字排序，......
	* 依次重复，直至对最高位关键字k1排序后，便成为一个有序序列
*  例子

<svg width="450" height="225">
  <ellipse ry="22" rx="22" id="svg_1" cy="67.64214" cx="42.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="75.64214" x="30.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_5" cy="67.64214" cx="102.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="75.64214" x="90.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_7" cy="67.64214" cx="162.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="75.64214" x="149.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_9" cy="67.64214" cx="222.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="75.64214" x="207.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_11" cy="67.64214" cx="282.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="75.64214" x="270.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_13" cy="67.64214" cx="342.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="75.64214" x="330.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_15" y="35.64214" x="30.52626" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="35.64214" x="90.52626" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_17" y="35.64214" x="150.52626" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_18" y="35.64214" x="210.52626" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_19" y="35.64214" x="270.52626" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_20" y="35.64214" x="330.52626" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <ellipse ry="22" rx="22" id="svg_32" cy="127.64214" cx="42.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_33" y="135.64214" x="30.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_34" cy="127.64214" cx="102.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_35" y="135.64214" x="90.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_36" cy="127.64214" cx="162.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="22" rx="22" id="svg_38" cy="127.64214" cx="222.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_39" y="135.64214" x="147.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <ellipse ry="22" rx="22" id="svg_40" cy="127.64214" cx="282.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_41" y="135.64214" x="210.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_42" cy="127.64214" cx="342.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_43" y="135.64214" x="270.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_37" y="135.64214" x="329.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <ellipse ry="22" rx="22" id="svg_44" cy="187.64214" cx="42.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="22" rx="22" id="svg_46" cy="187.64214" cx="102.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <ellipse ry="22" rx="22" id="svg_48" cy="187.64214" cx="162.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_45" y="194.53103" x="150.52626" stroke-width="0" stroke="#000" fill="#000000">21</text>
  <ellipse ry="22" rx="22" id="svg_49" cy="187.64214" cx="222.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_47" y="195.08659" x="210.52626" stroke-width="0" stroke="#000" fill="#000000">25</text>
  <ellipse ry="22" rx="22" id="svg_51" cy="187.64214" cx="282.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_50" y="195.64214" x="267.52626" stroke-width="0" stroke="#000" fill="#000000">25*</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_52" y="195.64214" x="90.52626" stroke-width="0" stroke="#000" fill="#000000">16</text>
  <ellipse ry="22" rx="22" id="svg_53" cy="187.64214" cx="342.52626" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_54" y="195.64214" x="30.52626" stroke-width="0" stroke="#000" fill="#000000">08</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_55" y="195.64214" x="329.52626" stroke-width="0" stroke="#000" fill="#000000">49</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_56" y="136.83334" x="385.27666" stroke-width="0" stroke="#000" fill="#000000">个位</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_57" y="194.05547" x="381.94767" stroke-width="0" stroke="#000" fill="#000000">十位</text>
</svg>

####  二、链式基数排序  

* 1）定义
	*  基数排序：借助“分配”和“收集”对单逻辑关键字进行排序的一种方法
	*  链式技术排序方法：用链表做存储结构的基数排序
	*  设置10个队列，f[i]和e[i]分别为第i个队列的头指针和尾指针
	*  第i趟分配：根据第i位关键字的值，改变记录的指针，将链表中记录按次序分配至10个链表队列中（采用队尾插入法）；每个队列中记录关键字的第i位关键字相同
	*  第i趟收集：改变所有非空队列的队尾记录的指针域，令其指向下一个非空队列的队头记录，重新将10个队列链成一个链表
	*  从最低位至最高位，逐位执行上述两步操作，最后得到一个有序序列

<svg width="690" height="750" >
  <rect stroke="#000" id="svg_1" height="17.13125" width="35.33319" y="24.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_2" y="38.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_3" y="38.83115" x="137.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="38.83376" x="79.51575" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_26" height="17.13125" width="35.33319" y="24.47515" x="165.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_27" y="38.15186" x="172.78861" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_28" y="38.83115" x="197.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_35" height="17.13125" width="35.33319" y="24.47515" x="225.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_36" y="38.15186" x="232.78861" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_37" y="38.83115" x="257.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_38" height="17.13125" width="35.33319" y="24.47515" x="285.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_39" y="38.15186" x="292.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_40" y="38.83115" x="317.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_41" height="17.13125" width="35.33319" y="24.47515" x="345.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_42" y="38.15186" x="352.78861" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_43" y="38.83115" x="377.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_44" height="17.13125" width="35.33319" y="24.47515" x="405.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_45" y="38.15186" x="412.78861" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_46" y="38.83115" x="437.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_47" height="17.13125" width="35.33319" y="24.47515" x="465.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_48" y="38.15186" x="472.78861" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_49" y="38.83115" x="497.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_50" height="17.13125" width="35.33319" y="24.47515" x="525.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_51" y="38.15186" x="532.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_52" y="38.83115" x="557.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_53" height="17.13125" width="35.33319" y="24.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_54" y="38.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_55" y="38.83115" x="617.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_56" height="17.13125" width="35.33319" y="24.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_57" y="38.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_59" y="94.99962" x="111.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[0]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_60" y="224.519" x="111.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[0]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_61" y="95.47581" x="172.47523" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[1]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_62" y="224.04281" x="171.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[1]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_63" y="94.99962" x="231.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[2]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_64" y="224.519" x="231.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[2]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_65" y="94.99962" x="291.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[3]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_66" y="224.519" x="291.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[3]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_67" y="94.99962" x="351.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[4]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_68" y="224.519" x="351.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[4]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_69" y="94.99962" x="411.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[5]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_70" y="224.519" x="411.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[5]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_71" y="94.99962" x="471.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[6]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_72" y="224.519" x="471.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[6]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_73" y="94.99962" x="531.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[7]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_74" y="224.519" x="531.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[7]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_75" y="94.99962" x="591.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[8]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_76" y="224.519" x="591.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[8]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_77" y="94.99962" x="651.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[9]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_78" y="224.519" x="651.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[9]</text>
  <rect stroke="#000" id="svg_79" height="17.13125" width="35.33319" y="184.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_80" y="268.1519" x="412.20026" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <rect stroke="#000" id="svg_81" height="17.13125" width="35.33319" y="184.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_82" y="268.1519" x="530.4356" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <rect stroke="#000" id="svg_83" height="17.13125" width="35.33319" y="184.47515" x="285.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_84" y="267.56367" x="171.61207" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <rect stroke="#000" id="svg_85" height="17.13125" width="35.33319" y="184.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_86" y="268.74014" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <rect stroke="#000" id="svg_87" height="17.13125" width="35.33319" y="154.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_88" y="268.74015" x="592.78857" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <rect stroke="#000" id="svg_89" height="17.13125" width="35.33319" y="184.47515" x="345.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_90" y="268.1519" x="292.78857" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <rect stroke="#000" id="svg_91" height="17.13125" width="35.33319" y="184.47515" x="405.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_92" y="268.1519" x="352.20034" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <rect stroke="#000" id="svg_93" height="17.13125" width="35.33319" y="124.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_94" y="267.5637" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <rect stroke="#000" id="svg_95" height="17.13125" width="35.33319" y="154.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_96" y="269.91663" x="473.965" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <rect stroke="#000" id="svg_97" height="17.13125" width="35.33319" y="154.47515" x="285.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_98" y="269.32839" x="232.78857" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_99" y="210.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_101" y="210.88235" x="300.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_102" y="210.88235" x="360.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_103" y="210.88235" x="420.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_104" y="210.88235" x="600.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_105" y="210.88235" x="660.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_106" y="180.88235" x="660.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_107" y="150.88235" x="660.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_108" y="180.88235" x="600.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_109" y="180.88235" x="300.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_110" y2="51.99207" x2="63.76455" y1="20.88225" x1="63.76455" fill-opacity="null" stroke-opacity="null" stroke="#000" fill="none"/>
  <line stroke="#000" stroke-linecap="null" stroke-linejoin="null" id="svg_111" y2="227.28624" x2="63.76456" y1="80.88224" x1="63.76456" fill-opacity="null" stroke-opacity="null" fill="none"/>
  <rect stroke="#000" id="svg_112" height="17.13125" width="35.33319" y="254.47515" x="105.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_114" y="268.83115" x="137.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_115" y="268.83376" x="79.51575" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_116" height="17.13125" width="35.33319" y="254.47515" x="165.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_118" y="268.83115" x="197.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_119" height="17.13125" width="35.33319" y="254.47515" x="225.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_121" y="268.83115" x="257.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_122" height="17.13125" width="35.33319" y="254.47515" x="285.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_124" y="268.83115" x="317.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_125" height="17.13125" width="35.33319" y="254.47515" x="345.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_127" y="268.83115" x="377.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_128" height="17.13125" width="35.33319" y="254.47515" x="405.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_130" y="268.83115" x="437.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_131" height="17.13125" width="35.33319" y="254.47515" x="465.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_133" y="268.83115" x="497.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_134" height="17.13125" width="35.33319" y="254.47515" x="525.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_136" y="268.83115" x="557.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_137" height="17.13125" width="35.33319" y="254.47515" x="585.63712" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_139" y="268.83115" x="617.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_140" height="17.13125" width="35.33319" y="254.47515" x="645.63712" stroke-width="1.5" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_142" y2="281.99207" x2="63.76455" y1="250.88225" x1="63.76455" fill-opacity="null" stroke-opacity="null" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_143" y="198.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_144" y="198.15186" x="292.78861" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_145" y="168.15186" x="292.78861" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_146" y="198.15186" x="352.78861" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_147" y="198.15186" x="412.78861" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_148" y="197.56363" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_149" y="168.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_150" y="198.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_151" y="168.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_152" y="138.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_153" y="324.99962" x="111.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[0]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_154" y="454.519" x="111.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[0]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_155" y="325.47581" x="172.47523" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[1]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_156" y="454.04281" x="171.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[1]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_157" y="324.99962" x="231.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[2]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_158" y="454.519" x="231.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[2]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_159" y="324.99962" x="291.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[3]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_160" y="454.519" x="291.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[3]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_161" y="324.99962" x="351.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[4]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_162" y="454.519" x="351.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[4]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_163" y="324.99962" x="411.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[5]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_164" y="454.519" x="411.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[5]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_165" y="324.99962" x="471.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[6]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_166" y="454.519" x="471.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[6]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_167" y="324.99962" x="531.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[7]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_168" y="454.519" x="531.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[7]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_169" y="324.99962" x="591.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[8]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_170" y="454.519" x="591.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[8]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_171" y="324.99962" x="651.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[9]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_172" y="454.519" x="651.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[9]</text>
  <rect stroke="#000" id="svg_173" height="17.13125" width="35.33319" y="414.47515" x="525.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_174" height="17.13125" width="35.33319" y="354.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_175" height="17.13125" width="35.33319" y="414.47515" x="465.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_176" height="17.13125" width="35.33319" y="414.47515" x="285.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_177" height="17.13125" width="35.33319" y="354.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_178" height="17.13125" width="35.33319" y="384.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_179" height="17.13125" width="35.33319" y="414.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_180" height="17.13125" width="35.33319" y="384.47515" x="465.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_181" height="17.13125" width="35.33319" y="384.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_182" height="17.13125" width="35.33319" y="414.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_183" y="440.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_184" y="440.88235" x="300.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_185" y="410.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_186" y="440.88235" x="540.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_187" y="440.88235" x="600.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_188" y="440.88235" x="480.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_189" y="410.88235" x="600.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_190" y="380.88235" x="600.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_191" y="410.88235" x="480.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_192" y="380.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <line stroke="#000" stroke-linecap="null" stroke-linejoin="null" id="svg_193" y2="457.28624" x2="63.76456" y1="310.88224" x1="63.76456" fill-opacity="null" stroke-opacity="null" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_194" y="428.15186" x="292.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_195" y="428.15186" x="472.78861" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_196" y="428.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_197" y="398.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_198" y="428.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_199" y="427.56363" x="532.78861" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_200" y="398.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_201" y="368.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_202" y="368.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_203" y="398.15186" x="472.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_215" y="498.83115" x="137.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_216" y="498.83376" x="79.51575" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_218" y="498.83115" x="197.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_220" y="498.83115" x="257.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_222" y="498.83115" x="317.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_224" y="498.83115" x="377.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_226" y="498.83115" x="437.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_228" y="498.83115" x="497.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_230" y="498.83115" x="557.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_232" y="498.83115" x="617.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_234" y2="511.99207" x2="63.76455" y1="480.88225" x1="63.76455" fill-opacity="null" stroke-opacity="null" stroke="#000" fill="none"/>
  <rect stroke="#000" id="svg_237" height="17.13125" width="35.33319" y="484.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_238" y="498.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <rect stroke="#000" id="svg_239" height="17.13125" width="35.33319" y="484.47515" x="165.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_240" y="498.15186" x="172.78861" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <rect stroke="#000" id="svg_241" height="17.13125" width="35.33319" y="484.47515" x="225.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_242" y="498.15186" x="232.78861" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <rect stroke="#000" id="svg_243" height="17.13125" width="35.33319" y="484.47515" x="285.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_244" y="498.15186" x="292.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <rect stroke="#000" id="svg_246" height="17.13125" width="35.33319" y="484.47515" x="345.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_247" y="498.15186" x="352.78861" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <rect stroke="#000" id="svg_248" height="17.13125" width="35.33319" y="484.47515" x="405.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_249" y="498.15186" x="412.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <rect stroke="#000" id="svg_250" height="17.13125" width="35.33319" y="484.47515" x="465.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_251" y="497.56363" x="472.78861" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <rect stroke="#000" id="svg_253" height="17.13125" width="35.33319" y="484.47515" x="525.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_254" y="498.15186" x="532.78861" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <rect stroke="#000" id="svg_255" height="17.13125" width="35.33319" y="484.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_256" y="498.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <rect stroke="#000" id="svg_257" height="17.13125" width="35.33319" y="484.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_258" y="498.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_259" y="544.99962" x="111.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[0]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_260" y="674.519" x="111.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[0]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_261" y="545.47581" x="172.47523" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[1]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_262" y="674.04281" x="171.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[1]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_263" y="544.99962" x="231.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[2]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_264" y="674.519" x="231.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[2]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_265" y="544.99962" x="291.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[3]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_266" y="674.519" x="291.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[3]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_267" y="544.99962" x="351.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[4]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_268" y="674.519" x="351.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[4]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_269" y="544.99962" x="411.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[5]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_270" y="674.519" x="411.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[5]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_271" y="544.99962" x="471.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[6]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_272" y="674.519" x="471.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[6]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_273" y="544.99962" x="531.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[7]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_274" y="674.519" x="531.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[7]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_275" y="544.99962" x="591.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[8]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_276" y="674.519" x="591.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[8]</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_277" y="544.99962" x="651.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">e[9]</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_278" y="674.519" x="651.99904" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">f[9]</text>
  <rect stroke="#000" id="svg_279" height="17.13125" width="35.33319" y="604.47515" x="225.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_280" height="17.13125" width="35.33319" y="634.47515" x="165.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_281" height="17.13125" width="35.33319" y="604.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_282" height="17.13125" width="35.33319" y="634.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_283" height="17.13125" width="35.33319" y="604.47515" x="405.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_284" height="17.13125" width="35.33319" y="604.47515" x="165.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_285" height="17.13125" width="35.33319" y="634.47515" x="405.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_286" height="17.13125" width="35.33319" y="634.47515" x="225.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_287" height="17.13125" width="35.33319" y="634.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_288" height="17.13125" width="35.33319" y="574.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_289" y="660.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_290" y="660.88235" x="180.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_291" y="630.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_292" y="660.88235" x="240.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_293" y="660.88235" x="660.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_294" y="660.88235" x="420.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_295" y="630.88235" x="180.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_296" y="630.88235" x="240.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_297" y="630.88235" x="420.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_298" y="600.88235" x="120.23513" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">↑</text>
  <line stroke="#000" stroke-linecap="null" stroke-linejoin="null" id="svg_299" y2="677.28624" x2="63.76456" y1="530.88224" x1="63.76456" fill-opacity="null" stroke-opacity="null" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_300" y="648.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_301" y="618.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_302" y="588.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_303" y="618.15186" x="172.78861" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_304" y="648.15186" x="412.78861" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_305" y="617.56363" x="232.78861" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_306" y="648.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_307" y="648.15186" x="172.78861" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_308" y="618.15186" x="412.78861" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_309" y="648.15186" x="232.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_310" y="718.83115" x="137.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_311" y="718.83376" x="79.51575" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_320" y2="731.99207" x2="63.76455" y1="700.88225" x1="63.76455" fill-opacity="null" stroke-opacity="null" stroke="#000" fill="none"/>
  <rect stroke="#000" id="svg_321" height="17.13125" width="35.33319" y="704.47515" x="105.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_341" y="718.15186" x="112.78861" stroke-width="0" stroke="#000" fill="#000000">008</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_342" y="718.83115" x="197.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_343" y="718.83115" x="257.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_344" y="718.83115" x="317.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_345" y="718.83115" x="377.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_346" y="718.83115" x="437.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_347" y="718.83115" x="497.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_348" y="718.83115" x="557.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_349" y="718.83115" x="617.51573" stroke-width="0" stroke="#000" fill="#000000">→</text>
  <rect stroke="#000" id="svg_351" height="17.13125" width="35.33319" y="704.47515" x="165.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_352" y="718.15186" x="172.78861" stroke-width="0" stroke="#000" fill="#000000">063</text>
  <rect stroke="#000" id="svg_353" height="17.13125" width="35.33319" y="704.47515" x="225.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_354" y="718.15186" x="232.78861" stroke-width="0" stroke="#000" fill="#000000">083</text>
  <rect stroke="#000" id="svg_355" height="17.13125" width="35.33319" y="704.47515" x="275.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_356" height="17.13125" width="35.33319" y="704.47515" x="345.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_357" y="718.15186" x="352.78861" stroke-width="0" stroke="#000" fill="#000000">184</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_358" y="718.15186" x="282.78861" stroke-width="0" stroke="#000" fill="#000000">109</text>
  <rect stroke="#000" id="svg_361" height="17.13125" width="35.33319" y="704.47515" x="465.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_362" height="17.13125" width="35.33319" y="704.47515" x="405.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_363" y="717.56363" x="472.78861" stroke-width="0" stroke="#000" fill="#000000">278</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_364" y="718.15186" x="412.78861" stroke-width="0" stroke="#000" fill="#000000">269</text>
  <rect stroke="#000" id="svg_365" height="17.13125" width="35.33319" y="704.47515" x="585.63712" stroke-width="1.5" fill="#fff"/>
  <rect stroke="#000" id="svg_366" height="17.13125" width="35.33319" y="704.47515" x="525.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_367" y="718.15186" x="532.78861" stroke-width="0" stroke="#000" fill="#000000">505</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_368" y="718.15186" x="592.78861" stroke-width="0" stroke="#000" fill="#000000">589</text>
  <rect stroke="#000" id="svg_369" height="17.13125" width="35.33319" y="704.47515" x="645.63712" stroke-width="1.5" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="14" id="svg_370" y="718.15186" x="652.78861" stroke-width="0" stroke="#000" fill="#000000">930</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_371" y="46.15283" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_372" y="156.15283" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_373" y="275.38361" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_374" y="385.38361" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_375" y="505.38361" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_376" y="615.38361" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_377" y="725.38361" x="27.69931" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">6</text>
</svg>

* 2) 性能分析
	* 若每个关键字有d位，关键字的基数为radix
	* 需要重复执行d趟“分配与“收集”
	* 每趟对n个对象进行“分配”，对radix个队列进行“收集”
	* 总时间复杂度为O(d(n+radix))
	* 若基数radix相同，对于对象较多而关键字位数较少的情况，使用链式基数排序较好
	* 基数排序需要增加n+2radix个附加链接指针
	* 基数排序是稳定的排序方法 

---

### **第七节 各种排序方法比较**

|排序方法|平均时间 ----|最坏情况---------|辅助存储---|稳定排序|适合情况|
|-
|插入排序|$$O(n^2)$$|$$O(n^2)$$|$$O(1)$$|稳定|记录数较少|
|希尔排序|$$O(n(\log_2n)^2)$$|$$O(n^2)$$|$$O(1)$$|不稳定|不太多|
|起泡排序|$$O(n^2)$$|$$O(n^2)$$|$$O(1)$$|稳定|不太多|
|快速排序|$$O(n\log_2n)$$|$$O(n^2)$$|$$O(\log_2n)$$|不稳定|较多|
|简单选择排序|$$O(n^2)$$|$$O(n^2)$$|$$O(1)$$|不稳定|不太多|
|堆排序|$$O(n\log_2n)$$|$$O(n\log_2n)$$|$$O(1)$$|不稳定|记录多|
|归并排序|$$O(n\log_2n)$$|$$O(n\log_2n)$$|$$O(n)$$|稳定|都可以|
|基数排序|$$O(d(n+rd))$$|$$O(d(n+rd))$$|$$O(rd)$$|稳定|关键字位数少|
