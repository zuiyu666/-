---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块洞穴命令*

>[!block cave keyword:]
>list  &nbsp;&nbsp;&nbsp;&nbsp;  model  &nbsp;&nbsp;&nbsp;&nbsp;  material  &nbsp;&nbsp;&nbsp;&nbsp;  percent  &nbsp;&nbsp;&nbsp;&nbsp;  zero

Simulate effects of rock fracturing that occurs in a block-cave mining operation. The area of cave is defined as a Mohr-Coulomb material. The stresses in a block are reset to zero whenever the userspecified percentage of zones has yielded. New material property numbers and constitutive laws may also be assigned. The following keywords may be used.
>模拟块状洞穴采矿作业中发生的岩石压裂的影响。洞穴的面积被定义为莫尔库仑材料。每当用户指定的区域百分比产生时，块中的应力就会重置为零。也可以分配新的材料属性编号和构成法。可以使用以下关键字。

## List
List block caving settings. This displays the current settings used in simulation of a block caving mining operation.
>列出块探洞设置。这将显示用于模拟区块探洞采矿作业的当前设置。

(1)	shows if cave material property substitution is on or off
(2)	failed zone percent limit
(3)	new material type number
(4)	new constitutive model number
(5)	stress zeroing state
(6)	sum of number of blocks modified
>（1）显示洞穴材料属性替代是开启还是关闭
（2） 故障区域百分比限制
（3）新材料型号
（4）新本构型号
（5）应力归零状态
（6）修改的块数之和

## model n
Assign constitutive model number n. If this value is not set, the constitutive model will remain unchanged from the default (Mohr-Coulomb).
>分配本构型号 n。如果未设置此值，则本构模型将与默认值（摩尔库仑）保持不变。

## material n
Assign material number n. If this value is not set, the material number will remain unchanged.
>分配物料编号 n。如果未设置此值，则物料编号将保持不变。

## percent f
Set the percentage of zones in a block that must fail in order to trigger the changes.
>设置块中必须失败才能触发更改的区域的百分比。

## zero b
Zero the stresses when percent is exceeded. If this switch is not used, stresses will not be changed. The default is off.
>超过百分比时将应力归零。如果不使用此开关，则不会改变应力。默认值为关闭。