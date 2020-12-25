# 局部变量的存储

> 寄存器和内存都可以用来存放`函数执行时`所需的`数据`。寄存器的存取速度比内存快很多，所以通常会优先把数据存入寄存器中。但是由于寄存器数量有限，因此当寄存器不够用时会将数据存放在`栈`内存中。

**我们可以把`栈指针`（sp）向`栈顶移动`来为函数在栈中分配用于存放`局部数据`的内存空间。**

例如有如下C语言代码：

```c
void main() {
    long foo = 100;
    long bar = 200;
}
```

代码中定义了两个`long`类型变量`foo`和`bar`，我们假设它们都放在`栈`中，由于`long`类型占用8个字节，因此我们需要在栈中分配16个字节的空间。

分配过程（一个单元格8个字节）：

![](https://image.coder.cat/stack13.png)



最后再把这两个变量分别存入栈中：

![](https://image.coder.cat/stack14.png)