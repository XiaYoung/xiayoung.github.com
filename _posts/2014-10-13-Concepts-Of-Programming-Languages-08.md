---
layout : post
category : programming language
tags : [Programming language]
---

## 第8章 语句级控制结构

---

*  程序的控制流程，或者说执行序列，可以从多个层次来考虑：
	* 表达式控制流程
	* 语句控制流程
	* 程序单元之间的控制流程 

### 8.1 概述

*  两类语言结构
	* 一类是能够在(语句执行中)多个控制流程路径间进行选择的结构，
	* 另一类是能够重复执行某条语句或语句组的结构 
*  控制结构包含控制语句和被它控制执行的语句集合两部分。
	* 控制结构应该有多个入口吗？
		* 多个入口只能在包含goto语句和标签语句的语言中实现。

---

### 8.2 选择语句

*  选择语句提供了从2个或多个执行路径中选择的方法。它是所有编程语言的必要部分。

#### 8.2.1 双路选择语句

* 一般形式

		if 控制语句表达式
			then 子句
			else 子句

##### 8.2.1.1 设计问题

* 控制选择方向的表达式的形式与类型是怎样的？
* then 和 else 子句如何确定？
* 嵌套选择器的含义如何确定？

##### 8.2.1.2 控制表达式

* 如果不使用then保留字（或其他的语法记号）来引导then子句，控制表达式就放在圆括号中
*  C89语言没有布尔数据类型，所以把算术表达式用作控制表达式。Python C99 C++也兼容这样的语法。现代其他语言中，只能将布尔表达式作为控制表达式

##### 8.2.1.3 子句的形式

*  在许多当代语言中，then和else子句表示为单条语句或复合语句。许多语言用大括号构成复合语句，来作为then好else子句的内容。
* 在Fortran95 Ada Python 和Ruby语言中，then和else子句是语句序列，而不是复合语句。在这些语言中，使用一个保留字来结束完整的选择结构。 

##### 8.2.1.4 嵌套选择器

##### 8.2.1.5 选择器表达式

#### 8.2.2 多重选择语句

##### 8.2.2.1 设计问题

*  控制这个选择的表达式是什么形式和类型？
* 可选择语句段是怎样指定的？
* 通过结构的执行流是否限定为只包含一个可选段？
* case值是怎样指定的？
* 如果选择器表达式的值根本就无法表述，那应该如何处理它呢？

##### 8.2.2.2 多重选择器的例子

*  C C++ Java JavaScript 中的switch

		switch(控制表达式)
		{
		case 常量表达式 1 : 语句1;
		...
		case 常量表达式n : 语句n;
		[default : 语句n+1] 
		}

*  break语句（实际上是个受限制的goto语句）通常用来退出switch结构

##### 8.2.2.3 多重选择结构的实现

##### 8.2.2.4 用if实现多重选择

* else-if 子句 Python例子
	
		if count < 10 :
		bag1 = True
		elif count < 100:
		bag2 = True
		elif count <1000:
		bag3 = True
	
* 	这个例子是用switch语句是不容易模拟的，因为每个可选语句是依据布尔表达式来选择的。	因此，else-if 结构不是switch的冗余形式。

---  

### 8.3 迭代语句

* 迭代语句能使一条语句或一块语句执行零次、一次、或者多次。迭代语句一般称为循环。
*  迭代是计算机能力的精华。
* 设计问题：
	* 怎样控制语句的迭代？
	* 控制机制在循环语句中的哪里体现？

#### 8.3.1 计数控制循环

* 计数控制语句包含一个变量，叫做循环变量，它记录着目前的计数。这个控制语句也包含循环变量的起始和终止方式，以及循环变量前后的差值，即步长。
* 循环的起始、终止和步长称为循环参数。

##### 8.3.1.1 设计问题

*  循环变量的类型和作用域是什么？
* 在循环体中修改循环变量和循环参数是否合法？如果合法，这样的修改会影响循环控制吗？
* 循环参数应该只计算一次，还是每次迭代都计算？

##### 8.3.1.2 Ada 语言中的for 语句

*  形式
	
		for 变量 in [reverse] 离散范围 loop
		...
		end loop; //离散范围是整数或枚举类型的子范围比如1..10或周一..周五

##### 8.3.1.3 基于C的语言的for语句

*  一般形式
		
		for(表达式1；表达式2；表达式3)
			循环体 //循环体可以是一条单个的语句、复合语句或空语句。
			
*  操作语义

			表达式1
		loop:
			if 表达式2 = 0 goto out
			[循环体]
			表达式3
			goto loop
		out: ...
	
* 设计方案 
	* 没有显式的循环变量或循环参数
	* 所有相关的变量都能在循环体中修改
	* 表达式将按照之前定义的顺序执行
	* 分支进入for循环体也是合法的，尽管这样会造成破坏		
* **C的所有语句都有值**

##### 8.3.1.4 Python中的for语句

*  形式

		for 循环变量 in object：
		-循环体
		[else:
		-else子句]

##### 8.3.1.5 函数式语言中的计数控制循环

*  函数式语言不使用迭代来控制语句的重复执行，而是使用递归来控制。函数式语言不使用语句，而使用递归函数。

#### 8.3.2 逻辑控制循环

*  在很多情况下，都必须重复执行大量语句，而对这种重复执行的控制基于一个布尔表达式，而不是计数器。
*  任何一个计数循环都可以用逻辑控制循环来构建，但反之不一定成立。
*  只有选择语句和逻辑循环才是流程图中控制结构的基本组成要素。

##### 8.3.2.1 设计问题

*  控制应当是前测试型还是后测试性？
* 逻辑控制循环应当是一种特殊形式的计数循环还是其他形式的语句？

##### 8.3.2.2 例子

* 形式

		while（控制表达式）
			循环体
		
		或者	
		do
			循环体
		while(控制表达式)；//注意这个分号


#### 8.3.3 用户自定义的循环控制机制

*  在某些情况下，程序员不将循环控制语句放在循环体头部或末尾会更加方便。这种循环具有死循环结构，但包括了用户定义的循环退出语句。
* 设计问题：
	* 条件语句是退出机制中不可或缺的一部分吗？
	* 只能从一个循环体中退出，还是能从封闭的多个嵌套循环中推出？

#### 8.3.4 基于数据结构的迭代

---

### 8.4 无条件分支

*  无条件分支语句goto，是控制程序语句执行流程的最有力的语句。

---

### 8.5 防护命令

---

### 8.6 结论