---
title: 标签和政策
description: 了解 Adobe Experience Platform 中定义的数据标签和政策如何影响 Customer Journey Analytics 中的数据视图和报告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 950c121e6c889e202f048d4a33e8fecde3cd9efe
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 67%

---

# 标签和政策

在Experience Platform中创建数据集时，可以创建 [数据使用标签](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) 数据集中的部分或全部元素。 可以在 Customer Journey Analytics 中查看这些标签和政策。

以下标签对于 Customer Journey Analytics 特别有用：

* `C8` 标签 – **[!UICONTROL 无测量]**。此标签表示数据不能用于组织网站或应用程序上的分析。

* 此 `C12` 标签 —  **[!UICONTROL 无一般数据导出]**. 以这种方式标记的架构字段无法从 Customer Journey Analytics 导出或下载（通过报告、导出、API 等）

>[!NOTE]
>
>数据使用情况标签不会自动传播到拼合数据集。但可以手动添加它们。

标签本身并不意味着强制执行这些数据使用情况标签。这就是政策的用途。您可以使用创建策略 [EXPERIENCE PLATFORMUI](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) 或通过 [策略服务API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) Experience Platform中。

两个 Adobe 定义的政策显示在 Customer Journey Analytics 中，并影响报告和下载/共享：

* **[!UICONTROL 强制分析]**&#x200B;策略
* **[!UICONTROL 强制下载]**&#x200B;策略

## 查看 Customer Journey Analytics 数据视图中的数据标签

您或其他人在Experience Platform中创建的数据标签显示在数据视图用户界面的三个位置：

| 位置 | 描述 |
| --- | --- |
| 架构字段上的信息按钮 | 单击此按钮表示当前应用于字段的[!UICONTROL 数据使用情况标签]：<p>![](assets/data-label-left.png) |
| 在[组件设置](/help/data-views/component-settings/overview.md)下的右边栏 | 此处列出了任何[!UICONTROL 数据使用情况标签]：<p>![](assets/data-label-right.png) |
| 将数据标签添加为列 | 您可以将[!UICONTROL 数据使用情况标签]作为列添加到数据视图中[!UICONTROL 包含的组件]列中。只需单击列选择器图标并选择&#x200B;**[!UICONTROL 数据使用情况标签]**：<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## 筛选数据视图中的数据管理标签

在数据视图编辑器中，单击左边栏中的[!UICONTROL 过滤器]图标，并按&#x200B;**[!UICONTROL 数据管理]**&#x200B;和&#x200B;**[!UICONTROL 标签]**&#x200B;类型过滤数据视图组件：

![](assets/filter-labels.png)

单击&#x200B;**[!UICONTROL 应用]**&#x200B;查看哪些组件附有标签。

## 筛选数据视图中的数据管理策略

您可以检查是否启用了某个策略（例如，一个名为“Enforce Analytics”的策略），以及该策略是否阻止将某些Customer Journey Analytics数据视图元素用于Analytics。

再次单击左边栏中的[!UICONTROL 过滤器]图标，在&#x200B;**[!UICONTROL 数据管理]**&#x200B;下，单击&#x200B;**[!UICONTROL 政策]**：

![所含组件的筛选依据列表，其中显示选择了“强制分析”](assets/filter-policies.png)

单击 **[!UICONTROL 应用]** 查看已启用的策略。

## 启用的策略如何影响数据视图

如果开启了&#x200B;**[!UICONTROL 强制分析]**&#x200B;策略，则无法将这些有某些数据标签（如 C8）与自身关联的架构组件添加到数据视图。

这些组件在左边栏中显示为灰色 [!UICONTROL 架构字段] 列表：

![灰显的组件和策略消息表示已将策略应用于此字段，限制使用这些数据](assets/component-greyed.png)

您还无法保存其中有被阻止的字段的数据视图。

如果尝试在Experience Platform中的字段或字段组上应用访问和数据治理标签，并且已在数据视图中为其定义了组件，请务必谨慎。 您可能会看到此对话框。

![违规](assets/violation.png)

首先需要解决违规（例如，从数据视图中删除元件）。


>[!MORELIKETHIS]
>
>[下载敏感数据](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder 中受到限制的标签是什么？](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


