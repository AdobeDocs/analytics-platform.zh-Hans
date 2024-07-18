---
title: 标签和政策
description: 了解 Adobe Experience Platform 中定义的数据标签和政策如何影响 Customer Journey Analytics 中的数据视图和报告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 100%

---

# 标签和政策

在 Experience Platform 中创建数据集时，可以为数据集中的部分或所有元素创建[数据使用情况标签](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-governance/labels/reference)。可以在 Customer Journey Analytics 中查看这些标签和政策。

以下标签对于 Customer Journey Analytics 特别有用：

* `C8` 标签 – **[!UICONTROL 无测量]**。此标签表示数据不能用于组织网站或应用程序上的分析。

* `C12` 标签 – **[!UICONTROL 无一般数据导出]**。以这种方式标记的架构字段无法从 Customer Journey Analytics 导出或下载（通过报告、导出、API 等）

>[!NOTE]
>
>数据使用情况标签不会自动传播到拼合数据集。但可以手动添加它们。

标签本身并不意味着强制执行这些数据使用情况标签。这就是政策的用途。您可以使用 [Experience Platform UI](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-governance/policies/user-guide) 或通过 Experience Platform 中的[政策服务 API](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-governance/api/overview) 创建政策。

在 Experience Platform 中，有两个 Adobe 定义的策略可以在 Customer Journey Analytics 中显示并影响报告和数据导出：

* **[!UICONTROL 限制使用分析和基于用户的测量]** 策略（使用 `C8` 标签）
* **[!UICONTROL 限制数据导出]** 策略（使用 `C12` 标签）

## 查看 Customer Journey Analytics 数据视图中的数据标签

您或他人在 Experience Platform 中创建的数据标签显示在数据视图用户界面的三个位置：

| 位置 | 描述 |
| --- | --- |
| 架构字段上的信息按钮 | 单击此按钮表示当前应用于字段的 [!UICONTROL 数据使用情况标签]：<p>![](assets/data-label-left.png) |
| 在[组件设置](/help/data-views/component-settings/overview.md)下的右边栏 | 此处列出了任何[!UICONTROL 数据使用情况标签]：<p>![](assets/data-label-right.png) |
| 将数据标签添加为列 | 您可以将 [!UICONTROL 数据使用情况标签] 作为列添加到数据视图中 [!UICONTROL 包含的组件] 列中。只需选择列选择器图标并选择 **[!UICONTROL 数据使用情况标签]**：<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## 过滤数据视图中的数据治理标签

在数据视图编辑器中，选择左边栏中的 [!UICONTROL 过滤器] 图标，并按 **[!UICONTROL 数据治理]** 和 **[!UICONTROL 标签]** 类型过滤数据视图组件：

![](assets/filter-labels.png)

单击&#x200B;**[!UICONTROL 应用]**&#x200B;查看哪些组件附有标签。

## 筛选数据视图中的数据管理策略

您可以检查某个策略（例如，您创建的名为 **[!UICONTROL 强制分析]** 的策略）是否已启用。以及该策略是否阻止使用某些 Customer Journey Analytics 数据视图元素进行分析或数据导出。

再次选择左边栏中的 [!UICONTROL 过滤器] 图标，在 **[!UICONTROL 数据治理]** 下，选择 **[!UICONTROL 策略]**：

![按列表过滤包含的组件，显示已选择“限制使用分析和基于用户的测量”](assets/filter-policies.png)

单击 **[!UICONTROL 应用]** 查看已启用的策略。

## 启用的策略如何影响数据视图

如果启用了一个或多个带有 C8 或 C12 标签的策略，则无法将具有某些数据标签应用的架构组件添加到数据视图中。

这些组件在左边栏 [!UICONTROL 架构字段] 列表中显示为灰色：

![灰显的组件和策略消息表示已将策略应用于此字段，限制使用这些数据](assets/component-greyed.png)

您还无法保存其中有被阻止的字段的数据视图。

请谨慎尝试在 Experience Platform 中的字段或字段组上应用访问和数据治理标签（通过策略），因为您已经在数据视图中定义了这些组件。您可能会看到此对话框。

![违规](assets/violation.png)

您首先需要解决违规问题（例如，从数据视图中移除组件）。


>[!MORELIKETHIS]
>
>[下载敏感数据](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder 中受到限制的标签是什么？](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


