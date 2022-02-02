---
title: 删除后果
description: 在 Customer Journey Analytics 或 Adobe Experience Platform 中删除连接、数据集或批次后发生的情况。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '339'
ht-degree: 100%

---

# 删除后果

在 Customer Journey Analytics 或 Adobe Experience Platform 中删除连接、数据集或批次前应考虑这些情况。

| 当... | 产生的后果... |
| --- | --- |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接 | 将显示一条错误消息，指示：<ul><li>为已删除的连接创建的所有数据视图都将不再起作用。</li><li> 同样地，任何依赖于已删除连接中的数据视图的工作区项目都将停止运行。</li></ul> |
| 删除 [!UICONTROL Adobe Experience Platform] (AEP) 中的数据集 | 如果删除 AEP 中的某个数据集，则将阻止从该数据集到包含该数据集的任何连接的数据流量。来自该数据集的任何数据都不会自动从关联的 CJA 连接中删除。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集 | 当前，无法删除已保存的连接中的数据集。您必须删除整个连接，然后重新开始创建连接。（但是，您可以删除 [!UICONTROL Adobe Experience Platform] 中的数据集。） |
| 从数据集中删除批次（在 [!UICONTROL Adobe Experience Platform] 中） | 如果从 [!UICONTROL Adobe Experience Platform] 数据集中删除了某个批次，则会从包含该特定批次的所有 [!UICONTROL Customer Journey Analytics] 连接中删除该批次。[!UICONTROL Customer Journey Analytics] 会收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| **批次被摄取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 的同时删除批次 | 如果数据集中只有一个批次，则该批次中只会有部分数据或没有任何数据显示在 [!UICONTROL Customer Journey Analytics] 中。系统将回滚该摄取操作。例如，如果数据集中共有 5 个批次，且在删除该数据集时已摄取其中 3 个批次，那么这 3 个批次中的数据将显示在 [!UICONTROL Customer Journey Analytics] 中。 |
| 删除 [!UICONTROL Adobe Experience Platform] 中的查找数据集 | 尽管其他源连接器可以删除数据集，但目前不支持 [Analytics Classifications Data Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=zh-Hans) 这样做。如果您误删除了一个数据集，请联系 Adobe 客户关怀部门。 |
