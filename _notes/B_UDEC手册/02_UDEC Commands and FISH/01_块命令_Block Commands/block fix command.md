---
aliases: 
tags: 
width:
date created: 星期六, 十月 15日 2022, 4:24:32 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块固定命令*
block fix \<keywords\> range 
>[!block fix keywords:]
>all    velocity-x    velocity-y    rotation

Fix current velocities of all blocks with centroids in the specified range. Deformable blocks cannot be fixed. Velocity histories may be applied using FISH functions. Note: This command does not zero the current velocity, so, if the block centroid velocity is non-zero, it will continue with that value held constant.
>固定质心在指定范围内的所有块的当前速度。无法修复可变形块。速度历史可以使用FISH函数应用。注意：此命令不会将当前速度归零，因此，如果块质心速度不为零，它将继续保持该值不变

### all 
Fix x,y and rotational velocities.
>固定所有x，y和旋转速度。

### velocity-x
Fix only in the x-direction.
>仅固定x方向。

### velocity-y
Fix only in the y-direction.
>仅固定y方向。

### rotation
Fix only rotation.
>仅固定旋转
