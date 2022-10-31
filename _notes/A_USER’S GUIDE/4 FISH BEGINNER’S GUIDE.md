---
aliases: 
tags: 
width:
date created: 星期三, 十月 5日 2022, 6:54:20 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---

## 4.1 Introduction and Overview
*介绍和概述*
FISH is a programming language embedded within UDEC that enables the user to define new variables and functions. These functions may be used to extend UDEC's usefulness or add userdefined features. For example, new variables may be plotted or printed, special model generators may be implemented, servo control may be applied to a numerical test, unusual distributions of properties may be specified, and parameter studies may be automated.
>FISH是一种嵌入UDEC的编程语言，使用户可以定义新的变量和函数。这些功能可用于扩展UDEC的用途或添加用户定义的功能。例如，可以绘制或打印新变量，可以使用特殊模型生成器，可以将伺服控制应用于数值试验，可以指定特性的异常分布，并且可以自动进行参数研究。

FISH was developed in response to requests from users who wanted to do things with Itasca software that were either difficult or impossible to do with existing program structures. Rather than incorporate many new and specialized features into the standard code, an embedded language was provided so that users could write their own functions. Some useful FISH functions have already been written; a library of these is provided with the UDEC program (see the FISH library in the Help in UDEC.
>FISH是为了响应用户的请求而开发的，这些用户希望使用Itasca软件来处理现有程序结构难以处理或不可能处理的事情。它没有将许多新的和专门的特性纳入标准代码，而是提供了一种嵌入式语言，以便用户可以编写自己的函数。已经编写了一些有用的FISH函数；UDEC程序提供了这些文件的库（请参阅UDEC帮助中的FISH库）。

It is possible for someone without experience in programming to write simple FISH functions or to modify some of the simpler existing functions. Section 4.2 contains an introductory tutorial for non-programmers. However, FISH programs can also become very complicated (which is true of code in any programming language) – for more details, refer to the FISH section in the Help in UDEC.
>对于没有编程经验的人来说，可以编写简单的FISH函数或修改一些更简单的现有函数。第4.2节包含非程序员的入门教程。然而，FISH程序也可能变得非常复杂（任何编程语言中的代码都是如此）-有关更多详细信息，请参阅UDEC帮助中的FISH部分。

As with all programming tasks, FISH functions should be constructed in an incremental fashion, checking operations at each level before moving on to more complicated code. FISH does less error-checking than most compilers, so all functions should be tested on simple data sets before they are used for real applications. However, the built in text editor in the GUI wil flag incorrect FISH functions.
>与所有编程任务一样，FISH函数应该以增量的方式构造，在进入更复杂的代码之前检查每个级别的操作。FISH比大多数编译器做的错误检查更少，所以所有函数在用于实际应用之前都应该在简单的数据集上进行测试。然而，GUI中的内置文本编辑器将标记不正确的FISH函数。

FISH programs are simply embedded in a normal UDEC data file (lines following the word fish define are processed as a FISH function); the function terminates when the word end is encountered.
Functions may invoke other functions, which may invoke others, and so on. The order in which functions are defined does not matter, as long as they are all defined before they are used (e.g., invoked by a UDEC command). Since the compiled form of a FISH function is stored in UDEC's memory space, the [[model save command|model save command]] saves the function and the current values of associated variables.
>FISH程序只是嵌入到普通的UDEC数据文件中（FISH define一词后面的行作为FISH函数处理）；当遇到单词end时，函数终止。
>函数可以调用其他函数，这些函数可能会调用其他函数等等。函数的定义顺序无关紧要，只要它们在使用之前都已定义好（例如，由UDEC命令调用）。由于FISH函数的编译形式存储在UDEC的内存空间中，因此模型保存命令保存函数和相关变量的当前值。

All of the FISH language rules and intrinsic functions are discussed in the FISH section in the Help in UDEC.
>UDEC帮助中的FISH部分讨论了所有FISH语言规则和内部函数。

This includes rules for syntax, data types, arithmetic, variables and functions. All FISH language names are described in the FISH section in the Help in UDEC.
>这包括语法、数据类型、算术、变量和函数的规则。UDEC帮助中的FISH部分描述了所有FISH语言名称。

## 4.2 Beginner's Guide and Tutorial
This section is intended for people who have run UDEC (at least for simple problems) but have not used the FISH language; no programming experience is assumed. To get the maximum benefit from the examples given here, you should try them out with UDEC running interactively. The short programs may be typed in directly. After running an example, give the UDEC command model new, to “wipe the slate clean,” ready for the next example. Alternatively, the more lengthy programs may be created on file and called when required.
>本节适用于运行UDEC（至少针对简单问题）但未使用FISH语言的人员；假设没有编程经验。为了从这里给出的示例中获得最大的好处，您应该使用UDEC交互运行来尝试它们。短程序可以直接键入。运行完一个示例后，给UDEC命令模型添加新的，以“清除石板”，为下一个示例做好准备。或者，可以在文件中创建更长的程序，并在需要时调用。

Type the lines in Example 4.1 after UDEC's command prompt, pressing \<Enter\> at the end of each line.
>在UDEC命令提示符后键入示例4.1中的行，在每行末尾按\<Enter\>。

Example 4.1 Defining a FISH function
```fish
model new
fish def abc
abc = 22 * 3 + 5
end
```

Note that the command prompt changes to Def> after the first line has been typed in; then it changes back to the usual prompt when the end command is entered. This change in prompt lets you know whether you are sending lines to UDEC or to FISH. Normally, all lines following the fish define statement are taken as part of the definition of a FISH function (until the end statement is entered). However, if you type in a line that contains an error (e.g., you type the = sign instead of the + sign), then you will get the UDEC prompt back again. In this case, you should give the model new command and try again from the beginning. Since it is very easy to make mistakes, FISH programs are normally typed into a file using the editor. These are then called into UDEC just like a regular UDEC data file. We will describe this process later; for now, we'll continue to work interactively. Assuming that you typed in the preceding lines without error, and that you now see the UDEC prompt udec:, you can “execute” the function abc,* defined earlier in Example 4.1 by typing the line
>请注意，**输入第一行后，命令提示符变为Def\>；然后，当输入end命令时，它会变回通常的提示。这个提示符的更改让您知道是向UDEC还是向FISH发送行**。通常，fish define语句后面的所有行都被视为fish函数定义的一部分（直到输入end语句）。但是，如果您键入包含错误的行（例如，您键入=符号而不是+符号），那么您将再次得到UDEC提示符。在这种情况下，您应该向模型发出新命令，然后从头开始重试。由于很容易出错，FISH程序通常使用编辑器键入文件。然后，它们被调用到UDEC中，就像普通的UDEC数据文件一样。我们稍后将描述这个过程；现在，我们将继续交互工作。假设您在前面的行中输入了正确的内容，并且现在看到了UDEC提示符UDEC:，**那么您可以通过输入以下行来“执行”前面示例4.1中定义的函数abc**

```fish
;print abc
这里最好使用fish list @abc
```

The message **abc = 71** should appear on the screen. By defining the symbol abc (using the fish define ... end construction, as in Example 4.1), we can now refer to it in many ways using UDEC commands. Note that any FISH function or variable must be preceeded by the “@” character when used in a command outside of a FISH function. This also applies to usage inside of a command ... end command.
>屏幕上应显示消息**abc=71**。通过定义符号abc（使用fish define…end构造，如示例4.1所示），我们现在可以使用UDEC命令以多种方式引用它。请注意，在FISH函数之外的命令中使用任何FISH功能或变量时，必须以“@”字符开头。这也适用于命令…end命令内部的用法。

For example, the fish list @abc command causes the value of the FISH symbol abc to be displayed; the value is computed by the series of arithmetic operations in the line abc = 22 * 3 + 5
>例如，fish list@abc命令会显示fish符号abc的值；该值由abc=22\*3+5行中的一系列算术运算计算得出

This is an “assignment statement.” If an equal sign is present, the expression on the right-hand side of the equal sign is evaluated and given to the variable on the left-hand side. Note that arithmetic operations follow the usual conventions: addition, subtraction, multiplication and division are done with the signs +, -, \* and /, respectively. The sign ˆ denotes “raised to the power of.”
>这是一个“赋值语句”。如果存在等号，等号右侧的表达式将被求值并赋给左侧的变量。注意，算术运算遵循通常的约定：加法、减法、乘法和除法分别用+、-、\*和\/符号完成。符号ˆ表示“提升到的力量”

We now type in a slightly different program (using the command model new to erase the old one):
>现在，我们输入一个稍有不同的程序（使用命令model new删除旧程序）：

Example 4.2 Using a variable
```fish
model new
fish def abc
hh = 22
abc = hh * 3 + 5
end
```

Here we introduce a “variable,” hh, which is given the value of 22 and then used in the next line. If we give the command fish list @abc, then exactly the same output as in the previous case appears.
However, we now have two FISH symbols; they both have values, but one (abc) is known as a “function” and the other (hh) as a “variable.” The distinction is as follows.
>这里我们引入一个“变量”hh，它的值为22，然后在下一行中使用。如果我们给出命令fish-list@abc，那么会出现与前一个例子完全相同的输出。
>然而，我们现在有两个FISH符号；它们都有值，但其中一个（abc）被称为“函数”，另一个（hh）被称之为“变量”。区别如下。

When a FISH symbol name is mentioned (e.g., in a fish list statement), the associated function is executed if the symbol corresponds to a function. However, if the symbol is not a function name, then the current value of the symbol is used.
>当提及FISH符号名称时（例如，在FISH list语句中），如果符号对应于函数，则执行相关函数。但是，如果符号不是函数名，则使用符号的当前值。

The following experiment may help to clarify the distinction between variables and functions.
(Before doing the experiment, note that UDEC's fish set command can be used to set the value of any user-defined FISH symbol, independent of the FISH program in which the symbol was introduced.) Now type in the following lines without giving the model new command, since we want to keep our previously entered program in memory.
>以下实验可能有助于澄清变量和函数之间的区别。
（在进行实验之前，请注意，UDEC的fish set命令可用于设置任何用户定义的fish符号的值，而不依赖于引入该符号的fish程序。）现在输入以下行，而不给model新命令，因为我们希望将之前输入的程序保存在内存中。

Example 4.3 SETting variables
```fish
fish set @abc=0
fish set @hh=0
fish list @hh
fish list @abc
fish list @hh
```

The fish set command sets the values of both abc and hh to zero. Since hh is a variable, the first fish list command simply displays the current value of hh, which is zero. The second fish list command causes abc to be executed (since abc is the name of a function); the values of both hh and abc are thereby recalculated. Accordingly, the third fish list statement shows that hh has indeed been reset to its original value. As a test of your understanding, you should type in the slightly modified sequence shown in Example 4.4 and figure out why the displayed answers are different.
>fish set命令将abc和hh的值都设置为零。由于hh是一个变量，因此**第一个fish list命令只显示hh的当前值**，即零。**第二个fish list命令导致执行abc（因为abc是函数名）；因此，重新计算hh和abc的值**。因此，**第三个fish list语句显示hh确实已重置为其原始值**。为了测试您的理解力，您应该键入示例4.4中稍微修改的顺序，并找出显示的答案不同的原因。

Example 4.4 Test your understanding of function and variable names
```fish
model new
fish def abc
abc = hh * 3 + 5
end
fish set @hh=22
fish list @abc
fish set @abc=0 @hh=0
fish list @hh
fish list @abc
fish list @hh
```

At this stage, it may be useful to list the most important UDEC commands that directly refer to simple FISH variables or functions. (In Table 4.1, var stands for the name of the variable or function.)
>在此阶段，列出直接引用简单FISH变量或函数的最重要的UDEC命令可能很有用。（在表4.1中，var代表变量或函数的名称。）

Table 4.1 Commands that directly refer to FISH names
>表4.1直接引用FISH名称的命令

![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210161311023.png)

We have already seen examples of the first two (refer to Examples 4.3 and 4.4); the third case is useful when histories of things that are not provided in the standard UDEC list of history variables are required. Example 4.5 shows how this can be done.
>我们已经看到了前两个示例（参见示例4.3和4.4）；当需要标准UDEC历史变量列表中未提供的历史记录时，第三种情况非常有用。示例4.5显示了如何做到这一点。

Example 4.5 Capturing the history of a FISH variable
```fish
model new
block create polygon 0,0 0,10 10,10 10,0
block zone gen edge 10
block property mat=1 dens 1000 bulk 1e9 shear 0.7e9
block gridpoint apply vel-y 0.0 range pos-y -0.01, 0.01
block mech grav 0 -10
fish def stress_y
zoneIdx = bl.zone(block.head)
stress_y = bl.zo.str.yy(zoneIdx)
end
fish history @stress_y
block cycle 200
```

In this example, a history of the vertical stress in one zone is recorded. The symbols block.zone(), block.head and block.zone.stress.yy() are predefined names that permit access to UDEC's data structures. We obtained the index of the first zone in the one block in our model. With that index we can access a number of parameters associated with that zone. In this case, we have accessed the vertical stress and monitored its change in a history.
>在这个例子中，记录了一个区域内垂直应力的历史。符号块。zone（），块。头部和block.zone.stress.yy() 是允许访问UDEC数据结构的预定义名称。我们获得了模型中一个区块中第一个区域的索引。通过该索引，我们可以访问与该区域相关的许多参数。在这种情况下，我们访问了垂直应力并监测了其历史变化。

In addition to the predefined variable names mentioned above, there are many other predefined objects available to a FISH program. These fall into several classes. One such class consists of scalar variables, which are single numbers. For example:
>除了上面提到的预定义变量名之外，FISH程序还可以使用许多其他预定义对象。这些可分为几类。其中一个类由标量变量组成，这些变量是单个数字。完整列表见UDEC帮助中的FISH索引。

Another useful class of built-in objects is the set of intrinsic functions, which enable things like sines and cosines to be calculated from within a FISH program. A complete list is provided in the FISH index in the Help in UDEC. 
>另一类有用的内置对象是一组内部函数，它可以在FISH程序中计算正弦和余弦。UDEC帮助中的FISH索引中提供了完整列表。

An example in the use of intrinsic functions will be presented later, but now we must discuss one more way a UDEC data file can make use of user-defined FISH names:
>稍后将介绍使用内部函数的示例，但现在我们必须讨论UDEC数据文件使用用户定义的FISH名称的另一种方法：

Wherever a number is expected in a UDEC input line, you may substitute the name of a FISH variable or function.
>只要UDEC输入行中需要数字，就可以替换FISH变量或函数的名称。

This simple statement is the key to a very powerful feature of FISH that allows such things as ranges, applied stresses, properties, etc. to be computed in a FISH function and used by UDEC input in symbolic form. Hence, parameter changes can be made very easily, without the need to change many numbers in an input file.
>这个简单的语句是FISH的一个非常强大的特性的关键，它允许在FISH函数中计算范围、施加的应力、属性等，并由UDEC以符号形式输入使用。因此，可以非常容易地更改参数，而无需更改输入文件中的许多数字。

As an example, let us assume that we know the Young's modulus and Poisson's ratio of a material.
Since UDEC needs the bulk and shear moduli, these may be derived with a FISH function, using Eqs.
>例如，假设我们知道材料的杨氏模量和泊松比。
由于UDEC需要体积模量和剪切模量，因此可以通过FISH函数，使用公式。

$$\begin{aligned}
G &=\frac{E}{2(1+v)}\\  
K &=\frac{E}{3(1-2 \nu)}
\end{aligned}$$   
Coding Eqs. (4.1) and (4.2) into a FISH function (called derive) can then be done as shown in Example 4.6:
>可以如示例4.6所示将（4.1）和（4.2）转换为FISH函数（称为派生）：

Example 4.6 FISH functions to calculate bulk and shear moduli
```fish
model new
fish def derive
s_mod = y_mod / (2.0 * (1.0 + p_ratio))
b_mod = y_mod / (3.0 * (1.0 - 2.0 * p_ratio))
end
fish set @y_mod = 5e8 @p_ratio = 0.25
@derive
fish list @b_mod
fish list @s_mod
```

Note that here we execute the function derive by giving its name by itself on a line; we are not interested in its value, only what it does. If you run this example, you will see that values are computed for the bulk and shear moduli, b mod and s mod, respectively. These can then be used, in symbolic form, in UDEC input as shown in Example 4.7:
>注意，这里我们通过在一行上给出函数名来执行函数derive；我们对它的价值不感兴趣，只对它的作用感兴趣。如果运行此示例，您将看到分别计算了体积模量和剪切模量b mod和s mod的值。然后可以在UDEC输入中以符号形式使用，如示例4.7所示：

Example 4.7 Using symbolic variables in UDEC input
>示例4.7在UDEC输入中使用符号变量

```fish
block create polygon 0,0 0,10 10,10 10,0
block zone gen edge 10
block zone cmodel assign elastic bulk=@b_mod shear=@s_mod
list zone property bulk
list zone property shear
```

The validity of this operation may be checked by printing out bulk and shear in the usual way. In these examples, our property input is given via the fish set command (i.e., to variables y mod and p ratio, which stand for Young's modulus and Poisson's ratio, respectively).
>此操作的有效性可以通过以通常方式打印出批量和剪切来检查。在这些例子中，我们的属性输入是通过fish set命令给出的（即变量y mod和p ratio，分别代表杨氏模量和泊松比）。

Note that there is great flexibility in choosing names for FISH variables and functions. For instance, the underscore character (\_) may be included in a name. Names must begin with a non-number and must not contain any of the arithmetic operators (+, -, /, * or ˆ).
>请注意，在为FISH变量和函数选择名称时有很大的灵活性。例如，名称中可能包含下划线字符（\_）。**名称必须以非数字开头，并且不能包含任何算术运算符**（+、-、\/、\*或\ 710；）。

In the preceding examples, we checked the computed values of FISH variables by giving their names explicitly as arguments to a fish list command. Alternatively, we can list all current variables and functions. A printout of all current values, sorted alphabetically by name, is produced by giving the command **fish list**
>在前面的示例中，我们检查了FISH变量的计算值，方法是将它们的名称显式地作为FISH list命令的参数。或者，我们可以列出所有当前变量和函数。通过给出命令**fish-list**，可以生成所有当前值的打印输出，按名称的字母顺序排序

We now examine ways decisions can be made, and repeated operations done, in FISH programs.
Two FISH statements allow specified sections of a program to be repeated many times:
>现在，我们研究在FISH计划中可以做出决策的方式以及重复操作的方式。
两个FISH语句允许程序的特定部分重复多次：

13_Loop EndLoop_循环

The words loop and endloop are FISH statements, the symbol var stands for the loop variable, and expr1 and expr2 stand for expressions (or single variables). Example 4.8 shows the use of a loop (or repeated sequence) to produce the sum and product of the first ten integers.
>单词loop和endloop是FISH语句，符号var代表循环变量，expr1和expr2代表表达式（或单个变量）。示例4.8显示了使用循环（或重复序列）来生成前十个整数的和和乘积。

Example 4.8 Controlled loop in FISH
```fish
model new
fish def xxx
sum = 0
prod = 1
loop n (1,10)
sum = sum + n
prod = prod * n
end_loop
end
@xxx
fish list @sum
fish list @prod
ret
```

In this case, the loop variable n is given successive values from 1 to 10, and the statements inside the loop (between the loop and endloop statements) are executed for each value. As mentioned, variable names or an arithmetic expression could be substituted for the numbers 1 or 10.
>在这种情况下，循环变量n被赋予从1到10的连续值，循环内的语句（在循环和endloop语句之间）针对每个值执行。如前所述，变量名或算术表达式可以替换数字1或10。

A practical use of the loop construct is to install a nonlinear initial distribution of elastic moduli in a UDEC grid. Suppose that the Young's modulus at a site is given by Eq. (4.3)
>回路结构的实际用途是在UDEC网格中安装弹性模量的非线性初始分布。假设场地的杨氏模量由公式（4.3）给出

$$E=E_{\circ}+c \sqrt{z}        （4.3）$$
where z is the depth below surface, and c and E◦ are constants. We write a FISH function to install appropriate values of bulk and shear modulus in the grid, as in Example 4.9:
>式中，z是表面以下的深度，c和E◦ 是常量。我们编写FISH函数，在网格中安装适当的体积模量和剪切模量值，如示例4.9所示：

Example 4.9 Applying a nonlinear initial distribution of moduli
```fish
model new
;
block tolerance corner-round-length 0.1
block create polygon 0 -30 0 0 30 0 30 -30
block cut joint-set angle 36 0 trace 50 0 gap 0 0 spacing 8 0
block cut joint-set angle -58 0 trace 50 0 gap 0 0 spacing 12 0
block zone gen edge 1
block zone cmodel assign mohr-c
;
fish def install
; smoothness is the elevation tolerance on changing moduli
bi = block.head
loop while bi # 0
zi = bl.zone(bi)
loop while zi # 0
z_depth = float(int(-bl.zone.pos.y(zi)/smoothness))
y_mod = y_zero + cc * math.sqrt(z_depth)
_shear = y_mod / (2.0*(1.0+p_ratio))
_bulk = y_mod / (3.0*(1.0-2.0*p_ratio))
bl.zone.prop(zi,'bulk') = _bulk
bl.zone.prop(zi,'shear') = _shear
zi = bl.zone.next(zi)
end_loop
bi = bl.next(bi)
endloop
end
;
fish set @p_ratio=0.25 @y_zero=1e7 @cc=1e8 @smoothness=6.0
block property mat 1 dens 2000 bulk 1e8 shear 1e7
@install
ret
```

例子中用到的命令、语法
block cut command

Again, you can verify correct operation of the function by printing or plotting shear and bulk moduli. A plot of the model is shown in Figure 4.1:
>同样，您可以通过打印或绘制剪切和体模来验证函数的正确操作。模型示意图如图4.1所示:

Figure 4.1 Model constructed in Example 4.9
>图4.1例4.9构建的模型

![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210170847141.png)


In the function install, we have two loops: the outer loop scans through the blocks in the model, while the inner loop scans through the list of zones within each block. The parameter smoothness controls the tolerance on the change of the moduli, allowing the creation of strata of common moduli. We obtain the depth of the zone with the function block.zone.pos.y(zi); the value is smoothed to provide a more distinct banding. The elastic moduli are then computed according to our rule and assigned to the zones via the block.zone.prop(zi,“bulk”) function call.
>在函数安装中，我们有两个循环:外部循环扫描模型中的块，而内部循环扫描每个块中的区域列表。
参数的平滑度控制了模量变化的公差，允许形成公共模量层。
我们通过函数block.zone.pos.y(zi)得到区域的深度;
该值被平滑以提供更清晰的条带。
然后根据我们的规则计算弹性模量，并通过block.zone.prop(zi，“bulk”)函数调用分配给区域。

Having seen several examples of FISH programs, let's briefly examine the question of program syntax and style. There is no limit to the length of a FISH statement. However, for readability one may want to split a statement into two lines. This may be done useing an elipsis for a continuation or may be done using intermediate values. Example 4.10 shows how this can be done:
>看过几个FISH程序的例子后，让我们简要地研究一下程序语法和样式的问题。
FISH语句的长度没有限制。
然而，为了可读性，可能需要将语句分成两行。
这可以使用延续的省略号来完成，也可以使用中间值来完成。
例4.10展示了如何做到这一点:

Example 4.10 Splitting lines
```fish
model new
fish def long_sum ;example of a sum of many things
temp1 = v1 + v2 + v3 + v4 + v5 + v6 + v7 + v8 + v9 + v10
long_sum = temp1 + v11 + v12 + v13 + v14 + v15
end
```

In this case, the sum of 15 variables is split into two parts. Also note also the use of the semicolon in line 2 of Example 4.10 to indicate a comment. Any characters that followa semicolon are ignored by the FISH compiler, but they are echoed to the log file. It is good programming practice to annotate programs with informative comments. Someof the programs have been shownwith indentation (i.e., space inserted at the beginning of some lines to denote a related group of statements). Any number of space characters may be inserted (optionally) between variable names and arithmetic operations to make the program more readable. Again, it is good programming practice to include indentation to indicate things like loops, conditional clauses and so on. Spaces in FISH are significant in the sense that space characters may not be inserted into a variable or function name.
>在本例中，15个变量的总和被分成两部分。
还要注意在例4.10的第2行中使用分号来表示注释。
分号后面的任何字符都会被FISH编译器忽略，但是它们会被反馈到日志文件中。
用有用的注释注释程序是一种很好的编程实践。
有些程序采用了缩进(即，在某些行的开头插入空格，表示一组相关语句)。
可以在变量名和算术运算之间插入任意数量的空格字符(可选)，以使程序更具可读性。
同样，使用缩进来表示循环、条件子句等是一种很好的编程实践。
FISH中的空格非常重要，因为空格字符不能插入到变量或函数名中。

One other topic that should be addressed now is that of variable type. You may have noticed, when printing out variables from the various program examples, that numbers are either printed without decimal points, or in “E-format” (i.e., as a number with an exponent denoted by “E”). At any instant in time, a FISH variable or function name is classified as one of many types, the most common three types are: integer, floating-point or string. These types may change dynamically, depending on context, but the casual user should not normally have to worry about the type of a variable, since it is set automatically. Consider Example 4.11:
>现在应该讨论的另一个主题是变量类型。
您可能已经注意到，当从各种程序示例中打印出变量时，数字要么不带小数点，要么以“E格式”打印(即，作为带有指数的数字，用“E”表示)。
在任何时候，FISH变量或函数名都被归类为多种类型之一，最常见的三种类型是:整数、浮点或字符串。
这些类型可能根据上下文动态更改，但普通用户通常不必担心变量的类型，因为它是自动设置的。
考虑示例4.11:

Example 4.11 Variable types
```fish
model new
fish def haveone
aa = 2
bb = 3.4
cc = 'Have a nice day'
dd = aa * bb
ee = cc + ', old chap'
end
@haveone
fish list
```

The resulting screen display is.
>屏幕显示为：

![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210170853565.png)

The variables aa, bb and cc are converted to integer, float and string, respectively, corresponding to the numbers (or strings) that were assigned to them. Integers are exact numbers (without decimal points), with a limit of about 10 decimal places (after which they will be converted to a real); floating-point numbers have 15 digit precision, with a much greater range than integers; string variables are arbitrary sequences of characters. There are various rules for conversion between the three types. For example, dd becomes a floating-point number because it is set to the product of a floating-point number and an integer; the variable ee becomes a string because it is the sum (concatenation) of two strings.
>变量aa、bb和cc分别被转换为整数、浮点数和字符串，对应于分配给它们的数字(或字符串)。
整数是精确数字(没有小数点)，限制在大约10位小数点后将被转换为实数;
浮点数有15位精度，范围比整数大得多;
字符串变量是任意的字符序列。
这三种类型之间的转换有多种规则。
例如，dd成为一个浮点数，因为它被设置为浮点数与整数的乘积;
变量ee成为一个字符串，因为它是两个字符串的和(连接)。

There is another language element in FISH that is commonly used: the if statement. Three statements allow decisions to be made within a FISH program:
>FISH中还有另一个常用的语言元素:if语句。
三个语句允许在FISH程序中做出决策:

![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210170855448.png)


These statements allowconditional execution of FISH program segments; else and then are optional.
The item test consists of one of the following symbols or symbol-pairs:
>这些语句允许有条件地执行FISH程序段;
Else和then是可选的。
项目测试由以下符号或符号对之一组成:

= # > < >= <=

The meanings are standard except for #, which means “not equal.” The items expr1 and expr2 are any valid expressions or single variables. If the test is true, then the statements immediately following if are executed until else or endif is encountered. If the test is false, the statements between else and endif are executed if the else statement exists; otherwise, the program jumps to the first line after endif. The action of these statements is illustrated in Example 4.12:
>除了**表示“不相等”的#之外**，其他含义都是标准的。
项目expr1和expr2是任何有效表达式或单个变量。
如果测试为true，则执行紧接在If后面的语句，直到遇到else或endif。
如果测试为false，如果else语句存在，则执行else和endif之间的语句;
否则，程序将跳转到endif之后的第一行。
例4.12说明了这些语句的作用:

Example 4.12 Action of the IF ELSE ENDIF construct
>例4.12 IF ELSE ENDIF构造的动作

```fish
model new
fish def abc
if xx > 0 then
abc = 33
else
abc = 11
end_if
end
fish set @xx = 1
fish list @abc
fish set @xx = -1
fish list @abc
```

The displayed value of abc in Example 4.12 depends on the set value of xx. You should experiment with different test symbols (e.g., replace > with <).
>例4.12中abc的显示值依赖于xx的设置值。
您应该尝试使用不同的测试符号(例如，将>替换为<)。

Until now, our FISH programs have been invoked from UDEC, either by using the fish list command or by giving the name of the function on a separate line of UDEC input. It is also possible to do the reverse (i.e., to give UDEC commands from within a FISH function). Most valid UDEC commands can be embedded between two FISH statements:
>到目前为止，我们的FISH程序都是从UDEC调用的，方法要么是使用FISH list命令，要么是在UDEC输入的单独一行上给出函数名。
也可以做相反的事情(例如，从FISH函数中给出UDEC命令)。
大多数有效的UDEC命令可以嵌入在两个FISH语句之间:

```fish
command
endcommand
```

There are two main reasons for sending out UDEC commands from a FISH program. First, it is possible to use a FISH function to perform operations that are not possible using the predefined variables that we already discussed. Second, we can control a complete UDEC run with FISH.
remember that FISH functions and variables must be preceeded by a “@” inside of command endcommand.
>从FISH程序发送UDEC命令主要有两个原因。
首先，可以使用FISH函数执行使用我们已经讨论过的预定义变量无法执行的操作。
其次，我们可以用FISH控制一个完整的UDEC运行。
记住，FISH函数和变量必须在命令endcommand中前面加上一个“@”。

As an illustration of the first use of the command statement, we can write a FISH program to place a number of cable elements around a specific segment of a tunnel.
>作为命令语句第一次使用的示例，我们可以编写一个FISH程序，在隧道的特定段周围放置一些电缆元素。

Starting and ending angles (counterclockwise from the positive x-axis) are specified. The variable radius1 is the radius of the tunnel, and radius2 gives the outer ends of the cables. Example 4.13 shows the code:
>指定了起始角和结束角(从正x轴逆时针方向)。
变量radius1是隧道的半径，radius2是电缆的外端。
例4.13显示了代码:

Example 4.13 Automated placing of cable elements

```fish
model new
fish def setup
; Create vars for later use
; 创建变量以供以后使用
xCentre = 0.0 ; x-coord of tunnel centre
yCentre = 0.0 ; y-coord of tunnel centre
theta1 = 10.0 ; starting angle for cables
theta2 = 160.0 ; ending angle for cables
; radius1是隧道的半径，radius2是电缆的外端
; (don’t wrap back on theta1)
radius1 = 8.0 ; radius of tunnel
radius2 = 16.0 ; ending radius for remote end of cables
nCables = 15 ; number of cables
end
fish def place_cables
; This example places cable elements along a given arc of tunnel.
; 本例将电缆单元沿给定的隧道弧线放置。
; calculate angle increment between successive cables
; 计算相邻电缆之间的角度增量
theta1 = math.degrad * theta1
theta2 = math.degrad * theta2
_angInc = (theta2 - theta1) / float(nCables - 1)
_ang = theta1
; get endpoint coordinates
loop ii (1, nCables)
_x1 = radius1 * math.cos(_ang) + xCentre
_y1 = radius1 * math.sin(_ang) + yCentre
_x2 = radius2 * math.cos(_ang) + xCentre
_y2 = radius2 * math.sin(_ang) + yCentre
; place the cable
command
cable @_x1 @_y1 @_x2 @_y2 5 2 3
endcommand
_ang = _ang + _angInc
endloop
end
@setup
block create polygon -25.0, -25.0 -25.0, 25.0 25.0, 25.0 25.0, -25.0
block cut split 0.0, -25.0 0.0, 25.0
block cut split -25.0, 0.0 25.0, 0.0
block cut tunnel 0.0, 0.0, @radius1, 16
block zone gen edge 10
block delete range annulus center 0.0, 0.0 rad 0 8
@place_cables
```

Each time through the loop, rectangular coordinates are calculated from the polar data in the model.
These coordinates are passed to the CABLE command inside the command – endcommand structure, where the cable element is actually created. The results can be seen in Figure 4.2: UDEC
>每次通过循环，从模型中的极坐标数据计算矩形坐标。
这些坐标被传递给command - endcommand结构中的CABLE命令，CABLE元素就是在这个结构中实际创建的。
结果见图4.2:UDEC

Figure 4.2 Model constructed in Example 4.13
![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210170859891.png)


