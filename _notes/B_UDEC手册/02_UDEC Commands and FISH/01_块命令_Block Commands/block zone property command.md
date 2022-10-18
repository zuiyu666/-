---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 7:10:38 晚上
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块分区特性设置命令*
block zone property s f 

Assign values to one or more properties of zones of deformable blocks within the given range. The advantage of assigning models and properties with this command is that each zone has its own local properties.
>将值指定给给定范围内可变形块分区的一个或多个属性。使用此命令指定模型和特性的优点是，每个分区都有自己的本地特性。

The keywords that assign material properties and are model-specific. The property keywords are presented below, according to each model type. The model must be defined before assigning properties. If properties are given that are not consistent with zone’s constitutive model, a warning message will be issued to inform the user that the unneeded properties were not accepted.
>指定材质特性的关键字和特定于模型的关键字。根据每个模型类型，属性关键字如下所示。必须在分配属性之前定义模型。如果给出的特性与分区的本构模型不一致，将发出警告消息，通知用户不接受不需要的特性。

Zone properties can be listed (see block zone list property) and plotted. In addition to the input properties, other properties calculated by the models can be printed or plotted. These are listed with the other model properties.
>可以列出分区特性（请参见块分区列表特性）并进行打印。除了输入特性外，还可以打印或打印模型计算的其他特性。这些属性与其他模型属性一起列出。

WARNING: If a model is assigned to zones in a specified range via the block zone cmodel command, all properties associated with that model are initialized to zero in that range. Properties previously assigned to that range must be specified again, even if their values have not changed.
>警告：如果通过块分区cmodel命令将模型分配给指定范围内的分区，则与该模型关联的所有特性在该范围内都将初始化为零。必须再次指定以前分配给该范围的属性，即使其值没有更改。

Properties to be assigned with this command are sorted by constitutive model in the table below. Use the model name to link to the list of properties associated with that model. (The models are listed by name, followed by the keyword associated with their designation in the block zone cmodel command.)
>使用此命令分配的属性按下表中的本构模型排序。使用模型名称链接到与该模型关联的特性列表。（模型按名称列出，后跟与块区cmodel命令中的名称相关联的关键字。）

Table 1: Constitutive Models
| Null Model             | null (null)                                                        |
| ---------------------- | ------------------------------------------------------------------ |
| Elastic Models         | isotropic elastic (elastic)                                        |
|                        | transversely isotropic elastic (anisotropic)                       |
| Elastic-Plastic Models | Drucker-Prager (drucker)                                           |
|                        | Mohr-Coulomb (mohr-coulomb)                                        |
|                        | ubiquitous-joint (ubiquitous)                                      |
|                        | strain-hardening/softening (ss)                                    |
|                        | Bilinear Strain-Hardening/Softening Ubiquitous-Joint (subiquitous) |
|                        | double-yield (dy)                                                  |
|                        | modified Cam-Clay (cam-clay)                                       |
|                        | simplified Cysoil-Chsoil (cap-yield-simplified)                    |
|                        | cap-yield (cap-yield)                                              |
|                        | Hoek-Brown (hoekbrown)                                             |
|                        | modified Hoek-Brown (mhoek)                                        |
| Creep Models           | classical viscoelastic (Maxwell subst.) (viscous)                  |
|                        | Burgers (burgers)                                                  |
|                        | power law (power)                                                  |
|                        | WIPP (wipp)                                                        |
|                        | Burgers-creep viscoplastic (svisc)                                 |
|                        | power law viscoplastic (cpow)                                      |
|                        | WIPP-creep viscoplastic (pwipp)                                    |
|                        | crushed salt (cwipp)                                               |
