---
aliases: Section 1 Introduction
---

## 1.1 Overview 综述 
>The **Universal Distinct Element Code (UDEC)** is a two-dimensional numerical program based on the distinct element method for discontinuum modeling.
>**通用离散元程序**(UDEC)是一个基于*非连续*介质模型的不同单元法的*二维数值程序*。

>UDEC is based on a “Lagrangian” calculation scheme that is well-suited to model the large movements and deformations of a blocky system.
>基于“拉格朗日”计算方案，非常适合于对块状系统的大型运动和变形建模。

>UDEC also contains the powerful built-in programming language FISH (short for FLACish; FISH was originally developed for our two-dimensional, finite-difference, continuum program: FLAC)
>UDEC使用FISH语言，这一语言一开始是为Flac开发的

>discrete element method
>UDEC原理是*离散元法*

## 1.3 General Features
>UDEC is primarily intended for analysis in *rock engineering projects*, ranging from studies of *the progressive failure of rock slopes* to *evaluations of the influence of rock joints, faults, bedding planes, etc. on underground excavations and rock foundations*. UDEC is ideally suited to study potential modes of failure directly related to the presence of discontinuous features.
>UDEC主要*用于岩石工程项目的分析，从研究岩石边坡的渐进破坏，到评估岩石节理、断层、层理面等对地下开挖和岩石基础的影响*。 UDEC非常适合研究与不连续特征直接相关的潜在失效模式。

>The basic model is the Coulomb slip criterion, which assigns elastic stiffness, frictional, cohesive and tensile strengths, and dilation characteristics to a joint.
>其基本模型为*库仑滑移准则*，该准则将弹性刚度、摩擦强度、粘结强度、抗拉强度和剪胀特性赋予*节点*。

>**Blocks in UDEC can be either rigid or deformable**. There are seven built-in material models for deformable blocks, ranging from the “null” block material (which represents holes – excavations), to the shear and volumetric yielding models (which include strain-hardening/softening behavior and represent nonlinear, irreversible shear failure and compaction). Thus, **blocks can be used to simulate backfill and soil materials as well as intact rock**.
>UDEC中的块可以是刚性的，也可以是可变形的。
>因此，块体可以用来模拟回填土材料以及完整的岩石。

>UDEC is able to simulate the flow of fluid through the discontinuities and voids in the model.At present, blocks are impermeable. 
>UDEC能够模拟流体通过模型中的不连续面和空隙的流动。
>砌块是*不透水*的。

>There is also a **thermal model** available in UDEC. This model simulates the transient flux of heat in materials, and the subsequent development of thermally induced stresses. The heat flux is modeled by either isotropic or anisotropic conduction. **Heat sources can be added**, and can be made to decay exponentially with time.
>UDEC中有热模型
>可以增加热源

## 1.4 What’s New in UDEC 7.0
>The development that went into UDEC 7.0 had two main objectives. The first was to implement a new graphical interface (GUI) for the command line users of UDEC . For those familiar with the interface in the Itasca codes PFC, Flac3D, and 3DEC, this interface will be familiar. The second objective was to create a common command syntax that is consistent across all Itasca codes. **This resulted in a change to all commands in UDEC** . There are also many new model building features in UDEC.
>7.0中，命令更改了

### 1.4.1 New user interface
>You now have access to the best of two worlds: *the familiar UDEC GIIC* (Graphical Interface for Itasca Codes) with interactive modeling tools and *the new UDEC 7.0 GUI* (Graphics User Interface), which incorporates the interface used by 3DEC, with advanced graphics and powerful pre- and post-processing tools. Although project fifiles are unique to each of these platforms, UDEC 7.0 data and save fifiles can be readily exchanged by each program
>代码界面、图形界面

![Pasted image 20220521213921](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202206121527720.png)

### 1.4.2 New Command [[X_Attachment/01_Words Attachments/syntax|syntax]]（新命令语法）
>**All commands are reformulated in UDEC 7.0 (GUI and GIIC**) to follow a syntactical pattern of *NOUN - VERB - OPTION - MODIFIERS - RANGE*. Commands are more explicit and more [[X_Attachment/01_Words Attachments/intuitive (zh)|intuitive]]. They are easier to learn and apply, and are consistent in usage with other Itasca numerical modeling codes.
>7.0的所有代码均重制了。(提供了工具可以转换)
>语序为：*名词-动词-选项-修饰语-范围*
>例如```block create polygon 0,0 0,10 10,10 10,0```

### 1.4.3 Added FISH functionality (FISH功能增加)
>New Data Types In addition to the previous data types (integer, flfloating-point, string, and pointers), FISH variables now include several new data types: Boolean: Either a value of true or false. Vector: 2D or 3D vector of flfloating-point types. Array: A collection of FISH variables with specifified dimensionality. Matrix: Matrix of numeric values with specifified dimensionality. Tensor: A symmetric tensor (e.g., stress and strain). Map: An associative array with string or number key and any FISH variable as value. Structure: A structure may contain multiple FISH variables.
>加了几种新的数据模型。

>FISH variables can now be specifified as either local (to a particular FISH function) or global (UDEC 6 convention). 
>FISH变量可指定全部或局部

### 1.4.4 Built in Editor (GUI)
>automatic syntax color-coding
>UDEC 的代码编辑器可以实现自动语法颜色编码

### 1.4.5 Easy Stress Initialization (易于应力初始化)
### 1.4.6 New Block Creation Tools
>Built-in automatic block generation commands to create bricks and asymmetric Voronoi blocks.
>内置自动块生成命令，创建砖块和不对称Voronoi块。

### 1.4.7 Import Geometries (such as DXF)
>DXFs are required to be watertight and of good quality.
可从DXF文件导入模型（cad文件）,要求是防水和质量好。

### 1.4.8 Rock Support Additional Features
>In addition to improved visualization (GUI) for structural elements, a rock support database, including fully grouted bolts, end-anchor bolts, Swellex bolts, and split-set bolts (GIIC) is included. More examples for replicating manufacturer pull-test results have also been included (GUI/GIIC) to aid with model calibration.
>新加了岩石支持数据库，其中包括全灌浆螺栓、端锚螺栓、Swellex螺栓和分座螺栓(GIIC)。

### 1.4.9 Groups, Extra Variables
>**Up to 128 extra variables are now available for all objects** (blocks, zones, grid points, structural elements, contacts, etc.). See Help->Program Guide->Common Commands and FISH->Extra. The group logic is the tool used to categorize model objects. **Up to 128 different slot names can now be assigned to each group.** A slot can be thought of as an independent container of groups. See Help->Program Guide->Common Commands and FISH->Group
>现在有多达128个额外的变量可用于所有对象(块，区域，网格点，结构元素，接触，等等)。
>组逻辑是用来对模型对象进行分类的工具。最多128个不同的槽名现在可以分配给每个组。可以将槽看作组的独立容器。

### 1.4.10 3D joint specifification （三维接头规范）
### 1.4.11 Discrete Fracture Network (DFN离散裂缝网络）
>UDEC 7.0 also includes DFN logic with a built-in DFN generator based on a statistical description.
>UDEC 7.0还包括DFN逻辑与一个内置的基于统计描述的DFN生成器。

### 1.4.12 Factor of Safety [[X_Attachment/01_Words Attachments/Contours|Contours]]
>UDEC uses a factor of safety calculation for stability analyses based upon the “strength reduction metho”. A “factor of safet” index can be defifined for any relevant problem parameter by taking the ratio of the calculated [[X_Attachment/01_Words Attachments/parameter|parameter]] value under given conditions to the critical value of the parameter, at which the onset of an unacceptable outcome manifests itself. 
>UDEC在基于“强度折减法”的稳定性分析中使用了一个安全计算因子。
>对于任何相关的问题参数，可以定义一个“安全系数”指标，即给定条件下计算出的参数值与参数临界值的比值，在临界值处出现不可接受的结果。

### 1.4.13 Graphical Information Retrieval
>**When a View pane (plot) is active, the toolbar includes a group of buttons to set the current mouse mode to one of four states: Select, Query, Center, and Distance.** When the Query mode is selected, as highlighted in the image below, you can use the mouse [[X_Attachment/01_Words Attachments/cursor|cursor]] to inspect your model. Clicking on a location in the model will provide a list of one or more objects that can be queried (e.g., block, zone, gridpoint). Selecting an object from the menu will open a dialog that contains model information [[X_Attachment/01_Words Attachments/pertinent|pertinent]] to it as shown; data can be copied to the clipboard or logged.
>**当View窗格(绘图)处于活动状态时，工具栏包含一组按钮，用于将当前鼠标模式设置为以下四种状态之一:选择、查询、居中和距离**。
>当选择Query模式时，如下图所示，您可以使用鼠标光标检查您的模型。 点击模型中的一个位置将提供一个或多个可查询对象的列表(例如，块、区域、网格点)。
>从菜单中选择一个对象将打开一个对话框，其中包含与该对象相关的模型信息，如图所示;数据可以复制到剪贴板或记录。![Pasted image 20220521221103](https://obsidianxjb.oss-cn-hangzhou.aliyuncs.com/obsidian/202206121527746.png)

### 1.4.14 Contact Failure States
### 1.4.15 Added future Save File Compatiblity
### 1.4.16 GUI project fifiles
>A project in UDEC (GUI) may now be created. The use of project fifile in the UDEC GUI is highly recomended. **The fifile contains all plots and links to all input and save fifiles. The project fifile and all data and save fifiles can be bundles for achiving or sharing.** See Help->Program Guide->Program Mechanics->Projects.
>该文件包含所有绘图和到所有输入和保存文件的链接。该项目文件和所有数据和保存文件可以捆绑实现或共享。

### 1.4.17 Technical Support Dialog
### 1.4.18 Dynamic Input [[X_Attachment/01_Words Attachments/Wizard|Wizard]]
### 1.4.19 Updated save/restore system

## 1.5 Fields of Application（应用）
>UDEC was originally developed to perform stability analysis of jointed rock slopes. The discontinuum formulation for rigid blocks and the explicit time-marching solution of the full equations of motion (including inertial terms) facilitate the analysis of progressive, large-scale movements of slopes in [[X_Attachment/01_Words Attachments/blocky rock|blocky rock]]
>UDEC 最初是为**进行节理岩质边坡的稳定性分析**而开发的。

>UDEChas been applied most often in studies related to mining engineering.
>在**矿业工程**相关研究中，应用最多的是udec

>UDEChas also been applied in the fifields of underground construction and deep underground storage of high-level radioactive waste.
>该技术还被应用于**地下建筑和高放射性废物的深层地下储存领域**。

>However, the program is better-suited to investigate potential failure [[X_Attachment/01_Words Attachments/mechanisms|mechanisms]] associated with the response of a jointed rock mass. The nature of a jointed rock mass is that it is a “data-limited” system (i.e., the internal structure and stress state are, in large part, unknown and unknowable).
>该程序更适合于**研究与节理岩体响应相关的潜在破坏机制**。

>The new cell space detection logic in UDEC does allow for the analysis of flflying blocks, but is not effificient for problems with thousands of tiny particles. Finally, in order to evaluate the importance of three-dimensional geometry on response of a system, a three-dimensional numerical program, such as the Itasca code 3DEC or PFC3D, is required.
>UDEC中新的单元空间检测逻辑确实允许对飞散块进行分析，但对于数千个微小粒子的问题来说，它并不有效.
>三维数值程序，如Itasca代码3DEC或PFC3D。

## 1.6 Guide to the Manual
![[A_UDEC用户手册/B_UDEC手册/1.6 用户手册整理]]