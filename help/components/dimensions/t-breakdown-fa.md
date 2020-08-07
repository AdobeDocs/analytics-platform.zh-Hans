---
description: 在 Analysis Workspace 中划分维度和维度项目。
keywords: Analysis Workspace
title: 划分维度
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: cee89d021e9cd034246fe9367bc8910dac7ca7cf
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 94%

---


# 划分维度

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中划分维度和维度项目。

为了满足您的特定需求，划分数据的方法可以不受限制；您可以使用相关的量度、维度、区段、时间线以及其他分析划分值来构建查询。

1. [创建项目](/help/analysis-workspace/home.md)，其中包含一个数据表。
1. 在数据表中，右键单击某个行项目，然后选择&#x200B;**[!UICONTROL 划分]** > *`<item>`*。

   ![步骤结果](assets/fa_data_table_actions.png)

   您可以按维度项或受众段在选定时间段内细分指标。 此外，您还可以进一步深入到更精细的粒度级别。

   >[!NOTE]
   >
   >数据表可显示的划分数量最多为 200 个。在导出划分时，该限额会有所增加。

[YouTube 上的 Analysis Workspace 中的维度](https://www.youtube.com/watch?v=P9W0hhIHhCs&amp;index=12&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:54)

[YouTube 上的维度划分](https://www.youtube.com/watch?v=3mQ2HN7-lIc&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=13) (2:02)

## 将归因模型应用于划分

也可以对表中的任何划分应用归因模型。此归因模型可能与父列相同或不同。例如，您可以对“营销渠道”维度上的线性订单进行分析，但同时将 U 型订单应用于渠道中的特定跟踪代码。要编辑已应用于划分的归因模型，只需将鼠标悬停在划分模型上，然后单击&#x200B;**[!UICONTROL 编辑]**：

![划分设置](assets/breakdown_settings.png)
