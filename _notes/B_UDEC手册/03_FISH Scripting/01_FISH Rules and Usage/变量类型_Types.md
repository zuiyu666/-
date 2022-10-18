---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 4:29:43 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
There are five basic variable types. The types are: Boolean (bool), integer (int), float (flt), vector (vec), string (str). In addition, there are three special types — number (num), any (any), and symbol (sym) — that are explained below. Multiple instances of the same type in a command signature are most often numbered (i1 i2 i3 … and so on).
>有五种基本变量类型。
>类型有:Boolean (bool)， integer (int)， float (flt)， vector (vec)， string (str)。
>此外，还有三种特殊类型——number (num)、any (any)和symbol (sym)，下面将对此进行解释。
>命令签名中相同类型的多个实例通常被编号(i1 i2 i3…等等)。

### bool 
A Boolean value (b), with six valid expressions: on off true false yes no. If no value is found, a Boolean is assumed to be true. No value, on, true, and yes are all equivalent. off, false, and no are all equivalent. Multiple instances in a command are numbered (b1 b2 b3 etc.).
>布尔值(b)，有6个有效表达式:on off true false yes no。如果没有找到值，则假定布尔值为真。No value, on, true和yes都是等价的。Off, false和no都是等价的。对命令中的多个实例进行编号(b1 b2 b3等)。

### int 
An integer (i), positive or negative. An integer cannot contain a decimal. Multiple instances in a command are numbered (i1 i2 i3 etc.).
>int整数(i)，正的或负的。整数不能包含小数。对命令中的多个实例进行编号(i1 i2 i3等)。

### ind 
An index (ind), positive integer. Multiple instances in a command are numbered (ind1 ind2 ind3 etc.).
>ind索引(ind)，正整数。对命令中的多个实例进行编号(ind1 ind2 ind3等)。

### flt 
A real number (f), positive or negative. It may be written in scientific e notation. Multiple instances in a command are numbered (f1 f2 f3 etc.).
>flt实数（f），正数或负数。它可以用科学e表示法书写。一个命令中的多个实例被编号（f1 f2 f3等）。

map 
A map (m) container of key-value pairs.
键值对的映射（m）容器。
#未完成 
vec 
A vector (v or v2 or v3) expressed as a matrix with one row. v2 and v3 denote that a 2D or 3D vector, respectively, is required. A plain “v” indicates that a vector of the same dimensionality as the code is required, that is, a 3D vector is required if the code is a 3D code, and a 2D vector is required if the code is a 2D code. In FLAC3D, v always indicates a 3D vector. When more than one vector of the same type in is required in a command these are distinguished with underscore-appended letters (v2_a v2_b or v_a v_b, etc.).
>用一行矩阵表示的向量(v或v2或v3)。
v2和v3分别表示需要一个2D或3D向量。
纯“v”表示需要一个与代码相同维度的向量，即如果代码是3D代码，则需要一个3D向量，如果代码是2D代码，则需要一个2D向量。
在FLAC3D中，v总是表示一个3D向量。
当一个命令中需要多个相同类型的向量时，这些向量用加下划线的字母(v2_a v2_b或v_a v_b等)进行区分。

str 
A string (s) of alphanumeric characters. Multiple instances in a command are numbered (s1 s2 s3 etc.).
str由字母数字组成的字符串。
一个命令中的多个实例被编号(s1 s2 s3等)。

num 
A number (n), for which either a flt or an int is valid. Multiple instances in a command are numbered (n1 n2 n3 etc.).
num一个数字(n)，对于它flt或int都是有效的。
一个命令中的多个实例被编号(n1 n2 n3等)。


any 
A catch-all for any (a) of the above types (though not sym). Multiple instances in a command are numbered (a1 a2 a3 etc.). 
This type is also indicated when a specific combination of types from those above is acceptable (for instance, the common case where a string s or an integer i may be supplied). When this is the case, the specific acceptable types are indicated in the explanatory text.
上述任何（A）类型的catch-all（尽管不是sym）。命令中的多个实例被编号（a1 a2 a3等）。当可以接受上述类型的特定组合时（例如，可能提供字符串s或整数i的常见情况），也会指示此类型。在这种情况下，具体可接受的类型在解释文本中指明。


sym 
A FISH symbol (name) — where name is the name of either a FISH variable or a FISH function.
sym FISH符号（名称）-其中name是FISH变量或FISH函数的名称。
