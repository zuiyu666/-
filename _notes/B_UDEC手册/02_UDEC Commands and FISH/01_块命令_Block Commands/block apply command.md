---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---


>[!block apply keywords:]
force-x &nbsp;&nbsp;&nbsp;  force-y&nbsp;&nbsp;&nbsp;rotation&nbsp;&nbsp;&nbsp;velocity-x&nbsp;&nbsp;&nbsp; velocity-y

Set block or gridpoint variables to initial values. Loads and velocities apply to rigid block centroids only. Initialized values for rigid blocks can be made permanent by using the FIX command. The following keywords are available.
>将块或网格点变量设置为初始值。 载荷和速度仅适用于刚性块形心。 刚性块的初始化值可以使用 FIX 命令永久化。 可以使用以下关键字。

| 关键词        | 释义                                                              |
|------------|-----------------------------------------------------------------|
| force-x    | Set rigid block x-load.                                         |
| force-y    | Set rigid block y-load.                                         |
| rotation   | Set both the x- and y-component of rigid block θ velocity to v. |
| velocity-x | Set the gridpoint x-velocity.                                   |
| velocity-y | Set the gridpoint y-velocity.                                   |

Block of Modifiers for the Command Value
>命令值的修饰符块

The following keyword are available to modify the value given in the keyword over the \[range\] supplied. The following keywords are available:
>以下关键字可用于在提供的范围内修改关键字中给出的值。 可以使用以下关键字：

| 关键词 | 释义                                                                                                                                                                                   |
| ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| add    | Add (including any specified variations) to existing values of the given variable. The default is to replace the existing value.                                                       |
| mul    | Multiply by f(including any specified variations) the existing values of the given variable by value. |
|gradient| Apply a gradient to the main value, or to the value obtained in conjunction with add or mult. The x and y gradient is obtained by the following equation. ![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210122057819.png)                                                                                                                           |


