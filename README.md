# CStack

CStack是一个基于C标准库的字典树库，采用C语言开发，方便，快捷，简单。

### 使用方法

将``stack.h``复制到指定目录中。只需``#include "stack.h"``即可开始使用。

### 接口介绍

* ``STACK* InitStack();``：初始化一个栈，成功返回栈指针，否则返回NULL
* ``int ClearStack(STACK* stack);``：清空一个栈，成功返回1，否则返回0
* ``int DestroyStack(STACK* stack);``：销毁一个栈，成功返回1，否则返回0
* ``int StackEmpty(STACK* stack);``：判断栈是否为空，是则返回1，否则返回0，出错返回-1
* ``int StackLength(STACK* stack);``：返回栈的长度，出错返回-1
* ``void* GetTop(STACK* stack);``：返回栈顶元素数据，出错返回NULL
* ``int PushStack(STACK* stack,void* data);``：入栈 ，成功返回1，否则返回0
* ``void* PopStack(STACK* stack);``：出栈并返回出栈的数据，错误返回NULL
* ``int StackTraverse(STACK* stack,STACK_VISIT visit);``：从栈底到栈顶一次调用visit函数，要求visit函数参数为数据，visit返回1代表处理成功，并开始处理下一个元素，返回0代表处理失败，StackTraverse则终止处理并退出，返回成功处理的元素个数