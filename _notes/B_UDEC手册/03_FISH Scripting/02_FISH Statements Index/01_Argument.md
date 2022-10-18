---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 8:17:45 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
argument name
```

Create a local variable in a manner similar to the way the local statement does, except that an initializing expression is not accepted. This is a special value that is taken as an argument to the FISH function in which it is contained. argument statements must precede any local statements. The argument statement can be used in addition to arguments provided in the define command.
>以与局部语句类似的方式创建局部变量，只是不接受初始化表达式。
这是一个特殊值，作为包含它的FISH函数的参数。
实参语句必须在任何局部语句之前。
除了define命令中提供的参数之外，还可以使用argument语句。

To execute the function, arguments must be given as parenthesis-bound lists, both in FISH statements and in the command line. For example, the function abc, defined as:
>要执行函数，参数必须以括号绑定列表的形式给出，在FISH语句和命令行中都是如此。
例如，函数abc，定义为:

```fish
DEFINE abc
   argument one
   argument two
END
```
may be called in FISH code as:
>可在FISH代码中称为:

```fish
var = abc(1.0, 2.0)
```
or referred to on the command line as:
>或者在命令行中被称为:

```fish
SET creep dt @abc(1.0,2.0)
```

Note that this is the same syntax used to provide array indices. The argument list is not necessary when assigning values to the function.
>注意，这与提供数组索引所用的语法相同。给函数赋值时不需要实参列表。

