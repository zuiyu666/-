---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块边缘属性命令*

Syntax

block edge property keyword <[range](../../../../../../common/module/doc/manual/range_manual/range_commands/rangephrasereference.html "range")>

Primary keywords:

[bulk](#kwd:block.edge.property.bulk "block edge property bulk")    [density](#kwd:block.edge.property.density "block edge property density")    [material](#kwd:block.edge.property.material "block edge property material")    [poisson](#kwd:block.edge.property.poisson "block edge property poisson")    [shear](#kwd:block.edge.property.shear "block edge property shear")    [young](#kwd:block.edge.property.young "block edge property young")

This command defines properties that are needed for dynamic boundary conditions (viscous boundaries). The deformational properties may be specified using: bulk and shear; a material number; or Youngs modulus and Poisson’s ratio.

bulk [f](../../../../../../common/docproject/utilities/types.html#type:flt "type:flt")

Bulk modulus for for outside rock mass.

density [f](../../../../../../common/docproject/utilities/types.html#type:flt "type:flt")

Density for outside rock mass.

material [i](../../../../../../common/docproject/utilities/types.html#type:int "type:int")

Material property number to use for dynamic boundaries.

poisson [f](../../../../../../common/docproject/utilities/types.html#type:flt "type:flt")

Poisson’s ratio for outside rock mass.

shear [f](../../../../../../common/docproject/utilities/types.html#type:flt "type:flt")

Shear modulus for outside rock mass.

young [f](../../../../../../common/docproject/utilities/types.html#type:flt "type:flt")

Young’s modulus for outside rock mass.