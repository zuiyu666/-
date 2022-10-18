2022/06/29
*用UDEC解决岩石力学工程相关问题的指导*
# 3 PROBLEM SOLVING WITH UDEC（综述）
在3.1节中，给出了进行地质力学分析的建议步骤概要，在3.2节至3.10节中，检查了在任何模型创建和解决方案中必须考虑的具体方面，包括:
• 选择刚性或变形块分析(章节3.3);
• 边界和初始条件(3.4和3.5节);
• 加载和顺序建模(章节3.6);
• 块体和节理本构模型和材料性能的选择(章节3.7和章节3.8);
• 提高建模效率的方法(第3.9节);
• 结果解释(章节3.10)

| 章节  | 内容                           |
| ----- | ------------------------------ |
| [3.1节](obsidian://open?vault=XU&file=A_%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95%2F2022.06-07%2F3.1%20%E4%B8%80%E8%88%AC%E6%96%B9%E6%B3%95%EF%BC%88%E7%BB%BC%E8%BF%B0%EF%BC%89) | 进行地质力学分析的建议步骤概要 |
| [3.2节](obsidian://open?vault=XU&file=A_%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95%2F2022.06-07%2F3.2%20%E6%A8%A1%E5%9E%8B%E7%94%9F%E6%88%90) | 模型生成                       |
| [3.3节](obsidian://open?vault=XU&file=A_%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95%2F2022.06-07%2F3.3%20%E5%8F%AF%E5%8F%98%E5%BD%A2%E5%9D%97%E4%B8%8E%E5%88%9A%E6%80%A7%E5%9D%97%E7%9A%84%E9%80%89%E6%8B%A9) | 可变形块与刚性块的选择         |
| [3.4节](obsidian://open?vault=XU&file=A_%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95%2F2022.06-07%2F3.4%E8%BE%B9%E7%95%8C%E6%9D%A1%E4%BB%B6) | 边界条件                       |
|       |                                |

>You will note that FISH is used in this section to assist with model generation and problem solving.
>您将注意到，本节使用FISH来协助模型生成和问题解决。

>If you have not used FISH before, we recommend that you fifirst read the FISH tutorial in Section 4.
>如果您以前没有使用过FISH，我们建议您首先阅读第4节中的FISH教程。

>Finally, the philosophy of modeling in the fifield of geomechanics is examined in Section 3.11; the novice modeler in this fifield may wish to consult this section fifirst.
>最后，在3.11节中考察了地质力学领域的建模学;新手建模先看这一节。

>The methodology of modeling in geomechanics can be signifificantly different from that in other engineering fifields, such as structural engineering. It is important to keep this in mind when performing any geomechanics analysis. 
>地质力学的建模方法与结构工程等其他工程领域的建模方法有很大的不同。在进行任何地质力学分析时，牢记这一点很重要。

>The discussion and examples provided in this section use the command-line approach to input data to UDEC. Although all of the operations can be achieved by means of the graphical interface (the GIIC – see Section 2.2.1), the principles of model setup, execution and interpretation remain the same.  [^1]
>本节中的讨论和示例**使用命令行方法向UDEC输入数据**。

[^1]:本节中的数据文件存储在Datafiles\Users Guide\Problem Solving with extension " . dat "文件夹中。还为每个示例提供了一个项目文件。



