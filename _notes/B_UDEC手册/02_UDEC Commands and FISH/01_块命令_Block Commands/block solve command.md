---
aliases: 
tags: 
width:
date created: 星期日, 十月 16日 2022, 9:25:55 上午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*求解运行限制命令*
>[!block solve keywords:]
>age &nbsp;&nbsp;&nbsp; clock &nbsp;&nbsp;&nbsp; cycle &nbsp;&nbsp;&nbsp; elastic &nbsp;&nbsp;&nbsp; force &nbsp;&nbsp;&nbsp; fscontour &nbsp;&nbsp;&nbsp; factor-increment &nbsp;&nbsp;&nbsp; contact &nbsp;&nbsp;&nbsp; maximum-cycles &nbsp;&nbsp;&nbsp; minimum-factor &nbsp;&nbsp;&nbsp; structure &nbsp;&nbsp;&nbsp; message &nbsp;&nbsp;&nbsp; no-age &nbsp;&nbsp;&nbsp; ratio &nbsp;&nbsp;&nbsp; ratio-average &nbsp;&nbsp;&nbsp; ratio-local &nbsp;&nbsp;&nbsp; ratio-maximum &nbsp;&nbsp;&nbsp; relax &nbsp;&nbsp;&nbsp; step

Enable the automatic detection of the steady-state solution for mechanical problems. A calculation is performed until the limiting conditions, as defined by the following keywords, are reached. SOLVE force must be used for rigid block models. The SOLVE command does not monitor fluid flow. It is possible that mechanical equilibrium may be reached prior to fluid-flow equilibrium for steady-state flow. CYCLE ftime should be used for transient fluid flow.
>能够自动检测机械问题的稳态解决方案。
计算一直进行到达到由以下关键字定义的极限条件为止。
对于刚性块体模型必须使用SOLVE力。
SOLVE命令不监视流体流动。
对于稳态流动，机械平衡可能在流体-流动平衡之前达到。
对于瞬态流体流动应使用CYCLE ftime。