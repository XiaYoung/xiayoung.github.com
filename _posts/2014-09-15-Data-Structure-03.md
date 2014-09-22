---
layout : post
category : MSE
tags : [Data structure, progaming basic] 
---
##第三章 栈和队列 

### **第一节 栈**  

####  一、栈

*  栈是限定仅在表尾（top）进行插入或删除操作的线性表
*  允许插入和删除的一端称为栈顶（top，表尾），另一端称为栈底（bottom，表头）
*  特点：后进先出（LIFO）

#### 二、栈的实现 

*  栈的存储结构主要有两种
	1. 顺序栈
	2. 链式栈

### **第二节 顺序栈**  

####  一、顺序栈

*  顺序栈是栈的顺序存储结构
*  利用一组地址连续的存储单元依次存放自栈底到栈顶的数据元素
*  指针top指向栈顶元素在顺序栈中的下一个位置
*  base为栈底指针，指向栈底的位置

#### 二、顺序栈的定义

*  采用C语言中动态分配的**一维数组**表示顺序表

		#define STACK_INIT_SIZE 100    //栈存储空间的初始分配量
		#define STACKINCREMENT 10    //栈存储空间的分配增量
		Typedef struct
		{
			SElemType *base;    // 栈底指针，也是栈的基址
			SElemType *top;    //栈顶指针 
			int stacksize;    //当前分配的存储容量（元素数）
		} SqStack;

#### 三、顺序栈的特性

*  top == 0 或 top ==base 表示空栈
*  base == NULL 表示栈不存在
*  当插入新的栈顶元素时，指针top+1
*  删除栈顶元素时，指针top-1
*  当top>stacksize时，栈满，溢出

#### 四、顺序栈的主要操作

* ADT Stack
	{ 
		数据对象：D ={$$a_i | a_i \in ElemSet, i =1, 2, 3, ..., n$$}  
		数据关系：R ={$$<a_{i-1}, a_i> |a_{i-1}, a_i \in D$$}  
		基本操作：InitStack(&S)   //构造空栈
						Push(&S, e)    //进栈
						Pop(&S, &e)    //出栈
						GetTop(S,&e)    //取栈顶元素值
						StackEmpty(S)    //栈是否为空
	} ADT Stack


#### 五、创建顺序栈

	Status InitStack(SqStack &S)
	{
		S.base =(SElemType *) malloc(STACK_INIT_SIZE * sizeof(SElemType)); //类型强转
		if(!S.base) exit(OVERFLOW);//存储分配失败
		S.top = S.base;
		S.stacksize = STACK_INIT_SIZE;
		return OK；
	} //InitStack

#### 六、进栈（插入新元素）

	Status Push(SqStack &S, SElemType e)
	{
		if(S.top - S.base >= S.stacksize)
		{  //栈满，追加存储空间
			S.base = (SElemType *)realloc(S.base,(S.stacksize + STACKINCRMENT * sizeof(SElemType)));
			
			if(!S.base)
				exit(OVERFLOW);
			
			S.top = S.base + S.stacksize;
			S.stacksize += STACKINCRMENT;
		}
		
		*S.top++ = e;
		
		return OK;
	} //Push

#### 七、出栈（删除元素）

	Status Pop(SqStack &S, SElemType &e)
	{
		if(S.top == S.base)
			return ERROR;
		e = *--S.top;
		return OK;
	} //Pop

#### 八、取栈顶元素

	Status Pop(SqStack &S, SElemType &e)
	{
		if(S.top == S.base)
			return ERROR;
		e = *(S.top-1);
		return OK;
	} //GetTop

### **第三节 栈的应用举例**

####  一、数值转换（八进制）

#### 二、行编辑程序

#### 三、迷宫求解

#### 四、后缀表达式计算[实验二]

### **第四节 队列**

####  一、队列

*  队列1是只允许在表的一端进行插入，而在另一端删除元素的线性表。
*  在队列中，允许插入的一端叫队尾（rear）, 允许删除的一端称为对头（front）。
*  特点：先进先出（FIFO）

#### 二、顺序队列

*  顺序队列：采用一组地址连续的存储单元一次存储从队列头到队列尾的元素
*  顺序队列有两个指针： 队头指针front和队尾指针rear

#### 三、顺序队列的进队和出队原则

*  进队时，新元素按rear指针位置插入，然后队尾指针增一，即rear = rear + 1
*  出队时，将对头指针位置的元素取出，然后队头指针增一，即front = front + 1
*  队头指针始终指向队列头元素
*  队尾指针始终指向队列尾元素的下一个位置

#### 四、顺序队列的进队和出队举例

#### 五、顺序队列存在的问题

*  当队尾指针指向队列存储结构中的最后单元时，如果再继续插入新的元素，则会产生溢出
*  当队列发生溢出时，队列存储结构中可能还存在一些空白位置（已被取走的数据的元素）
* 解决办法之一：将队列存储结构首尾相接，形成循环（环形）队列

### **第五节 循环队列**

####  一、循环队列

*  循环队列采用一组地址连续的存储单元
*  将整个队列的存储单元首位相连

#### 二、循环队列空与满

*  front == rear ,循环队列空
*  （rear+1）%MAXQSIZE = front，循环队列满

#### 三、循环队列定义

	#define MAXQSIZE 100
	Typedef struct
	{
		QElemType *base;
		int front;
		int rear;
	} SqQueue;

#### 四、循环队列插入元素

	Status EnQueue(SqQueue &Q, QElemType e)
	{
		if((Q.rear + 1) % MAXQSIZE == Q.front)
			return ERROR; //队满
		Q.base[Q.rear]= e;
		Q.rear = (Q.rear + 1)%MAXQSIZE;
		return OK;
	}

#### 五、循环队列删除元素

	Status DeQueue(SqQueue &Q, QElemType e)
	{
		if(Q.rear == Q.front)
			return ERROR; //队满
		e = Q.base[Q.front];
		Q.front = (Q.front + 1)%MAXQSIZE;
		return OK;
	}

### **第六节 链队列**

####  一、链队列

*  链队列采用链表存储单元
*  链队列中，有两个分别指示队头和队尾的指针
*  链式队列在进队时无队满问题，但有队空间问题

#### 二、链队列指针变化状况

*  链队列是链表操作的子集

