---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块边界元素命令*
>[!block boundary-elements keywords:]
>fix(固定) &nbsp;&nbsp;&nbsp;&nbsp; generate(生成) &nbsp;&nbsp;&nbsp;&nbsp; halfspace &nbsp;&nbsp;&nbsp;&nbsp; list &nbsp;&nbsp;&nbsp;&nbsp; property &nbsp;&nbsp;&nbsp;&nbsp; stiff

Apply boundary-element conditions to the boundary domain (limit 300). Boundary elements are on by default.
>将边界元素条件应用于边界域（限制为300）。默认情况下，边界元素处于启用状态。

It is recommended that the user apply the block boundary-element commands after the model comes to initial (i.e.,consolidation)equilibrium under in-situ loading conditions.\[1\](Use the block edge apply stress for example,to apply boundary stresses initially.)The recommended order of the block boundary-element commands is as follows.
>建议用户在模型在原位加载条件下达到初始（即固结）平衡后应用块边界元素命令。\[1\]（例如，使用块边缘施加应力，以初始施加边界应力。）块边界元素的建议命令顺序如下。

```udec
block boundary-elements generate
block boundary-elements halfspace
block boundary-elements material
block boundary-elements fix
block boundary-elements stiff
```

>[!note]
>Contacts at the boundary are assigned material properties according to the block boundary-element property command. Use the block change command to set different material conditions at the boundary.
>边界处的接触将根据块边界元素特性命令指定材质特性。使用块更改命令在边界处设置不同的材质条件。

fix f1 f2 f3 f4 
 Fix a point (f1, f2) in the -direction and a point (f3, f4) in the -direction outside the model region (must precede the stiff keyword).

generate <range> 
 Generate a boundary-element domain along the outer boundary of a region described by range  

halfspace 
 Half-plane solution for boundary-element domain, assuming surface at  = 0 (must precede the stiff keyword)  

list keyword 
 Print induced stress and displacements in boundary elements. The following keywords may be used to separate displacement and stress output.
  displacement 
   Displacement at boundary nodes. The column headings are as follows.
    (1)	boundary element node number 
    (2)	-coordinate of node 
    (3)	-coordinate of node
    (4)	-displacement of node 
    (5)	-displacement of node
    (6)	-direction traction at node 
    (7)	-direction traction at node 
    
    
stress Stresses at boundary nodes. The column headings are as follows.
(1)	boundary element node number (2)	-coordinate of node (3)	-coordinate of node (4)	tangential stress component in element (5)	normal stress component in element (6)	shear stress component in element location Boundary element position information. The column headings are as follows.
(1)	boundary corner index (2)	associated block corner index (3)	associated gridpoint index (4)	-coordinate of boundary corner (5)	-coordinate of boundary corner (6)	associated boundary element node (7)	second boundary element node (8)	boundary element load-distribution factor field n f1 f2 f3 f4 keyword List induced stress and displacements at :num:’n’ points along line between (f1, f2) and (f3, f4) in boundary element domain. The following keywords may be used to separate displacement and stress output.
disp Displacements at interior boundary element domain points. The column headings are as follows:  (1)	interior point number (2)	x-coordinate of point (3)	y-coordinate of point (4)	x-displacement of point (5)	y-displacement of point stress Stresses at interior boundary element domain points. The column headings are as follows:  (1)	interior point number (2)	x-coordinate of point (3)	y-coordinate of point (4)	xx-stress component of point (5)	xy-stress component of point (6)	yy-stress component of point (7)	major principal stress of point (8)	minor principal stress of point (9)	orientation of major principal stress from x-axis property keyword bulk f Bulk modulus for for outside rock mass.[2]  density f Density for outside rock mass.
material i Material property number to use for boundary-element properties.
poisson f Poisson’s ratio for outside rock mass.
shear f Shear modulus for outside rock mass.
young f Young’s modulus for outside rock mass.
stiff Automatically generate stiffness matrix.
Endnotes  [1]	Warning: All model stresses must be specified in units of MPa for the boundary-element boundary. Boundary-elements can only be applied for the plane-strain condition (see Section 3.4.4.3 in the User’s Guide).
[2]	Properties for boundary element domain (outside rock mass) are be specified by material number, bulk and shear modulus, or by Young’s modulus and Poisson’s ratio.