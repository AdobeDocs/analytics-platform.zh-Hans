---
title: 标签和策略
description: 了解 AEP 中定义的数据标签和策略如何影响 CJA 中的数据视图和报告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 7962114aaab42a283f1cb35a312b0a707038c31a
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# 标签和策略

在 Experience Platform 中创建数据集时，可以为数据集中的部分或所有元素创建[数据使用标签](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=zh-Hans)。 直到现在，这些标签还没有在 CJA 中公开。使用此版本，您可以在 CJA 中查看这些标签和策略。

CJA 特别感兴趣的是以下标签：

* `C8`标签 – **[!UICONTROL 无测量]**。 此标签表示数据不能用于组织网站或应用程序上的分析。

* `C12`标签 – **[!UICONTROL 无一般数据导出]**。 以这种方式标记的架构字段无法从 CJA 导出或下载（通过报告、导出、API 等）

标签本身并不意味着强制执行这些数据使用标签。 这就是政策的用途。 您可以通过 Experience Platform 中的 [策略服务 API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=zh-Hans) 创建策略。

两个 Adobe 定义的策略出现在 CJA 中，并影响报告和下载/共享：

* **[!UICONTROL 强制分析]**&#x200B;策略
* **[!UICONTROL 强制下载]**&#x200B;策略

## 在 CJA 数据视图中查看数据标签

在 Experience Platform 中创建的数据标签显示在数据视图用户界面的三个位置：

| 位置 | 描述 |
| --- | --- |
| 架构字段上的信息按钮 | 单击此按钮表示当前应用于字段的[!UICONTROL 数据使用标签]：<p>![](assets/data-label-left.png) |
| 在[组件设置](/help/data-views/component-settings/overview.md)下的右边栏 | 此处列出了任何[!UICONTROL 数据使用标签]：<p>![](assets/data-label-right.png) |
| 将数据标签添加为列 | 您可以将[!UICONTROL 数据使用标签]作为列添加到数据视图中[!UICONTROL 包含的组件]列中。 只需单击列选择器图标并选择&#x200B;**[!UICONTROL 数据使用标签]**：<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## 筛选数据视图中的数据管理标签

在数据视图编辑器中，单击左边栏中的过滤器图标，并按&#x200B;**[!UICONTROL 数据管理]**&#x200B;和&#x200B;**[!UICONTROL 标签]**&#x200B;类型过滤数据视图组件：

![](assets/filter-labels.png)

单击&#x200B;**[!UICONTROL 应用]**&#x200B;查看哪些组件附有标签。

## 筛选数据视图中的数据管理策略

您可以检查是否启用了阻止使用某些 CJA 数据视图元素进行分析或导出的策略。

再次单击左栏中的过滤器图标，在&#x200B;**[!UICONTROL 数据管理]**&#x200B;下，单击&#x200B;**[!UICONTROL 策略]**：

![](assets/filter-policies.png)

单击&#x200B;**[!UICONTROL 应用]**&#x200B;查看已启用的策略。

## 启用的策略如何影响数据视图

如果启用&#x200B;**[!UICONTROL 强制分析]**&#x200B;或&#x200B;**[!UICONTROL 强制下载]**&#x200B;策略，则无法将具有特定数据标签（如 C8 或 C12）的架构组件添加到数据视图中。

这些组件在左边栏[!UICONTROL 架构字段]列表中显示为灰色：

![](assets/component-greyed.png)

您也无法保存包含阻止字段的数据视图。

>[!MORELIKETHIS]
>[下载敏感数据](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Report Builder 中的限制标签是什么？](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=zh-Hans)


