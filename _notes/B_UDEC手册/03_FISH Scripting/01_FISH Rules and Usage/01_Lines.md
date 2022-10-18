---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
Lines
FISH programs can be embedded in a UDEC data file or may be entered directly into the console. Lines following the word define are taken to be statements of a FISH function; the function stops when the word end is encountered. A valid line of FISH code must take one of the following forms.
>FISH 程序可以嵌入到 UDEC 数据文件中，也可以直接输入到控制台中。单词定义后面的行被视为 FISH 函数的语句;该函数在遇到词尾时停止。有效的 FISH 代码行必须采用以下形式之一。

1. The line starts with a statement, such as if, loop, etc. (see “FISH statements”).
>该行以语句开头，例如 if、循环等（请参阅“FISH 语句”）。

2. The line contains one or more names of user-defined FISH functions, separated by spaces (for example, fun_1 fun_2 fun_3).
>该行包含用户定义的 FISH 函数的一个或多个名称，以空格分隔（例如，fun_1 fun_2 fun_3）。

3. The line consists of an assignment statement (i.e., the expression on the right of the = sign is evaluated, and the value is given to the variable or function name on the left of the = sign).
>该行由赋值语句组成（即，计算 = 符号右侧的表达式，并将值指定给 = 符号左侧的变量或函数名称）。

4. The line consists of a UDEC command, provided that the line is embedded in a section of FISH code delimited by command - endcommand.
>该行由 UDEC 命令组成，前提是该行嵌入在由命令 - endcommand 分隔的 FISH 代码部分中。

5. The line is blank or starts with a semicolon.
>该行为空或以分号开头。

FISH variables, function names, and statements must be spelled out in full—they cannot be truncated, unlike UDEC commands. Continuation lines are allowed with the ... control statement at the end of the line. FISH is “case-insensitive” at all times. Spaces are significant (unlike in FORTRAN) and serve to separate variables, keywords, etc.; no embedded blanks are allowed in variable or function names. 
>FISH 变量、函数名称和语句必须完整拼写出来 ，与 UDEC 命令不同，它们不能被截断。允许使用 ...控制语句在行的末尾。FISH 在任何时候都是“不区分大小写”的。空格是重要的（与FORTRAN不同），用于分隔变量，关键字等;变量或函数名称中不允许嵌入空格。

Extra spaces may be used to improve readability (for example, by indenting loops and conditional clauses). Any characters following a semicolon ( ; ) are ignored; comments may be embedded in a FISH program by preceding them with a semicolon. Blank lines may be embedded in a FISH program.
>可以使用额外的空格来提高可读性（例如，通过缩进循环和条件子句）。分号 （ ; ） 后面的任何字符都将被忽略;注释可以通过在注释前面加上分号来嵌入到 FISH 程序中。空白行可以嵌入到 FISH 程序中。