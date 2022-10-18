---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:36:19 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
>[!block contact change keywords:]
>material &nbsp;&nbsp;&nbsp;&nbsp;   model

Set or change joint models or material numbers. All joints with contact coordinates lying within the optional range have material numbers changed. If no range is specified, all joints will have material numbers changed according to the keywords given below.To change block material numbers, see block change; for cable material numbers, see cable change; for domain material numbers, see domain change. See block contact cmodel for extended joint models, and local storage joint models. To assign properties to the material numbers use the block contact property material command.
>设置或更改关节模型或材质编号。接触坐标位于可选范围内的所有关节都更改了材质编号。如果未指定范围，则所有接头都将根据下面给出的关键字更改材质编号。要更改块材料编号，请参见块更改；电缆材料编号见电缆变更；有关域材料编号，请参阅域更改。有关扩展关节模型和本地存储关节模型，请参见块接触cmodel。要将特性指定给材质编号，请使用块接触特性材质命令。

### material i 
Material property number i is assigned to designated rigid or deformable blocks. (All blocks initially default to mat = 1. The maximum value for i is 50.)  
>材质i将材质特性编号i指定给指定的刚性块或可变形块。（所有块最初默认为mat=1。i的最大值为50。）

### model i 
Constitutive number i is assigned to designated deformable blocks according to the following table.
>根据下表，本构编号i被分配给指定的可变形块体。

| model | Model Description                                                                                                                                                                                                                                                  |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1     | point contact elastic/plastic with Coulomb slip failure (units are [force/displacement] for contact stiffnesses, and [force] for cohesion and tension)                                                                                                             |
| 1翻译 | 具有库仑滑动破坏的点接触弹性/塑性（单位为接触刚度的[力/位移]，以及内聚力和张力的[力]）                                                                                                                                                                             |
| 2     | joint area [^1] contact elastic/plastic with Coulomb slip failure (units are [stress] for cohesion and tension, and [stress/displacement] for joint stiffnesses) (default)                                                                                           |
| 2翻译 | 接缝面积[1]与弹性/塑性接触，库仑滑动破坏（单位为内聚力和张力的[应力]，以及接缝刚度的[应力/位移]）（默认值）                                                                                                                                                        |
| 3     | continuously yielding joint model (see Section 2 in Constitutive Models for a detailed explanation)                                                                                                                                                                |
| 3翻译 | 连续屈服节理模型（详细说明见本构模型第2节）                                                                                                                                                                                                                        |
| 5     | same as model = 2, except that the internal fracture flag is set for each joint segment when joint shear or tensile strength is exceeded. If the fracture flag is set, residual values for friction, cohesion and tension are used in all subsequent calculations. |
| 5翻译 | 与模型=2相同，但当超过接头剪切或抗拉强度时，为每个接头段设置内部断裂标志。如果设置了断裂标志，则摩擦力、内聚力和张力的剩余值将用于所有后续计算。                                                                                                                   |
| 7     | optional Barton-Bandis (BB) joint model. For details see Section 3 in the Constitutive Models volume.                                                                                                                                                              |
| 7翻译 | 可选Barton Bandis（BB）关节模型。有关详细信息，请参阅本构模型卷第3节。
| 10    | joined contacts. Joined contacts cannot slip or open.                                                                                                                                                                                                              |
| 10翻译|  已加入节理。连接的触点不能滑动或打开。                                                                                                                                                                                                               |


[^1]:The minimum joint area is limited to twice the corner-round-length, so that it is not necessary to specify point contact properties if both point contacts and area contacts occur between blocks.>最小连接面积被限制为角圆长度的两倍，因此如果块之间发生点接触和区域接触，则不需要指定点接触属性。