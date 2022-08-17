---
title: 标签和策略
description: 了解AEP中定义的数据标签和策略如何影响CJA中的数据视图和报表。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 标签和策略

在Experience Platform中创建数据集时，您可以创建 [数据使用标签](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) ，用于数据集中的部分或全部元素。 迄今为止，CJA中尚未公开这些标签。 在此版本中，您可以在CJA中查看这些标签和策略。

CJA特别感兴趣的是以下标签：

* 的 `C8` 标签 —  **[!UICONTROL 无测量]**. 此标签表示数据不能用于贵组织网站或应用程序上的分析。

* 的 `C12` 标签 —  **[!UICONTROL 无常规数据导出]**. 无法从CJA导出或下载标记为此方式的架构字段（通过报表、导出、API等）

标签本身并不意味着强制使用这些数据。 这就是政策的用途。 您可以通过 [策略服务API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform。

CJA中显示了两个Adobe定义的策略，这些策略会影响报表和下载/共享：

* **[!UICONTROL 强制Analytics]** 策略
* **[!UICONTROL 强制下载]** 策略

## 在CJA数据视图中查看数据标签

在Experience Platform中创建的数据标签显示在数据视图用户界面的三个位置：

| 位置 | 描述 |
| --- | --- |
| 架构字段上的“信息”按钮 | 单击此按钮可指示 [!UICONTROL 数据使用情况标签] 当前适用于字段：<p>![](assets/data-label-left.png) |
| 下方的右边栏 [组件设置](/help/data-views/component-settings/overview.md) | 任意 [!UICONTROL 数据使用情况标签] 列在此处：<p>![](assets/data-label-right.png) |
| 将数据标签添加为列 | 您可以添加 [!UICONTROL 数据使用情况标签] 作为列 [!UICONTROL 包含的组件] 列。 只需单击列选择器图标并选择 **[!UICONTROL 数据使用情况标签]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## 在数据视图中过滤“数据管理”标签

在数据视图编辑器中，单击左侧跟踪中的过滤器图标，然后按 **[!UICONTROL 数据管理]** 和类型 **[!UICONTROL 标签]**:

![](assets/filter-labels.png)

单击 **[!UICONTROL 应用]** 以了解哪些组件附加了标签。

## 在数据视图中过滤数据管理策略

您可以检查是否开启了阻止将某些CJA数据视图元素用于分析或导出目的的策略。

再次单击左边栏和下方的过滤器图标 **[!UICONTROL 数据管理]**，单击 **[!UICONTROL 策略]**:

![](assets/filter-policies.png)

单击 **[!UICONTROL 应用]** 以查看已启用的策略。

## 启用的策略如何影响数据视图

如果 **[!UICONTROL 强制Analytics]** 或 **[!UICONTROL 强制下载]** 打开策略后，与这些策略组件关联的某些数据标签（如C8或C12）的架构组件无法添加到数据视图中。

这些组件在左边栏中呈灰显状态 [!UICONTROL 架构字段] 列表：

![](assets/component-greyed.png)

您也无法保存其中已阻止字段的数据视图。

>[!MORELIKETHIS]
>[下载敏感数据](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[什么是受限标签Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=en)

