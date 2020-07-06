---
description: Quick Insights是面向新Workspace用户的工具，可指导他们构建数据表和可视化
title: 快速分析面板
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 6%

---


# 快速分析面板

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL “快速分析]** ”面板当前处于有限测试中。 [了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights] 可为 [!UICONTROL Analysis Workspace] 的非分析师和新用户了解如何快速轻松地回答业务问题提供指导。对于希望快速回答简单问题的高级用户来说，它也是一个不错的工具，无需自己构建表。

当您首次使用此开始 [!UICONTROL 时]，您可能会想知道哪些可视化功能最有用，哪些维度和指标可以促进洞察，在何处拖放项目，在何处创建细分等。

为了帮助您，并根据公司对Analysis Workspace中数据组件 [!UICONTROL 的使用],Quick Insights  利用一种算法来向您展示公司使用的最流行维度、指标、细分和日期范围。 事实上，您将在下拉列表中看到标记为“ [!UICONTROL Popular] ”的维度、指标和细分，如下所示：

![](assets/popular-tag.png)

[!UICONTROL 快速洞察] ，助您一臂之力

* 正确构建数据表以及Analysis Workspace中随附的可 [!UICONTROL 视化]。
* 学习基本组件和Analysis Workspace的术语和 [!UICONTROL 词汇]。
* 在自由形式表中轻松进行维度的简单细分、添加多个指标或 [!UICONTROL 比较细分]。
* 更改或尝试各种可视化类型，快速、直观地找到适合您的分析的查找工具。

## 基本关键术语

以下是您需要熟悉的一些基本术语。 每个数据表都包含2个或多个用于讲述数据故事的构件块（组件）。

| 构建块（组件） | 定义 |
|---|---|
| [!UICONTROL 维度] | 维是度量数据的描述或特性，可在项目中查看、细分和比较。 它们是非数字值和日期，可划分为维项目。 例如，“browser”或“page”是维。 |
| [!UICONTROL 维项] | 维项是维的单个值。 例如，浏览器维度的维度项应为“Chrome”、“Firefox”、“Edge”等。 |
| [!UICONTROL 量度] | 量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。 |
| [!UICONTROL 可视化图表] | Workspace offers [a number of visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others. |
| [!UICONTROL 维度细分] | 维度细分是一种按其他维度来划分维度的方法。 在我们的示例中，您可以按移动设备划分美国州，以获取每个州的移动设备访问次数，或按移动设备类型、地区、内部活动等划分移动设备。 |
| [!UICONTROL 区段] | 细分允许您根据特征或网站交互确定访客子集。 例如，您可以根据属 [!UICONTROL 性] ，构建访客区段： 浏览器类型、设备、访问次数、国家／地区、性别或基于交互： 活动、关键字搜索、搜索引擎或基于退出和条目： 来自Facebook、已定义登陆页、引用域或基于自定义变量的访客: 表单字段、定义的类别、客户ID。 |

## 快速洞察入门

1. 使用您提供的凭据登录AdobeAnalytics。
1. 转到Workspace  ，单击 **[!UICONTROL 创建新项目]** ，然后单击 **[!UICONTROL “快速分析]**”。 (您还可以从左边栏的“面板 **[!UICONTROL ”菜单]** 访问此面板。)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. 首次开始时，请阅读简短的教程，其中教您一些“快速洞察” [!UICONTROL 面板基础知识] 。 或者，单击“跳过 **[!UICONTROL 教程”]**。
1. 选择构件块（也称为组件）: 维（橙色）、度量（绿色）、段（蓝色）或日期范围（紫色）您必须为要自动构建的表至少选择一个维度和一个度量。

   ![](assets/qibuilder2.png)

   您有三种选择构造块的方法：
   * 从左边栏拖放它们。
   * 如果您知道要查找的内容： 开始输 [!UICONTROL 入和] “快速洞察”将帮您填补空白。
   * 单击下拉框并搜索列表。

1. 添加至少一个维和一个度量后，将为您创建以下内容：

   * 一个自由形式表，其顶部为垂直尺寸（此处为美国州）和水平度量（此处为访问量）。 请查看此表：

   ![](assets/qibuilder3.png)

   * 随附的可视化，本例为条 [形图](/help/analysis-workspace/visualizations/bar.md)。 生成的可视化基于您添加到表中的数据类型。 任何基于时间的数据( [!UICONTROL 如每] 天／月的访问量)均默认为 [!UICONTROL 折线图] 。 任何非基于时间的数据(如每 [!UICONTROL 台设][!UICONTROL 备的访]问 [!UICONTROL 次数] )均默认为条形图。 您可以通过单击可视化类型旁边的下拉箭头来更改可视化类型。


1. （可选）通过单击维旁的>向右箭头，向下展开维并查看维项。

1. 尝试添加一些更多细化，如下面的“更多提示”中所述。

1. 通过单击“项目”>“保 **[!UICONTROL 存”保存您的项目]**。

## 更多提示

Quick Insights Builder中将弹出其 [!UICONTROL 他有用提示]，其中一些提示取决于您的上一个操作。

* 首先，完成更多 **[!UICONTROL 提示教程]** : 通过帮助(?)访问它 图标，单击“快 [!UICONTROL 速分析] ”标题。 本教程在创建至少具有一个维度和一个度量的项目后24小时内显示。

   ![](assets/qibuilder4.png)

* **细分依据**: 您最多可以对维度使用3个级别的细分，以细化您真正需要的数据。

   ![](assets/qibuilder5.png)

* **添加更多指标**: 使用AND运算符将多达2个指标添加到表中。

   ![](assets/qibuilder6.png)

* **添加更多区段**: 使用AND或OR运算符将多达2个区段添加到表中。 查看添加移动用户或忠诚访客时表格会发生什么情况。 它们彼此相邻，高于指标。 如果您添加了“移动用户”和“忠诚访客”，您将看到这两个细分的结果，并且它们会放在表中彼此之上。

   ![](assets/qibuilder7.png)

## 已知限制

如果尝试直接在表中编辑，将导致“快 [!UICONTROL 速分析] ”面板不同步。 单击面板右上方的“ [!UICONTROL 重新同步] Builder **** ”，可将其恢复为之前的“快速分析”设置。

![](assets/qibuilder9.png)

在将任何内容直接添加到表之前，您会收到警告：

![](assets/qibuilder8.png)

否则，直接构建将导致表现为传统的自由形式表，而新用户没有有用的功能。

