---
aliases: 
tags: 
width:
date created: 星期日, 十月 16日 2022, 9:36:43 上午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块循环控制命令*
>[!block cycle command keywords:]
>fluid-time &nbsp;&nbsp;&nbsp;&nbsp; message &nbsp;&nbsp;&nbsp;&nbsp; time

Executes i timesteps. (block cycle 0 is permitted as a check on data.) If the \<Esc\> key is pressed during execution, UDEC will return control to the user after the current cycle is completed. (Also see block solve command)
>执行步伐。(允许块周期0作为对数据的检查。)
如果在执行过程中按下\<Esc\>键，UDEC将在当前周期完成后将控制权交还给用户。(参见block solve command)

### fluid-time f
If the fluid flow calculator is on, fluid steps are executed. f is the flow duration time. block cycle i can also be used for a flow calculation, in which i is the number of flow steps.
>如果流体流量计算器处于打开状态，则执行流体步骤。
F为流量持续时间。
块循环I也可以用于流量计算，其中I为流量步数。

### message b 
Used to inhibit the cycle progress from being displyed on the screen (default = on).
>用于禁止在屏幕上显示周期进度（默认打开）。

### time f 
f is mechanical time duration, in seconds, for this increment of cycling.
>f是循环增量的机械时间持续时间，单位为秒。