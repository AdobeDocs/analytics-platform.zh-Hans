---
title: 查看当前Customer Journey Analytics发行说明
description: 最新CJA发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 73%

---

# 最新Customer Journey Analytics发行说明

## 关键更新

|[!UICONTROL 持久性] 用于绑定维度和绑定量度的选项|在创建或编辑数据视图时，您可以将维度的持久性绑定到其他维度或量度。 这个概念在 Reports and Analytics 中称为&#x200B;_陈列_，现在 CJA 也支持这个概念。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)| 2022年1月19日 |

## 其他更新

| 功能 | 描述 | 目标日期 |
| ----------- | ---------- | ----- |
| [!UICONTROL 第一个已知]和[!UICONTROL 最后一个已知]分配模型 | 这两个新分配模型采用指定持久性范围（会话、人员或带回溯的自定义时间段）内某个维度的第一个或最后一个观察值。然后它们将分配模型应用于指定范围内的所有事件。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#allocation-settings) | 2022 年 1 月 19 日 |
| [!UICONTROL PersonID] 和 [!UICONTROL PersonID 命名空间]作为维度 | 将 `personID`（或 `customerID` 或任何用于在连接中合并数据集的 ID）公开为数据视图中的维度。此增强功能使您能够从连接拉入 `personID`，更轻松地将其作为维度包含在数据视图中。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional-standard-components) | 2022 年 1 月 19 日 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics文档更新](/help/doc-changes.md)
