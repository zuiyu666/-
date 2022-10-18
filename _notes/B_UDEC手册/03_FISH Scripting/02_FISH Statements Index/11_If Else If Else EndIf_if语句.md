---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 8:31:56 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
if expr1 test expr2 then 
 … 
else if expr1 test expr2 then
 … 
else  
 … 
endif
```

These statements allow conditional execution of FISH code segments; else and else if are optional, and the word then may be omitted if desired. The item test consists of one of the following symbols, or symbol pairs:
>这些语句允许有条件地执行FISH代码段；else和else-if是可选的，如果需要，可以省略单词then。项目测试由以下符号之一或符号对组成：

```fish
=  #  >  <  >=  <=
```

The meanings are standard, except for #, which means “not equal.” The items expr1 and expr2 are any valid algebraic expressions (which can involve functions, UDEC variables, etc.). If the test is true, then the statements immediately following if are executed until else or endif is encountered. If the test is false, the statements between else and endif are executed if the else statement exists; otherwise, control jumps to the first line after endif. All the given test symbols may be applied when expressions expr1 and expr2 evaluate to integers or floating-point values (or a combination of the two). If both expressions evaluate to strings, then only two tests are valid: = and #; all other operations are invalid for strings. Strings must match exactly for equality. Similarly, both expressions may evaluate to pointers, but only = and # tests are valid.
>除#表示“不相等”外，其含义是标准的。expr1和expr2项是任何有效的代数表达式（可能涉及函数、UDEC变量等）。如果测试为true，则在遇到else或endif之前，将执行紧跟在If后面的语句。如果测试为false，如果else语句存在，则执行else和endif之间的语句；否则，控件跳到endif之后的第一行。当表达式expr1和expr2的计算结果为整数或浮点值（或两者的组合）时，可以应用所有给定的测试符号。如果两个表达式的计算结果都是字符串，则只有两个测试有效：=和#；所有其他操作对字符串无效。字符串必须完全匹配才能相等。类似地，这两个表达式都可以计算为指针，但只有=和#测试有效。

IF … elseIF … else … endif clauses can be nested to any depth.
>IF…elseIF…elle…endif子句可以嵌套到任何深度。

