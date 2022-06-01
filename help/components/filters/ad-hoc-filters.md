---
description: 在 Analysis Workspace 中使用临时过滤器。
title: 临时项目过滤器
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 6627c8e8f6e88fd93ffaad12b38e5e1dbbc844a8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 100%

---

# 临时项目过滤器

通过临时项目过滤器，可以将任何组件直接拖放到面板拖放区域中来创建过滤器。 该过滤器将成为当前项目的本地 [项目级过滤器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html)。

以下是一段关于创建临时项目过滤器的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 将任意组件类型（维度、维度项、事件、指标、区段、区段模板、日期范围）拖入面板顶部的过滤器放置区域。 组件类型会自动转换为临时过滤器或 [快速过滤器](/help/components/filters/quick-filters.md)（如果兼容）。

   以下是如何为 Twitter 反向链接域创建过滤器的示例：

   ![](assets/ad-hoc1.png)

   您的面板自动应用此过滤器，而您可立即看到结果。

1. 可将无限量的过滤器添加到面板。
1. 如果决定要保存此过滤器，请参阅以下部分。

请记住：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入过滤器区域：不能从中生成过滤器的计算量度和维度/量度。
* 对于所有维度和事件，Analysis Workspace 将创建“存在”点击过滤器。示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如果将“未指定”或“无”拖入过滤器放置区域，则它自动转换为“不存在”过滤器，以使其在筛选时受到正确对待。

## 保存临时项目过滤器 {#ad-hoc-save}

可选择按以下这些步骤保存这些过滤器：

1. 将光标悬停在放置区域中的过滤器上，然后单击“i”图标。
1. 单击编辑铅笔转到过滤器生成器。
1. 单击&#x200B;**[!UICONTROL “使其对所有项目可用，并添加到组件列表”]**。
1. 单击&#x200B;**[!UICONTROL 保存]**。

保存后，该过滤器将显示在左边栏组件列表中，并可从过滤器管理器与其他用户共享。

