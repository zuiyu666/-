---
aliases: 
tags: 
width:
date created: 星期一, 十月 17日 2022, 1:31:35 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---

This section provides the first-time user with an introduction to UDEC. Getting Started contains instructions for program installation and start-up on your computer. It also outlines the recommended procedure for applying UDEC to problems in geo-engineering, and includes simple examples that demonstrate each step of this procedure. When UDEC is executed for the first time, a dialog requesting permission to copy the data files and other user resources to your documents folder will appear. This is done to avoid operating system permission conflicts when attempting to open files in the “C:\Program Files” folder. It is recommended that you allow UDEC to copy example files to your “My Documents\itasca\udec700” folder. (This can also be done at any time by clicking on Tools / Copy Application Data in the GUI or Help / Copy Application Data in the GIIC .)
>本节向首次使用UDEC的用户介绍。“入门”包含在计算机上安装和启动程序的说明。它还概述了将UDEC应用于地质工程问题的建议程序，并包括演示此程序每个步骤的简单示例。首次执行UDEC时，将出现一个对话框，请求将数据文件和其他用户资源复制到文档文件夹的权限。这样做是为了避免在试图打开“C:\Program files”文件夹中的文件时发生操作系统权限冲突。建议您允许UDEC将示例文件复制到“My Documents\itasca\udec700”文件夹。（这也可以随时通过单击GUI中的Tools\/Copy Application Data或GIIC中的Help\/Copy应用程序数据来完成。）

If you are familiar with the program but only use it occasionally, you may find this section (in particular, [[2.6 Mechanics of Using UDEC|2.6 Mechanics of Using UDEC]] ) helpful in refreshing your memory about the mechanics of running UDEC.
More complete information on problem solving is provided in Section 3 [[3 PROBLEM SOLVING WITH UDEC|3 PROBLEM SOLVING WITH UDEC]]. For Additional information on Running UDEC click on Tools in UDEC.
>如果您熟悉该程序，但只是偶尔使用它，您可能会发现本节（特别是2.6节  [[2.6 Mechanics of Using UDEC|2.6 Mechanics of Using UDEC]] ）有助于刷新有关运行UDEC的机制的记忆。
第3节 [[3 PROBLEM SOLVING WITH UDEC|3 PROBLEM SOLVING WITH UDEC]] 提供了关于解决问题的更多完整信息。有关运行UDEC的更多信息，请单击UDEC中的工具。

UDEC can be operated in command-driven using the GUI or graphical, menu-driven mode using the GIIC . For most of the examples in this manual, input is entered and results are viewed using the command-driven mode. We believe this is the clearest way for you to understand the operating procedures for UDEC. As explained previously in Section 1, the command-driven structure allows UDEC to be a very versatile tool for use in engineering analysis. However, this structure can present difficulties for new or occasional users. Command lines must be entered as input to UDEC, either interactively via the keyboard or from a remote data file, in order for the code to operate. There are over 65 main commands and more than 400 command modifiers (called keywords) recognized by UDEC.
>UDEC可以使用GUI以命令驱动方式操作，也可以使用GIIC以图形、菜单驱动方式操作。对于本手册中的大多数示例，输入的内容和结果都是使用命令驱动方式查看的。我们相信这是您了解UDEC操作程序的最清晰的方式。正如前面在第1节中所解释的，命令驱动结构使UDEC成为工程分析中使用的一个非常通用的工具。然而，这种结构可能会给新用户或临时用户带来困难。必须通过键盘或远程数据文件以交互方式输入命令行作为UDEC的输入，以便代码运行。UDEC可以识别65个以上的主命令和400多个命令修饰符（称为关键字）。

The menu-driven mode is an easy-to-use alternative to the command-driven procedure. All of the commands in UDEC can be accessed by point-and-click operation from the graphical mode. We call this mode the “GIIC, ” for Graphical Interface for Itasca Codes.
>菜单驱动模式是命令驱动程序的一种易于使用的替代方法。UDEC 中的所有命令都可以通过点击操作从图形模式访问。我们将这种模式称为“GIIC”，用于 Itasca 代码的图形接口。

Getting Started contains the following information:
>《入门篇》包含以下信息：

1. A step-by-step procedure to install and start up UDEC on your computer is given in Section 2.1. This includes the system requirements for operating UDEC (Section 2.1.1), the installation procedure (Section 2.1.2), a description of the components of the UDEC program and related files (Section 2.1.3), the memory allocation (Section 2.1.4), utility software and graphics devices (Section 2.1.5), start-up and operation procedures (Section 2.1.6), identification of version number (Section 2.1.7) and installation test (Section 2.1.8).
>第2.1节给出了在您的计算机上安装和启动UDEC的逐步程序。这包括操作UDEC的系统要求（第2.1.1节）、安装程序（第2.1.2节）、UDEC程序和相关文件的组件描述（第2.1.3节）、内存分配（第2.1.4节）、实用软件和图形设备（第2.1.5节），启动和操作程序（第2.1.6节）、版本号标识（第2.1.7节）和安装测试（第2.1.8节）。

2. This is followed in Section 2.2 by instructions on runningUDEC. Section 2.2.1 introduces the GIIC, and Section 2.2.2 provides a tutorial on running UDEC in menu-driven mode.Section 2.2.3 describes the procedure for running UDEC in the command-driven mode, and Section 2.2.4 includes a tutorial to help you become familiar with common input commands.
>2. 在第 2.2 节中，运行 UDEC 的说明如下。第 2.2.1 节介绍了 GIIC，第 2.2.2 节提供了在菜单驱动模式下运行 UDEC 的教程。第 2.2.3 节描述了在命令驱动模式下运行 UDEC 的过程，第 2.2.4 节包含一个教程，帮助您熟悉常见的输入命令。

3. There are a few things that you will need to know before creating and running your own UDEC model (i.e., you need to know the UDEC terminology). The nomenclature used for this program is described in Section 2.3. The definition of a UDEC model is given in Section 2.4. You should also know the syntax for the UDEC input language when running in command-driven mode; an overview is provided in Section 2.5.
>在创建和运行您自己的 UDEC 模型之前，您需要了解一些事情（即，您需要知道 UDEC 术语）。第 2.3 节描述了该程序使用的术语。第 2.4 节给出了 UDEC 模型的定义。在命令驱动模式下运行时，您还应了解 UDEC 输入语言的语法；概述见第 2.5 节。

4. The mechanics of running a UDEC model are described in separate steps; in Section 2.6, each step is discussed separately and simple examples are provided.*
>运行 UDEC 模型的机制在单独的步骤中描述；在 2.6 节中，每个步骤都单独讨论，并提供了简单的示例*

5. The sign conventions, systems of units and precision limits used in the program appear in Sections 2.7, 2.8 and 2.9, respectively.
>程序中使用的符号约定、单位制和精度限制分别出现在第 2.7、2.8 和 2.9 节中。

6. The different types of files used and created by UDEC are described in Section 2.10.
>第 2.10 节描述了 UDEC 使用和创建的不同类型的文件。



