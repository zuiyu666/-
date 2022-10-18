---
aliases: 
tags: 
width:
date created: 星期一, 十月 17日 2022, 9:32:22 上午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
```udec
block group s <keyword> <range>
```

>[!keywords:]
>remove    slot.

Add group name s to the blocks in the range. Use of the group logic is described in Group. A shortcut form of the command may be used. Block group “groupname” slot “slotname” is equivalent to block group "slotname = groupname" — quotation marks required, spaces at equals sign ignored — where slotname is the slot assignment and groupname is the group name.
>将组名s添加到范围内的块中。
group的使用在group中进行了描述。
可以使用命令的快捷形式。
块组" groupname" slot "slotname "等价于块组"slotname = groupname" -需要引号，等号处的空格忽略-其中slotname是槽位分配，groupname是组名。

A block may belong to many groups, up to a maximum of 128. The group range element can be used to select objects by group name. block list group can be used to identify existing block group names.
>一个块可以属于多个组，最多可以属于128个组。
组范围元素可用于按组名选择对象。
块列表组可用于识别现有块组名称。

The following optional keywords are available:
>可选关键字如下:

### remove 
Remove s from the blocks. If a slot is not specified, the group name is removed from all slots it is found in.
>从方块中移除s。
如果没有指定槽位，则从它所在的所有槽位中删除组名。

### slot s 
Assign the group to the slot named s. The default slot name is Default.
>slot s将组分配给名为s的槽位。默认槽位名称为default。
