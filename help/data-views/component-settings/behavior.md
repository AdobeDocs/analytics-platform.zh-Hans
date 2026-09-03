---
title: 行为组件设置
description: 指定维度或量度在报告中的行为方式。
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/ra-O8TGxS6ByFEClZR7FtOnJ70YwclBiVMh9vubmGxk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 341
ht-degree: 100%

---

# 行为组件设置 {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="行为"
>abstract="适用于维度和量度组件。 确定如何汇总此量度的各个明细项。 指定是否应将此维度的字符串值转换为小写。"

<!-- markdownlint-enable MD034 -->


在维度和量度上均可找到行为设置。 设置的可用性取决于组件类型和架构数据类型。

![行为设置](../assets/behavior-settings.png)

## 维度行为设置

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 小写] | 对具有相同值但大小写不同的行进行重复数据删除。 如果启用，则维度中所有具有相同值的实例都会以小写形式报告。 例如，您的数据在字符串维度中包含 `"liverpool"`、`"Liverpool"` 和 `"LIVERPOOL"` 值。 如果启用了[!UICONTROL 小写]，则所有三个值合并为 `"liverpool"`。 如果禁用，则将所有三个值都视为不同。 |

{style="table-layout:auto"}

>[!NOTE]
>
>如果在查找数据集维度上启用[!UICONTROL 小写]，则对于同一身份标识符可存在多个查找值。 如果发生此冲突，则 Customer Journey Analytics 会使用第一个按 ASCII 整理的值（大写值在小写值之前）。 Adobe 建议不要在启用[!UICONTROL 小写]后使用包含相同值的查找数据集。

![区分大小写的维度](../assets/case-sens-workspace.png)

## 指标行为设置

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 计入值] | 在 Integer 和 Double 架构数据类型上可见。 将量度增大指定的数量。 例如，如果列的值为 `50`，则将某个指标增大 50。 |
| [!UICONTROL 计入实例] | 在 Integer 和 Double 架构数据类型上可见。 无论值是什么，都将量度增大 1。 存在任何值都将增大量度。 例如，如果列的值为 `50`，则将某个指标增大 1。 |
| [!UICONTROL 要计入的值] | 在 Boolean 架构数据类型上可见。 使您可决定通过计入 `true`、`false` 还是两者而增大指标。 |

{style="table-layout:auto"}

可使用相同的事件数据集列配合不同的行为，在 Analysis Workspace 中生成“订单”和“收入”指标。 将“收入”数据集列拖入数据视图两次，并将其中一个设置为“计入值”，将另一个设置为“计入实例”。 “订单”量度计入实例，而“收入”量度计入值。
