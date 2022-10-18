---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
**block property material \[*i*\] keyword**
>块属性材料

Assign property values to material model numbers for blocks (BLOCK property method). The parameter \[*i*\] is the material number \[*i*must be in the range 1-50\]. Block properties are not assigned to specific blocks with this command; that is done using the block change material command.
>将属性值分配给块的材料型号（块属性方法）。 参数\[*i*\]是材料编号\[*i* 必须在1-50\]的范围内。 使用此命令不会将块属性分配给特定块； 这是使用块更改材料命令完成的。

>[!Note]
Block constitutive models and properties can also be assigned locally to block zones (ZONE property method) with the block zone cmodel assign command. If the ZONE property method is used, each block or contact will have its own set of properties. This method requires more computer memory. This method is required if FISH is used to modify properties of individual blocks.
>>块本构模型和属性也可以使用 block zone cmodel assign 命令在本地分配给块区域（ZONE 属性方法）。 如果使用 ZONE 属性方法，则每个块或接触都将具有自己的一组属性。 这种方法需要更多的计算机内存。 如果使用 FISH 修改单个块的属性，则需要此方法。


### Rigid blocks
Table 1: Property keywords for rigid blocks.
>表 1：刚性块的属性关键字。

| keyword | description |
| ------- | ----------- |
| density |  density [mass/volume] |
 
 The following properties are used by model numbers 0 (null), 1 (elastic), 3 (Mohr-Coulomb), and 6 (Drucker-Prager).
 >以下属性由型号 0（空）、1（弹性）、3（Mohr-Coulomb）和 6（Drucker-Prager）使用。

### Null
Block model 0 - null constitutive model. In spite of the fact that this is a null model, in order for it to work properly in UDEC, elastic properties must be assigned. The block properties are needed in the null model to allow internal gridpoints to move as the null block deforms. The choice of null property values will not affect model results, but values that won’t reduce the critical timestep should be selected.
>块模型 0 - 空本构模型。 尽管这是一个空模型，但为了使其在 UDEC 中正常工作，必须指定弹性属性。 空模型中需要块属性以允许内部网格点随着空块变形而移动。 选择空属性值不会影响模型结果，但应选择不会减少关键时间步长的值。

Table 2: Property keywords for constitutive model 0 (null)
>表 2：本构模型 0（空）的属性关键字

| keyword | Description                     |
|---------|---------------------------------|
| bulk    | Bulk Modulus [stress]           |
| density | density [mass/volume]           |
| poisson | Poisson’s ratio [length/length] |
| shear   | Shear modulus [stress]          |
| young   | tensile strength [stress]       |
>[!Note]
>The default value for these properties is zero. Elastic properties may be specified using either bulk and shear modulus, or young’s modulus and Poisson’s ratio.
>这些属性的默认值为零。 弹性特性可以使用体积和剪切模量，或杨氏模量和泊松比来指定。

### Elastic
Block model 1 - elastic constitutive model. This is the default constitutive model.
>块模型 1 - 弹性本构模型。 这是默认的本构模型。

Table 3: Property keywords for constitutive model 1 (elastic)
>表 3：本构模型 1（弹性）的属性关键字

| keyword           | Description                                                          |
|-------------------|----------------------------------------------------------------------|
| biot-c            | Biot’s constant for porous elastic rocks (optional) - default is 1.0 |
| bulk              | Bulk Modulus [stress]                                                |
| conductivity      | Thermal conductivity to be used for both axes                        |
| conductivity-x    | Thermal conductivity to be used for x axes                           |
| conductivity-y    | Thermal conductivity to be used for y axes                           |
| density           | density [mass/volume]                                                |
| poisson           | Poisson’s ratio [length/length]                                      |
| shear             | Shear modulus [stress]                                               |
| specific-heat     | Specific heat [heat]                                                 |
| thermal-expansion | Thermal expansion coefficient [length/length]                        |
| young             | tensile strength [stress]                                            |

>[!note]
>The default value for these properties (with the exceptions, as noted) is zero. Elastic properties may be specified using either bulk and shear modulus, or young’s modulus and Poisson’s ratio. Biot’s constant is optional and only used to calculate stress change in response to a pore-pressure change. Thermal-conductivity, Thermal-expansion, and Specific heat are only used in thermal calculations.
>这些属性的默认值（如所指出的除外）为零。 弹性特性可以使用体积和剪切模量，或杨氏模量和泊松比来指定。  Biot 常数是可选的，仅用于计算响应孔隙压力变化的应力变化。* 热导率、热膨胀和比热仅用于热计算*。

### Mohr-Coulomb
**Block model 3** - Mohr-Coulomb constitutive model.

Table 4: Property keywords for constitutive model 3 (Mohr-Coulomb)
>表 4：本构模型 3 (Mohr-Coulomb) 的属性关键字

| keyword           | Description                                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------- |
| biot-c            | Biot’s constant for porous elastic rocks (optional) - default is 1.0                         |
| bulk              | Bulk Modulus [stress]                                                                        |
| cohesion          | Cohesion [stress]                                                                            |
| conductivity      | Thermal conductivity to be used for both axes                                                |
| conductivity-x    | Thermal conductivity to be used for x axes                                                   |
| conductivity-y    | Thermal conductivity to be used for y axes                                                   |
| density           | density [mass/volume]                                                                        |
| dilation          | Dilation angle [degrees]                                                                     |
| flag-brittle      | Specifies whether the tensile strength drops to zero upon tensile failure. Default is false. |
| friction          | Internal angle of friction [degrees]                                                         |
| poisson           | Poisson’s ratio [length/length]                                                              |
| shear             | Shear modulus [stress]                                                                       |
| specific-heat     | Specific heat [heat]                                                                         |
| thermal-expansion | Thermal expansion coefficient [length/length]                                                |
| Tension           | tensile strength [stress]                                                                    |
| young             | tensile strength [stress]                                                                    |
|                   |                                                                                              |
|                   |                                                                                              |
>[!note]
>The default value for these properties (with the exceptions, as noted) is zero. Elastic properties may be specified using either bulk and shear modulus, or young’s modulus and Poisson’s ratio. Biot’s constant is optional and only used to calculate stress change in response to a pore-pressure change. Thermal-expansion, and Specific heat are only used in thermal calculations. The default value for flag-brittle is false. This is a change in the default tensile behavior for this model in UDEC from previous versions.
>>这些属性的默认值（如所指出的除外）为零。 弹性特性可以使用体积和剪切模量，或杨氏模量和泊松比来指定。  Biot 常数是可选的，仅用于计算响应孔隙压力变化的应力变化。 热膨胀和比热仅用于热计算。  flag-brittle 的默认值为 false。 这是 UDEC 中此模型的默认拉伸行为与以前版本相比的更改。

### Drucker-Prager(德鲁克-普拉格)
Block model 6 - Drucker-Prager constitutive model.

Table 5: Property keywords for constitutive model 6 (Drucker-Prager)
>表 5：本构模型 6 (Drucker-Prager) 的属性关键字

| keyword           | Description                                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------- |
| biot-c            | Biot’s constant for porous elastic rocks (optional) - default is 1.0                         |
| bulk              | Bulk Modulus [stress]                                                                        |
| cohesion          | Cohesion [stress]                                                                            |
| conductivity      | Thermal conductivity to be used for both axes                                                |
| conductivity-x    | Thermal conductivity to be used for x axes                                                   |
| conductivity-y    | Thermal conductivity to be used for y axes                                                   |
| density           | density [mass/volume]                                                                        |
| dilation          | Dilation angle [degrees]                                                                     |
| flag-brittle      | Specifies whether the tensile strength drops to zero upon tensile failure. Default is false. |
| friction          | Internal angle of friction [degrees]                                                         |
| poisson           | Poisson’s ratio [length/length]                                                              |
| shear             | Shear modulus [stress]                                                                       |
| specific-heat     | Specific heat [heat]                                                                         |
| thermal-expansion | Thermal expansion coefficient [length/length]                                                |
| Tension           | tensile strength [stress]                                                                    |
| young             | tensile strength [stress]                                                                    |
|                   |                                                                                              |
|                   |                                                                                              |
|                   |                                                                                              |
|                   |                                                                                              | 

>[!note]
>The default value for these properties (with the exceptions, as noted) is zero. Elastic properties may be specified using either bulk and shear modulus, or young’s modulus and Poisson’s ratio. Biot’s constant is optional and only used to calculate stress change in response to a pore-pressure change. Thermal-expansion, and Specific heat are only used in thermal calculations.
>这些属性的默认值（如所指出的除外）为零。 弹性特性可以使用体积和剪切模量，或杨氏模量和泊松比来指定。  Biot 常数是可选的，仅用于计算响应孔隙压力变化的应力变化。 热膨胀和比热仅用于热计算。

>[!注意]
>The default value for the block material properties is zero. For a rigid block model, density must be specified to execute a model run. For deformable blocks, density, bulk and shear must all be specified.
>The equations for bulk (K) and shear (G) modulus are
> K=E3(1−2ν)
> and
> G=E2(1+ν)
> where E is Young’s modulus, and ν is Poisson’s ratio. The user may enter either bulk and shear modulus, or Young’s modulus and Poisson’s ratio.
> 块材料属性的默认值为零。 对于刚性块模型，必须指定密度才能执行模型运行。 对于可变形块，必须指定密度、体积和剪切力。体积模量和剪切模量的方程是其中ν是杨氏模量，并且是泊松比。 用户可以输入体积和剪切模量，或杨氏模量和泊松比。