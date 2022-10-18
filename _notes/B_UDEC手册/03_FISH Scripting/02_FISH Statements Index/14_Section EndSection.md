---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
section

 …

endsection
```

The FISH language does not have a “GO TO” statement. The section construct allows control to jump forward in a controlled manner. The statements section … endsection may enclose any number of lines of FISH code; they do not affect the operation in any way. However, an exit section statement within the scope of the section so defined will cause control to jump directly to the end of the section. Any number of these jumps may be embedded within the section. 
>FISH 语言没有“转到”语句。截面构造允许控件以受控方式向前跳转。语句部分...末端部分可以包含任意数量的 FISH 代码行;它们不会以任何方式影响操作。但是，在如此定义的节范围内的退出节语句将导致控件直接跳转到节的末尾。这些跳转的任意数量都可以嵌入到该部分中。

The endsection statement acts as a label, similar to the target of a GO TO statement in C or FORTRAN. The logic is cleaner, however, because control may not pass to any place outside of the defined section, and flow is always “downward.” Sections may not be nested; there may be many sections in a function, but they must not overlap or be contained within one another.
>结束部分语句充当标签，类似于 C 或 FORTRAN 中 GO TO 语句的目标。但是，逻辑更清晰，因为控制可能不会传递到定义部分之外的任何地方，并且流始终是“向下”的。截面不得嵌套;一个函数中可能有许多部分，但它们不能相互重叠或包含在内。