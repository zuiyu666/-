---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 9:33:11 上午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
FISH Introduction
>FISH 介绍

FISH is an embedded programming language that enables the user to interact with and manipulate UDEC models, defining new variables and functions as needed. These functions may be used to extend UDEC’s usefulness or add user-defined features. For example, new variables may be plotted or printed, special particle generators may be implemented, servo controls may be applied to perform a numerical test, unusual distributions of properties may be specified, and parametric studies may be automated.
>FISH 是一种嵌入式编程语言，使用户能够与 UDEC 模型交互和操作 UDEC 模型，并根据需要定义新的变量和函数。这些函数可用于扩展 UDEC 的实用性或添加用户定义的功能。例如，可以绘制或打印新的变量，可以实现特殊的粒子发生器，可以应用伺服控制来执行数值测试，可以指定属性的异常分布，并且可以自动执行参数化研究。



FISH was developed in response to users who wanted to do things with Itasca software that were either difficult or impossible with existing program structures. Rather than incorporate many new and specialized features into UDEC, FISH was provided so that users could write functions to perform custom analyses. 
>FISH的开发是为了响应那些想要使用Itasca软件做一些事情的用户，这些事情在现有的程序结构中要么很困难，要么是不可能的。FISH没有将许多新的和专门的功能合并到UDC中，而是提供了FES，以便用户可以编写函数来执行自定义分析。

It is possible for someone without programming experience to write simple FISH functions. The following section contains an introductory tutorial for non-programmers. However, FISH programs can also become very complicated.
>没有编程经验的人可以编写简单的FISH函数。以下部分包含面向非程序员的入门教程。但是，FISH程序也可能变得非常复杂。

测试情况下，如果udec

As with all programming tasks, FISH functions should be constructed in an incremental fashion, checking operations at each level before moving on to more complicated code. FISH does less error-checking than most compilers, so all functions should be tested on simple data sets before they are used for real applications.
>与所有编程任务一样，FISH 函数应以增量方式构造，在转到更复杂的代码之前检查每个级别的操作。与大多数编译器相比，FISH 所做的错误检查更少，因此所有函数在用于实际应用程序之前，都应在简单的数据集上进行测试。

FISH programs are simply embedded in a normal UDEC data file. Lines following the word define are processed as a FISH function; the function terminates when the word end is encountered. Functions may invoke other functions, which may invoke others, and so on. 
>FISH 程序只是嵌入在普通的 UDEC 数据文件中。单词定义后面的行被处理为 FISH 函数;该函数在遇到词尾时终止。函数可以调用其他函数，也可以调用其他函数，依此类推。

The order in which functions are defined does not matter, as long as they are all defined before they are used (e.g., invoked by a UDEC command). Since the compiled form of a FISH function is stored in UDEC’s memory space, the model save command saves the function and the current values of associated variables.
>函数的定义顺序并不重要，只要它们在使用之前全部定义（例如，由 UDEC 命令调用）。由于 FISH 函数的编译形式存储在 UDEC 的内存空间中，因此模型 save 命令将保存函数和相关变量的当前值。

| 篇目                        | 释义             |
| --------------------------- | ---------------- |
| FISH Rules and Usage        | FISH的规则和用法 |
| FISH Statements Index       | FISH索引         |
| FISH Functions              | FISH语言的功能   |
| Library of FISH Functions   | FISH函数库       |
| FISH Type Index             | FISH指数         |
| Tutorial: Working with FISH | 教程，使用                 |
| UDEC FISH Data Program Guide    | FISH数据指南     |

