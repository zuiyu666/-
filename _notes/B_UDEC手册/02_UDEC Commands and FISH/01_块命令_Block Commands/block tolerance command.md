---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 2:16:37 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
>[!block tolerance keywords:]
>minimum-edge-length  &nbsp;&nbsp;&nbsp;&nbsp;  corner-round-length

Set default configuration values for blocks.
>设置块的默认配置值。

### minimum-edge-length f

Set the minimum block edge. The default value is twice the corner round length. f must be ≥ twice the corner round length. This command should be specified before the BLOCK command.
>最小边缘长度f设置最小块边缘。默认值是圆角长度的两倍。f必须≥ 圆角长度的两倍。此命令应在BLOCK命令之前指定。

### corner-round-length f

Each block corner is rounded with a circle that is tangential to the two corresponding edges at a distance f from the corner. The default value for f is 0.5. A round length equal to one percent of the typical block edge length is recommended. It should be noted that for deformable blocks, corner gridpoints are located at the corner of the unrounded block. It is also recommended that, once the round length is specified, it should not be changed, especially after cycling is initiated.
>每个块角都用一个圆进行圆角，该圆与距离角f的两个相应边相切。f的默认值为0.5。建议圆角长度等于典型块边长度的1%。应注意，对于可变形块，角网格点位于未圆角块的角。还建议，一旦规定了圆形长度，就不应更改，尤其是在循环开始后。
