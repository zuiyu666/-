---
aliases: 
tags: 
width:
date created: 星期六, 十月 15日 2022, 3:24:41 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块创建命令*
>[!block create keywords:]
>corner-angle &nbsp;&nbsp;&nbsp;&nbsp; brick &nbsp;&nbsp;&nbsp;&nbsp; circle &nbsp;&nbsp;&nbsp;&nbsp; fill &nbsp;&nbsp;&nbsp;&nbsp; polygon &nbsp;&nbsp;&nbsp;&nbsp; test

Create and perform other operations on rigid blocks.
>在刚性块上创建和执行其他操作。

Normally, only one BLOCK command is allowed. Additional blocks may be created with a CRACK, TUNNEL, ARC, JSET or VORONOI command, and unwanted blocks deleted with the DELETE command. Any block may be changed to deformable using the GENERATE command.
>通常，只允许一个BLOCK命令。
额外的块可以用CRACK、TUNNEL、ARC、JSET或VORONOI命令创建，不需要的块可以用DELETE命令删除。
使用GENERATE命令可以将任何块更改为可变形的。


When CONFIG cell has been specified, multiple BLOCK commands may be used. Also, the BLOCK fill command may be used at any time.
>当CONFIG cell被指定时，可以使用多个BLOCK命令。
此外，BLOCK填充命令可以在任何时候使用。

### corner-angle 

Corners are added to the block on straight edges so that any angle with its sides on two consecutive corners and its apex at the block’s center never exceeds f.
>在方块的直边上加上角，这样任何边在连续的两个角上且顶点在方块中心的角都不会超过f。

>[!note]
>This keyword should be used to control the boundary mesh refinement whenever a block fluid far-field command is to be invoked.
>>当调用块流体远场命令时，该关键字应用于控制边界网格细化。

### brick fxl fxu fyl fyu

Create a rectangular block, where (fxl, fxu) is the x coordinate range of the block, (fyl, fyu are the y coordinate range of the block.
>创建一个矩形块，其中(fxl, fxu)是块的x坐标范围，(fyl, fyu是块的y坐标范围。

#### material 
Material number i is assigned to the block. The default is i = 1. (See the block property material command.)  
>材料号i被分配给块。默认值是i = 1。

#### model i 
Constitutive number i is assigned to the block. The default is i = 1. (See the block change command.)  
>模型i本构数i被分配给块。默认值是i = 1。

#### group s
Make block a member of group s in optional slot i
>group s使块成为可选槽位i中group s的成员


### circle f1 f2 f3 f4
A circular block is created with the circular keyword, where (f1, f2) are the coordinates of the center of the circular block, f3 is the radius, and f4 is the number of edges along the outer boundary.
>使用circular关键字创建一个圆形块，其中(f1, f2)是圆形块的圆心坐标，f3是半径，f4是沿外边界的边数。

### fill f1, f2
May be used as an alternative to the null models. The problem with null models is that it is difficult to maintain the shape of the zones in the excavated area if large displacements occur. The fill step may result in a bad zone geometry, and cycling will not be possible. The alternative is to simply delete the excavated blocks and then use the block create fill command to refill the void. The new block may be cut with the block cut crack, block cut split, or block cut jointset command (use block cut cutting on first). The new block may also be zoned with the block zone generate command. This method of excavating and filling will also allow trimming of the top of the fill block so that the fill does not fit tight up against the top of the excavation. This command only works for fully enclosed excavations, and will not work to fill excavations that intersect the outer boundary of the model.
>可以用作空模型的替代。
空模型的问题是，如果发生大位移，很难维持开挖区域的形状。
填充步骤可能会导致一个糟糕的区域几何形状，循环将不可能。
另一种方法是简单地删除挖掘的块，然后使用块创建填充命令来填充空白。
新的块可以用块切割裂纹、块切割分裂或块切割jointset命令切割(首先使用块切割切割on)。
还可以使用block zone generate命令对新块进行分区。
这种挖掘和填埋的方法还允许修整填埋块的顶部，这样填埋物就不会紧贴在挖掘的顶部。
此命令仅适用于全封闭的挖掘，而不适用于与模型外边界相交的挖掘。

### polygon f f f f ... f f 
#### material i 
Material number i is assigned to the block. The default is i = 1. (See the block property material command.)  
>材料i材料编号i被指定给块。默认值为i=1。（请参见块特性材质命令。）

#### model i 
Constitutive number i is assigned to the block. The default is i = 1. (See the block change command.)  
>模型i本构编号i被指定给块。默认值为i=1。（请参阅块更改命令。）

#### group s \<i \> 
Make block a member of group s in optional slot i
>使块成为i中组s的成员