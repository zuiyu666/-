---
aliases: 
tags: 
width:
date created: 星期六, 十月 15日 2022, 9:45:46 上午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块区生成命令*
>[!block zone generate keywords:]
>edge-length  &nbsp;&nbsp;&nbsp;&nbsp;  match &nbsp;&nbsp;&nbsp;&nbsp;   manual  &nbsp;&nbsp;&nbsp;&nbsp;  mixed  &nbsp;&nbsp;&nbsp;&nbsp;  quad  &nbsp;&nbsp;&nbsp;&nbsp;  rezone  &nbsp;&nbsp;&nbsp;&nbsp;  single

Generate zones in blocks. All blocks with centroids lying within the optional range are discretized into deformable triangular finite-difference zones. If no range is given, then all blocks will be discretized.
>在块中生成分区。所有质心位于可选范围内的块都被离散为可变形三角形有限差分区域。如果没有给定范围，则所有块都将被离散化。

Zone generation can be performed automatically or manually. For automatic generation, one of the following keywords must be specified.
>分区生成可以自动或手动执行。要自动生成，必须指定以下关键字之一。

### edge-length f 
Specify automatic generation of zones for an arbitrarily shaped block. The value f defines the maximum edge length of the triangular zones. This is the most commonly used zone generation method in UDEC.
>边缘长度f为任意形状的块指定自动生成区域。值f定义三角形区域的最大边长度。这是UDEC中**最常用的区域生成方法**。

### match 
An optional keyword to force corners to be added to blocks to ensure that all gridpoints will match those on adjoining blocks.
>一个可选关键字，强制将角点添加到块中，以确保所有网格点都与相邻块上的网格点相匹配。

### manual 
keyword Manually generate zones by specifying lists of gridpoints and zones. Manual generation must be performed for each individual block. Only one block should be within the specified range. Both the lists in gridpoint and zone may extend over an arbitrary number of continuation lines, but doubles and triples should not be split over two lines. When using manual zoning, ensure that zoning completely fills the block.
>manual关键字通过指定网格点和区域列表手动生成区域。必须为每个单独的块执行手动生成。只有一个块应在指定范围内。gridpoint和zone中的列表都可以扩展到任意数量的连续行，但double和triple不应分割为两行。使用手动分区时，请确保分区完全填满块。

#### gridpoint fx1 fy1 ...
Specify gridpoints in a list of one to n gridpoints following the format fx1 fy1, fx2 fy2, … fxn fyn , where each x,y pair is a coordinate of a gridpoint. If a given coordinate lies within a certain tolerance of a block corner, the gridpoint is placed on that corner.
>在一到n个网格点的列表中指定网格点，格式为fx1 fy1、fx2 fy2、…fxn fyn，其中每个x，y对是网格点的坐标。如果给定坐标位于块角的某个公差范围内，则网格点位于该角上。

#### edge_tolerance fl1 
The edge_tolerance keyword allows setting a tolerance that controls how close to an edge a user specified gridpoint must be to be considered on the edge of a block. This is intended to solve issues of numerical precision when generating zones from outside sources. The tolerance is specified as a fraction of the block corner-round-length. A typical value would be 0.1. It is unknown how large this value may be before the model results would be adversely affected. This differs from the default tolerances in that it allows the gridpoint to be slightly outside of the block.
>edge_tolerance关键字允许设置容差，该容差控制块边缘上必须考虑的用户指定网格点与边缘的距离。这是为了解决从外部源生成分区时的数值精度问题。公差指定为块角圆角长度的分数。典型值为0.1。在模型结果受到不利影响之前，该值可能有多大尚不清楚。这与默认公差不同，因为它允许网格点稍微超出块。

#### zone fl1 fm1 fn1...
Specify zones in a list following the format fl1 fm1 fn1, fl2 fm2 fn2, etc. Each triple corresponds to the three gridpoints that define the zone, where the numbering of the gridpoints refers to the order in the gridpoint. The triple must be given in clockwise order. (Perform BLOCK CYCLE 0, then BLOCK ZONE LIST STATE to ensure that no negative zone volumes are created.) Both GRIDPOINT and ZONE may extend over an arbitrary number of continuation lines. When using manual zoning, ensure that zoning completely fills the block.
>按照格式fl1 fm1 fn1、fl2 fm2 fn2等在列表中指定分区。每个三元组对应于定义分区的三个网格点，其中网格点的编号是指网格点中的顺序。三元组必须按顺时针顺序给出。（执行BLOCK CYCLE 0，然后执行BLOCK ZONE LIST STATE，以确保没有创建负分区卷。）GRIDPOINT和ZONE都可以延伸到任意数量的续行。使用手动分区时，请确保分区完全填满块。

```udec
For example,
block create poly 0,10 0,20 10,20 10,10
block zone gen man grid 5,15 0,20 0,10 10,10 10,20 …
zone 1,2,5 1,5,4 1,4,3 1,3,2
will divide a block into four zones with five gridpoints.
```

### mixed 
subdivides triangular zones into 3 subzones with an overlay of 4 zones (12 total). The strain of these zones is averaged to avoid hourglass effects. This command only subdivides existing zones; GENERATE EDGE or GENERATE QUAD must be used first.
>将三角形区域细分为3个子区域，覆盖4个区域（共12个）。这些区域的应变是平均的，以避免沙漏效应。此命令仅细分现有分区；必须首先使用GENERATE EDGE或GENERATE QUAD。

### quad fx \<fy \>
Automatic generation of diagonally opposed triangular zones to improve plastic flow calculation. Parameters fx and fy are zone widths in the x- and y-directions. If fy is not given, the parameter defaults to fx. This form of zoning will not work for all block shapes; blocks must contain 4 or 5 corners, and at least 3 of the corners must not be co-linear. For blocks with 5 corners, the block is split into quadrilateral regions before zoning. For best results, the block sides should not be too different in size. If GENERATE QUAD does not work, or produces irregular zoning, the GENERATE EDGE command should be used for the remaining blocks.
>自动生成对角对角三角形区域，以改进塑性流动计算。参数fx和fy是x和y方向上的区域宽度。如果未给定fy，则参数默认为fx。这种分区形式不适用于所有块形状；块必须包含4个或5个角，并且至少3个角不能是共线的。对于具有5个角的块，在分区之前将块分割为四边形区域。为了获得最佳效果，砌块侧面的尺寸不应太大。如果GENERATE QUAD不工作，或产生不规则分区，则应对其余块使用GENERATE EDGE命令。

### rezone 
This keyword is designed to be added in front of other keywords. This allows a block to be rezoned. This command should be used to correct problems with zone degeneration that can result from deformation of null blocks. It may be necessary to rezone a block containing null material if the block is then assigned non-null material. When the block is rezoned, stresses in the block are set to zero. All gridpoints along the edges of blocks are retained and used for the new zoning. The zone edge length used with REZONE can be specified to generate smaller zoning.
>此关键字被设计为添加在其他关键字之前。这允许重新分区块。此命令应用于纠正因空块变形而导致的区域退化问题。如果块体随后被指定为非空材料，则可能需要重新分区包含空材料的块体。重新分区块时，块中的应力设置为零。沿区块边缘的所有网格点都将保留，并用于新的分区。可以指定与REZONE一起使用的分区边缘长度，以生成较小的分区。

### single
mixed discretization with single layer of zones (no overlay), when used instead of the MIXED keyword.
>使用单个混合离散化和单层分区（无覆盖），而不是mixed关键字。