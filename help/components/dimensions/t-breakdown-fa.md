---
description: 在 Analysis Workspace 中划分维度和维度项目。
keywords: Analysis Workspace
title: 划分维度
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 64%

---


# 划分维度

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中划分维度和维度项目。

为了满足您的特定需求，划分数据的方法可以不受限制；您可以使用相关的量度、维度、区段、时间线以及其他分析划分值来构建查询。

1. [创建项目](/help/analysis-workspace/home.md)，其中包含一个数据表。
1. 在数据表中，右键单击某个行项目，然后选择&#x200B;**[!UICONTROL 划分]** > *`<item>`*。

   ![步骤结果](assets/fa_data_table_actions.png)

   您可以按照维度值或受众区段，在选定的时间期限内划分量度。此外，您还可以进一步深入到更精细的粒度级别。

   >[!NOTE]数据表可显示的划分数量最多为 200 个。在导出划分时，该限额会有所增加。

[YouTube 上的 Analysis Workspace 中的维度](https://www.youtube.com/watch?v=P9W0hhIHhCs&amp;index=12&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:54)

[YouTube 上的维度划分](https://www.youtube.com/watch?v=3mQ2HN7-lIc&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=13) (2:02)

## 将归因模型应用于划分

表中的任何细分也可以应用任何归因模型。 此归因模型可以与父列相同或不同。 例如，您可以分析“营销渠道”维上的线性订单，但将U形订单应用于渠道内的特定跟踪代码。 To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![细分设置](assets/breakdown_settings.png)
