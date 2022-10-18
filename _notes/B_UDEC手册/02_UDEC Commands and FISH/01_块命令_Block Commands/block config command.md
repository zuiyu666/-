---
aliases: 
tags: 
width:
date created: 星期六, 十月 15日 2022, 3:15:53 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
>[!block config keywords:]
>array &nbsp;&nbsp;&nbsp;&nbsp; axisymmetry &nbsp;&nbsp;&nbsp;&nbsp; barton-bandis &nbsp;&nbsp;&nbsp;&nbsp; cellspace &nbsp;&nbsp;&nbsp;&nbsp; 
>cpp &nbsp;&nbsp;&nbsp;&nbsp; creep &nbsp;&nbsp;&nbsp;&nbsp; energy &nbsp;&nbsp;&nbsp;&nbsp; fluid &nbsp;&nbsp;&nbsp;&nbsp; plane-stress &nbsp;&nbsp;&nbsp;&nbsp; thermal

Specify optional calculation modes. These require specifying in advance to allow extra memory to be assigned to each zone or gridpoint. The options are cell space detection logic, plane stress, fluid flow, creep, user-defined models and heat transfer. If any of these options are desired, CONFIG must be given before the BLOCK command. The following keywords apply.
>指定可选的计算模式。
这需要预先指定，以便为每个区域或网格点分配额外的内存。
可选项包括单元空间检测逻辑、平面应力、流体流动、蠕变、用户定义的模型和传热。
如果需要这些选项中的任何一个，CONFIG必须在BLOCK命令之前给出。
以下关键字适用。

array n
Set the amount of memory (in MB) available in UDEC. This value will be stored in the registry, and will be used for all future UDEC instances. (UDEC must be restarted for this to take effect.)
>设置UDEC中可用的内存量(MB)。
该值将存储在注册表中，并将用于所有未来的UDEC实例。
(UDEC必须重新启动才能生效。)