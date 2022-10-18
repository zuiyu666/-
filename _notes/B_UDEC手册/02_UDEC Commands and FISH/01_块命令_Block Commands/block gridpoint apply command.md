---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 2:24:44 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*指定块边界条件*
>[!block gridpoint apply keywords:]
>force-x &nbsp;&nbsp;&nbsp;&nbsp; force-y&nbsp;&nbsp;&nbsp;&nbsp;free-x&nbsp;&nbsp;&nbsp;&nbsp;free-y&nbsp;&nbsp;&nbsp;&nbsp;
>velocity-gradient&nbsp;&nbsp;&nbsp;&nbsp;velocity-normal&nbsp;&nbsp;&nbsp;&nbsp;veolocity-shear&nbsp;&nbsp;&nbsp;&nbsp;
>velocity-x&nbsp;&nbsp;&nbsp;&nbsp;velocity-y&nbsp;&nbsp;&nbsp;&nbsp;viscous-x&nbsp;&nbsp;&nbsp;&nbsp;viscous-y&nbsp;&nbsp;&nbsp;&nbsp;
>bulk&nbsp;&nbsp;&nbsp;&nbsp;shear&nbsp;&nbsp;&nbsp;&nbsp;density&nbsp;&nbsp;&nbsp;&nbsp;young&nbsp;&nbsp;&nbsp;&nbsp;poisson&nbsp;&nbsp;&nbsp;&nbsp;material&nbsp;&nbsp;&nbsp;&nbsp;history

Boundary conditions are specified for an external boundary over a specified range. If BLOCK CONFIG CELL has been specified, boundary commands will apply to the outer edges of all blocks with the range. Otherwise the boundary conditions are applied only to the outside edges of the model. If the range is omitted, the boundary condition applies to the entire model boundary. Boundary forces can be applied to both rigid and deformable blocks. Boundary velocities can only be applied to deformable blocks. Boundary conditions are defined by a given boundary condition keyword. See also the block edge apply command for free-field, fluid, and stress boundaries. The keywords and associated parameters are as follows.
>为指定范围内的外部边界指定边界条件。如果指定了BLOCK CONFIG CELL，边界命令将应用于范围内所有块的外边缘。否则，边界条件仅应用于模型的外边缘。如果忽略范围，则边界条件将应用于整个模型边界。边界力可以应用于刚性块和可变形块。边界速度只能应用于可变形块。边界条件由给定的边界条件关键字定义。另请参见自由场、流体和应力边界的块边应用命令。关键字和相关参数如下所示。

## **Forces**（力边界条件）
### force-x f 
Set x-direction load to apply to each gridpoint (see Note 1).

### force-y f 
Set -direction load to apply to each gridpoint (see Note 1).
>设置应用于每个网格点的X/Y方向载荷

>[!note]
>All forces are assumed to be constant and permanent by default, and are added to the existing permanent loads.
CAUTION: The BLOCK EDGE APPLY stress command affects all degrees of freedom. For example, if BLOCK EDGE APPLY stress follows a BLOCK GRIDPOINT vel-x or vel-y command affecting the same gridpoint(s), then the effect of the previously prescribed vel-x or vel-y will be lost (.i.e. do stresses before velocities).
>默认情况下，假设所有力都是恒定和永久的，并将其添加到现有的永久荷载中。
>注意：BLOCK EDGE APPLY应力命令会影响所有自由度。例如，如果BLOCK EDGE APPLY应力遵循影响同一网格点的BLOCK GRIDPOINT vel-x或vel-y命令，则先前规定的vel-x和vel-y的效果将消失（即**先应力后速度**）。

## **Free Boundaries**(释放边界)
### free-x 
Remove a boundary condition and all forces in the x-direction.

### free-y 
Remove a boundary condition and all forces in the y-direction.
>移除边界条件和x/y方向上的所有力。

## **Velocity boundaries**（速度边界条件）
### velocity-gradient fxo fyo fxx fxy fyx fyy 
Apply a velocity gradient to the boundary.
将速度梯度应用于边界。

### velocity-normal f 
Apply normal direction velocity for deformable blocks.
对可变形块应用法向速度。

### veolocity-shear f 
Apply shear direction velocity for deformable blocks.
对变形块应用切向速度。

### velocity-x f 
Apply -direction velocity for deformable blocks.
应用可变形块的方向速度。

### velocity-y f 
Apply -direction velocity for deformable blocks.
应用可变形块的y方向速度。

### viscous-x f 
Apply -direction velocity for deformable blocks.
适用于可变形块的方向速度。

### viscous-y f 
Apply -direction velocity for deformable blocks.
适用于可变形块的y方向速度。

## **Boundary properties**（边界特性）
These properties are used for boundary-element boundaries, the dynamic free-field boundaries and for viscous (quiet) boundaries.
>这些属性用于边界元素边界、动态自由场边界和粘性（安静）边界。

### bulk f 
Apply far-field bulk modulus (see Note 2).
应用远场体积模量（见注2）。

### shear f 
Apply far-field shear modulus (see Note 2).
应用远场剪切模量（见注2）。

### density f 
Apply far-field density (see Note 2).
应用远场密度（见注2）。

### young f 
Apply far-field Young’s modulus (see Note 2).
应用远场杨氏模量（见注2）。

### poisson f 
Apply far-field Poisson’s ratio (see Note 2).
应用远场泊松比（见注2）。

### material i 
Assign material number i to far-field properties (required for nonreflecting boundaries; see Note 2).
材料i将材料编号i指定给远场特性（非反射边界需要；见注2）。

>[!note2]
>Far-field elastic properties can be specified in three ways: by material number (in which case the properties are specified using the block property command); by density, bulk and shear modulus; or by density, Young’s modulus and Poisson’s ratio.
>场弹性特性可以通过三种方式指定：通过材料编号（在这种情况下，使用块特性命令指定特性）；密度、体积模量和剪切模量；或者通过密度、杨氏模量和泊松比。

## **Histories**
A time varying history may be applied to an applied boundary condition.
应用之前的条件于边界。

The keyword history defines a time history that is a multiplier for all the forces and x- and y-velocities given on the same input line.
>关键字history定义了一个时间历程，它是同一输入线上给定的所有力以及x和y速度的乘数。

>[!note]
>Loads assigned a history are considered transient loads, and are stored separately from any permanent loads assigned to the same corners. If a corner already has a transient load, any new load with the same history type (see below) is added to it; however, a new transient load with a different history type replaces the old transient load.
>指定历史的载荷被视为瞬态载荷，并与指定给相同转角的任何永久载荷分开存储。如果拐角已经有瞬态载荷，则会向其添加具有相同历史类型（见下文）的任何新载荷；然而，一个具有不同历史类型的新瞬态负载取代了旧的瞬态负载。

Boundary forces and velocities can be applied as a constant, sinusoidal or user-defined FISH function, or they may consist of a series of points given by a TABLE command or read from a file. The keywords must be given on the same line specifying the load, stress or velocity.
>边界力和速度可以作为常数、正弦曲线或用户定义的FISH函数应用，也可以由TABLE命令给出的一系列点或从文件中读取的点组成。关键字必须在指定载荷、应力或速度的同一行上给出。

#未完成
### cosine ffreq ftime 
Get a history of cosine wave load with frequency ffreq (cycles/sec) applied for a problem time period of ftime.

### funcname 
Use the user-defined fish function named funcname as the history multiplier.

### sine ffreq ftime 
Get a history of cosine wave load with frequency ffreq (cycles/sec) applied for a problem time period of ftime.

### table i 
Input the history via the table commands. Table i consists of a list of pairs: , . Linear interpolation is performed between the given discrete points.

Multipliers Multipliers can be applied to load and velocity boundaries using the following keywords.
>乘数可以使用以下关键字将乘数应用于载荷和速度边界。

multiply-normal f 
Normal-direction load multiplier (default = 1.0)  
multiply-shear f 
Shear-direction load multiplier (default = 1.0)  
multiply-x f 
x-direction load multiplier (default = 1.0)  
multiply-y f 
y-direction load multiplier (default = 1.0)