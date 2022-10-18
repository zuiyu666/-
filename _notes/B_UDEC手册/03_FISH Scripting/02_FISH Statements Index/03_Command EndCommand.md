---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 8:24:02 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```fish
command
 …
endcommand
```

UDEC commands may be inserted between this pair of FISH statements; the commands will be interpreted when the FISH function is executed. There are a number of restrictions concerning the embedding of UDEC commands within a FISH function. The model new and model restore commands cannot be invoked from within a FISH function. The lines found between a command — endcommand pair are simply stored by FISH as a list of symbols; they are not checked at all, and the function must be executed before any errors can be detected.
>UDEC命令可以插入这对FISH语句之间；执行FISH函数时，将解释这些命令。在FISH函数中嵌入UDEC命令有很多限制。无法从FISH函数内调用模型新建和模型还原命令。在命令endcommand对之间找到的行被FISH简单地存储为符号列表；它们根本没有被检查，并且必须在检测到任何错误之前执行该函数。

A FISH function definition may appear within a command — endcommand pair, and may itself contain the command statement. A function that is the subject of a callback event may contain the command statement. However, this construction should be used with caution, and avoided if possible. A FISH definition inside of the command — endcommand pair should not redefine the FISH function in which it is currently executing.
>FISH函数定义可能出现在命令端命令对中，并且本身可能包含命令语句。回调事件的主题函数可能包含命令语句。然而，应谨慎使用这种结构，并尽可能避免。命令-endcommand对内的FISH定义不应重新定义其当前正在执行的FISH函数。

Comment lines (starting with ;) are taken as UDEC comments, rather than FISH comments; it may be useful to embed an explanatory message within a function, to be printed out when the function is invoked. If the echo mode is off (program echo off), then any UDEC commands coming from the function are not displayed to the screen or recorded to the log file.
>注释行（以；开头）被视为UDEC评论，而非FISH评论；在函数中嵌入解释性消息，以便在调用函数时打印出来，这可能很有用。如果echo模式关闭（程序echo关闭），则来自该功能的任何UDEC命令都不会显示在屏幕上或记录到日志文件中。
