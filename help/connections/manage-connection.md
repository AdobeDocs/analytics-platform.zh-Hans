---
title: 管理连接
description: 介绍如何管理与 Platform 数据集的连接。
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---


# 管理连接

创建一个或多个连接后，即可在[!UICONTROL 连接]管理器中管理它们。您可以

* 删除连接。
* 重命名连接。
* 从连接中创建一个数据视图。
* 开始和停止数据流。

![连接管理器](assets/connections-manager.png)

1. 单击&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。

2. 选择要编辑或管理的连接。

3. 完成以下操作之一：

   | 操作 | 描述 |
   |---|---|
   | [!UICONTROL 删除] | 删除连接不会删除数据集，因为数据仍然在 [!DNL Adobe Experience Platform] 中。请参阅下面的“删除连接”。 |
   | [!UICONTROL 重命名] | 可以使用描述性更强的名称重命名连接。 |
   | [!UICONTROL 创建数据视图] | 此链接会将您转到[数据视图生成器](/help/data-views/create-dataview.md)。 |
   | [!UICONTROL 开始和停止数据流] | “流”是指如果将任何新数据批次添加到连接中的任何数据集，则会将这些新数据引入到 [!UICONTROL Customer Journey Analytics] 报表。 |

## 删除连接

| 如果... | 产生的后果 |
| --- | --- |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接？ | 将显示一条错误消息，指示：<ul><li>为已删除的连接创建的所有数据视图都将不再起作用。</li><li> 同样地，任何依赖于已删除连接中的数据视图的工作区项目都将停止运行。</li></ul> |
| 删除 [!UICONTROL Adobe Experience Platform] 中的数据集？ | 如果删除 AEP 中的某个数据集，则将阻止从该数据集到包含该数据集的任何连接的数据流量。来自该数据集的任何数据都不会自动从关联的 CJA 连接中删除。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集？ | 当前，无法删除已保存的连接中的数据集。您必须删除整个连接，然后重新开始创建连接。（但是，您可以删除 [!UICONTROL Adobe Experience Platform] 中的数据集。） |
| 从数据集中删除批次（在 [!UICONTROL Adobe Experience Platform] 中）？ | 如果从 [!UICONTROL Adobe Experience Platform] 数据集中删除了某个批次，则会从包含该特定批次的所有 [!UICONTROL Customer Journey Analytics] 连接中删除该批次。[!UICONTROL Customer Journey Analytics] 会收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| **在将批次摄取到** [!UICONTROL Customer Journey Analytics] 时将其删除？ | 如果数据集中只有一个批次，则该批次中只会有部分数据或没有任何数据显示在 [!UICONTROL Customer Journey Analytics] 中。系统将回滚该摄取操作。例如，如果数据集中共有 5 个批次，且在删除该数据集时已摄取其中 3 个批次，那么这 3 个批次中的数据将显示在 [!UICONTROL Customer Journey Analytics] 中。 |
