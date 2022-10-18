---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 8:34:53 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
local name <= expression>
```
Create a local variable named “name.” From this point until the end of the function (the end statement), this variable will supersede any existing global symbol with the same name. The variable is only available inside the function, and ceases to exist once the function has completed execution. A separate copy of the variable is created for each function execution. The variable may be initialized with an optional assignment immediately after creation. For example:
>创建一个名为“name”的局部变量。从这一点到函数结束（end语句），此变量将取代任何具有相同名称的现有全局符号。变量只在函数内部可用，一旦函数执行完毕，变量就不再存在。为每个函数执行创建变量的单独副本。变量可以在创建后立即使用可选赋值进行初始化。例如：

```fish
local abc
```

creates a local variable abc, whose initial value is the integer zero. This:
>创建一个局部变量abc，其初始值为整数零：

```fish
local abc = one * two
```

creates a local variable whose initial value is the result of the expression one * two. Only one variable may be created per local statement. No argument statements may follow a local statement in a function.
>创建一个局部变量，其初始值是表达式1\*2的结果。每个局部语句只能创建一个变量。函数中的局部语句后面不能有参数语句。
