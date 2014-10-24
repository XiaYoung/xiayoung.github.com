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


* 6）性质
	* 对于有向图的邻接表，其第i个链表中结点的个数只是该顶点的出度；如果要计算入度，必须遍历整个链接表[也可以建立一个逆邻接表]
	* 要判定两个顶点i和j是否有边(或弧)，必须搜索整个第i个和第j个链表，不及邻接矩阵方便
* 7）有向图的逆邻接表
	* 逆邻接表中，弧的箭头向内（入弧）  
	
<svg width="261" height="161" >
 <g>
  <rect id="svg_1" height="149.33325" width="79" y="7.83334" x="12.16666" stroke-width="1.5" fill="#fff" stroke="#000"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_2" y2="157.04632" x2="60.49999" y1="9.16668" x1="60.49999" stroke-width="1.5" fill="none" stroke="#000"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_8" y2="38.99997" x2="91.40914" y1="38.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_29" y2="68.99997" x2="91.40914" y1="68.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_33" y2="98.99997" x2="91.40914" y1="98.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_34" y2="128.99997" x2="91.40914" y1="128.99997" x1="12.99994" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_37" height="23.33334" width="50.00001" y="42.23213" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_38" y2="65.57499" x2="151.84968" y1="42.23213" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_69" height="23.33334" width="50.00001" y="102.91346" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_39" y="123.56546" x="130.68301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <rect id="svg_40" height="23.33334" width="50.00001" y="74.73213" x="205.06042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_41" y2="98.07499" x2="235.06042" y1="74.73213" x1="235.06042" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_43" height="23.33334" width="50.00001" y="135.23212" x="205.56044" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_44" y2="158.57498" x2="235.56045" y1="135.23212" x1="235.56045" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_46" y2="158.57498" x2="235.56045" y1="135.23212" x1="235.56045" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_53" height="23.33334" width="50.00001" y="72.23954" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_54" y2="95.5824" x2="151.84968" y1="72.23954" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_70" y2="126.25632" x2="151.84968" y1="102.91346" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <rect id="svg_85" height="23.33334" width="50.00001" y="133.42329" x="121.84967" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="#fff"/>
  <line stroke-linecap="null" stroke-linejoin="null" id="svg_86" y2="156.76615" x2="151.84968" y1="133.42329" x1="151.84968" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_134" y="61.00738" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_144" y="30.99996" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_148" y="94.25663" x="215.16489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <g id="svg_237">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_234" y2="85.3988" x2="203.02956" y1="85.3988" x1="162.16664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_235" y2="80.73213" x2="196.16665" y1="85.3988" x1="203.49998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_236" y2="90.06546" x2="197.49998" y1="86.06546" x1="202.16665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_261">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_258" y2="52.8988" x2="120.52956" y1="52.8988" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_259" y2="48.23213" x2="113.66665" y1="52.8988" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_260" y2="57.56546" x2="114.99998" y1="53.56546" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_265">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_262" y2="82.8988" x2="120.52956" y1="82.8988" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_263" y2="78.23213" x2="113.66665" y1="82.8988" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_264" y2="87.56546" x2="114.99998" y1="83.56546" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_269">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_266" y2="112.8988" x2="120.52956" y1="112.8988" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_267" y2="108.23213" x2="113.66665" y1="112.8988" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_268" y2="117.56546" x2="114.99998" y1="113.56546" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_273">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_270" y2="144.8988" x2="120.52956" y1="144.8988" x1="79.66664" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_271" y2="140.23213" x2="113.66665" y1="144.8988" x1="120.99998" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_272" y2="149.56546" x2="114.99998" y1="145.56546" x1="119.66665" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <g id="svg_285">
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_282" y2="145.89879" x2="203.11968" y1="145.89879" x1="162.25676" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_283" y2="141.23212" x2="196.25677" y1="145.89879" x1="203.5901" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
   <line stroke-linecap="null" stroke-linejoin="null" id="svg_284" y2="150.56545" x2="197.5901" y1="146.56545" x1="202.25677" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  </g>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_4" y="159.89879" x="240.89378" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_5" y="35.83331" x="69.89377" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_6" y="127.8988" x="156.89377" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_9" y="156.18129" x="213.66487" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_10" y="153.70127" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">4</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_11" y="92.24679" x="130.16489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">1</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_12" y="122.19113" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">3</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_13" y="65.8988" x="156.39377" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">^</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_48" y="153.56545" x="131.18301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_49" y="62.56546" x="131.68301" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">0</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_50" y="91.68129" x="31.66489" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">2</text>
 </g>
</svg>

####  三、十字链表（Orthogonal List）  

*  1）定义
	* 十字链表是有向图的另一种存储结构
	* 十字链表是将有向图的邻接表和逆邻接表结合起来的一种存储结构 

####  四、邻接多重表（Adjacency Multilist）  

* 1）定义
	* 邻接多重表是无向图的另一种存储结构
	* 在无向图邻接表中，一条边要用2个结点表示（分别从2个顶点的角度看）
	* 在邻接多重表中，一条边只用一个结点表示
	* 将所有具有某顶点的结点，全部用链连结起来，链所在的域为该顶点对应的指针域

---

### **第三节 图的遍历**  

####  一、图的遍历  

*  从图的某一顶点开始，访遍图中其余顶点，且使每个顶点仅被访问一次
*  图的遍历主要应用于无向图

####  二、深度优先搜索（DFS） 

* 1）定义
	*  图的深度优先搜索是树的先根遍历的推广
	*  图中可能存在回路，且图的任一顶点都可能与其它顶点相通，在访问完某个顶点之后可能会沿着某些边又回到了曾经访问过的顶点
	*  DFS是一个递归过程（DFS需要用到栈）
	*  为了避免重复访问，可设置一个标志顶点是否被访问过的辅助数组 visited[ ]
* 2）算法
	* 所有顶点访问标志visited[ ]设置为FALSE
	* 从某顶点v0开始，设 v= v0
		1. 如果visited[v] == FALSE,则访问该顶点v,并将顶点v压入栈中，且设visited[v] = TRUE
		2. 如果找到当前顶点的一个新的相邻顶点 w（即visited[w] == FALSE）,设v = w，重复1
		3. 否则（说明当前顶点的所有相邻顶点都已被访问过，或者当前顶点没有相邻顶点），如果当前顶点是v0，退出；否则返回上一级顶点（即从栈中弹出一个顶点），重复2

####  三、广度优先搜索（BFS）

* 1）定义
	*  广度优先搜索（BFS）是一种分层搜索方法
	* BFS每向前走一步可能访问一批顶点，不存在往回退的情况
	* BFS不是一个递归的过程
	* BFS需要用到队列
* 2）算法
	* 所有顶点访问标志visited[ ]设置为FALSE
	* 从某顶点v0开始，访问v0，visited[v0]=TRUE，将v0插入队列Q
		1. 如果对立Q不空，则从队列Q头上取出一个顶点v，否则结束
		2. 依次找到顶点v的所有相邻顶点v'，如果visited[v'] == FALSE，则访问该顶点v',然后将 v'插入队列Q，并使visted[v'] = TRUE,
		3. 重复1，2

---

### **第四节 图的连通性问题**  

####  一、无向图的连通性

*  如果无向图中，存在不连通的顶点，则该图称为非连通图

####  二、无向图的连通分量 （生成树）

*  非连通图的极大连通子图叫做连通分量
*  若从无向图的每一个连通分量中的一个顶点出发进行DFS或BFS遍历，可求得无向图的所有连通分量的生成树(DFS或BFS生成树)
*  所有连通分量的生成树组成了非连通图的生成森林

####  三、最小生成树

* 1）定义
	*  如果无向图中，边上有权值，则称该无向图为无向网
	*  如果无向网中的每个顶点都相通，称为连通网
	*  最小生成树(Minimum Cost Spanning Tree)是代价最小的连通网的生成树，即该生成树上的边的权值和最小
* 2）准则
	*  必须使用且仅使用连通网中的n-1条边来联结网络中的n个顶点；
	* 不能使用产生回路的边；
	* 各边上的权值的总和达到最小 

####  四、普利姆（prim）算法生成最小生成树 

*  假设N =(V, E)是连通网
* TE是N上最小生成树中边的集合
1. $$U=\{u_0\}, (u_0)\in V, TE = \{\}$$
2. 在所有$$u \in U, v \in V-U$$的边$$(u, v) \in E$$中找一条代价最小的边$$(u, v_0)$$并入集合TE，同时$$v_0$$并入U 
3. 重复2，直到 U= V

####  五、克鲁斯卡尔（Kruskal）算法生成最小生成树

*  假设N =(V, E)是连通网
1.  非连通图 T = {V, {}},图中每个顶点自成一个连通分量
2.  在E中找一条代价最小，且其两个顶点分别依附不同的连通分量的边，将其加入T中
3.  重复2，直到T中所有的顶点都在同一连通分量上

---

### **第五节 最短路径**  

####  一、最短路径

*  最短路径是求从图（或网）中某一顶点，到其余各顶点的最短路径
* 最短路径与最小生成树主要有三点不同
1.  最短路径的操作对象主要是有向图（网），而最小生成树的操作对象是无向图
2. 最短路径有一个始点，最小生成树没有
3.  最短路径关心的是始点到每个顶点的路径最短，而最小生成树关心的是整个树的代价最小

####  二、Dijkstra算法

*  Dijkstra 算法采用按路径长度递增的次序产生最短路径
*  在Dijkstra算法中，引进了一个辅助向量D
*  每个分量D[i]表示当前所找到的从始点到每个终点$$v_i$$的最短路径长度 
*  D[i]初值为始点$$v_0$$到各终点$$v_i$$的直接距离，即若从始点到某终点有（出）弧，则为弧上的权值，否则为$$\infty$$  
*  对于下图，如果0是始点$$v_0$$，则D[i] 的初值为：$$D[i] =\{5, \infty ,7, 15\}$$  
*  显然，$$D[j] =Min\{ D[i]  | v_i \in V\}$$是从始点出发的长度最短的一条最短路径 
 
<svg width="279" height="245">
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="90" cy="211.74829" id="svg_3" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="81.5" y="220.24829" id="svg_4" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="131" cy="30.5" id="svg_5" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="122.5" y="39" id="svg_6" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="39" cy="111.5" id="svg_7" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.5" y="120" id="svg_8" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="243" cy="102.5" id="svg_9" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="234.5" y="111" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="199" cy="213.5" id="svg_11" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="190.5" y="222" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="121" y1="47.5" x2="57" y2="101.5" id="svg_29" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="44" y1="131.5" x2="83" y2="197.5" id="svg_30" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="151" y1="42.5" x2="226" y2="88.5" id="svg_31" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="135" y1="51.5" x2="192" y2="194.5" id="svg_32" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="180" y1="216.5" x2="114" y2="214.5" id="svg_33" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="105" y1="197.5" x2="226" y2="114.5" id="svg_34" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="56.00236" y1="101.50043" x2="58.66898" y2="94.16722" id="svg_36" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="57.00235" y1="100.83377" x2="64.66888" y2="101.1671" id="svg_37" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="82.0019" y1="194.49875" x2="83.66853" y2="186.83222" id="svg_38" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="78.3353" y1="193.49877" x2="74.6687" y2="193.49877" id="svg_39" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="112.33469" y1="213.49841" x2="121.33452" y2="209.16516" id="svg_40" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="112.66801" y1="216.49836" x2="118.00125" y2="219.4983" id="svg_41" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="193.99988" y1="193.8321" x2="194.66654" y2="187.83221" id="svg_42" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="192.9999" y1="197.16537" x2="185.6667" y2="193.8321" id="svg_44" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="226.99929" y1="113.50021" x2="225.66598" y2="119.83343" id="svg_45" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="225.33265" y1="113.83354" x2="219.99942" y2="113.83354" id="svg_46" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="227.66594" y1="87.834" x2="224.99933" y2="81.50079" id="svg_47" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="226.66596" y1="90.50062" x2="220.66607" y2="91.16728" id="svg_48" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_2" y="108.5" x="133.5" stroke-width="0" stroke="#000" fill="#e01d1d">7</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_13" y="206.5" x="145.5" stroke-width="0" stroke="#000" fill="#e01d1d">2</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_14" y="51.5" x="208.5" stroke-width="0" stroke="#000" fill="#e01d1d">15</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_15" y="64.5" x="74.5" stroke-width="0" stroke="#000" fill="#e01d1d">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_16" y="168.5" x="37.5" stroke-width="0" stroke="#000" fill="#e01d1d">5</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="24" id="svg_17" y="166.5" x="123.5" stroke-width="0" stroke="#000" fill="#e01d1d">1</text>
</svg>

* 设S为已求得的最短路径的终点的集合
*  下一条最短路径（设其终点为$$v_i$$）为以下之一：
	* 中间只经过S中顶点j而后到达顶点$$v_i$$的路径
	*  弧$$<v_0, v_i>$$  
*  $$D[i]=Min\{<v_0,v_i> or D[j] + <v_j,  v_i>\} i \in V-S$$ 
* 算法 
	1. 初始化：  
		S←｛$$v_0$$｝；  
		D[i]←arc[0][i], i = 1,2,..., n-1;  
		P[i] = {0, i} // 从$$v_0$$到$$v_i$$的路径  
	2. 求出最短路径的长度：  
		D[j]←min{D[i]}, i$$\in$$V-S; S←S$$\cup$$ {j};  
	3. 修改：  
		if(D[i]>D[j] + arc[j][i]) {D[i] = D[j] + arc[j][i]; P[i] = P[j]$$\cup$${i};} i$$\in$$V-S  
		 //更新从$$v_0$$到$$v_i$$的路径
	4. 判断：	  
		若S = V ,则算法结束，否则转 2
*  例子

	|顶点|||||
	|-
	|1|5<br/>{0,1}|
	|2|$$\infty$$|10<br/>{0,1,2}|9<br/>{0,3,2}|
	|3|7<br/>{0,3}|7<br/>{0,3}|
	|4|15<br/>{0,4}|15<br/>{0,4}|15<br/>{0,4}|10<br/>{0,3,2,4}|
	|终点j|1|3|2|4|
	|S|{0,1}|{0,1,3}|{0,1,3,2}|{0,1,3,2,4}|
	

---

### **第六节 有向无环图及其应用**  

####  一、有向无环图(DAG)

*  有向无环图（DAG : Directed Acycline Graph）是图中无环的有向图
*  有向图中，可以用深度优先搜索(DFS)，找出是否存在环
*  从某个顶点v出发，进行DFS，如果存在一条从顶点u到v的回边，则有向图中存在环

####  二、拓扑排序（**需要离散数学知识！！**）

1.  偏序
	*  若集合X上的关系R是：
		* (1). 自反的：$$xRx$$   
		* (2). 反对称的：$$xRy \Rightarrow  yRx$$  
		* (3). 传递的：$$xRy \& yRz \Rightarrow  xRz$$ 
	* 则称R是集合X上的偏序关系 
2.  全序  
	*  设关系R是集合X上的偏序，如果对每个$$x,y \in X$$, 必有xRy或者yRX, 则称R是X上的全序关系
	*  偏序指集合中仅有部分成员之间可比较
	*  全序指集合中全体成员之间均可比较 
3.  拓扑有序
	*  第五节二中图是一个偏序关系，因为1,3没有先后关系
	*  如果人为地增加1,3先后关系，如1先于3，则右图变为全序，称为拓扑有序
4.  拓扑排序
	*  由偏序定义得到的拓扑有序的操作称拓扑排序
	*  算法：
		* （1）在有向图中选一个没有前驱的顶点且输出之
		* （2）从图中删除该顶点和所有以它为尾的弧
		* 重复（1）（2）两步，直到所有顶点输出为止
* 例子

<svg width="580" height="464" >
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="233.83319" cy="406.91506" id="svg_3" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="225.33319" y="415.41506" id="svg_4" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="496.16682" cy="294.33343" id="svg_9" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="487.66682" y="302.83343" id="svg_10" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="149.33319" cy="403.50012" id="svg_11" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="140.83319" y="412.00012" id="svg_12" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="130.33319" y1="406.50012" x2="64.33319" y2="404.50012" id="svg_33" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="248.83319" y1="392.66677" x2="369.83319" y2="309.66677" id="svg_34" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="62.66788" y1="403.49853" x2="71.66771" y2="399.16528" id="svg_40" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="63.0012" y1="406.49848" x2="68.33444" y2="409.49842" id="svg_41" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="370.83248" y1="308.66698" x2="369.49917" y2="315.0002" id="svg_45" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="369.16584" y1="309.00031" x2="363.83261" y2="309.00031" id="svg_46" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="90" cy="211.74829" id="svg_2" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="81.5" y="220.24829" id="svg_13" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="131" cy="30.5" id="svg_14" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="122.5" y="39" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="39" cy="111.5" id="svg_16" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="30.5" y="120" id="svg_17" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="243" cy="102.5" id="svg_18" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="234.5" y="111" id="svg_19" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="199" cy="213.5" id="svg_20" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="190.5" y="222" id="svg_21" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="121" y1="47.5" x2="57" y2="101.5" id="svg_22" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="44" y1="131.5" x2="83" y2="197.5" id="svg_23" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="151" y1="42.5" x2="226" y2="88.5" id="svg_24" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="135" y1="51.5" x2="192" y2="194.5" id="svg_25" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="180" y1="216.5" x2="114" y2="214.5" id="svg_26" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="105" y1="197.5" x2="226" y2="114.5" id="svg_27" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="56.00236" y1="101.50043" x2="58.66898" y2="94.16722" id="svg_28" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="57.00235" y1="100.83377" x2="64.66888" y2="101.1671" id="svg_35" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="82.0019" y1="194.49875" x2="83.66853" y2="186.83222" id="svg_43" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="78.3353" y1="193.49877" x2="74.6687" y2="193.49877" id="svg_49" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="112.33469" y1="213.49841" x2="121.33452" y2="209.16516" id="svg_50" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="112.66801" y1="216.49836" x2="118.00125" y2="219.4983" id="svg_51" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="193.99988" y1="193.8321" x2="194.66654" y2="187.83221" id="svg_52" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="192.9999" y1="197.16537" x2="185.6667" y2="193.8321" id="svg_53" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="226.99929" y1="113.50021" x2="225.66598" y2="119.83343" id="svg_54" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="225.33265" y1="113.83354" x2="219.99942" y2="113.83354" id="svg_55" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="227.66594" y1="87.834" x2="224.99933" y2="81.50079" id="svg_56" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="226.66596" y1="90.50062" x2="220.66607" y2="91.16728" id="svg_57" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="381.00001" cy="171.08149" id="svg_96" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="372.50001" y="179.58149" id="svg_97" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="330.00001" cy="70.8332" id="svg_98" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="321.50001" y="79.3332" id="svg_99" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="534.00001" cy="61.8332" id="svg_100" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="525.50001" y="70.3332" id="svg_101" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="490.00001" cy="172.8332" id="svg_102" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="481.50001" y="181.3332" id="svg_103" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="335.00001" y1="90.8332" x2="374.00001" y2="156.8332" id="svg_104" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="471.00001" y1="175.8332" x2="405.00001" y2="173.8332" id="svg_105" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="396.00001" y1="156.8332" x2="517.00001" y2="73.8332" id="svg_106" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="373.00191" y1="153.83195" x2="374.66854" y2="146.16542" id="svg_107" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="369.33531" y1="152.83197" x2="365.66871" y2="152.83197" id="svg_108" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="403.3347" y1="172.83161" x2="412.33453" y2="168.49836" id="svg_109" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="403.66802" y1="175.83156" x2="409.00126" y2="178.8315" id="svg_110" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="517.9993" y1="72.83341" x2="516.66599" y2="79.16663" id="svg_113" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="516.33266" y1="73.16674" x2="510.99943" y2="73.16674" id="svg_114" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="40.33319" cy="401.74841" id="svg_117" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="31.83319" y="410.24841" id="svg_118" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="193.33319" cy="292.50012" id="svg_119" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="184.83319" y="301.00012" id="svg_120" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="55.33319" y1="387.50012" x2="176.33319" y2="304.50012" id="svg_121" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="177.33248" y1="303.50033" x2="175.99917" y2="309.83355" id="svg_122" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="175.66584" y1="303.83366" x2="170.33261" y2="303.83366" id="svg_123" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="386.83319" cy="297.66677" id="svg_124" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="378.33319" y="306.16677" id="svg_125" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
</svg> 

####  三、AOV-网

*  如果用有向图的顶点表示**活动**，用弧表示活动间的优先关系，则称该有向图为顶点表示活动的网
*  AOV（Activity On Vertex Network）
*  AOV一定是DAG，即图中不存在环，因为存在环意味着某项活动应以自己为先决条件
*  AOV的应用包括流程图等

####  四、AOE-网

*  如果用有向图的顶点表示**事件**，用弧表示活动，则称该有向图为边表示活动的网
*  AOE（Activity On Edge）
*  AOE同样是DAG
*  AOE包括估算工程的完成时间

####  五、关键路径

*  求工程的完成时间是AOE的一个应用
*  在工程问题中，需要研究的问题有：
	* （1）完成整个工程至少需要多少时间？
	* （2）哪些活动是影响工程进度的关键？
*  1关键路径
	* 工程问题的AOE网中，从工程开始（顶点）到工程结束（顶点）之间路径长度最长的路径叫关键路径
	* 提前完成关键路径上的活动，工程进度会加快
	* 提前完成非关键路径上的活动，对工程无帮助 
*  2关键活动
	* 关键路径上的所有活动称为关键活动
	* 找到工程AOE中的所有关键活动，即找到了关键路径
*  3关键活动有关的量
	* e(i) : 活动$$a_i$$最早开始时间 
	*  l(i) : 活动$$a_i$$最迟开始时间
	*  l(i) - e(i) : 活动$$a_i$$开始时间余量
	*  如果l(i) = e(i)，则称活动$$a_i$$为关键活动 
	* ve(j) : 事件$$v_j$$最早开始时间 
	* vl(j) : 事件$$v_j$$最迟开始时间
	* `e(i) = ve(j)`
	* `l(j) = vl(k) - dut(<j, k>) //dut(<j, k>)`为活动$$a_j$$的持续时间 
	* 从ve(0) = 0 开始向前递推  
	  `ve(j) = Max{ve(i)+dut(<i, j>)}`  $$<i, j> \in T$$, T是所有以第j个顶点为头的弧的集合  
	* 从 vl(n-1) = ve(n-1)起向后递推  
	  `vl(i) = Min{vl(j)-dut(<i,j>)}`   $$<i, j> \in S$$, S是所有以第i个顶点为尾的弧的集合  

*  4 求关键活动算法
	*  从始点$$v_0$$出发，令ve[0]=0, 按拓扑有序求ve[j]
	*  从终点$$v_{n-1}$$，令vl[n-1] = ve[n-1], 按逆拓扑有序求vl[i] 
	*  根据各顶点的ve和vl值，求每条弧（活动）$$a_i$$的最早开始时间$$e[a_i]$$和最迟开始时间$$l[a_i]$$
	*  如果$$e[a_i] = l[a_i]$$， 则$$a_i$$为关键活动 
*  例子 

	`ve(j) = Max{ve(i)+dut(<i, j>)}  vl(i) = Min{vl(j)-dut(<i,j>)}`   
	`e(i) = ve(j)  l(j) = vl(k) - dut(<j, k>)`  
	拓扑有序 0，1，3，2，4

<svg width="667" height="380" >
   <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="490.000035" cy="299.74829" id="svg_2" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="481.500035" y="308.24829" id="svg_13" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="531.000035" cy="118.5" id="svg_14" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="522.500035" y="127" id="svg_15" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="439.000035" cy="199.5" id="svg_16" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="430.500035" y="208" id="svg_17" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="643.000035" cy="190.5" id="svg_18" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke-width="0" x="634.500035" y="199" id="svg_19" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve" stroke="#000">4</text>
  <ellipse fill="#fff" stroke="#000" stroke-width="1.5" cx="599.000035" cy="301.5" id="svg_20" rx="19.5" ry="19.5"/>
  <text fill="#000000" stroke="#000" stroke-width="0" x="590.500035" y="310" id="svg_21" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="521.000035" y1="135.5" x2="457.000035" y2="189.5" id="svg_22" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="444.000035" y1="219.5" x2="483.000035" y2="285.5" id="svg_23" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="551.000035" y1="130.5" x2="626.000035" y2="176.5" id="svg_24" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="535.000035" y1="139.5" x2="592.000035" y2="282.5" id="svg_25" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="580.000035" y1="304.5" x2="514.000035" y2="302.5" id="svg_26" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="505.000035" y1="285.5" x2="626.000035" y2="202.5" id="svg_27" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="456.002395" y1="189.50043" x2="458.669015" y2="182.16722" id="svg_28" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="457.002385" y1="188.83377" x2="464.668915" y2="189.1671" id="svg_35" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="482.001935" y1="282.49875" x2="483.668565" y2="274.83222" id="svg_43" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="478.335335" y1="281.49877" x2="474.668735" y2="281.49877" id="svg_49" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="512.334725" y1="301.49841" x2="521.334555" y2="297.16516" id="svg_50" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="512.668045" y1="304.49836" x2="518.001285" y2="307.4983" id="svg_51" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="593.999915" y1="281.8321" x2="594.666575" y2="275.83221" id="svg_52" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="592.999935" y1="285.16537" x2="585.666735" y2="281.8321" id="svg_53" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="626.999325" y1="201.50021" x2="625.666015" y2="207.83343" id="svg_54" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="625.332685" y1="201.83354" x2="619.999455" y2="201.83354" id="svg_55" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="627.665975" y1="175.834" x2="624.999365" y2="169.50079" id="svg_56" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="626.665995" y1="178.50062" x2="620.666105" y2="179.16728" id="svg_57" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <rect stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="4" y="61.500002" width="163.999998" height="299" id="svg_3"/>
  <rect stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x="177" y="12.500002" width="235.000003" height="347" id="svg_4"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="69" y1="59.500002" x2="69" y2="362.01777" id="svg_5" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="120" y1="61.500002" x2="120" y2="360.98289" id="svg_6" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="299" y1="11.500002" x2="299" y2="359.591944" id="svg_7" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="243" y1="13.500002" x2="243" y2="359.783123" id="svg_8" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line fill="none" stroke="#000" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="359" y1="11.500002" x2="359" y2="361.505716" id="svg_9" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="178" y1="216.500003" x2="410.12827" y2="216.500003" id="svg_10" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="180" y1="267.500003" x2="411.760252" y2="267.500003" id="svg_11" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="180" y1="318.500003" x2="408.064795" y2="318.500003" id="svg_12" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="179" y1="63.500003" x2="411.260282" y2="63.500003" id="svg_29" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="178" y1="165.500003" x2="411.064786" y2="165.500003" id="svg_30" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="4" y1="213.500002" x2="165.128228" y2="213.500002" id="svg_31" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="6" y1="264.500002" x2="165.260238" y2="264.500002" id="svg_32" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="6" y1="315.500002" x2="165.064761" y2="315.500002" id="svg_33" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="4" y1="111.500002" x2="165.260237" y2="111.500002" id="svg_34" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="4" y1="162.500002" x2="166.064757" y2="162.500002" id="svg_36" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <line stroke="#000" fill="none" stroke-width="1.5" stroke-opacity="null" fill-opacity="null" x1="178" y1="114.500003" x2="409.260259" y2="114.500003" id="svg_37" stroke-linejoin="undefined" stroke-linecap="undefined"/>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="183" y="48.500002" id="svg_39" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">活动</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="14" y="93.500002" id="svg_40" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">顶点</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="34" y="148.000002" id="svg_41" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31" y="196.500002" id="svg_42" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="30" y="246.500002" id="svg_44" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="31" y="293.500002" id="svg_45" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="379.837722" y="146.000002" id="svg_46" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="85" y="91.500002" id="svg_47" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">ve</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="135" y="91.500002" id="svg_48" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">vl</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="89" y="149.000002" id="svg_58" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="268" y="199.500002" id="svg_59" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="381" y="201.500002" id="svg_60" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="320.837722" y="148.000002" id="svg_61" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="262" y="348.500002" id="svg_62" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="324" y="347.500002" id="svg_63" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">14</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="267" y="253.500002" id="svg_64" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="313" y="248.500002" id="svg_65" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">12</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="80" y="342.500002" id="svg_66" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">15</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="133" y="343.500002" id="svg_67" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">15</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="266" y="44.500002" id="svg_68" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">e</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="329" y="47.500002" id="svg_69" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">l</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="372" y="45.500002" id="svg_70" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">l-e</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="138.837722" y="149.000002" id="svg_71" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="30" y="344.500002" id="svg_72" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="88" y="196.500002" id="svg_73" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="137" y="195.500002" id="svg_74" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">9</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="382" y="346.500002" id="svg_75" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="379" y="100.500002" id="svg_76" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="268.837722" y="148.000002" id="svg_77" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="380" y="252.500002" id="svg_78" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#f41111" stroke="#000" stroke-width="0" stroke-opacity="null" x="380" y="302.500002" id="svg_79" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="87" y="299.500002" id="svg_80" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="133" y="296.500002" id="svg_81" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">12</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="322" y="201.500002" id="svg_82" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="79" y="247.500002" id="svg_83" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">10</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="130" y="249.500002" id="svg_84" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">14</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="322" y="98.500002" id="svg_85" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="271" y="96.500002" id="svg_86" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#f41111" stroke="#000" stroke-width="0" stroke-opacity="null" x="274" y="304.500002" id="svg_87" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#f41111" stroke="#000" stroke-width="0" stroke-opacity="null" x="327" y="303.500002" id="svg_88" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">0</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="508.000035" y="254.500002" id="svg_89" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a6=1</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="442.000035" y="154.500002" id="svg_90" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a1=5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="415.000035" y="276.500002" id="svg_91" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a2=5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="503.000035" y="197.500002" id="svg_92" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a3=7</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="520.000035" y="330.500002" id="svg_93" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a4=2</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="574.000035" y="128.500002" id="svg_94" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a5=15</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="198" y="100.500002" id="svg_95" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a1</text>
  <text fill="#f71313" stroke="#000" stroke-width="0" stroke-opacity="null" x="201" y="298.500002" id="svg_96" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a5</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="202" y="203.500002" id="svg_97" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a3</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="202" y="346.500002" id="svg_98" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a6</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="202" y="251.500002" id="svg_99" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a4</text>
  <text fill="#000000" stroke="#000" stroke-width="0" stroke-opacity="null" fill-opacity="null" x="202.837722" y="148.000002" id="svg_100" font-size="24" font-family="Helvetica, Arial, sans-serif" text-anchor="left" xml:space="preserve">a2</text>
</svg>

---
