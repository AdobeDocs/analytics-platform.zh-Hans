---
title: 将量子度量数据添加到Customer Journey Analytics
description: 使用量子量度收集用户历程和行为的数据，然后从收集的数据中增强CJA的功能，以得出更丰富的见解。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# 将量子度量数据添加到Customer Journey Analytics

>[!IMPORTANT]
>
>量子量度源连接器目前尚不可用。

CJA解锁对QM数据、顺序数据分析、富归因和其他高级报表的报表时间控制。  可以使用QM源连接器或Quantum Metrics Tags扩展将QM发送到AEP。

## 步骤1：创建量子度量源连接器

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到[!UICONTROL Experience Platform] > [!UICONTROL 连接] > [!UICONTROL 源]。
1. 添加量子度量源连接器，并按照提示完成操作。

有关详细信息，请参阅[Adobe Experience Platform源连接器](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)。

## 步骤2：在Customer Journey Analytics中创建连接

为Quantum Metric数据创建源连接器会自动在Adobe Experience Platform中创建数据集。 将此数据集添加到Customer Journey Analytics中的新连接或现有[连接](/help/connections/overview.md)。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL 连接]**。
1. 为连接命名，然后将Quantum量度数据集添加到连接。
1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>虽然您可以将Quantum量度数据添加到与Customer Journey Analytics其余数据相同的连接，但如果没有两个数据集之间通用的人员ID，则无法拼合这些数据。 如果需要此行为，Adobe建议使用[标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)而不是源连接器。

## 步骤3：在Customer Journey Analytics中创建数据视图

创建[数据视图](/help/data-views/data-views.md)以配置维度和量度设置。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL 数据视图]**。
1. 选择所需的数据视图，或创建数据视图。
1. 在右侧的架构字段列表中找到所需的量度维度和量度，并将它们拖动到中心的维度和量度区域。
1. 使用右侧窗格配置每个所需的维度和量度。

## 步骤4：在Customer Journey Analytics中开始报告和分析

现在，数据在Customer Journey Analytics中可用，您可以开始报告数据。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 选择现有项目，或创建项目。
1. 将任何所需的量度维度或量度拖到Workspace画布上以分析数据。
