---
description: 借助计算量度生成器，任何人都可以创建参与量度。
title: 参与率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d55df4ea2086278a243af51b698a9822a9a04e04
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 32%

---

# 生成“参与率”量度

以下信息介绍了如何创建量度，以显示哪些页面促成了（或参与了）包含订单的会话。

此类信息对任何内容所有者都很有用。

>[!NOTE]
>
>具有其他归因模型（例如参与率）的量度也可以由管理员作为的一部分创建。 [数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 以下示例显示了任何有权访问工作区中的计算量度生成器的用户可怎样创建这些量度。

1. 开始构建量度，如中所述 [生成量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 在计算量度生成器中，将量度命名为“参与率”或类似名称
1. 将成功事件“订购”拖到“定义”画布。
1. 在[设置](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)齿轮下，将该事件的&#x200B;**[!UICONTROL 归因模型]**&#x200B;更改为&#x200B;**[!UICONTROL 参与率]**。选择 **[!UICONTROL 会话]** 回顾。 定义应该类似于：

   ![](assets/participation.png)

1. 选择 [!UICONTROL **保存**] 以保存指标。
1. 在&#x200B;**[!UICONTROL 页面]**&#x200B;报表中使用计算量度。

   ![](assets/participation-pages.png)

1. （可选）与组织中的其他用户共享该量度，如中所述 [共享计算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
