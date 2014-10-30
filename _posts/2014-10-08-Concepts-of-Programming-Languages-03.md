---
layout : post
category : A Programming languages
tags : [Programming language]
---

# 编程语言原理(第10版)  


## 第3章 描述语法和语义

### 3.1 概述

* 学习程序设计语言与学习自然语言一样，可以分为语法的学习和语义的学习。
	* 程序设计语法是它的表达式、语句和程序单元的形式；
	* 它的语义是这些表达式、语句和程序单元的意义。
* 在设计良好的程序设计语言中，语法应该直接体现语义，也就是说，语句的表现形式应该强烈暗示语句要完成的功能

### 3.2 描述语法的普遍问题

*  最低级语法单元称为词素。词素的描述由词法说明给出，通常与语言的语法描述是分开的。可以将程序看成是词素串，而不是字符串。
*  词素可以分为几组，每个词素组是用名称或标记（token）表示的，因此语言的标记是一类词素。

#### 3.2.1 语言识别器

*  编译器的语法分析部分是编译器所翻译的语言的识别器。

#### 3.2.2 语言生成器

### 3.3 描述语法的形式化方法

*  形式化的语言生成机制，通常称为文法，常用来描述程序设计语言的语法

#### 3.3.1 巴克斯·诺尔范式和上下文无关文法

##### 3.3.1.1 上下文无关文法  

*  程序设计语言的标记形式可以用**正则文法**来描述  
*  而整个程序设计语言的语法，除了极少数例外，都可以用上下文无关文法来描述。

##### 3.3.1.2 巴科斯-诺尔范式的起源  

*  BNF是一种描述语法的自然标记方法。实际上，公元前几百年Panini就曾使用类似于BNF的方法来描述梵语的语法

##### 3.3.1.3 基本原理  

*  元语言是描述其他语言的语言，BNF是描述程序设计语言的元语言
*  BNF 对语法结构进行抽象。
*  例子： Java赋值语句的抽象<赋值>（尖括号通常用于界定抽象的名称）。<赋值>的实际定义是：
	* <赋值>→<变量>=<表达式>  
	* 箭头左边的文本称为左手边(left-hand side, LHS)，是所定义的抽象
	* 箭头右边的文本是LHS的定义，称为右手边(right-hand side, RHS)，由标记、词素以及其他抽象的引用所组成
	* 整个定义称为**规则**或**产生式**
*  BNF描述（或文法）中，抽象通常称为非终结符，规则的词素和标记称为终结符。BNF描述（或文法）是一个规则集。

##### 3.3.1.4 描述列表  

*  用递归的方法描述列表：规则的LHS出现在RHS中

		 <标识符列表>→标识符
				   | 标识符，<标识符列表>

##### 3.3.1.5 文法和推导  
  
* 文法是一种定义语言的生成工具。通过对规则的一系列应用，可以生成语言的句子，该句子的开头是文法的一个特定非终结符，称为起始符号。所应用的这一系列规则称为**推导**。
	
		一种简单语言的文法
		<程序>    → begin <语句列表> end  
		<语句列表> → <语句>
					| <语句>；<语句列表>  
		<语句>    → <变量> = <表达式>  
		<变量>    → A | B | C  
		<表达式>  → <变量> + <变量>  
					| <变量> - <变量>
					| <变量>    

		其推导如下：
		<程序>=> begin <> end  
		     => begin <语句> ; <语句列表> end      
		     => begin <变量> = <表达式> ; <语句列表> end  
		     => begin <A> = <表达式> ; <语句列表 end  
		     => begin <A> = <变量> + <变量>  ; <语句列表> end	  	     	
		     => begin <A> = <B> + <变量>  ; <语句列表> end	  	     	
		     => begin <A> = <B> + <C>  ; <语句列表> end	  	  
		     => begin <A> = <B> + <C>  ; <语句> end	 
		     => begin <A> = <B> + <C>  ; <变量> = <表达式>  end	 
		     => begin <A> = <B> + <C>  ; <B> = <表达式>  end	 
		     => begin <A> = <B> + <C>  ; <B> = <变量>  end	 
		     => begin <A> = <B> + <C>  ; <B> = <C>  end	 

*  符号=>读作"推出"。推导序列中，每一个后面的字符串都是用非终结符的一个定义来替代前面字符串中的一个非终结符而推出的。推导过程中的每个字符串，包括<程序>，都称为句型。

##### 3.3.1.6 语法分析树

*  语法分析树的每个中间结点都标记着非终结符
*  每个叶子结点都标记着终结符
*  语法分析树的每一棵子树都描述了句子中的一个抽象的实例

<svg width="254" height="359">

  <line transform="rotate(-90 199.6056823730469,227.76034545898438) " stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_1" y2="253.542523" x2="173.826994" y1="201.981879" x1="225.387638" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_3" y2="253.542523" x2="123.826994" y1="201.981879" x1="175.387638" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_4" y2="245.920744" x2="174.646902" y1="205.870775" x1="174.646902" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line transform="rotate(-90 197.7537536621094,165.90985107421875) " stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_8" y2="191.691066" x2="171.975154" y1="140.130423" x1="223.535798" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_9" y2="191.691066" x2="121.975154" y1="140.130423" x1="173.535798" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_10" y2="184.069287" x2="172.795062" y1="144.019319" x1="172.795062" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line transform="rotate(-90 146.2735290527344,104.05932617187501) " stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_11" y2="129.83961" x2="120.494002" y1="78.278966" x1="172.054646" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_12" y2="129.83961" x2="70.494002" y1="78.278966" x1="122.054646" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_13" y2="122.217831" x2="121.31391" y1="82.167862" x1="121.31391" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line transform="rotate(-90 94.42280578613281,42.207656860351555) " stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_14" y2="67.988153" x2="68.642481" y1="16.427509" x1="120.203125" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_15" y2="67.988153" x2="18.642481" y1="16.427509" x1="70.203125" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke="#000" stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_16" y2="340.364581" x2="228.350265" y1="306.240501" x1="228.350265" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none"/>
  <line stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_17" y2="60.366374" x2="69.462389" y1="20.316405" x1="69.462389" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" stroke="#000" fill="none"/>
  <line stroke="#000" stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_18" y2="104.440164" x2="19.833078" y1="79.204917" x1="19.833078" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none"/>
  <line stroke="#000" stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_19" y2="172.21751" x2="70.943861" y1="144.019317" x1="70.943861" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none"/>
  <line stroke="#000" stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_20" y2="291.105631" x2="124.647223" y1="266.240754" x1="124.647223" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none"/>
  <line stroke="#000" stroke-linecap="undefined" stroke-linejoin="undefined" id="svg_21" y2="291.476003" x2="227.239161" y1="264.018549" x1="227.239161" fill-opacity="null" stroke-opacity="null" stroke-width="1.5" fill="none"/>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_23" y="12.000972" x="50.370362" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;赋值&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_24" y="141.259403" x="47.037049" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;标识符&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_25" y="140.889037" x="148.14751" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;表达式&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_28" y="78.296844" x="0.000313" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;标识符&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_29" y="302.739852" x="204.073083" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;标识符&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_30" y="78.296844" x="101.110776" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;表达式&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_31" y="264.962318" x="199.999029" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;表达式&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_32" y="198.666446" x="150.369718" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;表达式&gt;</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_33" y="266.814156" x="99.629306" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">&lt;标识符&gt;</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_34" y="351.258063" x="225.184059" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">C</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_35" y="205.333069" x="222.591476" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">)</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_36" y="116.074381" x="17.037243" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">A</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_37" y="185.333197" x="67.407291" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">B</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_38" y="305.33243" x="124.073597" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">A</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_39" y="76.074637" x="65.55545" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">=</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_40" y="137.926092" x="119.629177" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">*</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_41" y="266.443789" x="174.073272" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">+</text>
  <text style="cursor: move;" xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_42" y="206.073805" x="118.888439" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">(</text>
  <text xml:space="preserve" text-anchor="left" font-family="Helvetica, Arial, sans-serif" font-size="12" id="svg_43" y="356.443215" x="34.07417" fill-opacity="null" stroke-opacity="null" stroke-width="0" stroke="#000" fill="#000000">A = B*(A+C)的语法分析树</text>

</svg>


##### 3.3.1.7 歧义

* 文法生成的句型有两种或多种不同的语法分析树，称为有歧义
* 语言结构的语法歧义是一个难题，因为编译器通常将这些结构的语法形式作为语义的基础。具体而言，编译器要根据语句的语法分析树来决定为该语句生成什么样的代码。

##### 3.3.1.8 运算符的优先级

##### 3.3.1.9 运算符的结合性

*  在大多数情况下，计算机中加法的结合性无关紧要。
	* 在数学中，加法是结合的，意味着左结合顺序和右结合顺序是一样的
	* 然而计算机中浮点加法不一定是结合的。
*  不管是在数学中还是在计算机中，减法和除法都不是结合的。
* 当文法规则的LHS还出现在RHS的开头，这样的规则称为左递归。左递归表示左结合性。
	* 可惜左递归不允许使用一些重要的语法分析算法，当使用这样的算法时，必须修改文法，去除左递归，进而使文法不能准确地表示某些运算符是左结合的。幸运的是，左结合性可以由编译器强制实现，即时文法没有规定这一点。
* 如果文法规则的LHS出现在RHS的右端，它就是右递归的。右结合性。

##### 3.3.1.10 if-then-else 的无歧义文法

#### 3.3.2 扩展的BNF

*  EBNF 这些扩展并没有增强BNF的描述能力，只是增加了它的可读性和可写性
	* 第一种 表示RHS的可选部分，用方括号括起来
		* 例如，C语言的if-else 语句可以描述为：  

				<if 语句>→if (<表达式>)<语句>[else<语句>] 
				
				如果不用方括号，这个语句的语法描述就需要以下两条规则：
				
				<if 语句>→if (<表达式>)<语句>
						|if (<表达式>)<语句> else <语句>
	* 第二种扩展是在RHS中使用花括号，表示括起来的部分可以重复无数次或整体省去  
		* 例如，由逗号分隔的标识符列表可以用一下规则描述：
			
				<标识符列表>→<标识符>{, <标识符>} 
	*  第三种常用扩展可处理多个选项。当必须从一组元素中选出一个时，选项可以放在圆括号中，并用OR运算符"|"分隔开
		* 例如 

				<项>→<项>(* | / | %)<因子>
				
				在BNF中，<项>的描述需要下面三条规则：
				
				<项>→<项>*<因子>
					|<项>/<因子>
					|<项>%<因子>

*  EBNF扩展中的方括号、花括号和圆括号都是元符号，即它们是标记工具，而不是所描述的语法实体中的终结符。
* BNF 和 EBNF的变体：
	* 使用冒号来代替箭头，并把RHS放在下一行
	* 可选的RHS不是用竖线分隔，而是简单地放在不同的行上
	* 不使用方括号来表示可选的内容，而是使用下标opt
	* 不是在圆括号括起来的元素列表中使用"|"符号表示选项，而是使用词"one of"	
* EBNF 标准 ISO/IEC 14977:1966
	* 使用等号(=)代替规则中的箭头
	* 用分号结束每一个RHS
	* 要求所有终结符使用引号  				

#### 3.3.3 文法与识别器

### 3.4 属性文法

#### 3.4.1 静态语义

*  有些程序设计语言的结构特点很难用BNF描述，有些无法描述
	* 很难：类型兼容性规则，如Java中,浮点值不能赋值给整型变量，而反过来是可以的
	* 无法：所有变量必须在引用前先声明这一规则无法用BNF表示
*  上述问题示例的这类语言规则称为静态语义规则。语言的静态语义与程序执行过程中程序的意义只有间接关系，但它与正确的程序形式（语法而不是语义）有关。
*  之所以称为静态语义，是因为检查这些规定所需的分析可以在编译时进行。
* 动态语义，即表达式、语句和程序单元的意义

#### 3.4.2 基本概念

*  属性文法是添加了属性、属性计算函数、谓词函数的上下文无关文法
	* 属性与文法符号（终结符和非终结符）相关，从可赋值的意义上说，它与变量类似。
	* 属性计算函数有时称为**语义函数**，与文法规则相关，用于说明如何计算属性值。
	* 谓词函数规定了语言的静态语义规则，与文法规则相关。

#### 3.4.3 属性文法定义

#### 3.4.4 本质属性

#### 3.4.5 属性文法的例子

#### 3.4.6 计算属性值

#### 3.4.7 评价

### 3.5 描述程序的意义：动态语义

#### 3.5.1 操作语义

##### 3.5.1.1 基本过程

*  虚拟机（解释器）

##### 3.5.1.2 评价 

*  操作语义是基于较低级程序设计语言的，而不是数学。
* 一种程序设计语言的语句用较低级程序语言的语句来描述，这种方法会导致循环定义，即概念间接地被自身所定义。

#### 3.5.2 指称语义

*  指称语义是描述程序意义的最严格、最广为人知的正式方法，牢固地建立在递归函数理论的基础之上。
*  为程序设计语言构建指称语义说明的过程，需要为每一个语言实体定义一个数学对象，和一个将语言实体的实例映射到该数学对象实例上的函数。
*  在程序设计语言规范的指称语义中，映射函数与数学中的所有函数一样，具有定义域和值域。
	* 其定义域是函数参数的有效值集合，在指称语义中，定义域称为语法域
	* 值域是参数所映射对象的集合，在指称语义中，值域称为语义域

##### 3.5.2.1 两个简单例子

##### 3.5.2.2 程序的状态

##### 3.5.2.3 表达式

##### 3.5.2.4 赋值语句

##### 3.5.2.5 逻辑前测试循环

##### 3.5.2.6 评价

#### 3.5.3 公理语义

*  公理语义之所以这样命名是因为它基于数理逻辑。
*  验证程序的正确性和说明程序语义

##### 3.5.3.1 断言

*  公理语义中使用的逻辑表达式称为谓词或断言
*  紧靠在程序语句前面的断言描述了程序在那一点上程序变量的约束条件，紧跟在语句后的断言描述了在语句执行后这些变量（可能还有其他变量）的新约束条件，这些断言分别称为语句的前置条件和后置条件。

##### 3.5.3.2 最弱前置条件  

* 推理规则是一种基于其他断言取值来推断一条断言真实性的方法。
* 推理规则的一般形式是：  
$$\frac{S1, S2,...,Sn }{S}$$    
这个 规则表示，如果S1,S2,...Sn为真，那么可以推出S为真。推理规则的上面部分称为前提（antecedent）,下面部分称为结论(consequent).
*  公理是假设为真的逻辑陈述，因此公理是没有前提的推理规则。

##### 3.5.3.3 赋值语句

##### 3.5.3.4 语句序列

##### 3.5.3.5 选择语句

##### 3.5.3.6 逻辑前测试循环  

##### 3.5.3.7 程序证明

##### 3.5.3.8 评价
