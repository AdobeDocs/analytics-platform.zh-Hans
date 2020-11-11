---
title: 管理连接
description: 介绍如何管理与 Platform 数据集的连接。
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 22%

---


# 管理连接

创建一个或多个连接后，可在[!UICONTROL 连接]管理器中管理这些连接。 您可以

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
   | [!UICONTROL 开始或停止数据流] | “流”是指如果将任何新批次添加到连接中的任何数据集，则此新数据将引入[!UICONTROL Customer Journey Analytics]以进行报告。 |

## 删除连接

| 如果我…… | 此情况发生 |
| --- | --- |
| 是否在[!UICONTROL Customer Journey Analytics]中删除连接？ | 将显示一条错误消息：<ul><li>为已删除的连接创建的任何数据视图将不再工作。</li><li> 同样，任何依赖于已删除连接中的数据视图的Workspace项目都将停止工作。</li></ul> |
| 是否删除[!UICONTROL Adobe Experience Platform]中的数据集？ | 在AEP中删除数据集将停止数据从该数据集流向包含该数据集的任何连接。 来自该数据集的任何数据不会自动从关联的CJA连接中删除。 |
| 是否删除[!UICONTROL Customer Journey Analytics]中的数据集？ | 当前，无法删除已保存的连接中的数据集。 您必须删除整个连接并结束开始。 (但是，您可以删除[!UICONTROL Adobe Experience Platform]中的数据集。) |
| 是否从数据集中删除批(在[!UICONTROL Adobe Experience Platform]中)? | 如果从[!UICONTROL Adobe Experience Platform]数据集中删除了某个批，则从包含该特定批的任何[!UICONTROL Customer Journey Analytics]连接中删除同一批。 [!UICONTROL 客户旅] 程分析会通知在Adobe Experience Platform删除的批 [!UICONTROL 次]。 |
| 在将批&#x200B;**收录到[!UICONTROL Customer Journey Analytics]时删除它？** | 如果数据集中只有一个批，则该批中的数据或部分数据将不会显示在[!UICONTROL Customer Journey Analytics]中。 摄取将回滚。 例如，如果数据集中有5个批，且删除数据集时已摄取其中3个，则这3个批的Customer Journey Analytics将显示在中。 |
