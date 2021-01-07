# 前置知识

> 这里先对一些基础知识做一些简单说明，以方便后面阅读。



## 函数定义

> 计算机中的函数（有时也被称为过程或方法）提供了一种`封装代码`的方式，用一组指定的参数和可选的返回值实现了某种功能。然后可以在程序不同的地方调用这个函数。它通过从`调用方`接受一组参数用于函数执行，也可以向`被调用方`返回执行结果。

在进行函数调用时，计算机底层需要提供如下机制：

* 控制转移

  需要把`控制转移`到被调用函数，然后当被调用函数`执行完毕`后再回到原来的位置继续执行。

* 数据传递

  调用者可以向被调用者`传递参数`，同时被调用者也可以向调用者`返回数据`。

* 内存分配与释放

  在开始时，可能需要为被调用者分配`局部内存`来存储`局部变量`，在函数返回时必须对这些内存进行释放。



## 栈

栈是一种数据结构，可以把它理解为一个容纳数据的容器，它具有`先进后出`（也等价于后进先出）的特性，也就是先进入`栈`的数据，最后才能出来。也可以把它想象成你桌面的一摞书，每次只能取最上面的一本书，新到来的书只能放在最上面。或者也可以把它想像成你身上的衣服，最先穿的衣服，最后才能脱掉。因此对于`栈`来说就有两个重要的操作即`压栈`（push）和`出栈`（pop）。`压栈`表示从栈的顶部新新增一条数据，`出栈`表示把栈顶部的数据取出来。栈这种数据结构具有`记忆功能`，也就是出栈的值永远是最近被压入且仍然在栈中的值。



## 内存

内存是计算机中一组`连续的`存储区域，这块区域被计算机组织成由无数个连续的以`字节`（8个二进制位）大小为单元的集合。并且为每个`内存单元`提供一个唯一的`内存地址`用于计算机方便对某个内存单元进行访问，也就是每个字节都会有一个`内存地址`。例如第一个字节的地址是0，和它挨着的第二个字节地址就是1，以此类推。我们把内存地址较大的一端称作`高地址`，内存地址较小的一端称作`低地址`。



## 汇编指令

`汇编语言`是直接工作在机器之上的语言。计算机只能识别由0，1组成的二进制序列，所以CPU也只能执行由0，1所组成的`机器指令`。汇编语言是机器指令的`助忆符`，它可以方便人类辨别和记忆。每一条汇编指令会对应一条或多条机器指令。本文中会使用一种类似于C语言的伪代码来描述栈的变化过程。



## 寄存器

`CPU`的内部有一组存储器用来存放一些较小的临时数据，称这组存储器为`寄存器`，寄存器的访问速度比内存快很多，通过快速地访问数据来加速计算机程序的运行。CPU想要访问内存中的数据就必须把内存中的数据转移到寄存器中然后CPU再从寄存器中读取。寄存器位于存储器层次结构的最顶端，也是CPU可以读写的最快的存储器。每个寄存器有专门的名字，不同的寄存器用途也不一样。

