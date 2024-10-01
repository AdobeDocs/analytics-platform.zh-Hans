---
description: 通过筛选单个量度，可在同一报表中比较量度。
title: 过滤指标
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# 过滤指标

在[计算量度生成器](cm-build-metrics.md#definition-builder)中，您可以在量度定义中应用筛选器。 如果要在分析中为数据子集使用量度，应用过滤器会很有帮助。

>[!NOTE]
>
>筛选器定义已通过[筛选器生成器](/help/components/filters/filter-builder.md)更新。 如果您对过滤器进行了更改，则无论何时使用该过滤器，都会自动更新该过滤器，其中包括该过滤器是否为计算指标定义的一部分。
>

您希望比较与您的品牌互动的德国人员与德国以外人员的量度。 因此，您可以回答类似下面的问题：

1. 有多少德国和国际人士访问您最受欢迎的[页面](#popular-pages)。
1. 本月[总计](#totals)有多少德国和国际人员与您的品牌进行了在线互动。
1. 访问您热门页面的德国人和国际人士的[百分比](#percentages)是多少？

请参阅以下部分，以说明过滤量度如何帮助您回答这些问题。 在适当的情况下，会参考更详细的文档。

## 受欢迎页面

1. [从名为`German people`的Workspace项目创建计算量度](cm-workflow.md)。
1. 在[计算量度生成器](cm-build-metrics.md)中，[创建一个名为`Germany`的筛选器](/help/components/filters/filter-builder.md)，该筛选器使用您CRM数据中的“CRM国家/地区”字段来确定人员的来源。

   >[!TIP]
   >
   >在计算量度生成器中，您可以使用组件面板直接创建过滤器。
   >   

   您的过滤器可能如下所示。

   ![筛选器德国](assets/filter-germany.png)

1. 返回计算指标生成器，然后使用该过滤器更新计算指标。

   ![计算量度Germany](assets/calculated-metric-germany.png)

对计算指标的国际版本重复上述步骤。

1. 从您的Workspace项目创建一个名为`International people`的计算指标。
1. 在计算量度生成器中，创建一个名为`Not Germany`的筛选器，该筛选器使用您CRM数据中的CRM国家/地区字段来确定人员的来源。

   您的过滤器应类似于。

   ![筛选器德国](assets/filter-not-germany.png)

1. 返回计算指标生成器，然后使用该过滤器更新计算指标。

   ![计算量度Germany](assets/calculated-metric-notgermany.png)


1. 在Analysis Workspace中创建一个项目，该项目可让您查看德国和国际人士访问的页面。

   ![Workspace自由格式表可视化图表，显示德语人员与国际人员](assets/workspace-german-vs-international.png)


## 总计

1. 根据总计创建两个新筛选器。 打开之前创建的每个筛选器，重命名筛选器，将&#x200B;**[!UICONTROL 人员]**&#x200B;的&#x200B;**[!UICONTROL 度量类型]**&#x200B;设置为&#x200B;**[!UICONTROL 总计]**，并使用&#x200B;**[!UICONTROL 另存为]**&#x200B;以使用新名称保存筛选器。 例如：

   德国![总量度](assets/calculated-metric-germany-total.png)

1. 在您的Workspace项目中添加一个新的自由格式表可视化图表，以显示当月的总页数。

   ![Workspace自由格式表可视化图表，显示德语人员与国际人员总数](assets/workspace-german-vs-international-totals.png)


## 百分比

1. 创建两个新的计算量度，以根据您之前创建的计算量度计算百分比。

   ![Workspace自由格式表可视化图表显示德语人员与国际总人员百分比](assets/calculated-metric-germany-total-percentage.png)


1. 更新您的Workspace项目。

   ![Workspace自由格式表可视化图表，显示德语人员与国际人员总数](assets/workspace-german-vs-international-totals-percentage.png)


+++ 以下视频演示了如何将过滤的计算量度用作无实施量度。

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

{{videoaa}}

+++
