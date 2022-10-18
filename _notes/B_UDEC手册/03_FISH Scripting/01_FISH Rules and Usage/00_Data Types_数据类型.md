---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
# Data Types

FISH variables can be of many types. These include:
>FISH 变量可以有多种类型。这些包括：

Integer: Exact numbers in the range -2,147,483,648 to +2,147,483,647.
>整数：-2，147，483，648 到 +2，147，483，647 范围内的确切数字。

Boolean: Either a value of true or false.
>布尔值：真值或假值。

Floating-point: Approximate numbers with about fourteen decimal digits of precision, with a range of approximately 10-308 to 10308.
>浮点数：精度约为十四位十进制数字的近似数字，范围约为 10-308 到 10308。

String: Packed sequence of any printable characters; the sequence may be any length, but it may be truncated when printed. Strings are denoted in FISH and UDEC by a sequence of characters enclosed by single or double quotes (e.g., 'Have a nice day' or "Have a nice day"). See the “Strings” section for further details.
>字符串：任何可打印字符的压缩序列;序列可以是任意长度，但在打印时可能会被截断。字符串在 FISH 和 UDEC 中由单引号或双引号括起来的字符序列表示（例如，“祝你有美好的一天”或“祝你有美好的一天”）。有关更多详细信息，请参阅“字符串”部分。


Pointer: Machine address used when looping through a list and marking references to an object. They have an associated type from the object to which the pointer refers, except for the null pointer. See the “Pointers” section for further details.
>指针：循环遍历列表并标记对对象的引用时使用的计算机地址。它们具有指针所引用对象的关联类型，但空指针除外。有关更多详细信息，请参阅“指针”部分。

Vector: 2D or 3D vector of floating-point types. See the “Vectors” section for further details.
>矢量：浮点类型的 2D 或 3D 矢量。有关更多详细信息，请参阅“矢量”部分。

Array: A collection of FISH variables with specified dimensionality. See the “Arrays” section for further details.
>数组：具有指定维度的 FISH 变量的集合。有关更多详细信息，请参阅“数组”部分。

Matrix: Matrix of numeric values with specified dimensionality. See the “Matrices” section for further details.
>矩阵：具有指定维度的数值矩阵。有关更多详细信息，请参阅“矩阵”部分。

Tensor: A symmetric tensor. See the “Tensors” section for further details.
>张量：对称张量。有关更多详细信息，请参阅“张量”部分。

Map: An associative array with string or number key and any FISH variable as value. See the “Maps” section for further details.
>Map：一个具有字符串或数字键以及任何 FISH 变量作为值的关联数组。有关更多详细信息，请参阅“地图”部分。

Structure: A structure may contain multiple FISH variables. See the “Structures” section for further details.
>结构：一个结构可以包含多个 FISH 变量。有关更多详细信息，请参阅“结构”部分。

A variable in FISH can change its type dynamically, depending on the type of the expression to which it is set. To make this clear, consider the assignment statement:
>FISH 中的变量可以动态更改其类型，具体取决于将其设置为的表达式的类型。为了明确这一点，请考虑赋值语句：

```fish
var1 = var2
```

f var1 and var2 are of different types, then two things are done. First, var1’s type is converted to var2’s type; second, var2’s data are transferred to var1. In other languages, such as FORTRAN or C, the type of var1 is not changed, although data conversion is done. By default, all variables in FISH start as integers; however, a statement such as:
>f var1 和 var2 属于不同的类型，然后完成两件事。首先，将 var1 的类型转换为 var2 的类型;其次，var2 的数据被传输到 var1。在其他语言（如 FORTRAN 或 C）中，尽管进行了数据转换，但 var1 的类型不会更改。默认情况下，FISH 中的所有变量都以整数开头。但是，语句如下：

```fish
var1 = 3.4
```

causes var1 to become a floating-point variable when it is executed. The current types of all variables may be determined with the fish list symbols command.
>使 var1 在执行时成为浮点变量。所有变量的当前类型都可以使用鱼列表符号命令来确定。

The dynamic typing mechanism in FISH was devised to make programming easier for non-programmers. In languages such as BASIC, numbers are stored in floating-point format, which can cause difficulties when integers are needed for loop counters, for example. In FISH, the type of the variable adjusts naturally to the context in which it is used. For example, in the code fragment:
>FISH中的动态类型机制旨在使非程序员更容易编程。在 BASIC 等语言中，数字以浮点格式存储，例如，当循环计数器需要整数时，这可能会导致困难。在 FISH 中，变量的类型会根据使用它的上下文自然调整。例如，在代码片段中：

```fish
n = n + 2
xx = xx + 3.5
```

the variable n will be an integer and will be incremented by exactly 2, and the variable xx will be a floating-point number, subject to the usual truncation error but capable of handling a much larger dynamic range. The rules governing type conversion in arithmetic operations are explained in “Arithmetic: Expressions and Type Conversions.” 
>变量 n 将是一个整数，并将正好递增 2，变量 xx 将是一个浮点数，受通常的截断误差的影响，但能够处理更大的动态范围。“算术运算：表达式和类型转换”中介绍了在算术运算中控制类型转换的规则。

The type of a variable is determined by the type of the object on the right-hand side of an assignment statement; this applies both to FISH statements and to assignments made with the fish set command. Both types of assignment may be used to change the type of a variable according to the value specified, as follows:
>变量的类型由赋值语句右侧的对象类型确定;这既适用于 FISH 语句，也适用于使用 fish set 命令进行的赋值。这两种类型的赋值都可用于根据指定的值更改变量的类型，如下所示：

1. An integer assignment (digits 0-9 only) will cause the variable to become an integer (e.g., var1 = 334).
>整数赋值（仅限数字 0-9）将导致变量变为整数（例如，var1 = 334）。

2. If the assigned number has a decimal point or an exponent denoted by “e” or “E,” then the variable will become a floating-point number (e.g., var1 = 3e5; var2 = -1.2).
>如果分配的数字具有小数点或由“e”或“E”表示的指数，则该变量将成为浮点数（例如，var1 = 3e5; var2 = -1.2）。

3. If the assignment is delimited by single or double quotes, the variable becomes a string, with the “value” taken to be the list of characters inside the quotes (e.g., var1 = 'Have a nice day'). 
>如果赋值由单引号或双引号分隔，则变量将变为字符串，其中“value”被视为引号内的字符列表（例如，var1 = “度过美好的一天”）。

The following sections detail specifics of the data types introduced above:
>以下各节详细介绍了上面介绍的数据类型的详细信息：





