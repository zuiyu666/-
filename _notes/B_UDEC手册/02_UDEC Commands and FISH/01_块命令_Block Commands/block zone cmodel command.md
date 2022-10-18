---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 2:09:05 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*zone赋值命令*
block zone cmodel 

>[!block zone cmodel keywords:]
>assign  &nbsp;&nbsp;&nbsp;&nbsp;  list  &nbsp;&nbsp;&nbsp;&nbsp;  load

Assign constitutive models to zones.
>将本构模型指定给分区。

This command assigns a constitutive model and/or one or more properties with all zones (of deformable blocks) that have centroids in the given range. The advantage of assigning models and properties with the BLOCK ZONE CMODEL ASSIGN command is that each zone has its own local properties. This is reffered to as the ZONE property method (see block change model command for the BLOCK property method).
>该命令指定了一个本构模型一个或多个属性，其中所有区域（变形块）的质心都在给定范围内。使用BLOCK ZONE CMODEL ASSIGN命令指定模型和特性的优点是，每个分区都有自己的本地特性。这称为ZONE特性方法（请参见block特性方法的块更改模型命令）。

This command is also used to assign user-defined models (UDM) to zones in UDEC. This command is also used to assign properties to these zones. The UDM option is required for user-defined models. Also, :block config cpp must be used in order for the user-defined models to be accepted. Models exist as dynamic linked libraries and must be loaded prior to assignment. User defined models that are placed in the “pluginsmodels” folder will be loaded automatically at runtime. If the model is not automatically loaded at runtime it may be loaded using the block zone cmodel load command. The models may then be assigned to zones via the block zone cmodel assign command.
>此命令还用于将用户定义的模型（UDM）分配给UDEC中的分区。此命令还用于为这些分区指定特性。用户定义的模型需要UDM选项。此外，必须使用：block config cpp才能接受用户定义的模型。模型作为动态链接库存在，必须在分配之前加载。放置在“pluginsmodels”文件夹中的用户定义模型将在运行时自动加载。如果模型在运行时未自动加载，则可以使用块区cmodel加载命令加载。然后可以通过块分区cmodel assign命令将模型分配给分区。

The built-in models are described in Section 1 in Constitutive Models. Any block constitutive models that already exist for some or all of the zones in the given range (as specified by block change model command) are ignored. The model keyword assigns constitutive models via the following names
>本构模型第1节中描述了内置模型。忽略给定范围内部分或所有分区（如块更改模型命令所规定）已经存在的任何块体本构模型。model关键字通过以下名称指定本构模型。

#未做完

null

Assign null model used for excavations.

elastic

Assign the isotropic elastic model.

anisotropic

Assign the transversely anisotropic elastic model.

drucker-prager

Assign the Drucker-Prager plasticity model.

mohr-coulomb

Assign the Mohr-Coulomb plasticity model.

ubiquitous-joint

Assign the ubiquitous joint model.

strain-softening

Assign the strain softening plasticity model.

softening-ubiquitous

Assign the bilinear strain softening ubiquitous joint model.

double-yield

Assign the double yield plasticity model.

modified-cam-clay

Assign the modified cam-clay plasticity model.

cap-yield

Assign the Cap-Yield (cysoil) plasticity model.

cap-yield-simplified

Assign the cap-yield-simplified (chsoil) plasticity model.

hoek-brown-pac

Assign the generalized Hoek-Brown plasticity model.

hoek-brown

Assign the modified Hoek-Brown plasticity model.