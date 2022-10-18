---
aliases: 
tags: 
width:
date created: 星期日, 十月 16日 2022, 9:14:46 上午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*为块的边缘指定边界条件*
file:///C:/Program%20Files/Itasca/UDEC700/exe64/doc/udec/docproject/source/elements/block/block.edge_commands/cmd_block.edge.apply.html

>[!block edge apply keywords:]
>convection &nbsp;&nbsp;&nbsp;  dynamic-free-field &nbsp;&nbsp;&nbsp;  flux &nbsp;&nbsp;&nbsp;  free-x &nbsp;&nbsp;&nbsp;  free-y &nbsp;&nbsp;&nbsp;  history &nbsp;&nbsp;&nbsp;  history-time-reference &nbsp;&nbsp;&nbsp;  history-normal &nbsp;&nbsp;&nbsp;  history-shear &nbsp;&nbsp;&nbsp;  history-x &nbsp;&nbsp;&nbsp;  history-y &nbsp;&nbsp;&nbsp;  impermeable &nbsp;&nbsp;&nbsp;  interior &nbsp;&nbsp;&nbsp;  multiply-normal &nbsp;&nbsp;&nbsp;  multiply-shear &nbsp;&nbsp;&nbsp;  multiply-x &nbsp;&nbsp;&nbsp;  multiply-y &nbsp;&nbsp;&nbsp;  
>nonwetting-gradient-x &nbsp;&nbsp;&nbsp;  nonwetting-gradient-y &nbsp;&nbsp;&nbsp;  nonwetting-impermeable &nbsp;&nbsp;&nbsp;  permeable &nbsp;&nbsp;&nbsp;  nonwetting-permeable &nbsp;&nbsp;&nbsp;  nonwetting-pressure &nbsp;&nbsp;&nbsp;  pore-pressure &nbsp;&nbsp;&nbsp;  pressure-gradient-x &nbsp;&nbsp;&nbsp;  pressure-gradient-y &nbsp;&nbsp;&nbsp;  radiation &nbsp;&nbsp;&nbsp;  saturation &nbsp;&nbsp;&nbsp;  saturation-gradient-x &nbsp;&nbsp;&nbsp;  saturation-gradient-y &nbsp;&nbsp;&nbsp;  seepage &nbsp;&nbsp;&nbsp;  stress-principal &nbsp;&nbsp;&nbsp;  stress

Boundary conditions are specified for edges of blocks. This functionality is limited to the edges that lie on the outer domain (external boundary) of a block model. If block config cell has been used, the boundary conditions will be applied to any block edges within the specified range. If the range is omitted, the boundary condition applies to the entire boundary. Boundary stresses can be applied to both rigid and deformable blocks (use block gridpoint apply to set velocity boundary conditions). Boundary conditions are defined by a given boundary condition keyword as follows.
>为块的边缘指定边界条件。
此功能仅限于位于块模型的外部域(外部边界)上的边缘。
如果使用了块配置单元格，则边界条件将应用于指定范围内的任何块边。
如果省略范围，则边界条件适用于整个边界。
边界应力既可应用于刚性块体，也可应用于可变形块体(使用块格点应用来设置速度边界条件)。
边界条件由一个给定的边界条件关键字定义如下。