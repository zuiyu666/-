---
aliases: 
tags: 
width:
date created: 星期六, 十月 15日 2022, 4:15:46 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块切割命令*

>[!block cut keywords:]
>arc &nbsp;&nbsp;&nbsp;&nbsp; crack &nbsp;&nbsp;&nbsp;&nbsp; cutting &nbsp;&nbsp;&nbsp;&nbsp; dfn &nbsp;&nbsp;&nbsp;&nbsp; geometry   
> join &nbsp;&nbsp;&nbsp;&nbsp; jointset-id &nbsp;&nbsp;&nbsp;&nbsp; joint-set &nbsp;&nbsp;&nbsp;&nbsp; split &nbsp;&nbsp;&nbsp;&nbsp; table   
>  tunnel &nbsp;&nbsp;&nbsp;&nbsp; voronoi

Cut blocks.
>切割块。

>[!note]
>Block cutting commands must be issued before blocks are made deformable.
必须在块设置为可变形之前发出块切割命令。
If no range is given, the entire model is used for generation. In most cases, the range is defined by range joint-region n, where n refers to the id in a previous block joint-region command. Other range keywords (e.g., mat n) may also be used to restrict the blocks to be cut. Joint segments that do not cut blocks are stored to be used in conjunction with succeeding block cut commands. The area of block cutting is controlled by the range keywords. The area of storage is not affected by the range keywords. Only totally unsuccessful joint segments are stored. The remainder ends of joint segments that do not cut blocks are not stored. The stored joint segments can be removed by the block joint-delete command. All incomplete joint segments are discarded automatically before zone generation or cycling. Partial cracks are not modeled in UDEC (only completed blocks). A block that wraps completely around another block will not behave correctly. This is because a block cannot form contacts with itself.
>如果未给出范围，则使用整个模型进行生成。在大多数情况下，范围由范围关节区域n定义，其中n是指先前块关节区域命令中的id。其他范围关键字（例如mat n）也可用于限制要切割的块。将存储不剪切块的关节段，以便与后续块剪切命令一起使用。块切割的面积由范围关键字控制。存储区域不受范围关键字的影响。仅存储完全不成功的关节段。不会存储未剪切块的关节段的其余端点。存储的关节段可以通过块关节删除命令删除。在分区生成或循环之前，将自动放弃所有不完整的关节段。UDEC中未对部分裂缝进行建模（仅完成的砌块）。完全环绕另一个块的块将无法正常工作。这是因为块不能与自身形成接触。
The block contact change command can be used to assign material properties and constitutive models to the contacts along the crack.
The optional Jointset-ID number is used to specify the jointset ID for any contacts created by use of this command. If no ID is specified, a sequential number is used.
If the optional join keyword is used, any new contacts formed because of the crack will be joined contacts. Contacts that have been joined will be listed as having a constitutive model of 10.
块接触更改命令可用于将材料特性和本构模型指定给沿裂纹的接触。
可选的Jointset ID号用于为使用此命令创建的任何联系人指定Jointset ID。如果未指定ID，则使用序列号。
如果使用了可选的join关键字，则由于裂纹而形成的任何新触点都将是连接的触点。已连接的触点将被列为本构模型为10。

### arc fxc fyc fxb fyb ftheta i
Create an arc pattern of cracks. i cracks are created, which conform to an arc of a circle centered at (fxc, fyc), with a beginning point of (fxb, fyb) and a counterclockwise angle of ftheta degrees.
>创建裂纹的弧形图案。i产生裂纹，裂纹与以（fxc，fyc）为中心的圆弧一致，起点为（fxb，fyb），逆时针角度为ftheta度。

### crack fx1 fy1 fx2 fy2
Create a crack. A crack is created between points (fx1, fy1) and (fx2, fy2). This command can be used to create a discontinuous fracture in part of a block. Two cracks will be connected if their endpoint locations are within a distance of twice the corner-round-length from each other. All discontinuous cracks that do not link to form blocks are deleted when the block zone generate or block cycle command is executed.
>制造裂缝。在点（fx1，fy1）和（fx2，fy 2）之间创建裂纹。此命令可用于在块的部分创建**不连续断裂**。如果两条裂缝的端点位置彼此之间的距离是圆角长度的两倍，则这两条裂缝将连接起来。执行块区生成或块循环命令时，将删除所有未连接到形成块的不连续裂纹。

### cutting b
Allow cutting of blocks created via the block fill command to occur after cycling. Default is off.
>允许在循环后切割通过块填充命令创建的块。默认设置为禁用。

### join
If the optional join keyword is used, any new contacts formed because of the crack will be joined contacts. Contacts that have been joined will be listed as having a constitutive model of 10.
>如果使用了可选的join关键字，则由于裂纹而形成的任何新触点都将是连接的触点。已连接的触点将被列为本构模型为10。

### jointset-id i
The optional jointset id number is used to specify a specifiic id to be assigned by the cut commands and will be applied to any contacts created by use of these commands. If no jointset id is specified, a sequential number is used.
>可选的jointset id号用于指定由剪切命令指定的特定id，并将应用于使用这些命令创建的任何触点。如果未指定jointset id，则使用序列号。

### joint-set keyword
Generate a joint set in the range with characteristics defined by the following keywords (see Figure 1 for illustration of parameters).
>在具有以下关键字定义的特征的范围内生成关节集（有关参数的说明，请参见图1）。

Figure 1: Joint set parameters (joint region is defined by JREGION id 1 x1,y1 x2,y2 x3,y3 x4,y4)
>图1：关节集参数（关节区域由JREGION id 1 x1、y1 x2、y2 x3、y3 x4、y4定义）

![](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202210151622523.png)

