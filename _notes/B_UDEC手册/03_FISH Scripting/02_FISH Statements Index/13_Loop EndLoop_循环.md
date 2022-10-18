---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
# Loop EndLoop

Loop EndLoop
The four valid loop constructions are:
>四种有效的循环是：

```fish
loop <local> var (expr1, expr2)
…
endloop
or
loop while expr1 test expr2
…
endloop
or
loop for (initialize, test, modify)
…
endloop
or
loop foreach <local> var expr1

…
endloop
```

The FISH program lines between loop and endloop are executed repeatedly until certain conditions are met.
>循环和端环之间的 FISH 程序重复执行，直到满足某些条件。

In the first form, which uses an integer counter, var is given the value of expr1 initially, and is incremented by 1 at the end of each loop execution until it reaches the value of expr2. The local statement may optionally be used at this point to create var as a variable local to the function. Note that expr1 and expr2 (which may be arbitrary algebraic expressions) are evaluated at the start of the loop; redefinition of their component variables within the loop has no effect on the number of loop executions. var is a single integer variable; it may be used in expressions within the loop (even in functions called from within the loop, if it is a global variable), and may even be redefined. The code snippet below demonstrate basic usage of this form to sum all integers below a specified value.
>在第一种形式中使用整数计数器，var 最初被赋予 expr1 的值，并在每次循环执行结束时递增 1，直到达到 expr2 的值。此时可以选择使用 local 语句来创建 var 作为函数的局部变量。请注意，expr1 和 expr2（可以是任意代数表达式）在循环开始时计算;在循环中重新定义其组件变量对循环执行次数没有影响。var 是单个整数变量;它可以用于循环内的表达式（即使是在循环内调用的函数中，如果它是全局变量），甚至可以重新定义。下面的代码段演示了此表单的基本用法，以求和低于指定值的所有整数。

```fish
define sum(n)
  local s = 0
  loop local i (1,n)
    s += i  
  endloop
  sum = s
end
[s = sum(10)]
list @s
```

With n=10, the end result of the sum is 55.
>当 n=10 时，求和的最终结果为 55。

In the second form of the loop structure, the loop body is executed while the test condition is true; otherwise, control passes to the next line after the endloop statement. The form of test is identical to that described for the if statement. The expressions may involve floating-point variables as well as integers; the use of Boolean, strings and pointers is also permitted under the same conditions that apply to the if statement. The code snippet below demonstrate basic usage of this form to sum all even integers below a specified value.
>在循环结构的第二种形式中，在测试条件为真时执行循环体;否则，控制权将传递到 endloop 语句之后的下一行。测试的形式与 if 语句所描述的形式相同。表达式可能涉及浮点变量以及整数;在适用于 if 语句的相同条件下，也允许使用布尔值、字符串和指针。下面的代码段演示了此表单的基本用法，以求和指定值以下的所有偶数。

```fish
define sum_even(n)
  local s = 0
  local i = 0
  loop while i <= n
    s += i
    i +=2
  endloop
  sum_even = s
end
[s2 = sum_even(10)]
list @s2
```

With n=10, the end result of the sum is 30.

The main function of the third form of the loop structure is to repeat execution of the loop body while the test condition is true, similar to the loop while form. But, in addition, the loop for construct provides specific locations to contain an initialize field and a modify field. So this loop is specially designed to perform a repetitive action with a counter which is initialized and modified on each iteration. It works in the following way:
>循环结构的第三种形式的主要功能是在测试条件为真时重复执行循环体，类似于循环同时形式。但是，此外，构造循环提供特定位置以包含初始化字段和修改字段。因此，此循环专门设计用于使用计数器执行重复操作，该计数器在每次迭代时初始化和修改。它的工作方式如下：

Initialization is executed. Generally it is an initial value setting for a counter variable (which can be local or global). This is executed only once.
>执行初始化。通常，它是计数器变量（可以是局部或全局）的初始值设置。此操作仅执行一次。

1. Condition is checked. If it is true, the loop continues; otherwise, the loop ends and the loop body is not executed.
>已检查条件。如果为真，循环将继续;否则，循环结束，不执行循环主体。

2. Loop body is executed.
>执行循环正文。

3. Finally, whatever is specified in the modify field is executed, and the loop goes back to step 2.
>最后，执行修改字段中指定的任何内容，循环返回到步骤 2。

The code snippet below demonstrate basic usage of this form to sum all odd integers below a specified value.
>下面的代码片段演示了此表单的基本用法，以求和指定值以下的所有奇数。

```fish
define sum_odd(n)
  local s= 0
  loop for (local i=1, i <=n, i+=2)
    s += i  
  endloop
  sum_odd = s
end
[s_odd = sum_odd(10)]
list @s_odd
```

With n=10, the end result of the sum is 25.

The first three forms of the loop statement may be contrasted. In the first, the test is done at the end of the loop (so there will be at least one pass through the loop); in the second and third, the test is done at the start of the loop (so the loop will be bypassed if the test is false initially).
>循环语句的前三种形式可以进行对比。
在第一种情况下，测试在循环的末尾完成(因此至少会有一次通过循环);
在第二个和第三个测试中，测试在循环开始时完成(因此，如果测试初始值为假，则循环将被绕过)。

The fourth form of the loop statement is a specialized syntax to allow iterating through all objects inside a given container. In this case, expr1 must return a pointer to a list, or a container of objects. For example, all scalars in the list of user-defined scalars are returned by the data.scalar.list intrinsic. As with the first loop form, var may be preceded by the local statement to indicate that a local variable is to be created instead of a global one. var will be assigned to be a pointer to each object in the list consecutively. If var is deleted during processing of the loop, the loop will continue normally as long as var is not referenced again within the same loop after deletion. If other items in the container are deleted (for example, if a function that deletes the contents of the container is called), then the loop might exit prematurely.
>loop语句的第四种形式是一种专门的语法，允许遍历给定容器内的所有对象。
在这种情况下，expr1必须返回指向列表或对象容器的指针。
例如，用户定义的标量列表中的所有标量都由data.scala .list intrinsic返回。
与第一个循环形式一样，var前面可以加local语句，以指示创建的是局部变量而不是全局变量。
Var将被连续赋值为指向列表中每个对象的指针。
如果在循环处理过程中删除了var，只要删除后在同一循环中没有再次引用var，循环就会正常继续。
如果容器中的其他项被删除(例如，如果调用了删除容器内容的函数)，那么循环可能会提前退出。

Loops may be nested to any depth. Within the loop, the exit loop statement may be used to break out of the loop and continue processing after the endloop statement. In addition, the continue statement may be used to stop processing the current iteration and continue to the next iteration.
>循环可以嵌套到任何深度。
在循环中，exit循环语句可用于跳出循环并在endloop语句之后继续处理。
此外，continue语句可用于停止处理当前迭代并继续到下一个迭代。