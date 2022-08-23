---
description: 了解如何在CJA实验面板中分析A/B测试的结果。
title: 实验面板
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 69331f1ad3699c4a01d782fe11d4f2212c703190
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 7%

---

# 实验面板

>[!NOTE]
>
>此功能当前正在进行[小范围测试](/help/release-notes/releases.md)。

的 **[!UICONTROL 实验]** 通过面板，分析人员可以比较不同的用户体验、营销或消息传递变量，从而确定哪个变量最适合产生特定结果。 您可以评估来自任何实验平台(在线、离线、Adobe解决方案、Adobe Journey Optimizer甚至BYO（自带）数据)的任何A/B实验的提升度和置信度。

>[!IMPORTANT]
>
>此时， [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=zh-Hans) (A4T)数据通过Analytics Source Connector引入Adobe Experience Platform **无法** 在 [!UICONTROL 实验] 的上界。 我们期待在2023年解决这一问题。

## 访问控制

所有Customer Journey Analytics(CJA)用户都可以使用“实验”面板。 无需管理员权限或其他权限。 但是，设置（下面的步骤1和2）需要只有管理员才能执行的操作。

## 步骤1:创建与实验数据集的连接

推荐的数据模式是，实验数据位于包含实验和两个不同维度的变体数据的对象数组中。 如果您在单个维度中拥有实验数据，并在一个分隔字符串中具有实验和变体数据，则可以使用 [子字符串](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=en#) 在数据视图中设置，将它们拆分为两个，以在面板中使用。

在您的实验数据 [摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) 进入Adobe Experience Platform, [在CJA中创建连接](/help/connections/create-connection.md) 到一个或多个实验数据集。

## 步骤2:在数据视图中添加上下文标签

在CJA数据视图设置中，管理员可以添加 [上下文标签](/help/data-views/component-settings/overview.md) 到维度或量度和CJA服务，例如 [!UICONTROL 实验] 面板可以将这些标签用于其用途。 实验面板使用两个预定义的标签：

* [!UICONTROL 实验]
* [!UICONTROL 变体]

在包含实验数据的数据视图中，选取两个维度，一个包含实验数据，一个包含变体数据。 然后，使用 **[!UICONTROL 实验]** 和 **[!UICONTROL 变体]** 标签。

![上下文标签](../assets/context-label.png)

如果没有这些标签，“实验”面板将不起作用，因为将没有可用的实验。

## 步骤3:配置“实验”面板

1. 在CJA工作区中，将“实验”面板拖到项目中。

![实验面板](../assets/experiment.png)

>[!IMPORTANT]
>如果CJA数据视图中的必需设置尚未完成，则在继续操作之前，您将收到一则相关消息。

1. 配置面板输入设置。

   | 设置 | 定义 |
   | --- | --- |
   | **[!UICONTROL 实验]** | 面向最终用户的体验的一组变体，用于确定哪些体验最好永久保留。 实验由两个或多个变体组成，其中一个变体被视为控制变体。 此设置已预填充已标有的维度  **[!UICONTROL 实验]** 标签，以及最近3个月的实验数据。 |
   | **[!UICONTROL 控制变量]** | 为了确定更好的替代方案而正在比较的最终用户体验中的两个或多个更改之一。 必须选择一个变体作为控制，并且只能将一个变体视为控制变体。 此设置已预填充已标有的维度  **[!UICONTROL 变体]** 标签。 此设置将提取与此实验关联的变体数据。 |
   | **[!UICONTROL 成功量度]** | 用户比较变体的量度或量度。 对于转化量度（无论最高还是最低），具有最理想结果的变体将被声明为实验的“性能最佳的变体”。 您最多可以添加5个量度。 |
   | **[!UICONTROL 标准化量度]** | 基准([!UICONTROL 人员], [!UICONTROL 会话]或 [!UICONTROL 事件])。 例如，测试可能会比较多个变体的转化率，其中 **[!UICONTROL 转化率]** 计算为 **[!UICONTROL 每个会话的转化数]** 或 **[!UICONTROL 每人转化]**. |
   | **[!UICONTROL 日期范围]** | 日期范围会根据在CJA中为所选实验收到的首次点击自动设置。 如果需要，可以修改此设置以限制日期范围或将其扩展到更具体的时间范围。 |

1. 单击&#x200B;**[!UICONTROL 生成]**。

## 步骤4:解释面板输出

“实验”面板可返回一组丰富的数据和可视化图表，帮助您更好地了解实验的效果。 将添加全局过滤器，以考虑显示在多个变体中的人员或会话。 无法编辑或删除此过滤器。 在该面板顶部，提供了一个摘要行，用于提醒您选择的面板设置。您可以随时通过单击右上方的编辑铅笔图标来编辑面板。

您还会获得一个文本摘要，指示实验是否结果，并总结结果。 结论性基于统计意义。 （请参阅下面的“统计方法”。） 性能最佳的变体仅提供给具有结论性的实验，并基于显着变体的转化率进行选择。 您可以看到具有最高提升度和置信度的最佳变体的概要数字。

文本摘要和概要数字仅针对在面板输入中选取的第一个成功量度生成。

>[!NOTE]
>
>提升度和置信度也是CJA中高级的计算量度函数，因此您可以构建自己的提升度和置信度量度。

![实验输出](../assets/exp-output1.png)

对于您选择的每个成功指标，将显示一个自由格式表和一个转化率趋势图：

![实验输出](../assets/exp-output2.png)

的 [!UICONTROL 折线图] 图表为您提供 [!UICONTROL 控制] 与 [!UICONTROL 控制变量] 性能：

![实验输出](../assets/exp-output3.png)
>[!NOTE]
>
>此面板当前不支持分析A/A测试。

## 统计方法

要关注的内容.
