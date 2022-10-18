---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 8:14:52 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
define function-name <(arg ...)>
 …
end
```

The FISH program between the define and end statements is compiled and stored in UDEC’s memory space. The compiled version of the function is executed whenever its name is mentioned, as explained in Functions: Structure, Evaluation, and Calling Scheme. The function name does not need to be assigned a value in the program section that follows. Any tokens following the function name are interpreted as arguments to the function. These arguments must be given any time the function is to be executed (whether from a FISH statement or from the command line). See the Argument statement.
>定义语句和结束语句之间的FISH程序被编译并存储在UDEC的内存空间中。每当提到函数名称时，就会执行该函数的编译版本，如函数：结构、求值和调用方案中所述。函数名不需要在接下来的程序段中赋值。函数名后面的任何标记都被解释为函数的参数。在执行函数时，必须提供这些参数（无论是从FISH语句还是从命令行）。请参阅Argument语句。

The definition:(定义：)
```fish
define abc(one,two)
end
```

is equivalent to:(等于：)
```fish
define abc
   argument one
   argument two
end
```