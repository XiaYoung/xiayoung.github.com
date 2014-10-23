---
layout : post
category : mse
tags : [Data structure]
--- 
##第七章 图 

### **第一节 图的定义与术语**  

####  一、图的定义（Graph）  

*  图是由顶点集合(vertex)及顶点间的关系集合组成的一种数据结构：
	* Graph = （V, E）
	* 其中 $$V = \{x | x \in 数据对象\}$$ 是顶点的有穷非空集合，所有顶点的地位完全相同
	* E 是顶点之间关系的有穷集合，包括
		* $$E1 = \{(x, y) | x. y \in V\}$$ 边的集合
		* $$E2 = \{<x, y> | x. y \in V\}$$ 弧的集合

####  二、无向图（Undigraph）  

*  用(x,y)表示两个顶点x,y之间的一条边(edge)
*  N = {V, E}, 
	* V = {0, 1, 2, 3, 4, 5}, 
	* E = {(0,1), (0,4), (0,5), (1,2), (1,3), (1,5), (2,3), (3,4), (3,5), (4,5) }

<svg width="375" height="250" >
  <ellipse ry="19.5" rx="19.5" id="svg_1" cy="129.74829" cx="340.05551" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="138.24829" x="333.55551" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <ellipse ry="19.5" rx="19.5" id="svg_3" cy="129.74829" cx="28" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="138.24829" x="19.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <ellipse ry="19.5" rx="19.5" id="svg_5" cy="31.5" cx="239" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="40" x="230.5" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <ellipse ry="19.5" rx="19.5" id="svg_7" cy="31.5" cx="104" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="40" x="95.5" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <ellipse ry="19.5" rx="19.5" id="svg_9" cy="220.5" cx="243" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="229" x="234.5" stroke-width="0" fill="#000000">4</text>
  <ellipse ry="19.5" rx="19.5" id="svg_11" cy="220.5" cx="108" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="229" x="99.5" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_13" y2="29.5" x2="220.52105" y1="29.5" x1="125.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_14" y2="220.5" x2="223.68929" y1="220.5" x1="128.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_15" y2="202.5298" x2="104.5" y1="51.5" x1="104.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_16" y2="203.76621" x2="240.5" y1="51.5" x1="240.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_17" y2="123.5" x2="318.5" y1="47.5" x1="119.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_18" y2="135.5" x2="320.5" y1="210.5" x1="126.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_19" y2="114.5" x2="326.5" y1="43.5" x1="256.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_20" y2="148.5" x2="329.5" y1="211.5" x1="262.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_21" y2="112.5" x2="42.5" y1="46.5" x1="93.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_22" y2="208.5" x2="91.5" y1="148.5" x1="33.5" stroke-width="1.5" stroke="#000" fill="none"/>
</svg>

*  如果无向图有n(b-1)/2条边，则称为无向完全图

<svg width="375" height="250" >
  <ellipse ry="19.5" rx="19.5" id="svg_1" cy="129.74829" cx="340.05551" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="138.24829" x="333.55551" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <ellipse ry="19.5" rx="19.5" id="svg_3" cy="129.74829" cx="28" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="138.24829" x="19.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <ellipse ry="19.5" rx="19.5" id="svg_5" cy="31.5" cx="239" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="40" x="230.5" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <ellipse ry="19.5" rx="19.5" id="svg_7" cy="31.5" cx="104" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="40" x="95.5" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <ellipse ry="19.5" rx="19.5" id="svg_9" cy="220.5" cx="243" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="229" x="234.5" stroke-width="0" fill="#000000">4</text>
  <ellipse ry="19.5" rx="19.5" id="svg_11" cy="220.5" cx="108" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="229" x="99.5" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_13" y2="29.5" x2="220.52105" y1="29.5" x1="125.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_14" y2="220.5" x2="223.68929" y1="220.5" x1="128.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_15" y2="202.5298" x2="104.5" y1="51.5" x1="104.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_16" y2="203.76621" x2="240.5" y1="51.5" x1="240.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_17" y2="123.5" x2="318.5" y1="47.5" x1="119.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_18" y2="135.5" x2="320.5" y1="210.5" x1="126.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_19" y2="114.5" x2="326.5" y1="43.5" x1="256.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_20" y2="148.5" x2="329.5" y1="211.5" x1="262.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_21" y2="112.5" x2="42.5" y1="46.5" x1="93.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_22" y2="208.5" x2="91.5" y1="148.5" x1="33.5" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_23" y2="41.5" x2="219" y1="125.5" x1="49" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_25" y2="129.5" x2="318" y1="133.5" x1="49" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_26" y2="202.5" x2="232" y1="51.5" x1="114" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_27" y2="211.5" x2="227" y1="140.5" x1="46" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_28" y2="49.5" x2="227" y1="200.5" x1="120" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
</svg>

*  邻接点：如果$$(x, y) \in E$$，称x, y互为邻接点，即x, y相邻接
*  依附：边(x, y)依附于顶点x, y
*  相关联：边(x, y)与x, y相关联
*  顶点的度：和顶点相关联的边的数目，记为TD(x)

####  三、有向图（Digraph）  

*  用`<x, y>`表示从x 到y 的一条弧(Arc), 且称 x 为弧尾， y为弧头
*  N = {V, E}
	* V={0, 1, 2, 3, 4}
	* E={<0, 1>, <0, 3>, <0, 4>, <1, 2>, <2, 4>, <3, 2>}

<svg width="282" height="250" >
  <ellipse ry="19.5" rx="19.5" id="svg_3" cy="211.74829" cx="90" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="220.24829" x="81.5" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <ellipse ry="19.5" rx="19.5" id="svg_5" cy="30.5" cx="131" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="39" x="122.5" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <ellipse ry="19.5" rx="19.5" id="svg_7" cy="111.5" cx="39" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_8" y="120" x="30.5" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <ellipse ry="19.5" rx="19.5" id="svg_9" cy="102.5" cx="243" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text stroke="#000" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="111" x="234.5" stroke-width="0" fill="#000000">4</text>
  <ellipse ry="19.5" rx="19.5" id="svg_11" cy="213.5" cx="199" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="222" x="190.5" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_29" y2="101.5" x2="57" y1="47.5" x1="121" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_30" y2="197.5" x2="83" y1="131.5" x1="44" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_31" y2="88.5" x2="226" y1="42.5" x1="151" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_32" y2="194.5" x2="192" y1="51.5" x1="135" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_33" y2="214.5" x2="114" y1="216.5" x1="180" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_34" y2="114.5" x2="226" y1="197.5" x1="105" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_36" y2="94.16722" x2="58.66898" y1="101.50043" x1="56.00236" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_37" y2="101.1671" x2="64.66888" y1="100.83377" x1="57.00235" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_38" y2="186.83222" x2="83.66853" y1="194.49875" x1="82.0019" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_39" y2="193.49877" x2="74.6687" y1="193.49877" x1="78.3353" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_40" y2="209.16516" x2="121.33452" y1="213.49841" x1="112.33469" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_41" y2="219.4983" x2="118.00125" y1="216.49836" x1="112.66801" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_42" y2="187.83221" x2="194.66654" y1="193.8321" x1="193.99988" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_44" y2="193.8321" x2="185.6667" y1="197.16537" x1="192.9999" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_45" y2="119.83343" x2="225.66598" y1="113.50021" x1="226.99929" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_46" y2="113.83354" x2="219.99942" y1="113.83354" x1="225.33265" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_47" y2="81.50079" x2="224.99933" y1="87.834" x1="227.66594" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_48" y2="91.16728" x2="220.66607" y1="90.50062" x1="226.66596" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
</svg>

*  如果有向图有n(n-1)条边，则称为有向完全图

<svg width="188" height="179">
  <ellipse ry="19.5" rx="19.5" id="svg_3" cy="132.74802" cx="156.9998" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="141.24802" x="148.4998" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <ellipse ry="19.5" rx="19.5" id="svg_2" cy="134.74802" cx="31.9998" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_5" y="143.24802" x="23.4998" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <ellipse ry="19.5" rx="19.5" id="svg_6" cy="29.74802" cx="94.9998" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_7" y="38.24802" x="86.4998" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="78.4998" y1="35.49973" x2="26.4998" y2="113.49973" id="svg_12" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="47.4998" y1="119.49973" x2="92.4998" y2="48.49973" id="svg_13" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="113.4998" y1="37.49973" x2="161.4998" y2="113.49973" id="svg_14" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="99.4998" y1="49.49973" x2="140.4998" y2="119.49973" id="svg_15" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="51.4998" y1="133.49973" x2="141.4998" y2="131.49973" id="svg_16" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="44.4998" y1="153.49973" x2="140.4998" y2="151.49973" id="svg_17" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="77.60549" y1="38.75699" x2="70.27217" y2="41.75698" id="svg_18" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="77.60549" y1="46.45394" x2="77.60549" y2="37.12063" id="svg_19" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="45.93891" y1="119.78707" x2="46.60557" y2="112.78709" id="svg_20" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="57.27221" y1="120.45374" x2="48.60557" y2="121.1204" id="svg_22" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="137.93866" y1="131.12037" x2="128.60535" y2="125.78705" id="svg_25" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="137.60532" y1="131.45371" x2="130.27201" y2="138.45369" id="svg_26" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="98.93876" y1="49.1206" x2="97.2721" y2="58.45391" id="svg_27" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="99.93876" y1="50.1206" x2="108.6054" y2="53.78725" id="svg_28" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="161.93859" y1="111.78709" x2="161.93859" y2="102.78712" id="svg_29" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="160.27193" y1="111.45376" x2="153.60528" y2="108.7871" id="svg_30" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="45.60557" y1="153.12031" x2="54.27222" y2="149.12032" id="svg_31" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="45.27224" y1="153.78698" x2="52.93889" y2="159.1203" id="svg_32" stroke-linejoin="null" stroke-linecap="null"/>
</svg>

*  邻接： 如果$$<x, y> \in E$$, 称x邻接到y, 或y邻接自x
*  相关联：弧<x, y>与x, y相关联
*  入度： 以顶点为头的弧的数目，记为 ID(x)
*  出度： 以顶点为尾的弧的数目，记为OD(x)
* 度 ：TD(x) = ID(x) + OD(x)

####  四、网（Network）  

*  网：带权的图称为网
*  权：与图的边或弧相关的数

####  五、路径（Path）  

*  路径：是一个从顶点x到y的顶点序列$$(x, v_{i1}, v_{i2},..., v_{im},y)$$  
*  其中，$$(x, v_{i1}),... (v_{ij-1}, v_{ij}),... (v_{im}, y)$$皆属于E

####  六、回路  

*  回路或环：路径的开始顶点与最后一个顶点相同，即路径中$$(x, v_i1, v_i2, ..., v_im, y), x=y $$  
*  简单路径：路径的顶点序列中，顶点不重复出现

####  七、连通

*  连通：如果顶点x到y有路径，称x和y是连通的
*  连通图：图中所有顶点都连通

####  八、子图  

*  设有两个图 G=（V, E）和 G' = (V', E')。若$$V' \subseteq V$$且$$E' \subseteq E$$，称图G'是图G的子图

####  九、生成树  

*  一个连通图的生成树是一个极小连通子图，它含有图中全部n个顶点，但只有足以构成一棵树的n-1条边

---

### **第二节 图的存储结构**  

####  一、邻接矩阵（Adjacency Matrix）  

*  1）定义
	*  邻接矩阵：记录图中各顶点之间关系的二维数组
	*  对于不带权的图，以1表示两顶点存在边（或弧）（相邻接），以0表示两顶点不邻接，即
	$$A[i][j] = \begin{cases}  1 如果(i, j) \in E 或 <i, j> \in E\\0  其它\end{cases}$$
	*  无向图（图见第一节的二）的邻接矩阵  
	$$\begin{bmatrix} 0 & 1 & 0 & 0 & 1 & 1 \\ 1 & 0 & 1 & 1 & 0 & 1 \\ 0 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 1 \\ 1 & 0 & 0 & 1 & 0 & 1 \\ 1 & 1 & 0 & 1 & 1 & 0 \end{bmatrix}$$  

	* 有向图（第一节的三）的邻接矩阵  
$$\begin{bmatrix} 0 & 1 & 0 & 1 & 1 \\ 0 & 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 \end{bmatrix}$$  

*  2）性质
	* 无向图的邻接矩阵是对称的
	* 其第i行1的个数或第i列1的个数，等于顶点i的度数TD(i)
	* 有向图的邻接矩阵可能是不对称的
	*  其第i行1的个数等于顶点i的出度OD(i), 第j列1的个数等于顶点j的入度ID(j)  
*  3) 网络
	* 在网络中，两个顶点如果不邻接，则被视为距离无穷大；如果邻接，则两顶点之间存在一个距离值（即权值）
	*  $$A[i][j] = \begin{cases}  w_{i, j} 如果(i, j) \in E 或 <i, j> \in E\\\infty   其它\end{cases}$$  
	*  例子，有向网 N= {V, E} V={0, 1, 2, 3, 4}, E = {<0,1,5>, <0,3,7>, <0,4,15>, <1,2,5>, <2,4,1>, <3,2,2>}, E中每个元组的第三个元素表示权。  
	$$\begin{bmatrix} \infty  & 5 & \infty  & 7 & 15 \\ \infty  & \infty  & 5 & \infty  & \infty  \\ \infty  & \infty  & \infty  & \infty  & 1 \\ \infty  & \infty  & 2 & \infty  & \infty  \\ \infty  & \infty  & \infty  & \infty  & \infty  \end{bmatrix}$$   

####  二、邻接表（Adjacency List）  

*  1）定义
	* 邻接表是图的一种链式存储结构
	* 在邻接表中，每个顶点设置一个单链表，其每个结点都是依附于该顶点的边(或以该顶点为尾的弧)
*  2）结点结构
	* 边(弧)的结点结构  adjvex nextrac info
		
			adjvex; //该边(弧)所指向的顶点的位置
			nextarc; // 指向下一条边（弧）指针
			info; // 该边（弧）相关信息的指针或权值
	* 顶点的结点结构 data firstarc
		
			data; // 顶点信息
			firstarc; // 指向第一条依附该顶点的边（弧） 
* 3）无向图（图见第一节的二）

<svg width="437" height="197" >
 <g>
  <rect stroke="#000" id="svg_1" height="182.33325" width="79" y="7.83334" x="12.16666" stroke-width="1.5" fill="#fff"/>
  <line stroke="#000" stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_2" y2="190.54632" x2="60.49999" y1="9.16668" x1="60.49999" stroke-width="1.5" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_8" y2="38.99997" x2="91.40914" y1="38.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_29" y2="68.99997" x2="91.40914" y1="68.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_33" y2="98.99997" x2="91.40914" y1="98.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_34" y2="128.99997" x2="91.40914" y1="128.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_35" y2="158.99997" x2="91.40914" y1="158.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_37" height="23.33334" width="50.00001" y="11.66663" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_38" y2="35.00949" x2="151.84968" y1="11.66663" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_39" y="30.99996" x="129.18301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <rect id="svg_40" height="23.33334" width="50.00001" y="11.66663" x="202.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_41" y2="35.00949" x2="232.56042" y1="11.66663" x1="232.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_42" y="30.99996" x="209.89375" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <rect id="svg_43" height="23.33334" width="50.00001" y="11.66663" x="286.56043" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_44" y2="35.00949" x2="316.56044" y1="11.66663" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_45" y="30.99996" x="293.89377" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_46" y2="35.00949" x2="316.56044" y1="11.66663" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_53" height="23.33334" width="50.00001" y="41.67404" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_54" y2="65.0169" x2="151.84968" y1="41.67404" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_56" height="23.33334" width="50.00001" y="41.67404" x="202.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_57" y2="65.0169" x2="232.56042" y1="41.67404" x1="232.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_59" height="23.33334" width="50.00001" y="41.67404" x="286.56043" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_60" y2="65.0169" x2="316.56044" y1="41.67404" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_62" y2="65.0169" x2="316.56044" y1="41.67404" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_64" height="23.33334" width="50.00001" y="41.67404" x="371.23762" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_65" y2="65.0169" x2="401.23763" y1="41.67404" x1="401.23763" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_67" y2="65.0169" x2="401.23763" y1="41.67404" x1="401.23763" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_69" height="23.33334" width="50.00001" y="72.34796" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_70" y2="95.69082" x2="151.84968" y1="72.34796" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_71" y="91.68129" x="129.18301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <rect id="svg_72" height="23.33334" width="50.00001" y="72.34796" x="202.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_73" y2="95.69082" x2="232.56042" y1="72.34796" x1="232.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_85" height="23.33334" width="50.00001" y="102.85779" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_86" y2="126.20065" x2="151.84968" y1="102.85779" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_87" y="122.19113" x="129.18301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <rect id="svg_88" height="23.33334" width="50.00001" y="102.85779" x="202.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_89" y2="126.20065" x2="232.56042" y1="102.85779" x1="232.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_91" height="23.33334" width="50.00001" y="102.85779" x="286.56043" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_92" y2="126.20065" x2="316.56044" y1="102.85779" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_94" y2="126.20065" x2="316.56044" y1="102.85779" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_96" height="23.33334" width="50.00001" y="102.85779" x="371.23762" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_97" y2="126.20065" x2="401.23763" y1="102.85779" x1="401.23763" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_99" y2="126.20065" x2="401.23763" y1="102.85779" x1="401.23763" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_101" height="23.33334" width="50.00001" y="134.36794" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_102" y2="157.7108" x2="151.84968" y1="134.36794" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_104" height="23.33334" width="50.00001" y="134.36794" x="202.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_105" y2="157.7108" x2="232.56042" y1="134.36794" x1="232.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_107" height="23.33334" width="50.00001" y="134.36794" x="286.56043" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_108" y2="157.7108" x2="316.56044" y1="134.36794" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_110" y2="157.7108" x2="316.56044" y1="134.36794" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_117" height="23.33334" width="50.00001" y="164.43454" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_118" y2="187.7774" x2="151.84968" y1="164.43454" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_120" height="23.33334" width="50.00001" y="164.43454" x="202.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_121" y2="187.7774" x2="232.56042" y1="164.43454" x1="232.56042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_122" y="183.76787" x="209.89375" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <rect id="svg_123" height="23.33334" width="50.00001" y="164.43454" x="286.56043" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_124" y2="187.7774" x2="316.56044" y1="164.43454" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_126" y2="187.7774" x2="316.56044" y1="164.43454" x1="316.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_128" height="23.33334" width="50.00001" y="164.43454" x="371.23762" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_129" y2="187.7774" x2="401.23763" y1="164.43454" x1="401.23763" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_131" y2="187.7774" x2="401.23763" y1="164.43454" x1="401.23763" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_133" y="185" x="130.99825" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_134" y="61.00738" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_135" y="62.34795" x="211.66493" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_136" y="185.52447" x="294.99829" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_137" y="186.36795" x="377.66496" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_138" y="154.43453" x="296.33163" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_139" y="188.33333" x="404.56046" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_140" y="36.3333" x="321.89377" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_141" y="64.99997" x="407.22713" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_142" y="127.66665" x="403.89379" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_143" y="159.66665" x="319.89378" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_144" y="30.99996" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_145" y="123.6813" x="212.99826" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_146" y="154.19114" x="210.99826" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_147" y="183.76787" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_148" y="122.19113" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_149" y="91.68129" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_150" y="153.70127" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_151" y="62.43451" x="379.66498" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_152" y="62.3333" x="130.33158" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_153" y="154.99999" x="131.66491" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_154" y="92.85779" x="212.99826" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_155" y="123.76785" x="379.66498" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_156" y="62.19111" x="294.33162" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_157" y="123.0346" x="292.99828" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <g id="svg_237">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_234" y2="22.3333" x2="200.52956" y1="22.3333" x1="159.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_235" y2="17.66663" x2="193.66665" y1="22.3333" x1="200.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_236" y2="26.99996" x2="194.99998" y1="22.99996" x1="199.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_241">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_238" y2="52.3333" x2="200.52956" y1="52.3333" x1="159.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_239" y2="47.66663" x2="193.66665" y1="52.3333" x1="200.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_240" y2="56.99996" x2="194.99998" y1="52.99996" x1="199.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_245">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_242" y2="82.3333" x2="200.52956" y1="82.3333" x1="159.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_243" y2="77.66663" x2="193.66665" y1="82.3333" x1="200.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_244" y2="86.99996" x2="194.99998" y1="82.99996" x1="199.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_249">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_246" y2="114.3333" x2="200.52956" y1="114.3333" x1="159.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_247" y2="109.66663" x2="193.66665" y1="114.3333" x1="200.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_248" y2="118.99996" x2="194.99998" y1="114.99996" x1="199.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_253">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_250" y2="145.66663" x2="200.52956" y1="145.66663" x1="159.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_251" y2="140.99996" x2="193.66665" y1="145.66663" x1="200.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_252" y2="150.3333" x2="194.99998" y1="146.3333" x1="199.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_257">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_254" y2="176.34916" x2="200.52956" y1="176.34916" x1="159.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_255" y2="171.6825" x2="193.66665" y1="176.34916" x1="200.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_256" y2="181.01583" x2="194.99998" y1="177.01583" x1="199.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_261">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_258" y2="22.3333" x2="120.52956" y1="22.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_259" y2="17.66663" x2="113.66665" y1="22.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_260" y2="26.99996" x2="114.99998" y1="22.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_265">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_262" y2="52.3333" x2="120.52956" y1="52.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_263" y2="47.66663" x2="113.66665" y1="52.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_264" y2="56.99996" x2="114.99998" y1="52.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_269">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_266" y2="82.3333" x2="120.52956" y1="82.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_267" y2="77.66663" x2="113.66665" y1="82.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_268" y2="86.99996" x2="114.99998" y1="82.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_273">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_270" y2="114.3333" x2="120.52956" y1="114.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_271" y2="109.66663" x2="113.66665" y1="114.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_272" y2="118.99996" x2="114.99998" y1="114.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_277">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_274" y2="145.66663" x2="120.52956" y1="145.66663" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_275" y2="140.99996" x2="113.66665" y1="145.66663" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_276" y2="150.3333" x2="114.99998" y1="146.3333" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_281">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_278" y2="176.34916" x2="120.52956" y1="176.34916" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_279" y2="171.6825" x2="113.66665" y1="176.34916" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_280" y2="181.01583" x2="114.99998" y1="177.01583" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_285">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_282" y2="22.3333" x2="284.11967" y1="22.3333" x1="243.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_283" y2="17.66663" x2="277.25676" y1="22.3333" x1="284.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_284" y2="26.99996" x2="278.59009" y1="22.99996" x1="283.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_289">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_286" y2="52.3333" x2="284.11967" y1="52.3333" x1="243.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_287" y2="47.66663" x2="277.25676" y1="52.3333" x1="284.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_288" y2="56.99996" x2="278.59009" y1="52.99996" x1="283.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_297">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_294" y2="114.3333" x2="284.11967" y1="114.3333" x1="243.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_295" y2="109.66663" x2="277.25676" y1="114.3333" x1="284.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_296" y2="118.99996" x2="278.59009" y1="114.99996" x1="283.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_301">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_298" y2="145.66663" x2="284.11967" y1="145.66663" x1="243.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_299" y2="140.99996" x2="277.25676" y1="145.66663" x1="284.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_300" y2="150.3333" x2="278.59009" y1="146.3333" x1="283.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_305">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_302" y2="176.34916" x2="284.11967" y1="176.34916" x1="243.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_303" y2="171.6825" x2="277.25676" y1="176.34916" x1="284.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_304" y2="181.01583" x2="278.59009" y1="177.01583" x1="283.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_313">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_310" y2="52.3333" x2="370.11967" y1="52.3333" x1="329.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_311" y2="47.66663" x2="363.25676" y1="52.3333" x1="370.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_312" y2="56.99996" x2="364.59009" y1="52.99996" x1="369.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_321">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_318" y2="114.3333" x2="370.11967" y1="114.3333" x1="329.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_319" y2="109.66663" x2="363.25676" y1="114.3333" x1="370.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_320" y2="118.99996" x2="364.59009" y1="114.99996" x1="369.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_329">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_326" y2="176.34916" x2="370.11967" y1="176.34916" x1="329.25675" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_327" y2="171.6825" x2="363.25676" y1="176.34916" x1="370.59009" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_328" y2="181.01583" x2="364.59009" y1="177.01583" x1="369.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_330" y="96.99998" x="235.89376" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
 </g>
</svg>

* 4）有向图（图见第一节的三） 			

<svg width="342" height="161">
 <g>
  <rect stroke="#000" fill="#fff" stroke-width="1.5" x="12.16666" y="7.83334" width="79" height="149.33325" id="svg_1"/>
  <line stroke="#000" fill="none" stroke-width="1.5" x1="60.49999" y1="9.16668" x2="60.49999" y2="157.04632" id="svg_2" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="12.99994" y1="38.99997" x2="91.40914" y2="38.99997" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="12.99994" y1="68.99997" x2="91.40914" y2="68.99997" id="svg_29" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="12.99994" y1="98.99997" x2="91.40914" y2="98.99997" id="svg_33" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="12.99994" y1="128.99997" x2="91.40914" y2="128.99997" id="svg_34" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="121.84967" y="11.66663" width="50.00001" height="23.33334" id="svg_37"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="151.84968" y1="11.66663" x2="151.84968" y2="35.00949" id="svg_38" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="129.18301" y="30.99996" id="svg_39" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="202.56042" y="11.66663" width="50.00001" height="23.33334" id="svg_40"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="232.56042" y1="11.66663" x2="232.56042" y2="35.00949" id="svg_41" stroke-linejoin="null" stroke-linecap="null"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="286.56043" y="11.66663" width="50.00001" height="23.33334" id="svg_43"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="296.89375" y="32.99996" id="svg_42" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="316.56044" y1="11.66663" x2="316.56044" y2="35.00949" id="svg_44" stroke-linejoin="null" stroke-linecap="null"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="316.56044" y1="11.66663" x2="316.56044" y2="35.00949" id="svg_46" stroke-linejoin="null" stroke-linecap="null"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="121.84967" y="41.67404" width="50.00001" height="23.33334" id="svg_53"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="151.84968" y1="41.67404" x2="151.84968" y2="65.0169" id="svg_54" stroke-linejoin="null" stroke-linecap="null"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="121.84967" y="72.34796" width="50.00001" height="23.33334" id="svg_69"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="151.84968" y1="72.34796" x2="151.84968" y2="95.69082" id="svg_70" stroke-linejoin="null" stroke-linecap="null"/>
  <rect fill="#fff" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="121.84967" y="102.85779" width="50.00001" height="23.33334" id="svg_85"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="151.84968" y1="102.85779" x2="151.84968" y2="126.20065" id="svg_86" stroke-linejoin="null" stroke-linecap="null"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31.66489" y="61.00738" id="svg_134" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31.66489" y="30.99996" id="svg_144" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="212.66489" y="31.19113" id="svg_148" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="130.16489" y="123.18129" id="svg_149" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="129.66489" y="91.20127" id="svg_150" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <g id="svg_237">
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="159.66664" y1="22.3333" x2="200.52956" y2="22.3333" id="svg_234" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="200.99998" y1="22.3333" x2="193.66665" y2="17.66663" id="svg_235" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="199.66665" y1="22.99996" x2="194.99998" y2="26.99996" id="svg_236" stroke-linejoin="null" stroke-linecap="null"/>
  </g>
  <g id="svg_261">
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="79.66664" y1="22.3333" x2="120.52956" y2="22.3333" id="svg_258" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="120.99998" y1="22.3333" x2="113.66665" y2="17.66663" id="svg_259" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="119.66665" y1="22.99996" x2="114.99998" y2="26.99996" id="svg_260" stroke-linejoin="null" stroke-linecap="null"/>
  </g>
  <g id="svg_265">
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="79.66664" y1="52.3333" x2="120.52956" y2="52.3333" id="svg_262" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="120.99998" y1="52.3333" x2="113.66665" y2="47.66663" id="svg_263" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="119.66665" y1="52.99996" x2="114.99998" y2="56.99996" id="svg_264" stroke-linejoin="null" stroke-linecap="null"/>
  </g>
  <g id="svg_269">
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="79.66664" y1="82.3333" x2="120.52956" y2="82.3333" id="svg_266" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="120.99998" y1="82.3333" x2="113.66665" y2="77.66663" id="svg_267" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="119.66665" y1="82.99996" x2="114.99998" y2="86.99996" id="svg_268" stroke-linejoin="null" stroke-linecap="null"/>
  </g>
  <g id="svg_273">
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="79.66664" y1="114.3333" x2="120.52956" y2="114.3333" id="svg_270" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="120.99998" y1="114.3333" x2="113.66665" y2="109.66663" id="svg_271" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="119.66665" y1="114.99996" x2="114.99998" y2="118.99996" id="svg_272" stroke-linejoin="null" stroke-linecap="null"/>
  </g>
  <g id="svg_285">
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="243.25675" y1="22.3333" x2="284.11967" y2="22.3333" id="svg_282" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="284.59009" y1="22.3333" x2="277.25676" y2="17.66663" id="svg_283" stroke-linejoin="null" stroke-linecap="null"/>
   <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="283.25676" y1="22.99996" x2="278.59009" y2="26.99996" id="svg_284" stroke-linejoin="null" stroke-linecap="null"/>
  </g>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="321.89377" y="36.3333" id="svg_4" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="70.89377" y="156.3333" id="svg_5" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="156.89377" y="97.3333" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="157.39377" y="125.8333" id="svg_7" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31.66489" y="91.68129" id="svg_9" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31.66489" y="153.70127" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="130.16489" y="61.68129" id="svg_11" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31.66489" y="122.19113" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="155.89377" y="65.8333" id="svg_13" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">^</text>
 </g>
</svg>

* 5）网络

<svg width="421" height="161" >
 <g>
  <rect id="svg_1" height="149.33325" width="79" y="7.83334" x="12.16666" stroke-width="1.5" fill="#fff" stroke="#000"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_2" y2="157.04632" x2="60.49999" y1="9.16668" x1="60.49999" stroke-width="1.5" fill="none" stroke="#000"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_8" y2="38.99997" x2="91.40914" y1="38.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_29" y2="68.99997" x2="91.40914" y1="68.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_33" y2="98.99997" x2="91.40914" y1="98.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_34" y2="128.99997" x2="91.40914" y1="128.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_37" height="23.33334" width="74" y="12.16663" x="337.34965" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_38" y2="35.50949" x2="367.34966" y1="12.16663" x1="367.34966" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_53" height="23.33334" width="74" y="41.67404" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_54" y2="65.0169" x2="151.84968" y1="41.67404" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_69" height="23.33334" width="74" y="72.34796" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_70" y2="95.69082" x2="151.84968" y1="72.34796" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_85" height="23.33334" width="74" y="102.85779" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_86" y2="126.20065" x2="151.84968" y1="102.85779" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_134" y="61.00738" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_144" y="30.99996" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_149" y="123.18129" x="130.16489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_150" y="32.70128" x="345.16487" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <g id="svg_261">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_258" y2="22.3333" x2="120.52956" y1="22.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_259" y2="17.66663" x2="113.66665" y1="22.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_260" y2="26.99996" x2="114.99998" y1="22.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_265">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_262" y2="52.3333" x2="120.52956" y1="52.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_263" y2="47.66663" x2="113.66665" y1="52.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_264" y2="56.99996" x2="114.99998" y1="52.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_269">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_266" y2="82.3333" x2="120.52956" y1="82.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_267" y2="77.66663" x2="113.66665" y1="82.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_268" y2="86.99996" x2="114.99998" y1="82.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_273">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_270" y2="114.3333" x2="120.52956" y1="114.3333" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_271" y2="109.66663" x2="113.66665" y1="114.3333" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_272" y2="118.99996" x2="114.99998" y1="114.99996" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_5" y="156.3333" x="70.89377" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="97.3333" x="182.47208" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_7" y="125.8333" x="182.97208" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_9" y="91.68129" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="153.70127" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_11" y="61.68129" x="130.16489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <rect id="svg_26" height="23.33334" width="74" y="11.66663" x="230.84966" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="32.69114" x="238.66487" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_13" y="65.8333" x="181.47208" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_14" y2="35.50949" x2="393.85438" y1="12.16663" x1="393.85438" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_15" y2="65.0169" x2="178.35439" y1="41.67404" x1="178.35439" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_16" y2="95.69082" x2="178.35439" y1="72.34796" x1="178.35439" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_17" y2="126.20065" x2="178.35439" y1="102.85779" x1="178.35439" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_22" height="23.33334" width="74" y="11.66663" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_23" y2="35.00949" x2="151.84968" y1="11.66663" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_24" y="122.99995" x="158.18301" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f93802">2</text>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_25" y2="35.00949" x2="178.35439" y1="11.66663" x1="178.35439" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_27" y2="35.00949" x2="260.84967" y1="11.66663" x1="260.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_30" y2="35.00949" x2="287.35439" y1="11.66663" x1="287.35439" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <g id="svg_237">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_234" y2="23.3333" x2="336.02955" y1="23.3333" x1="295.16663" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_235" y2="18.66663" x2="329.16664" y1="23.3333" x1="336.49997" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_236" y2="27.99996" x2="330.49997" y1="23.99996" x1="335.16664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_36">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_31" y2="22.3333" x2="228.52956" y1="22.3333" x1="187.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_32" y2="17.66663" x2="221.66665" y1="22.3333" x1="228.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_35" y2="26.99996" x2="222.99998" y1="22.99996" x1="227.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_40" y="30.99996" x="129.18301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_41" y="61.99996" x="158.68301" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f93802">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_42" y="31.99996" x="366.68299" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f93802">15</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_43" y="32.49996" x="267.683" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f93802">7</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_44" y="32.99996" x="159.68301" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f93802">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_45" y="91.99996" x="158.68301" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#f93802">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_46" y="122.69113" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_47" y="91.20127" x="129.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
 </g>
</svg>

####  三、十字链表（Orthogonal List）  

####  四、邻接多重表（Adjacency Multilist）  


---

### **第三节 图的遍历**  

####  一、图的遍历  

####  二、深度优先搜索（DFS） 

####  三、广度优先搜索（BFS）

---

### **第四节 图的连通性问题**  

####  一、无向图的连通性

####  二、无向图的连通分量 （生成树）

####  三、最小生成树

####  四、普利姆（prim）算法生成最小生成树 

####  五、克鲁斯卡尔（Kruskal）算法生成最小生成树

---

### **第五节 最短路径**  

####  一、最短路径

####  二、Dijkstra算法

---

### **第六节 有向无环图及其应用**  

####  一、有向无环图(DAG)

####  二、拓扑排序

####  三、AOV-网

####  四、AOE-网

####  五、关键路径

---
