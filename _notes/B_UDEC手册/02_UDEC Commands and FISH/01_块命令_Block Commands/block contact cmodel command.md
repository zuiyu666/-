---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
*块节理赋值命令*

>[!block contact cmodel keyword:]
>assign  &nbsp;&nbsp;&nbsp;&nbsp;  default  &nbsp;&nbsp;&nbsp;&nbsp;  default  &nbsp;&nbsp;&nbsp;&nbsp;  list  &nbsp;&nbsp;&nbsp;&nbsp;  load

There are presently two independant methods for assigning constitutive models and properties to contacts\[1\]. The method described here assigns a constitutive model to each contact and that contact has its own local set of properties. This method uses more mememory, but is more flexible. Using this method, FISH may be used to modify the properties during cycling. The basic form of this command will associate a constitutive model with contacts in the specified range. This command can also be used to assign properties to the contacts by following the model name with the property keywords. Contact model properties may also be assigned using the block contact property command. At present, five joint constitutive models are available through the use of this command: Coulomb slip (point contact); Coulomb slip (area contact); Coulomb slip with residual strength (area contact); continuously yielding; and Barton-Bandis (optional model).

>目前有两种独立的方法可以将本构模型和属性分配给联系人\[1\]。此处描述的方法为每个联系人分配一个本构模型，并且该联系人具有自己的本地属性集。这种方法使用更多的记忆，但更灵活。使用此方法，可以使用 FISH 在循环期间修改属性。此命令的基本形式是将本构模型与指定范围内的联系人相关联。此命令还可用于通过在模型名称后面跟有属性关键字来为联系人分配属性。还可以使用块联系人属性命令来分配联系人模型属性。目前，通过使用该命令可以获得五种联合本构模型：库仑滑移（点接触）;库仑滑移（区域接触）;具有残余强度的库仑滑移（区域接触）;持续屈服;和巴顿-班迪斯（可选型号）。

This command is also used to load and assign user defined contact (joint) models. The user defined contact models is an optional feature in UDEC. At present, one example user defined joint constitutive model is available through use of this command. This model is described in Section 4.2.2 in Constitutive Models.
>此命令还用于加载和分配用户定义的接触（关节）模型。用户定义的接触模型是 UDEC 中的可选功能。目前，一个用户定义的联合本构模型的例子可以通过使用这个命令来获得。此模型在本构模型的第 4.2.2 节中进行了描述。

The model must be assigned before assigning properties. If properties that are not consistent with the chosen model are given, a warning message will be issued to inform the user that the unneeded properties were not accepted. If a required property is not specified, the default will be used. WARNING: When a model is invoked over a specified range, all properties associated with that model are initialized to zero in that range. Properties previously assigned to that range must be specified again, even if their values have not changed.
>在分配属性之前，必须分配模型。如果给出了与所选模型不一致的属性，则将发出警告消息，通知用户不需要的属性未被接受。如果未指定必需属性，则将使用默认值。警告：在指定范围内调用模型时，与该模型关联的所有属性都将在该范围内初始化为零。必须再次指定以前分配给该范围的属性，即使其值未更改也是如此。

Examples of this command are:
```udec
block contact cmodel assign area
block contact cmodel assign area stiffness-normal 2e9 stiffness-shear 1e9
The model and properties that are assigned to new contacts that are formed during cycling can also be specified using this command. An example of this usage is:
block contact cmodel default area stiffness-normal 2e9 stiffness-shear 1e9
block comtact cmodel default 2 material 1
```

The Coulomb slip models are described in Section 1.2.4 in Theory and Background, the continuously yielding model is described in Section 2 in Constitutive Models, and the Barton-Bandis model is described in Section 3 in Constitutive Models. Any joint constitutive model that already exists for some or all of the contacts in the given range (as specified by the block contact change model command) is ignored. The block contact default-model command may be used to specify a model and properties to be used for new contacts.
>库仑滑移模型在《理论与背景》第1.2.4节中进行了描述，连续屈服模型在《本构模型》第2节中进行描述，Barton Bandis模型在《组织模型》第3节中进行介绍。对于给定范围内的部分或全部接触（如块接触更改模型命令所规定），已存在的任何联合本构模型均被忽略。块接触默认模型命令可用于指定用于新接触的模型和特性。

