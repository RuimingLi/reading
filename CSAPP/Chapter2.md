### Chapter2 信息的表示和处理

​		大多数计算机使用8位的块，或者字节（byte），作为最小的可寻址的内存单位，而不是访问内存中单独的位。机器级程序将内存视为一个非常大的字节数组，称为虚拟内存（virtual memory）。内存的每个字节都由一个唯一的数字来标识，称为它的地址，所有可能地址的集合就称为虚拟地址空间（virtual address space）。顾名思义，这个虚拟地址空间只是一个展现给机器级程序的概念性映像。实际的实现是将动态随机访问存储器（DRAM）、内存、磁盘存储器、特殊硬件和操作系统软件结合起来，为程序提供一个看上去统一的字节数组。

​		排列表示一个对象的字节有两个通用的规则。考虑一个n位的整数，最大位的是最高有效位，最小位的是最低有效位。假设n是8的倍数，这些位就能被分组成为字节，其中最高有效字节包含位最高到第8位，最低有效字节包含第7位到第0位。其他字节包含中间的位。某些机器选择在内存中按照从最低有效字节到最高有效字节的顺序存储对象，而另一些机器则按照从最高有效字节到最低有效字节的顺序存储。前一种规则-----最低有效字节在最前面的方式，称为小端法。后一种规则------最高有效字节在最前面的方式，称为大端法。

**无符号数**：所有的位都表示数值

**有符号数**：第一位是符号位（0 为正，1 为负），其余都表示数值

**原码**：就是符号位加上真值的绝对值, 即用第一位表示符号, 其余位表示值

**反码**：正数的反码是其本身

　　   负数的反码是在其原码的基础上, 符号位不变，其余各个位取反

**补码**：正数的补码就是其本身 

　　   负数的补码是在其原码的基础上, 符号位不变, 其余各位取反, 最后+1. (即在反码的基础上+1)

Java中只支持有符号整数，并且要求以补码运算来实现。正常的右移运算符>>被定义为执行算术右移，特殊的运算符>>>被指定为执行逻辑右移。