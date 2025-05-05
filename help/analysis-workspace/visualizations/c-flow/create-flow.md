---
description: 了解如何在Workspace项目中使用流量可视化图表。
title: 如何配置流量可视化图表
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 933b4005724aa438c3daeb58191e940821b5bb5f
workflow-type: tm+mt
source-wordcount: '1709'
ht-degree: 79%

---

# 配置流量可视化图表 {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_startswith"
>title="开始于"
>abstract="此字段只能在初始构建时设置。 要更新此字段，请选择&#x200B;**[!UICONTROL 重置]**&#x200B;以构建新的流量可视化图表。"

>[!CONTEXTUALHELP]
>id="workspace_flow_contains"
>title="包含"
>abstract="此字段只能在初始构建时设置。 要更新此字段，请选择&#x200B;**[!UICONTROL 重置]**&#x200B;以构建新的流量可视化图表。"

>[!CONTEXTUALHELP]
>id="workspace_flow_endswith"
>title="结束于"
>abstract="此字段只能在初始构建时设置。 要更新此字段，请选择&#x200B;**[!UICONTROL 重置]**&#x200B;以构建新的流量可视化图表。"

>[!CONTEXTUALHELP]
>id="workspace_flow_pathingdimension"
>title="路径维度"
>abstract="选择一个维度，用作通往或者离开您的选定组件的路径。"

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="流量容器"
>abstract="选择用于显示路径（的数字）的容器。"

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_disabled"
>title="包含重复项（已禁用）"
>abstract="无法从包含多值维度的 Flow 可视化中移除重复项。"

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_default"
>title="包括重复"
>abstract="流量可视化图表基于某个维度的实例。此设置使您可以选择包含或排除重复的实例，例如：页面重新加载。"

>[!CONTEXTUALHELP]
>id="workspace_flow_limit_occurrence"
>title="限制到第一次/最后一次发生次数"
>abstract="当第一个/最后一个接触点是入口/出口时，结果仅限于路径。"

>[!CONTEXTUALHELP]
>id="workspace_flow_numberofcolumns"
>title="列数"
>abstract="此字段只能在初始构建时设置。 要更新此字段，请选择&#x200B;**[!UICONTROL 重置]**&#x200B;以构建新的流量可视化图表。"

>[!CONTEXTUALHELP]
>id="workspace_flow_itemsexpandedpercolumn"
>title="每列扩展的项"
>abstract="此字段只能在初始构建时设置。 要更新此字段，请选择&#x200B;**[!UICONTROL 重置]**&#x200B;以构建新的流量可视化图表。"

>[!CONTEXTUALHELP]
>id="workspace_flow_resettoupdate"
>title="重置为更新"
>abstract="此字段只能在初始构建时设置。 要更新此字段，请选择&#x200B;**[!UICONTROL 重置]**&#x200B;以构建新的流量可视化图表。"


流量可视化帮助您了解源自网站或应用程序上特定转化事件的旅程。 或导致特定的转化事件。 可视化图表通过维度（和维度项）或量度跟踪路径。

您可以配置感兴趣的路径的起点或终点。 或者分析流经维度或维度项的所有路径。

![显示Starts with、Contains和Ends with字段的流配置屏幕。](assets/new-flow.png)

## 使用

1. 添加 ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;可视化图表。请参阅[将可视化图表添加到面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 使用以下选项之一锚定流量可视化图表：

   * 以（量度、维度或项目）[!UICONTROL **开头**]，或
   * [!UICONTROL **包含**]（维度或项目），或
   * 以（量度、维度或项目）[!UICONTROL **结束**]

   其中每种类别在屏幕上都显示为一个&#x200B;*放置区域*。可以通过3种方式填充放置区域：

   * 使用下拉菜单选择量度或维度。
   * 从左侧面板中拖动维度或量度。
   * 开始键入维度或量度的名称，然后在该维度或量度出现在下拉菜单中时将其选定。

   >[!IMPORTANT]
   >
   >计算量度不能用于&#x200B;**[!UICONTROL 开始于]**&#x200B;或&#x200B;**[!UICONTROL 结束于]**&#x200B;字段。

1. 如果您选择一个量度，则还需要提供一个&#x200B;[!UICONTROL **“路径”维度**]，用作通往或者来自选定组件的路径，如此处所示。默认的是 [!UICONTROL **页面**]。

   ![流量配置](assets/flow-configure.png)

1. （可选）选择&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;以配置以下任一选项：


   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 包装标签]** | 通常情况下，流量元素上的标签会被截断以节约屏幕资源，但您可以通过选中此框使整个标签可见。默认值 = 取消选中。 |
   | **[!UICONTROL 包括重复实例]** | 流量可视化图表基于某个维度的实例。此设置使您可以选择包含还是排除重复实例，例如页面重新载入。但是，不能从包含多值维度（例如 listVar、listProp、s.product、推销 eVar 等）的流量可视化图表中删除重复项。 <p>默认禁用此选项。</p> |
   | **[!UICONTROL 限制到第一次/最后一次发生次数]** | 将路径限制为以维度、项目或量度的第一次或最后一次发生次数开始或结束的路径。有关更详细的解释，请参阅[限制到第一次/最后一次发生次数](#example-scenario-for-limit-to-firstlast-occurrence)。 |
   | **[!UICONTROL 列数]** | 流量图中所需的列数。您最多可以指定 5 个列。 |
   | **[!UICONTROL 每列扩展的项]** | 每列中所需的项数。您最多可以指定每列扩展 10 个项。 |
   | **[!UICONTROL 流量容器]** | 您可以在&#x200B;**[!UICONTROL 全局帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 机会]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 购买群]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 会话]**&#x200B;和&#x200B;**[!UICONTROL 人员]**&#x200B;之间切换以分析路径。 这些设置可帮助您在人员级别（跨会话）了解人员参与度，或将分析限定于单次会话。 |

   >[!IMPORTANT]
   >
   >**[!UICONTROL 列数]**&#x200B;和&#x200B;**[!UICONTROL 每列扩展的项]**&#x200B;的组合确定创建流量可视化图表所需的基础请求数量。该数量越多，渲染可视化图表所需的时间就越长。


1. 选择&#x200B;**[!UICONTROL 生成]**。


### 示例

假设您要跟踪用户用来访问或离开您网站上最受欢迎页面的路径。

1. 创建流量可视化图表，如上所述。
1. 将&#x200B;[!UICONTROL **页面**]&#x200B;维度拖入&#x200B;**[!UICONTROL 包含]**&#x200B;字段中，然后选择&#x200B;[!UICONTROL **生成**]。
1. 流量可视化图表使用可视化图表中心的关注节点中可见的查看次数最多的页面来生成。您还可以看到进入该关注页面的查看次数最多的页面（位于关注节点的左侧）以及离开该关注页面的查看次数最多的页面（位于关注节点的右侧）。
1. 分析流量中的数据，如[配置](#configure)中所述。


## 配置

流量配置的摘要显示在可视化图表的顶部。图表中的路径按比例显示。活动越多，路径越粗。

![显示访问结束、路径维度的流量输出示例：页面和流量容器：访客。](assets/flow-output.png)

要进一步深入了解数据，您有几个选项：

* 流量图是交互式图表。将光标置于该图上可更改显示的详细信息。

* 选择图表中的节点时，将显示该节点的详细信息。再次选择该节点以将其折叠。

  ![显示节点详细信息的示例交互式流量图。](assets/node-details.png)

* 您可以通过筛选列仅显示某些结果，例如包括和排除、指定条件等。

* 选择左侧或右侧的 ![AddCircle](/help/assets/icons/AddCircle.svg) 以展开一列。

* 要自定义输出，请使用[上下文菜单](#context-menu)选项。

* 要编辑流量或使用不同选项重新生成流量，请选择配置摘要旁边的![编辑](/help/assets/icons/Edit.svg)。

## 过滤器

当您将光标悬停在每列上方时，会显示出一个![过滤器](/help/assets/icons/Filter.svg)过滤器。通过选择过滤器，您将获得与自由格式表中存在的相同的过滤器对话框。请参阅[过滤和排序](freeform-table/../../freeform-table/filter-and-sort.md)。

* 使用&#x200B;**[!UICONTROL 显示高级]**&#x200B;来配置高级设置，使用运算符列表包含或排除某些条件。有关更多信息，请参阅[过滤和排序](../freeform-table/filter-and-sort.md)。
* 一旦您过滤了某一列，该特定列就会反映出过滤结果。蓝色![过滤器](/help/assets/icons/FilterColored.svg)表示该列已被过滤。过滤器可以缩小列，仅显示过滤器中允许的项目。或除了所需的一个项目，移除过滤器中的所有项目。
* 只要有数据流入其余节点，所有下游和上游列都保持不变。
* 要移除过滤器，请选择![过滤器](/help/assets/icons/Filter.svg)以打开过滤器菜单。删除应用的任何过滤器，然后选择&#x200B;**[!UICONTROL 保存]**。流量应返回到其先前的未过滤状态。

## 上下文菜单

使用流量可视化图表中任意节点上的上下文菜单，其中包含以下选项：

| 选项 | 描述 |
|--- |--- |
| **[!UICONTROL 关注此节点]** | 转而关注选定的节点。关注节点在流量图表的中间显示。 |
| **[!UICONTROL 从头开始]** | 返回到自由格式图表生成器，您可从中生成新的流量图表。 |
| **[!UICONTROL 为此路径创建一个区段]** | 创建区段。此选择将带您进入区段生成器，您可以在其中配置新区段。 |
| **[!UICONTROL 细分]** | 按可用维度、量度或时间划分节点。 |
| **[!UICONTROL 过滤列]** | 显示的过滤选项与自由格式表中的相同。有关可用选项的更多信息，请参阅[过滤和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的“对表格应用简单或高级过滤器”部分。 |
| **[!UICONTROL 排除项]**&#x200B;或&#x200B;**[!UICONTROL 还原排除项]** | 从列中删除特定节点，并将其自动创建为列顶部的过滤器。要还原排除项，请从上下文菜单中选择&#x200B;**[!UICONTROL 还原排除项]**。您也可以打开列顶部的区段，移除带有您刚刚排除的项目的Pillbox。 |
| **[!UICONTROL 趋势]** | 为节点创建趋势图表。 |
| **[!UICONTROL 显示下一列]**/**[!UICONTROL 显示上一列]** | 显示可视化图表的下一列（右）或上一列（左）。 |
| **[!UICONTROL 隐藏列]**&#x200B;n | 在可视化图表中隐藏选定的列。 |
| **[!UICONTROL 扩展整列]** | 扩展某一列以显示全部节点。默认情况下，只会显示头五个节点。 |
| **[!UICONTROL 从选择创建受众]** | 根据所选的列创建受众。 |
| **[!UICONTROL 折叠整列]** | 隐藏某一列中的所有节点。 |

## 限制到第一次/最后一次发生次数

使用此选项时，请记住：

* **[!UICONTROL 限制到第一次/最后一次发生次数]**&#x200B;仅统计序列中的第一次/最后一次发生次数。所有其他满足&#x200B;**[!UICONTROL 开始于]**&#x200B;或&#x200B;**[!UICONTROL 结束于]**&#x200B;标准的发生次数均会被弃用。
* 如果与&#x200B;**[!UICONTROL 开始于]**&#x200B;流量一起使用，则只包括与开始标准匹配的第一次发生次数。在下面的示例中，包含流量每个步骤中&#x200B;*添加到购物车*&#x200B;和&#x200B;*产品主要类别*&#x200B;的&#x200B;**所有**&#x200B;发生次数。
  ![没有限制，第一次](assets/limitofffirst.png)

  在下面的示例中，仅包含流量每个步骤中&#x200B;*添加到购物车*&#x200B;和&#x200B;*产品主要类别*&#x200B;的&#x200B;**第一次**&#x200B;发生次数。
  ![限制，开始](assets/limitonfirst.png)
* 如果与&#x200B;**[!UICONTROL 结束于]**&#x200B;流量一起使用，则仅包含与结束标准匹配的最后一次发生次数。在下面的示例中，包含流量每个步骤中&#x200B;*产品主要类别*&#x200B;和&#x200B;*添加到购物车*&#x200B;的&#x200B;**所有**&#x200B;发生次数。
  ![没有限制，第一次](assets/limitofflast.png)

  在下面的示例中，仅包含流量每个步骤中&#x200B;*产品主要类别*&#x200B;和&#x200B;*添加到购物车*&#x200B;的&#x200B;**最后一次**&#x200B;发生次数。
  ![限制，开始](assets/limitonlast.png)
* 使用的系列因容器而异。如果使用&#x200B;**[!UICONTROL 人员]**&#x200B;容器，事件系列就是会话。如果使用&#x200B;**[!UICONTROL 会话]**&#x200B;容器，则事件系列就是给定用户在提供的日期范围内的所有事件。
* 在&#x200B;**[!UICONTROL 开始于]**&#x200B;或&#x200B;**[!UICONTROL 结束于]**&#x200B;字段中使用量度或维度项时，可以在高级设置中配置&#x200B;**[!UICONTROL 限制到第一次/最后一次发生次数]**&#x200B;的选项。


>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化图表设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化图表上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

