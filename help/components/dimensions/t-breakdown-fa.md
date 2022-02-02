---
description: 在 Analysis Workspace 中划分维度和维度项目。
keywords: Analysis Workspace
title: 划分维度
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
source-git-commit: 4bea8d7997d4084cfb87c1035689c0eea6b1f3b1
workflow-type: ht
source-wordcount: '381'
ht-degree: 100%

---

# 在 Workspace 中划分维度

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解详情...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中划分维度和维度项目。

根据特定需求，按照不计其数的方式划分您的数据；使用相关的指标、维度、筛选条件、时间线以及其他分析细分值构建查询。

1. [创建项目](/help/analysis-workspace/home.md)，其中包含一个数据表。
1. 在数据表中，右键单击某个行项目，然后选择&#x200B;**[!UICONTROL 划分]** > *`<item>`*。

   ![步骤结果](assets/fa_data_table_actions.png)

   您可以跨选定的时段，按维度项目或者受众筛选条件来划分指标。此外，您还可以进一步深入到更精细的粒度级别。

   >[!NOTE]
   >
   >数据表可显示的划分数量最多为 200 个。在导出划分时，该限额会有所增加。

**视频：Analysis Workspace 中的维度**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**视频：划分维度**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## 将归因模型应用于划分

也可以对表中的任何划分应用归因模型。此归因模型可能与父列相同或不同。例如，您可以对“营销渠道”维度上的线性订单进行分析，但同时将 U 型订单应用于渠道中的特定跟踪代码。要编辑已应用于划分的归因模型，只需将鼠标悬停在划分模型上，然后单击&#x200B;**[!UICONTROL 编辑]**：

![划分设置](assets/breakdown_settings.png)

将归因模型应用到细分或者编辑它们时的预期行为如下：

* 如果在没有其他归因存在时应用某个归因，则该归因应用到整个列树。

* 如果您在应用某个归因之后添加细分，则它会使用所添加给定细分的默认值（如果该维度有默认值）。否则，它会使用来自父列的细分。一些维度具有默认分配。例如，时间维度和反向链接使用同一接触。产品维度使用最后接触。其他维度没有默认值，将使用父列分配。

* 如果列树中已有归因，更改该归因仅影响您正在编辑的列。

## 视频

在 Analysis Workspace 中将维度和量度添加到项目：

>[!VIDEO](https://video.tv.adobe.com/v/30606)

在自由格式表中使用维度：

>[!VIDEO](https://video.tv.adobe.com/v/40179)

按位置划分维度：

>[!VIDEO](https://video.tv.adobe.com/v/24033)
