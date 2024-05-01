---
title: 删除后果
description: 在 Customer Journey Analytics 或 Adobe Experience Platform 中删除连接、数据集或批次后发生的情况。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 71%

---

# 删除后果

在 Customer Journey Analytics 或 Adobe Experience Platform 中删除连接、数据集或批次前应考虑这些情况。

| 当... | 产生的后果... |
| --- | --- |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接 | 将显示一条错误消息，指示：<ul><li>为已删除的连接创建的所有数据视图都将不再起作用。</li><li> 同样地，任何依赖于已删除连接中的数据视图的工作区项目都将停止运行。</li></ul>请注意，您无法删除绑定到您无权访问的Adobe Experience Platform沙盒的Customer Journey Analytics连接。 即使您有权访问基于这些连接构建的数据视图，但在您获得基础Adobe Experience Platform沙盒的权限之前，您无法删除这些连接。 |
| 删除中的数据集 [!UICONTROL Adobe Experience Platform] | 如果删除 AEP 中的某个数据集，则将阻止从该数据集到包含该数据集的任何连接的数据流量。来自该数据集的任何数据都会自动从关联的Customer Journey Analytics连接中删除。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集 | 当您从Customer Journey Analytics中的连接中删除数据集时，任何依赖该数据集的数据视图和项目将不再有效。 |
| 从数据集中删除批次（在 [!UICONTROL Adobe Experience Platform] 中） | 如果从 [!UICONTROL Adobe Experience Platform] 数据集中删除了某个批次，则会从包含该特定批次的所有 [!UICONTROL Customer Journey Analytics] 连接中删除该批次。[!UICONTROL Customer Journey Analytics] 会收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| **批次被摄取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 的同时删除批次 | 如果数据集中只有一个批次，则该批次中只会有部分数据或没有任何数据显示在 [!UICONTROL Customer Journey Analytics] 中。系统将回滚该摄取操作。例如，如果数据集中共有 5 个批次，且在删除该数据集时已摄取其中 3 个批次，那么这 3 个批次中的数据将显示在 [!UICONTROL Customer Journey Analytics] 中。 |
| 删除中的查找数据集 [!UICONTROL Adobe Experience Platform] | 虽然可以删除其他源连接器的数据集，但目前在[分析分类源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html)中不支持此类删除功能。如果您误删除了一个数据集，请联系 Adobe 客户关怀部门。 |
