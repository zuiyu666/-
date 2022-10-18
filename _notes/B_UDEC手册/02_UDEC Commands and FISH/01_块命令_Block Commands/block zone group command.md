---
aliases: 
tags: 
width:
date created: 星期六, 十月 15日 2022, 5:14:49 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块分区编组命令*

>[!block zone group keywords:]
>remove    slot

Add group name s to the zones in the range. Use of the group logic is described in Group. A shortcut form of the command may be used. Block zone group “groupname” slot “slotname” is equivalent to block zone group "slotname = groupname" — quotation marks required, spaces at equals sign ignored — where slotname is the slot assignment and groupname is the group name.
>将组名称添加到范围中的分区。组逻辑的使用在组中描述。可以使用命令的快捷方式。块分区组“groupname”slot“slotname”等同于块分区组”slotname=groupname“-需要引号，忽略等号处的空格-其中slotname是插槽分配，groupname是组名。

A zone may belong to many groups, up to a maximum of 128. The group range element can be used to select objects by group name. block zone list group can be used to identify existing zone group names.
>一个zone可以属于多个组，最多可以属于128个组。
组范围元素可用于按组名选择对象。
块区域列表组可用于标识现有的区域组名称。

The following optional keywords are available:
>可选关键字如下:

### remove 
Remove s from the zones. If a slot is not specified, the group name is removed from all slots it is found in.
>从分区中删除。如果没有指定槽位，则从它所在的所有槽位中删除组名。

### slot s 
Assign the group to the slot named s. The default slot name is Default.
>slot s将组分配给名为s的槽位。默认槽位名称为default。