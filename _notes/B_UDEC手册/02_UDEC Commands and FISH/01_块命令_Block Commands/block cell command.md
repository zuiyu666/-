---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块单元命令*
>[!block cell keyword:]
>remap  &nbsp;&nbsp;&nbsp;&nbsp;  list

Used to remap the cell space when using the alternate cell contact detection logic. This refers to the method used in UDEC to determine which blocks to consider for contact. The cell contact detection method is slower than the default “domain” contact detection logic, but it allows models with blocks that may bounce from one block to another. Fluid flow is not available with the cell logic. The command :cmd:*configcell*  must be given prior use of this command and also prior to creation of any blocks.
>用于在使用备用单元格接触检测逻辑时重新映射单元格空间。这是指 UDEC 中用于确定要考虑哪些块进行接触的方法。细胞接触检测方法比默认的“域”接触检测逻辑慢，但它允许具有可能从一个块反弹到另一个块的块的模型。流体流动在单元逻辑中不可用。命令 ：cmd：*configcell*  必须在使用此命令之前以及在创建任何块之前给出。

## remap nx \<ny \>
Specify the number of cells in the  x and y-directions.
>指定 x 和 y 方向中的单元格数
## list
Print a list of cells, and the block that each cell contains. Also prints settings associated with cell space contact detection logic.
>打印单元格列表以及每个单元格包含的块。还打印与细胞空间接触检测逻辑相关的设置。

(1)	number of cells in - and -directions
(2)	size of each cell
(3)	origin of cell space
(4)	index of cell space storage
>
（1） x 和 y 方向上的单元格数
（2）每个单元格的大小
（3）细胞空间的起源
（4）单元空间存储索引