---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 8:21:16 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
caseof expr  
 … 
 case n  
 … 
endcase
```

The action of these control statements is similar to the FORTRAN-computed GOTO statement or C’s SWITCH statement. It allows control to be passed rapidly to one of several code segments, depending on the value of an index. The use of the keywords is illustrated:
>这些控制语句的操作类似于FORTRAN计算的GOTO语句或C的SWITCH语句。它允许根据索引的值将控制权快速传递给几个代码段中的一个。关键字的使用如下图所示：

```fish
caseof expr
  ; ................. default code here
  case i1
  ; ................. case i1 code here
  case i2
  ; ................. case i2 code here
  case i3
  ; ................. case i3 code here
endcase
```

The object expr following caseof can be any valid algebraic expression; when evaluated, it will be converted to an integer. The items i1, i2, i3, … must be integers (not symbols) in the range 0 to 255. If the value of expr equals i1, then control jumps to the statements following the case i1 statement; execution then continues until the next case statement is encountered. Control then jumps to the code following the endcase statement; there is no “fall-through” as in the C language. Similar jumps are executed if the value of expr equals i2, i3, and so on. If the value of expr does not equal the numbers associated with any of the case statements, then any code immediately following the caseof statement is executed, with a jump to endcase when the first case is encountered. If the value of expr is less than zero or greater than the greatest number associated with any of the cases, then an execution error is reported, and processing stops. The numbers n (e.g., i1, i2, i3) need not be sequential or contiguous, but no duplicate numbers may exist.
>caseof后面的对象表达式可以是任何有效的代数表达式；计算时，它将转换为整数。项目i1、i2、i3…必须是0到255范围内的整数（非符号）。如果expr的值等于i1，则控制跳转到case i1语句后面的语句；然后继续执行，直到遇到下一个case语句。控件然后跳转到endcase语句后面的代码；在C语言中没有“失败”。如果expr的值等于i2、i3等，则会执行类似的跳转。如果expr值不等于与任何case语句关联的数字，则会立即执行caseof语句后面的任何代码，并在遇到第一个case时跳转到endcase。如果expr的值小于零或大于与任何案例相关联的最大值，则会报告执行错误，并停止处理。数字n（例如，i1、i2、i3）不必是连续的或连续的，但可能不存在重复的数字。

caseof … endcase sections may be nested to any degree; there will be no conflict between case numbers in the different levels of nesting (e.g., several instances of case 5 may appear, provided that they are all associated with different nesting levels). The use of case statements allows rapid decisions to be made (much more quickly than for a series of if … endif statements). However, the penalty is that some memory is consumed; the amount of memory used depends on the maximum numerical value associated with the case statements. The memory consumed is one plus the maximum case number in double-words (four-byte units).
>caseof…endcase截面可以任意嵌套；不同嵌套级别中的案例编号之间不会发生冲突（例如，如果案例5的几个实例都与不同的嵌套级别相关联，那么它们可能会出现）。使用case语句可以快速做出决策（比使用一系列if…endif语句要快得多）。然而，代价是消耗了一些内存；使用的内存量取决于与case语句相关联的最大数值。消耗的内存为1加上以双字（四字节单位）表示的最大事例数。